# GlobalEscrow-compound-supply


```solidity
//Ether supplying to Compound at the point of deposit:
CEther cEthToken = CEther("0x4ddc2d193948926d02f9b1fe9e1daa0718270ed5"); //contract address, the cEth contract address
uint256 mintResult = cEthToken.mint(e.fund); //num Tokens to supply
//mintResult = balance of cEth
```


```solidity
//Ether retrieved only at the point of withdrawal:
CEther cEthToken = CEther("0x4ddc2d193948926d02f9b1fe9e1daa0718270ed5"); //contract address, the cEth contract address
uint256 redeemResult = cEthToken.redeem(_amount); //num Tokens to redeem

// REDEEM_ERROR_CODES
emit MyLog("If this is not 0, there was an error", redeemResult);
require(redeemResult == 0, "redeemResult error"); //uint 0=success, otherwise a failure
```