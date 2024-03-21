# AladdinDAO Contracts in Ethereum Mainnet

## Governance Multisigs

Community Multisig:

- For Management: [0xc40549aa1D05C30af23a1C4a5af6bA11FCAFe23F](https://etherscan.io/address/0xc40549aa1D05C30af23a1C4a5af6bA11FCAFe23F)
- CLever Treasury: [0xFC08757c505eA28709dF66E54870fB6dE09f0C5E](https://etherscan.io/address/0xFC08757c505eA28709dF66E54870fB6dE09f0C5E)
- Concentrator Treasury: [0xA0FB1b11ccA5871fb0225B64308e249B97804E99](https://etherscan.io/address/0xA0FB1b11ccA5871fb0225B64308e249B97804E99)
- f(x) Treasury: [0x26B2ec4E02ebe2F54583af25b647b1D619e67BbF](https://etherscan.io/address/0x26B2ec4E02ebe2F54583af25b647b1D619e67BbF)

| Signer        |                                                        Address                                                        |
| ------------- | :-------------------------------------------------------------------------------------------------------------------: |
| Diligent Deer | [0xcdF067F306E7a511Ef701588AFCdcff292B19282](https://etherscan.io/address/0xcdF067F306E7a511Ef701588AFCdcff292B19282) |
| 0xLlama       | [0x7904Ad7c992CDAb500dAa0f3366301b1f5365B62](https://etherscan.io/address/0x7904Ad7c992CDAb500dAa0f3366301b1f5365B62) |
| chiaki644     | [0x4088421cBDBa1501d8Fd09fD241717097Afb42Cb](https://etherscan.io/address/0x4088421cBDBa1501d8Fd09fD241717097Afb42Cb) |
| Gordon        | [0x38a93e70b0D8343657f802C1c3Fdb06aC8F8fe99](https://etherscan.io/address/0x38a93e70b0D8343657f802C1c3Fdb06aC8F8fe99) |
| Guo Yu        | [0x74390470F4001Ca85D93bD546A4Ab1724359654B](https://etherscan.io/address/0x74390470F4001Ca85D93bD546A4Ab1724359654B) |
| Jamie         | [0xe3522d85d37F55735e9327CD7a5cDe3abaf28E03](https://etherscan.io/address/0xe3522d85d37F55735e9327CD7a5cDe3abaf28E03) |
| Martin Krung  | [0x8EcAB7B8ed8215cA52500cbf1548B9239173ef82](https://etherscan.io/address/0x8EcAB7B8ed8215cA52500cbf1548B9239173ef82) |
| Sharlyn Wu    | [0xF483De0f306952FA56ef56c1dbBDd2A70737bDd5](https://etherscan.io/address/0xF483De0f306952FA56ef56c1dbBDd2A70737bDd5) |
| vfat          | [0xef0ca09fbf9a5f61e657fb208b46b8685c1d4766](https://etherscan.io/address/0xef0ca09fbf9a5f61e657fb208b46b8685c1d4766) |

## V3 Contracts

### f(x) protocol

- [Fx.Governance](https://github.com/AladdinDAO/aladdin-v3-contracts/blob/main/deployments/mainnet/Fx.Governance.json)
- [Fx.stETH](https://github.com/AladdinDAO/aladdin-v3-contracts/blob/main/deployments/mainnet/Fx.stETH.json)

#### Governance

| Name                  |                  Address                   | Notes |
| --------------------- | :----------------------------------------: | ----- |
| TokenSale Round1      | 0x3eB6Da2d3f39BA184AEA23876026E0747Fb0E17f |       |
| TokenSale Round2      | 0x674A745ADb09c3333D655cC63e2d77ACbE6De935 |       |
| FXN                   | 0x365AccFCa291e7D3914637ABf1F7635dB165Bb09 |       |
| veFXN                 | 0xEC6B8A3F3605B083F7044C0F31f2cac0caf1d469 |       |
| VotingEscrowHelper    | 0xd766f2b87DE4b08c2239580366e49710180aba02 |       |
| VotingEscrowBoost     | 0x8Cc02c0D9592976635E98e6446ef4976567E7A81 |       |
| VotingEscrowProxy     | 0x1145f304d74f3295Fa38b82e7BB8704B0E187FA1 |       |
| TokenMinter           | 0xC8b194925D55d5dE9555AD1db74c149329F71DeF |       |
| GaugeController       | 0xe60eB8098B34eD775ac44B1ddE864e098C6d7f37 |       |
| GaugeControllerOwner  | 0x1Ca7b82c4265835C7841cf29407217D820a7DADb |       |
| SmartWalletWhitelist  | 0xD71B8B76015F296E53D41e8288a8a13eAfFff2ea |       |
| Vesting FXN           | 0x2290eeFEa24A6E43b26C27187742bD1FEDC10BDB |       |
| ManageableVesting FXN | 0x0E4f31a2f48418c90F5e9fa84Bf761D832C54ceD |       |
| CvxFxnVestingManager  | 0x43fCFe9F128b5e4271c7E25C47eFe91bA8896220 |       |
| SdFxnVestingManager   | 0xA2FaffE31153e5E60F2352e3ed28ff973309C156 |       |
| MultipleVestHelper    | 0x267b7A1d56d624293Ba1819f30B5bf0F12A524E4 |       |
| ReservePoolV2         | 0xb592E01dd77084b36430ffCB9c9D2F76fDE32631 |       |

#### Price Oracle

| Name                        |                  Address                   | Notes      |
| --------------------------- | :----------------------------------------: | ---------- |
| ChainlinkTwapOracleV3 ETH   | 0x460B3CdE57DfbA90DBed02fd83d3990a92DA1230 | 30min twap |
| ChainlinkTwapOracleV3 stETH | 0xD24AC180e6769Fd5F624e7605B93084171074A77 | 30min twap |
| FxStETHTwapOracle           | 0xa84360896cE9152d1780c546305BB54125F962d9 | 30min twap |
| FxFrxETHTwapOracle          | 0x939c38921c961DecB3cc16f601C32d07C41cd25C | 30min twap |
| FxEETHTwapOracle            | 0x834E87262A00b0aC38eD49Cb1110838866bE4a20 | 30min twap |

#### Liquidity Gauge

| Name         |                 LP Address                 |               Gauge Address                |   Notes   |
| ------------ | :----------------------------------------: | :----------------------------------------: | :-------: |
| ETH+FXN      | 0xE06A65e09Ae18096B99770A809BA175FA05960e2 | 0xA5250C540914E012E22e623275E290c4dC993D11 | dual farm |
| FXN+cvxFXN   | 0x1062FD8eD633c1f080754c19317cb3912810B5e5 | 0xfEFafB9446d84A9e58a3A2f2DDDd7219E8c94FbB | dual farm |
| FXN+sdFXN    | 0x28Ca243dc0aC075dD012fCf9375C25D18A844d96 | 0x5b1D12365BEc01b8b672eE45912d1bbc86305dba | dual farm |
| crvUSD+fxUSD | 0x8ffc7b89412efd0d17edea2018f6634ea4c2fcb2 | 0xF4Bd6D66bAFEA1E0500536d52236f64c3e8a2a84 | dual farm |
| PYUSD+fxUSD  | 0xd6982da59F1D26476E259559508f4135135cf9b8 | 0xeD113B925AC3f972161Be012cdFEE33470040E6a | dual farm |
| DOLA+fxUSD   | 0x189B4e49B5cAf33565095097b4B960F14032C7D0 | 0x61F32964C39Cca4353144A6DB2F8Efdb3216b35B | dual farm |
| GRAI+fxUSD   | 0x69Cf42F15F9325986154b61A013da6E8feC82CCF | 0xfa4761512aaf899b010438a10C60D01EBdc0eFcA | dual farm |
| FRAX+fxUSD   | 0x1EE81c56e42EC34039D993d12410d437DdeA341E | 0x31b630B21065664dDd2dBa0eD3a60D8ff59501F0 | dual farm |
| GHO+fxUSD    | 0x74345504Eaea3D9408fC69Ae7EB2d14095643c5b | 0xf0A3ECed42Dbd8353569639c0eaa833857aA0A75 | dual farm |
| mkUSD+fxUSD  | 0xca554e2e2948a211d4650fe0f4e271f01f9cb5f1 | 0xDbA9a415bae1983a945ba078150CAe8b690c9229 | dual farm |
| ULTRA+fxUSD  | 0xf33ab11e5c4e55dacb13644f0c0a9d1e199a796f | 0x0d3e9A29E856CF00d670368a7ab0512cb0c29FAC | dual farm |

#### Rebalance Pool Gauge

| Name    |               Gauge Address                |              Claimer Address               | Notes |
| ------- | :----------------------------------------: | :----------------------------------------: | ----- |
| fETH    | 0x9710ca7f3edd4893f399c89ea184d92cc7172e28 | 0x81243a88Dd9Fb963c643bD3f2194c2cA9CCFc428 |       |
| fstETH  | 0xf422446F7730e50B9CAb4618343425d9927b35ED | 0xCa0563ab14a87ee64d6b097B0dfC46E9B56820aD |       |
| ffrxETH | 0xB3886b8c94C8635B786b1CA88942337669BB1e1E | 0x4ae3BE52c411CC08434d28645FD391497C69c815 |       |
| feETH   | 0xf594bDfafE4197144C6459FcA611d7B868d36bEa | 0x835191186745e63f9e325E741B273ff925174d7e |       |

#### fxUSD, beta = 0

- FxUSD: 0x085780639CC2cACd35E474e71f4d000e2405d8f6
- FxUSDRebalancer: 0x78c3aF23A4DeA2F630C130d2E42717587584BF05

##### fstETH & xstETH

| Name                  |                  Address                   | Notes |
| --------------------- | :----------------------------------------: | ----- |
| Treasury              | 0xED803540037B0ae069c93420F89Cd653B6e3Df1f |       |
| Market                | 0xAD9A0E7C08bc9F747dF97a3E7E7f620632CB6155 |       |
| fstETH                | 0xD6B8162e2fb9F3EFf09bb8598ca0C8958E33A23D |       |
| xstETH                | 0x5a097b014C547718e79030a077A91Ae37679EfF5 |       |
| WstETHRateProvider    | 0x81A777c4aB65229d1Bf64DaE4c831bDf628Ccc7f |       |
| FxInitialFund         | 0xe6b953BB4c4B8eEd78b40B81e457ee4BDA461D55 |       |
| RebalancePoolRegistry | 0x86e987a89Fd7345457d97b9e82906f346D61Df39 |       |
| RebalancePoolSplitter | 0x78Ef19714c8b3c71997970C156f59605A99C3ff3 |       |
| RebalancePool.wstETH  | 0x9aD382b028e03977D446635Ba6b8492040F829b7 |       |
| RebalancePool.xstETH  | 0x0417CE2934899d7130229CDa39Db456Ff2332685 |       |
| LeveragedTokenWrapper | 0x6AF422087aBF42819F764FF8DE95269036b9A8F9 |       |

##### ffrxETH & xfrxETH

| Name                        |                  Address                   | Notes |
| --------------------------- | :----------------------------------------: | ----- |
| Treasury                    | 0xcfEEfF214b256063110d3236ea12Db49d2dF2359 |       |
| Market                      | 0x714B853b3bA73E439c652CfE79660F329E6ebB42 |       |
| ffrxETH                     | 0xa87F04c9743Fd1933F82bdDec9692e9D97673769 |       |
| xfrxETH                     | 0x2bb0C32101456F5960d4e994Bac183Fe0dc6C82c |       |
| ERC4626RateProvider sfrxETH | 0x7ceD6167b5A08111dC8d0D2f9F7E482c4Da62506 |       |
| FxInitialFund               | 0xFC3862c33b54E0BBA61d966Ff51973C20be4fC62 |       |
| RebalancePoolRegistry       | 0x345a345DAd48c3504113539ce83c0cB765627B54 |       |
| RebalancePoolSplitter       | 0xb26cA48fe4Ee94a4Fe8815F7E54E99124f997540 |       |
| RebalancePool.sfrxETH       | 0xb925F8CAA6BE0BFCd1A7383168D1c932D185A748 |       |
| RebalancePool.xfrxETH       | 0x4a2ab45D27428901E826db4a52Dae00594b68022 |       |
| LeveragedTokenWrapper       | 0x823BaF74524b707d649A2a78E66DF106f5A131aB |       |

#### rUSD, beta = 0

- rUSD: 0x65D72AA8DA931F047169112fcf34f52DbaAE7D18
- FxUSDRebalancer: 0x78c3aF23A4DeA2F630C130d2E42717587584BF05

##### feETH & xeETH

| Name                  |                  Address                   | Notes |
| --------------------- | :----------------------------------------: | ----- |
| Treasury              | 0x781BA968d5cc0b40EB592D5c8a9a3A4000063885 |       |
| Market                | 0x267C6A96Db7422faA60Aa7198FfEeeC4169CD65f |       |
| feETH                 | 0x9216272158F563488FfC36AFB877acA2F265C560 |       |
| xeETH                 | 0xACB3604AaDF26e6C0bb8c720420380629A328d2C |       |
| FxInitialFund         | 0x6dc7a100d09DDbF344FC4Dd0398f79500D0c2716 |       |
| RebalancePoolRegistry | 0xb1dD23468a69DFDDb7211298e609C0DB1522B2D6 |       |
| RebalancePoolSplitter | 0x015729C84A1C5E541DFbF6f0dDc59AE66527B5eD |       |
| RebalancePool.weETH   | 0xc2DeF1E39FF35367F2F2a312a793477C576fD4c3 |       |
| RebalancePool.xeETH   | 0x7EB0ed173480299e1310d55E04Ece401c2B06626 |       |
| LeveragedTokenWrapper | 0xA9414Ee8b2b2563E70174972FAa2E8B5197Feb5D |       |

#### f(x) on stETH, beta = 0.1

| Name                |                  Address                   | Notes      |
| ------------------- | :----------------------------------------: | ---------- |
| fETH                | 0x53805A76E1f5ebbFE7115F16f9c87C2f7e633726 |            |
| xETH                | 0xe063F04f280c60aECa68b38341C2eEcBeC703ae2 |            |
| stETHTreasury       | 0x0e5CAA5c889Bdf053c9A76395f62267E653AFbb0 |            |
| Market              | 0xe7b9c7c9cA85340b8c06fb805f7775e3015108dB |            |
| ReservePool         | 0x5d0Aacf75116d1645Db2B3d1Ca4b303ef0CA3752 | deprecated |
| FxGateway           | 0x5c28b966aB37cFB9397bBc04595f91F0fBf06d9b | deprecated |
| stETHGateway        | 0x9bF5fFABbF97De0a47843A7Ba0A9DDB40f2e2ed5 | deprecated |
| wstETHWrapper       | 0xb09e34dD25d5E88a1E9Ff6F6418109927675B658 |            |
| StETHAndxETHWrapper | 0xC2BdBF323304eaBd9260b42E4d0d429Ca3481d6E |            |

##### Rebalance Pool

- RebalancePoolRegistry: 0x4eEfea49e4D876599765d5375cF7314cD14C9d38
- RebalancePoolSplitter: 0x79c5f5b0753acE25ecdBdA4c2Bc86Ab074B6c2Bb
- Gauge: 0x9710ca7f3edd4893f399c89ea184d92cc7172e28
- RebalancePoolGaugeClaimer: 0x81243a88Dd9Fb963c643bD3f2194c2cA9CCFc428

| Name                          |                  Address                   |                 liquidator                 | Notes      |
| ----------------------------- | :----------------------------------------: | :----------------------------------------: | ---------- |
| RebalancePool.wstETH          | 0xa677d95B91530d56791FbA72C01a862f1B01A49e | 0x17f21f468d77E6e35702a9Ae7a9da50Db7F6a4f4 | deprecated |
| BoostableRebalancePool.wstETH | 0xc6dEe5913e010895F3702bc43a40d661B13a40BD | 0x74E9234A6e03c382A01Bb942B1aF05B639371309 |            |
| BoostableRebalancePool.xETH   | 0xB87A8332dFb1C76Bb22477dCfEdDeB69865cA9f9 | 0x5a161B94c737326cA115eC46f4Eaf4eEC5037dBE |            |

#### Revenue Sharing

| Name                  |                  Address                   | Notes      |
| --------------------- | :----------------------------------------: | ---------- |
| PlatformFeeSpliter    | 0x0084C2e1B1823564e597Ff4848a88D61ac63D703 |            |
| FeeDistributor stETH  | 0x851AAEA3A2757D457E1Ce88C3808C1690213e432 | deprecated |
| FeeDistributor wstETH | 0xd116513EEa4Efe3908212AfBAeFC76cb29245681 |            |

| Token Burner      |                  Address                   |  Note  |
| ----------------- | :----------------------------------------: | :----: |
| PlatformFeeBurner | 0x6440e21A3634C319c69CEf8d17601DBC4E97C3dB | wstETH |

#### Bridging

##### fETH

- Ethereum ProxyOFT: 0xc608Dfb90A430Df79a8a1eDBC8be7f1A0Eb4E763

| Chain      | Token Address                              |
| ---------- | ------------------------------------------ |
| Ethereum   | 0x53805A76E1f5ebbFE7115F16f9c87C2f7e633726 |
| Arbitrum   | 0xc608Dfb90A430Df79a8a1eDBC8be7f1A0Eb4E763 |
| BSC        | 0xF9E10DAA647E540BF3d1334377a88361aB980e94 |
| Optimistic | 0xc608Dfb90A430Df79a8a1eDBC8be7f1A0Eb4E763 |
| Polygon    | 0xc608Dfb90A430Df79a8a1eDBC8be7f1A0Eb4E763 |

##### xETH

- Ethereum ProxyOFT: 0x535f7Ca9637A5099DB568b79a3624CFd6B5fc833

| Chain      | Token Address                              |
| ---------- | ------------------------------------------ |
| Ethereum   | 0xe063F04f280c60aECa68b38341C2eEcBeC703ae2 |
| Arbitrum   | 0x55380fe7A1910dFf29A47B622057ab4139DA42C5 |
| BSC        | 0x62C6867e4f2e63302B15cbf9b8540214a13beeac |
| Optimistic | 0xa7580d4AdC6D302D2D4C7C3dB93E9aE3F82C4617 |
| Polygon    | 0xa7580d4AdC6D302D2D4C7C3dB93E9aE3F82C4617 |

##### FXN

- Ethereum ProxyOFT: 0x808130d89fC067a7a8D9dDF4ca2abf6EB5Ed3B32

| Chain      | Token Address                              |
| ---------- | ------------------------------------------ |
| Ethereum   | 0x365AccFCa291e7D3914637ABf1F7635dB165Bb09 |
| Arbitrum   | 0x179F38f78346F5942E95C5C59CB1da7F55Cf7CAd |
| BSC        | 0xa64f68c089B3E69d48F6047d3Be513349E74b3De |
| Optimistic | 0xC752C6DaA143e1a0ba3E7Df06f3117182432b991 |
| Polygon    | 0xC752C6DaA143e1a0ba3E7Df06f3117182432b991 |

### Concentrator

| Name                   |                  Address                   |
| ---------------------- | :----------------------------------------: |
| ProxyAdmin             | 0x12b1326459d72F2Ab081116bf27ca46cD97762A0 |
| CTR                    | 0xb3Ad645dB386D7F6D753B2b9C3F4B853DA6890B8 |
| veCTR                  | 0xe4C09928d834cd58D233CD77B5af3545484B4968 |
| SmartWalletWhitelist   | 0x3557bD058D674DD0981a3FF10515432159F63318 |
| PlatformFeeDistributor | 0xd2791781C367B2F512396105c8aB26479876e973 |
| GaugeRewardDistributor | 0xF57b53df7326e2c6bCFA81b4A128A92E69Cb87B0 |
| CTR Vesting            | 0x8341889905bdef85b87cb7644a93f7a482f28742 |
| Concentrator Harvester | 0xfa86aa141e45da5183B42792d99Dede3D26Ec515 |

#### Concentrator for cvxCRV

| Name                         |                  Address                   | Notes      |
| ---------------------------- | :----------------------------------------: | ---------- |
| AladdinCRV                   | 0x2b95A1Dcc3D405535f9ed33c219ab38E8d7e0884 |            |
| CvxCrvStakingWrapperStrategy | 0x94cC627Db80253056B2130aAC39abB252A75F345 |            |
| AladdinConvexVault           | 0xc8fF37F7d057dF1BB9Ad681b53Fa4726f268E0e8 | deprecated |
| ConcentratorIFOVault         | 0x3Cf54F3A1969be9916DAD548f3C084331C4450b5 |            |

[List of aCRV vaults](./pools.concentrator.aCRV.md)

#### Concentrator for Curve-FXS/cvxFXS-LP

| Name                  |                  Address                   | Notes |
| --------------------- | :----------------------------------------: | ----- |
| AladdinFXS            | 0xDAF03D70Fe637b91bA6E521A32E1Fb39256d3EC9 |       |
| AladdinFXSConvexVault | 0xD6E3BB7b1D6Fa75A71d48CFB10096d59ABbf99E1 |       |

[List of aFXS vaults](./pools.concentrator.aFXS.md)

#### Concentrator for Curve-ETH/frxETH-LP

| Name                              |                  Address                   | Notes |
| --------------------------------- | :----------------------------------------: | ----- |
| Curve ETH/frxETH LP               | 0xf43211935C781D5ca1a41d2041F397B8A7366C7A |       |
| AutoCompoundingConvexFraxStrategy | 0xc9cfD6205914AB1E209FfE70326d8dd15fc58187 |       |
| AladdinETH: afrxETH               | 0xb15Ad6113264094Fd9BF2238729410A07EBE5ABa |       |
| ConcentratorAladdinETHVault       | 0x50B47c4A642231dbe0B411a0B2FBC1EBD129346D |       |

[List of afrxETH vaults](./pools.concentrator.afrxETH.md)

#### Concentrator for Curve-ETH/stETH-LP

TBD

#### Concentrator for sdCRV

| Name                          |                  Address                   | Notes      |
| ----------------------------- | :----------------------------------------: | ---------- |
| StakeDAOLockerProxy           | 0x1c0D72a330F2768dAF718DEf8A19BAb019EEAd09 |            |
| VeSDTDelegation               | 0x6037Bb1BBa598bf88D816cAD90A28cC00fE3ff64 |            |
| AladdinSdCRV                  | 0x43E54C2E7b3e294De3A155785F52AB49d87B9922 |            |
| ConcentratorVaultForAsdCRV    | 0x59866EC5650e9BA00c51f6D681762b48b0AdA3de |            |
| StakeDAOCRVVault              | 0x2b3e72f568F96d7209E20C8B8f4F2A363ee1E3F6 | deprecated |
| SdCRVBribeBurner              | 0x9D6Dc3dbC7Cc5e1d7241601473FD63d2bD1573f9 | deprecated |
| ConcentratorSdCrvGaugeWrapper | 0x09B0E3A114135F528F762DB8363b4f5eae3F3bF1 |            |
| SdCRVBribeBurnerV2            | 0x680f26dbc8Fa2B463607ebb49A68A69c33476665 |            |

[List of asdCRV vaults](./pools.concentrator.asdCRV.md)

#### Concentrator for CLever CVX

| Name                   |                  Address                   | Notes |
| ---------------------- | :----------------------------------------: | ----- |
| Curve clevCVX/CVX LP   | 0xf9078fb962a7d13f55d40d49c8aa6472abd1a5a6 |       |
| abcCVX                 | 0xDEC800C2b17c9673570FDF54450dc1bd79c8E359 |       |
| AMOConvexCurveStrategy | 0x29E56d5E68b4819FC4a997b91fc9F4f8818ef1B4 |       |

#### Concentrator for CVX

| Name               |                  Address                   | Notes |
| ------------------ | :----------------------------------------: | ----- |
| CvxCompounder      | 0xb0903Ab70a7467eE5756074b31ac88aEBb8fB777 |       |
| CvxStakingStrategy | 0x837592b44EE5447074b80Cb21bF37a8c5E4c08f8 |       |

#### Revenue Sharing

| Name                |                  Address                   |
| ------------------- | :----------------------------------------: |
| PlatformFeeSpliter  | 0x32366846354db5c08e92b4ab0d2a510b2a2380c8 |
| aCRV FeeDistributor | 0xA5D9358c60fC9Bd2b508eDa17c78C67A43A4458C |

| Token Burner               |                  Address                   |   Note    |
| -------------------------- | :----------------------------------------: | :-------: |
| PlatformFeeBurner          | 0x695eb50a92ad2aebb89c6dd1f3c7546a28411403 | CVX, aFXS |
| ConvexFraxCompounderBurner | 0x789e729713ddc80cf2db4e59ca064d3770f1a034 |  afrxETH  |
| StakeDAOCompounderBurner   | 0xf954200fd969443b8f853b4083b71cd073c05d5b |  asdCRV   |

#### Liquidity Gauges

| Name              |                  LP Token                  |                   Gauge                    | Note       |
| ----------------- | :----------------------------------------: | :----------------------------------------: | ---------- |
| Curve CTR/ETH     | 0x3f0e7916681452D23Cd36B1281457DA721F2E5dF | 0x5BC3dD6E6b4E5DD811d558843DA6A1bfBB9c9dCa |            |
| Balancer aCRV/CTR | 0x80A8eA2f9EBFC2Db9a093BD46E01471267914E49 | 0x33e411ebE366D72d058F3eF22F1D0Cf8077fDaB0 | deprecated |

### CLever

| Name                   |                  Address                   |
| ---------------------- | :----------------------------------------: |
| CLever Treasury        | 0xFC08757c505eA28709dF66E54870fB6dE09f0C5E |
| TokenSale              | 0x07867298d99B95772008583bd603cfA68B8C75E7 |
| CLEV                   | 0x72953a5C32413614d24C29c84a66AE4B59581Bbf |
| CLEV Vesting           | 0x84C82d43f1Cc64730849f3E389fE3f6d776F7A4E |
| veCLEV                 | 0x94be07d45d57c7973A535C1c517Bd79E602E051e |
| PlatformFeeDistributor | 0xD6eFa5B63531e9ae61e225b02CbACD59092a35bE |
| VeFeeGateway           | 0x8Fc7906Fc6047679DaD53c0c3B40E135486421e9 |
| RewardClaimHelper      | 0xAf59d144357DCc8a852AD601f27BF6310b657a7f |
| SmartWalletWhitelist   | 0xFC7ea943F62aee5D40c0346DC45C464F74C35267 |
| GaugeController        | 0xB992E8E1943f40f89301aB89A5C254F567aF5b63 |
| CLEV Minter            | 0x4aa2afd5616bEEC2321a9EfD7349400d4F18566A |

#### CLever for CVX

| Name      |                  Address                   |
| --------- | :----------------------------------------: |
| clevCVX   | 0xf05e58fCeA29ab4dA01A495140B349F8410Ba904 |
| CVXLocker | 0x96C68D861aDa016Ed98c30C810879F9df7c64154 |
| Furnace   | 0xCe4dCc5028588377E279255c0335Effe2d7aB72a |

#### CLever for CRV

TBD

#### CLever for USD

| Name                  |                  Address                   |
| --------------------- | :----------------------------------------: |
| clevUSD               | 0x3C20Ac688410bE8F391bE1fb00AFc5C212972F86 |
| FRAX Furnace          | 0x7f160EFC2436F1aF4E9E8a57d0a5beB8345761a9 |
| FRAX/USDC CLever      | 0xEB0ea9D24235aB37196111eeDd656D56Ce4F53b1 |
| LUSD/FRAXBP CLever    | 0xb2Fcee71b25B62baFE442c58AF58c42143673cC1 |
| TUSD/FRAXBP CLever    | 0xad4caC207A0BFEd10dF8A4FC6A28D377caC730E0 |
| clevUSD/FRAXBP CLever | 0x2C37F1DcEd208530A05B061A183d8937F686157e |

##### Strategies

| Name                             |                  Address                   |
| -------------------------------- | :----------------------------------------: |
| FRAX/USDC Concentrator 100%      | 0xAdC6A89d6Df7374629eA3cFd0737843709d29F66 |
| LUSD/FRAXBP Concentrator 100%    | 0xC65D58A33D9917Df3e1a4033eD73506D9b6aCE6c |
| TUSD/FRAXBP Concentrator 100%    | 0xa7625Dd9F2D8a95a0D1Ac7E8671547197e9fcAf0 |
| clevUSD/FRAXBP Concentrator 100% | 0x5432526e75d45369970b8616F54b25c831d1e2b2 |

#### Curve Pool Checker

| Name              | Address |
| ----------------- | :-----: |
| Base Pool Checker |   TBD   |
| Meta Pool Checker |   TBD   |

#### Revenue Sharing

| Reward Token |               FeeDistributor               |
| ------------ | :----------------------------------------: |
| CVX          | 0x261E3aEB4cd1ebfD0Fa532d6AcDd4B21EbdCd2De |
| FRAX         | 0xb5e7F9cb9d3897808658F1991AD32912959b42E2 |
| CRV          |                    TBD                     |

#### Liquidity Gauges

| Name                     |                  LP Token                  |                   Gauge                    |
| ------------------------ | :----------------------------------------: | :----------------------------------------: |
| Curve CLEV/ETH           | 0x6C280dB098dB673d30d5B34eC04B6387185D3620 | 0x86e917ad6Cb44F9E6C8D9fA012acF0d0CfcF114f |
| ~~Balancer clevCVX/CVX~~ | 0x69671c808c8f1c1490a4c9e0145884dfb5631378 | 0x9b02548De409D7aAeE228BfA3ff2bCa70e7a2fe8 |
| ~~Curve clevCVX/CVX~~    | 0xF9078Fb962A7D13F55d40d49C8AA6472aBD1A5a6 | 0xF758BE28E93672d1a8482BE15EAf21aa5450F979 |
| abcCVX                   | 0xDEC800C2b17c9673570FDF54450dc1bd79c8E359 | 0xc5022291cA8281745d173bB855DCd34dda67F2f0 |

#### Fundraising Gauge

- FundraisingGaugeFactoryV1: 0x3abf0BE21E5020007B6e2e201E292a7119bC2b0d
- FundraisingGaugeV1: 0xB9CD9979718e7E4C341D8D99dA3F1290c908FBdd
- FundraisingGauge: 0x8A5eF9095795e9740Afc91C5Bd23B0e48d6bB7aE

### Token Converter

| Name                  |                  Address                   | Version |
| --------------------- | :----------------------------------------: | :-----: |
| ConverterRegistry     | 0xa617206663343b6353acF27566586eE9b53DFb2b |   v1    |
| GeneralTokenConverter | 0xa3F4fB87e19B60622bEA119C4469c0Df2c7c4739 |   v1    |
| LidoConverter         | 0x6F862115282037d60C7C185933664178cB3108C7 |   v1    |
| ConverterRegistry     | 0x997B6F43c1c1e8630d03B8E3C11B60E98A1beA90 |   v2    |
| GeneralTokenConverter | 0x11C907b3aeDbD863e551c37f21DD3F36b28A6784 |   v2    |
| LidoConverter         | 0xFFD43edCcec1c27091cB2Aef57b313037E135987 |   v2    |

### Gateways

| Name                   |                  Address                   | Notes      |
| ---------------------- | :----------------------------------------: | ---------- |
| CompounderGateway      | 0x883Fd355deBF417F82Aa9a3E2936971487F7Df1F |            |
| ConcentratorGateway    | 0xD069866AceD882582b88E327E9E79Da4c88292B1 |            |
| Balancer Gauge Gateway | 0xb44f8Ba6CD9FfeE97F8482D064E62Ba55edD4D72 | deprecated |
| AllInOneGateway        | 0x6e513d492Ded19AD8211a57Cc6B4493C9E6C857B |            |
| GatewayRouter          | 0xA5e2Ec4682a32605b9098Ddd7204fe84Ab932fE4 |            |

### Zap Contracts

| Name                  |                  Address                   | Notes      |
| --------------------- | :----------------------------------------: | ---------- |
| AladdinCRVZap         | 0x5EB30ce188B0abb89A942cED6Cbe114F4d852082 | deprecated |
| AladdinConvexVaultZap | 0x71Fb0cc62139766383C0F09F1E31375023592841 | deprecated |
| AladdinZap            | 0x1104b4DF568fa7Af90B1Bed1D78A2F71e748dc8a |            |

## V2 Contracts

### Misc

| Name        |                  Address                   |
| ----------- | :----------------------------------------: |
| xALD        | 0xb13B85363A25c7361877EebaEcCed99e353F2aF9 |
| wxALD       | 0xBDC423927e70E4013A7906FE54ad8209643f734C |
| Treasury    | 0x5aa403275cdf5a487D195E8306FD0628D4F5747B |
| Staking     | 0x71072Bd71Cc4f83154F1f77b4bD5E2D71BD6aa2c |
| Distributor | 0x1cCa80c17e9155eB1F5a1Df52Ef92Cc551A4b816 |
| Keeper      | 0xDC2673d6B09a022de00fFE16bf1aE7F8004a3230 |
| Airdrop     | 0x4c42A7C2Bb34e2b9dC43098B6874771e2116e940 |

### Bond

| Name                |                  Address                   |
| ------------------- | :----------------------------------------: |
| DirectBondDepositor | 0x8aE2a7E0C8627d6FA476aA3F89E1804dAfd2b7dD |
| RewardBondDepositor | 0xc6a477f1ef7B0Ac7530B6B78f52e270A973B0198 |

### Oracles

| Name                     |                  Address                   |
| ------------------------ | :----------------------------------------: |
| ChainlinkPriceOracle     | 0x7f751E35AFe72775Ec88e74386BbC9b68214153e |
| UniswapV2PriceOracle     | 0x1CD632E48BeBbdA94EA0431fb8979C3012E186e9 |
| UniswapV2PairPriceOracle | 0x41718d90B2889be621f17a7f7801aa1BBd9C6840 |

### Vaults

| Name                  |                  Address                   |
| --------------------- | :----------------------------------------: |
| MIMConvexVault        | 0x6787Db5223B84753AC597431E9137221C39DA212 |
| RenConvexVault        | 0x24b724aae64ccAB170fa05624A400215c59dB697 |
| STETHConvexVault      | 0x8D1631C549f4b08c4C72a874a69764AB56f7B4EA |
| TriCrypto2ConvexVault | 0x5f01D42Ac4529f79E7107138372Fea91D3f28cF1 |
| TriPoolConvexVault    | 0x6A975BB2b977361e53d37407CCa3e035528c14D8 |

## V1 Contracts

### Token

| Name               |                  Address                   |
| ------------------ | :----------------------------------------: |
| ALD                | 0xb26C4B3Ca601136Daf98593feAeff9E0CA702a8D |
| ALD-USDC UNI-V2-LP | 0xaAa2bB0212Ec7190dC7142cD730173b0A788eC31 |
| ALD-ETH UNI-V2-LP  | 0xED6c2F053AF48Cba6cBC0958124671376f01A903 |
| TokenDistributor   | 0x10aF3D70831A7F85192fB70CE6A7205F81294aD7 |
| TokenMaster        | 0xfF4446E9dF1c8281CE1d42610c3bC0342f93E4d7 |

### DAO

| Name     |                  Address                   |
| -------- | :----------------------------------------: |
| ALDDAO   | 0xB5495A8D85EE18cfD0d2816993658D88aF08bEF4 |
| ALDVOTE  | 0x6e2b4801040d5fab7D0d7700bE5903322BCf61Ce |
| ALDPlus  | 0x774E4Ee61dfcDBA5A574c113ABb03A0a6634Fbe4 |
| Treasury | 0x47e9517C2c179349c6C8F4a347acbeDFCA5E99Bc |

### Reward

| Name                   |                  Address                   |
| ---------------------- | :----------------------------------------: |
| RewardDistributor      | 0x0427a82Cc54509e16dCAA12802762331bd354707 |
| ALDDAO Staking Rewards | 0x78Dbc6888F6CCa11CAc3d4B0027557f25d15ad23 |

### Farms

| Name       |                  Address                   |
| ---------- | :----------------------------------------: |
| Controller | 0xA0C500eD25a88640F250C55Da7299c3345637F5E |

### Vaults & Strategies

| Vault Name        |               Vault Address                | Strategy Name        |              Strategy Address              |
| ----------------- | :----------------------------------------: | -------------------- | :----------------------------------------: |
| VaultCurveSETH    | 0xB17d98c36d2238Ffcb27bF797cA9967B3Cc9Aa07 | StrategyCurveSETH    | 0x0c6f6F52DC7a46b0Ed729231c1350d9D3ABb96F5 |
| VaultCurveRenWBTC | 0x4EE014060F4816ad294857d29C22fe62B0e9580B | StrategyCurveRenWBTC | 0x2602Ddd659Dd415473e5986aa5634d9623f9ef79 |
| VaultCurve3Pool   | 0x5C8dC3a18761e4F22F7B8D41228970477168d9e2 | StrategyCurve3Pool   | 0xE9bb64F916f2f4b5f946688fF28D222915a19e12 |
| VaultSushiETHWBTC | 0x1C7ed66abE1BA029c8EFceecfBfc4056B8C4bbfc | StrategySushiETHWBTC | 0xb9ee24714f35b5abcc769d9acd5483478fbd5955 |

KeeperUtil: [0x3566451bEB5bda28E75dDf56879c9b6aeab8dff9](https://etherscan.io/address/0x3566451bEB5bda28E75dDf56879c9b6aeab8dff9)
