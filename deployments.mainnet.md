# AladdinDAO Contracts in Ethereum Mainnet

## Governance Multisigs

Community Multisig:

- For Management: [0xc40549aa1D05C30af23a1C4a5af6bA11FCAFe23F](https://etherscan.io/address/0xc40549aa1D05C30af23a1C4a5af6bA11FCAFe23F)
- CLever Treasury: [0xFC08757c505eA28709dF66E54870fB6dE09f0C5E](https://etherscan.io/address/0xFC08757c505eA28709dF66E54870fB6dE09f0C5E)
- Concentrator Treasury: [0xA0FB1b11ccA5871fb0225B64308e249B97804E99](https://etherscan.io/address/0xA0FB1b11ccA5871fb0225B64308e249B97804E99)

| Signer       |                                                        Address                                                        |
| ------------ | :-------------------------------------------------------------------------------------------------------------------: |
| Alex Pack    | [0x4C2B418457880d9A2bC04079840e671E70DF7cD1](https://etherscan.io/address/0x4C2B418457880d9A2bC04079840e671E70DF7cD1) |
| 0xLlama      | [0x7904Ad7c992CDAb500dAa0f3366301b1f5365B62](https://etherscan.io/address/0x7904Ad7c992CDAb500dAa0f3366301b1f5365B62) |
| chiaki644    | [0x4088421cBDBa1501d8Fd09fD241717097Afb42Cb](https://etherscan.io/address/0x4088421cBDBa1501d8Fd09fD241717097Afb42Cb) |
| Gordon       | [0x38a93e70b0D8343657f802C1c3Fdb06aC8F8fe99](https://etherscan.io/address/0x38a93e70b0D8343657f802C1c3Fdb06aC8F8fe99) |
| Guo Yu       | [0x74390470F4001Ca85D93bD546A4Ab1724359654B](https://etherscan.io/address/0x74390470F4001Ca85D93bD546A4Ab1724359654B) |
| Jamie        | [0xe3522d85d37F55735e9327CD7a5cDe3abaf28E03](https://etherscan.io/address/0xe3522d85d37F55735e9327CD7a5cDe3abaf28E03) |
| Martin Krung | [0x8EcAB7B8ed8215cA52500cbf1548B9239173ef82](https://etherscan.io/address/0x8EcAB7B8ed8215cA52500cbf1548B9239173ef82) |
| Sharlyn Wu   | [0xF483De0f306952FA56ef56c1dbBDd2A70737bDd5](https://etherscan.io/address/0xF483De0f306952FA56ef56c1dbBDd2A70737bDd5) |
| vfat         | [0xef0ca09fbf9a5f61e657fb208b46b8685c1d4766](https://etherscan.io/address/0xef0ca09fbf9a5f61e657fb208b46b8685c1d4766) |

## V3 Contracts

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

#### Concentrator for cvxCRV

| Name                 |                  Address                   | Notes      |
| -------------------- | :----------------------------------------: | ---------- |
| AladdinCRV           | 0x2b95A1Dcc3D405535f9ed33c219ab38E8d7e0884 |
| AladdinConvexVault   | 0xc8fF37F7d057dF1BB9Ad681b53Fa4726f268E0e8 | deprecated |
| ConcentratorIFOVault | 0x3Cf54F3A1969be9916DAD548f3C084331C4450b5 |

#### Concentrator for cvxFXS

| Name                  |                  Address                   | Notes |
| --------------------- | :----------------------------------------: | ----- |
| AladdinFXS            | 0xDAF03D70Fe637b91bA6E521A32E1Fb39256d3EC9 |       |
| AladdinFXSConvexVault | 0xD6E3BB7b1D6Fa75A71d48CFB10096d59ABbf99E1 |       |

#### Concentrator for ETH

TBD

#### Concentrator for sdCRV

TBD

#### Revenue Sharing

| Reward Token |               FeeDistributor               |
| ------------ | :----------------------------------------: |
| aCRV         | 0xA5D9358c60fC9Bd2b508eDa17c78C67A43A4458C |
| aFXS         |                    TBD                     |

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

| Name               |                  Address                   |
| ------------------ | :----------------------------------------: |
| clevUSD            | 0x3C20Ac688410bE8F391bE1fb00AFc5C212972F86 |
| FRAX Furnace       | 0x7f160EFC2436F1aF4E9E8a57d0a5beB8345761a9 |
| FRAX/USDC CLever   | 0xEB0ea9D24235aB37196111eeDd656D56Ce4F53b1 |
| LUSD/FRAXBP CLever | 0xb2Fcee71b25B62baFE442c58AF58c42143673cC1 |
| TUSD/FRAXBP CLever | 0xad4caC207A0BFEd10dF8A4FC6A28D377caC730E0 |

##### Strategies

| Name                          |                  Address                   |
| ----------------------------- | :----------------------------------------: |
| FRAX/USDC Concentrator 100%   | 0xAdC6A89d6Df7374629eA3cFd0737843709d29F66 |
| LUSD/FRAXBP Concentrator 100% | 0xC65D58A33D9917Df3e1a4033eD73506D9b6aCE6c |
| TUSD/FRAXBP Concentrator 100% | 0xa7625Dd9F2D8a95a0D1Ac7E8671547197e9fcAf0 |

#### Curve Pool Checker

| Name              | Address |
| ----------------- | :-----: |
| Base Pool Checker |   TBD   |
| Meta Pool Checker |   TBD   |

#### Revenue Sharing

| Reward Token |               FeeDistributor               |
| ------------ | :----------------------------------------: |
| CVX          | 0xEA99147773782cc88a03d76a7c9E30152D97Fc0b |
| CRV          |                    TBD                     |
| FRAX         |                    TBD                     |

#### Liquidity Gauges

| Name                 |                  LP Token                  |                   Gauge                    |
| -------------------- | :----------------------------------------: | :----------------------------------------: |
| Curve CLEV/ETH       | 0x6C280dB098dB673d30d5B34eC04B6387185D3620 | 0x86e917ad6Cb44F9E6C8D9fA012acF0d0CfcF114f |
| Balancer clevCVX/CVX | 0x69671c808c8f1c1490a4c9e0145884dfb5631378 | 0x9b02548De409D7aAeE228BfA3ff2bCa70e7a2fe8 |
| Curve clevCVX/CVX    | 0xF9078Fb962A7D13F55d40d49C8AA6472aBD1A5a6 | 0xF758BE28E93672d1a8482BE15EAf21aa5450F979 |

#### Fundraising Gauge

- FundraisingGaugeFactoryV1: 0x3abf0BE21E5020007B6e2e201E292a7119bC2b0d
- FundraisingGaugeV1: 0xB9CD9979718e7E4C341D8D99dA3F1290c908FBdd
- FundraisingGauge: 0x8A5eF9095795e9740Afc91C5Bd23B0e48d6bB7aE

### Gateways

| Name                   |                  Address                   | Notes      |
| ---------------------- | :----------------------------------------: | ---------- |
| CompounderGateway      | 0x883Fd355deBF417F82Aa9a3E2936971487F7Df1F | deprecated |
| ConcentratorGateway    | 0xD069866AceD882582b88E327E9E79Da4c88292B1 | deprecated |
| Balancer Gauge Gateway | 0xb44f8Ba6CD9FfeE97F8482D064E62Ba55edD4D72 | deprecated |
| AllInOneGateway        | 0x6e513d492Ded19AD8211a57Cc6B4493C9E6C857B |            |

### Zap Contracts

| Name                  |                  Address                   | Notes                                 |
| --------------------- | :----------------------------------------: | ------------------------------------- |
| AladdinCRVZap         | 0x5EB30ce188B0abb89A942cED6Cbe114F4d852082 | currently used for AladdinCRV         |
| AladdinConvexVaultZap | 0x71Fb0cc62139766383C0F09F1E31375023592841 | deprecated                            |
| AladdinZap            | 0x1104b4DF568fa7Af90B1Bed1D78A2F71e748dc8a | currently used for AladdinConvexVault |

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
