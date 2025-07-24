# Understanding the Keeper in f(x) protocol

## Table of Contents

1. [Introduction](#Introduction)  
2. [Related Contract Addresses](#Related-contract-addresses)  
3. [Ticks](#1-Ticks)  
   - [Mathematical Foundation](#11-Mathematical-Foundation)  
   - [Primary Functions of Ticks](#12-Primary-functions-of-Ticks)  
   - [topTick](#13-topTick)  
   - [Trace Ticks](#14-Trace-ticks)  
4. [Long Pool Integration](#2-long-pool-integration)  
   - [Rebalance Operations](#21-rebalance-operations)  
     - [Pool-Wide Rebalance](#1-pool-wide-rebalance)  
     - [Tick-Specific Rebalance](#2-tick-specific-rebalance)  
   - [Liquidation Operations](#22-liquidation-operations)  
5. [Short Pool Integration](#3-short-pool-integration)  
   - [Contract Interface](#31-contract-interface)  
   - [Short Pool Specifics](#32-short-pool-specifics)  
6. [Keeper Bots](#keeper-bots)  
   - [State Syncing](#state-syncing)  
   - [Calculate How Much to Rebalance](#calculate-how-much-to-rebalance)  
   - [Calculate How Much to Liquidate](#calculate-how-much-to-liquidate)  
   - [Implementation References](#implementation-references)  


---

## Introduction

In DeFi, a Keeper is an entity or system responsible for *automating on-chain actions* that cannot execute themselves. Since smart contracts on blockchains are passive, they require an external trigger—this is where Keepers come in.

While f(x) is a fully on-chain system, the Keeper is designed to actively monitor positions and initiate actions once certain conditions are met. 

Maintaining an active Keeper community is critical for the f(x) Protocol. Therefore, we’ve written this document to help you understand some key concepts and processes related to Keepers.


### Related contract addresses:

Please double-check the address from official documents.

- PoolManager(Long): `0x250893CA4Ba5d05626C785e8da758026928FCD24`
- WBTC Long Pool: `0xAB709e26Fa6B0A30c119D8c55B887DeD24952473`,
- wstETH Long Pool: `0x6Ecfa38FeE8a5277B91eFdA204c235814F0122E8`,

- ShortPoolManager: `-`
- wstETH Short Pool: `-`

### 1. Ticks

**Ticks** are a fundamental concept in F(x) protocol that represent **discrete price points for debt-to-collateral ratios**. They serve as a risk categorization system that groups user positions with similar risk levels together. For more details, you can check `_getTick` function in contracts.

```solidity
// From TickMath.sol:
int24 internal constant MIN_TICK = -32767;
int24 internal constant MAX_TICK = 32767;

// Tick calculation uses 1.0015 as the base
// ratioX96 = (1.0015^tick) * 2^96
```

### 1.1. Mathematical Foundation

The core formula for the tick system is:
- **Ratio = (1.0015^tick) × 2^96**
- This ratio represents the **debts/collaterals** proportion
- Each tick represents approximately **0.15%** price change (1.0015 - 1 = 0.0015)

### 1.2. Primary functions of Ticks

All user positions with similar debt ratios are grouped into the same tick, enabling:
- **Efficient batch processing**: Multiple similar-risk positions can be handled simultaneously
- **Precise risk management**: Positions within the same tick share similar liquidation risks


### 1.3. topTick
The system processes ticks starting from the **highest risk tick** (topTick) in descending risk order.

The system maintains a topTick that points to the highest-risk tick with outstanding debt. Operations always start from this point and work downward through decreasing risk levels.

### 1.4 Trace ticks

There are many ways to trace ticks. Fundamentally, they are stored in the nodes of each pool contract. For more details, please view [PoolStorage.sol][https://github.com/AladdinDAO/fx-protocol-contracts/blob/main/contracts/core/pool/PoolStorage.sol)

As for a position, you can use `getPosition` in each pool to get the tick of the position. 

```solidity
  /// @notice Return the details of the given position.
  /// @param tokenId The id of position to query.
  /// @return rawColls The amount of collateral tokens supplied in this position.
  /// @return rawDebts The amount of debt tokens borrowed in this position.
  function getPosition(uint256 tokenId) external view returns (uint256 rawColls, uint256 rawDebts);
```

As for a tick, you can use `tickData` to fetch which node it belongs to:

```solidity
  /// @dev Mapping from tick to tree node id.
  mapping(int256 => uint48) public tickData;
```

As for a node, you can fetch the node's info through `tickTreeData` and `tickData`.

```solidity

  /// @dev Mapping from tree node id to tree node data.
  mapping(uint256 => TickTreeNode) public tickTreeData;
```

- tickData: tick -> node
- tickTreeData: node -> tick

However, the tick number returned by `getPosition` cannot be directly used in rebalance or liquidation operations unless its node's parent is 0. If the node's parent is not 0, you must trace the parent tick number upward until you reach a node whose parent is 0 (i.e., the root node).

```solidity
  /// @dev Internal function to get the root of the given tree node.
  /// @param node The id of the given tree node.
  /// @return root The root node id.
  /// @return collRatio The actual collateral ratio of the given node, multiplied by 2^60.
  /// @return debtRatio The actual debt ratio of the given node, multiplied by 2^60.
  function _getRootNode(uint256 node) internal view returns (uint256 root, uint256 collRatio, uint256 debtRatio) {
    collRatio = E60;
    debtRatio = E60;
    while (true) {
      bytes32 metadata = tickTreeData[node].metadata;
      uint256 parent = metadata.decodeUint(PARENT_OFFSET, 48);
      collRatio = (collRatio * metadata.decodeUint(COLL_RATIO_OFFSET, 64)) >> 60;
      debtRatio = (debtRatio * metadata.decodeUint(DEBT_RATIO_OFFSET, 64)) >> 60;
      if (parent == 0) break;
      node = parent;
    }
    root = node;
  }
```

Additionally, you can also use `TickBitmap` contract to track active ticks. 

## 2. Long Pool Integration

### 2.1 Rebalance Operations

For long pools, the rebalance operation has to be invoked through FxUSDBasePool.

Rebalance can only be operated when debt ratio is between the values fetched in `getRebalanceRatios`

As for `tokenIn` address, both **fxUSD** and **USDC** tokens are supported. The FxUSDBasePool contract uses the `_beforeRebalanceOrLiquidate` function to handle token conversion:


```solidity
function _beforeRebalanceOrLiquidate(
    address tokenIn,
    uint256 maxAmount
) internal view returns (RebalanceMemoryVar memory op) {
    op.stablePrice = getStableTokenPriceWithScale();
    op.totalYieldToken = totalYieldToken;
    op.totalStableToken = totalStableToken;

    uint256 amountYieldToken = op.totalYieldToken;
    uint256 amountStableToken;
    
    if (tokenIn == yieldToken) {
        // User pays fxUSD - direct usage
        // ... fxUSD handling logic
    } else {
        // User pays USDC - convert to USD equivalent
        uint256 maxAmountInUSD = (maxAmount * op.stablePrice) / PRECISION;
        if (maxAmountInUSD < amountYieldToken) {
            amountYieldToken = maxAmountInUSD;
        } else {
            amountStableToken = ((maxAmountInUSD - amountYieldToken) * PRECISION) / op.stablePrice;
        }
    }
    
    // Ensure we don't exceed available stable tokens
    if (amountStableToken > op.totalStableToken) {
        amountStableToken = op.totalStableToken;
    }

    op.yieldTokenToUse = amountYieldToken;
    op.stableTokenToUse = amountStableToken;
}
```

#### 1). Pool-Wide Rebalance

```solidity
/**
 * @notice Rebalance all eligible ticks in the pool through FxUSDBasePool
 * @param pool The address of the long pool
 * @param tokenIn The token to use (fxUSD or stable token)
 * @param maxAmount Maximum token amount to use
 * @param minBaseOut Minimum collateral expected
 * @return tokenUsed Amount of input token consumed
 * @return baseOut Amount of collateral tokens received
 */
function rebalance(
    address pool,
    address tokenIn,
    uint256 maxAmount,
    uint256 minBaseOut
) external returns (uint256 tokenUsed, uint256 baseOut);
```

**Usage Example:**
```solidity
// Approve tokens for rebalancing
IERC20(fxUSD).approve(fxUSDBasePool, maxFxUSD);
IERC20(stableToken).approve(fxUSDBasePool, maxStable);

// Rebalance entire pool
(uint256 tokenUsed, uint256 collateralReceived) = 
    IFxUSDBasePool(fxUSDBasePool).rebalance(
        poolAddress,      // target pool
        fxUSD,            // use fxUSD
        maxFxUSD,         // max amount
        minCollateral     // minimum expected
    );
```

#### 2). Tick-Specific Rebalance

```solidity
/**
 * @notice Rebalance positions in a specific tick through FxUSDBasePool
 * @param pool The address of the long pool
 * @param tick The specific tick to rebalance (risk level)
 * @param tokenIn The token to use (fxUSD or stable token)
 * @param maxAmount Maximum token amount to use
 * @param minBaseOut Minimum collateral expected
 * @return tokenUsed Amount of input token consumed
 * @return baseOut Amount of collateral tokens received
 */
function rebalance(
    address pool,
    int16 tick,
    address tokenIn,
    uint256 maxAmount,
    uint256 minBaseOut
) external returns (uint256 tokenUsed, uint256 baseOut);
```

*Notice*: The tick provided must always be a root tick—i.e., its node's parent must be 0. Otherwise, you need to trace the tick upward to identify the corresponding root tick.

**Usage Example:**
```solidity
// Get highest risk tick
int16 topTick = ILongPool(poolAddress).getTopTick(); // you may want to replace this with your own logic to fetch ticks

// Prepare tokens (fxUSD or USDC)
IERC20(tokenIn).approve(fxUSDBasePool, maxAmount);

// Rebalance specific tick
(uint256 tokenUsed, uint256 collateralReceived) = 
    IFxUSDBasePool(fxUSDBasePool).rebalance(
        poolAddress,      // target pool
        topTick,          // highest risk tick
        tokenIn,          // fxUSD or USDC address
        1000e18,          // max 1000 tokens
        0                 // minimum collateral (set based on slippage tolerance)
    );
```



### 2.2 Liquidation Operations

Rebalance can only be operated when debt ratio is between the values fetched in `getLiquidateRatios`


#### Contract Interface

```solidity
/**
 * @notice Liquidate high-risk positions through FxUSDBasePool
 * @param pool The address of the long pool
 * @param tokenIn The token to use (fxUSD or stable token)
 * @param maxAmount Maximum token amount to use
 * @param minBaseOut Minimum collateral expected
 * @return tokenUsed Amount of input token consumed
 * @return baseOut Amount of collateral tokens received
 */
function liquidate(
    address pool,
    address tokenIn,
    uint256 maxAmount,
    uint256 minBaseOut
) external returns (uint256 tokenUsed, uint256 baseOut);
```

**Usage Example:**
```solidity
// Check liquidation opportunity
bool canLiquidate = ILongPool(poolAddress).canLiquidate();
require(canLiquidate, "No liquidation opportunity");

// Prepare liquidation tokens
IERC20(tokenIn).approve(fxUSDBasePool, maxAmount);

// Execute liquidation
(uint256 tokenUsed, uint256 collateralReceived) = 
    IFxUSDBasePool(fxUSDBasePool).liquidate(
        poolAddress,      // target pool
        tokenIn,          // fxUSD or USDC
        maxAmount,        // max token amount
        minCollateral     // minimum expected collateral
    );
```


## 3. Short Pool Integration

### 3.1 Contract Interface

```solidity
interface IShortPoolManager {
    /**
     * @notice Rebalance positions in a specific tick
     * @param pool The address of short pool
     * @param receiver The address to receive fxUSD
     * @param tick The tick to rebalance
     * @param maxRawDebts Maximum raw debt tokens to use
     */
    function rebalance(
        address pool,
        address receiver,
        int16 tick,
        uint256 maxRawDebts
    ) external returns (uint256 colls, uint256 debts);

    /**
     * @notice Rebalance entire pool
     * @param pool The address of short pool
     * @param receiver The address to receive fxUSD
     * @param maxRawDebts Maximum raw debt tokens to use
     */
    function rebalance(
        address pool,
        address receiver,
        uint256 maxRawDebts
    ) external returns (uint256 colls, uint256 debts);

    /**
     * @notice Liquidate high-risk short positions
     * @param pool The address of short pool
     * @param receiver The address to receive fxUSD
     * @param maxRawDebts Maximum raw debt tokens to use
     */
    function liquidate(
        address pool,
        address receiver,
        uint256 maxRawDebts
    ) external returns (uint256 colls, uint256 debts);
}
```

### 3.2 Short Pool Specifics

#### Key Differences from Long Pool:
1. **Collateral**: fxUSD tokens
2. **Debt**: External tokens (ETH, BTC, etc.)

#### Rebalance Example:

```solidity
// Get debt token for the short pool
address debtToken = IShortPool(shortPoolAddress).debtToken();

// Approve debt tokens for rebalancing
IERC20(debtToken).approve(shortPoolManager, maxDebtAmount);

// Execute rebalance
(uint256 fxUSDReceived, uint256 debtUsed) = 
    IShortPoolManager(shortPoolManager).rebalance(
        shortPoolAddress,    // target short pool
        msg.sender,          // receive fxUSD
        maxDebtAmount        // max debt tokens to use
    );
```


## Keeper Bots

There is an open-source example keeper implementation available at [fx-keeper-example](https://github.com/starit/fx-protocol-keeper-example). 

### State Syncing

In this implementation, the bot relies on the `stateSync` class to synchronize states locally and reassemble the on-chain status. Based on the synchronized data, it calculates relevant metrics and executes rebalance and liquidate operations accordingly.

#### Calculate how much to rebalance

There are two known restrictions from the contracts:

1. `(debt - x) / (price * (coll - y * (1 + incentive))) ≤ target_ratio`

  where 
  - x = debt to be repaid
  - y = collateral to be removed
  - incentive = rebalance bounty ratio

2. ``` debt / (price * coll) >= target_ratio```

From these conditions, we derive the following formula:

```
x ≥ (debt - target_ratio × price × coll) / (1 - target_ratio × (1 + incentive))
```

Code implementation([source](https://github.com/AladdinDAO/aladdin-dao-sdk/blob/920f3918384e2773257670731042501bde90c254/src/bots/fx/Rebalance.ts#L45)):

```solidity
function getRawDebtToRebalance(tick: ITickToBalance): bigint {

  const rawDebts =
    (tick.rawDebts * PRECISION * PRECISION - tick.debtRatio * tick.price * tick.rawColls) /
    (PRECISION * PRECISION - (PRECISION * tick.debtRatio * (FEE_PRECISION + tick.bonusRatio)) / FEE_PRECISION);
  return rawDebts;
}
```


#### Calculate how much to liquidate:

Based on the restrictions from the contract:

```
rawDebts / price * (1 + bonus) <= position.rawColls + balance
```

We can derive:

```
 rawDebts <= (position.rawColls + balance) / (1 + bonus) * price
```

Code implementation([source](https://github.com/AladdinDAO/aladdin-dao-sdk/blob/920f3918384e2773257670731042501bde90c254/src/bots/fx/Liquidate.ts#L38)):

```solidity
function getRawDebtToLiquidate(position: IPositionToLiquidate, balance: bigint): bigint {
  // rawDebts / price * (1 + bonus) <= position.rawColls + balance
  // rawDebts <= (position.rawColls + balance) / (1 + bonus) * price
  let rawDebts =
    ((((position.rawColls + balance) * position.price) / PRECISION) * FEE_PRECISION) /
    (FEE_PRECISION + position.bonusRatio);
  (position.rawColls * position.price) / PRECISION;
  if (rawDebts > position.rawDebts) rawDebts = position.rawDebts;
  return rawDebts;
}
```


### Implementation Reference(s)

These are third-party implementations, please use at your own risk. 

**The team are not liable for any damages, losses, or issues arising from the use of the following software.**

- https://github.com/starit/fx-protocol-keeper-example