# GlobalEscrow-compound-supply

Supply Ether locked in the smart contract escrow to the Compound protocol via Solidity.
- https://github.com/compound-developers/compound-supply-examples

## Eher supply to Compound protocol

Ether is supplied to Compound at the point of deposit.

```solidity
205   //Ether supplying to Compound at the point of deposit:
206   CEther cEthToken = CEther("0x4ddc2d193948926d02f9b1fe9e1daa0718270ed5"); //contract address, the cEth contract address
207   uint256 mintResult = cEthToken.mint(e.fund); //num Tokens to supply
208   //mintResult = balance of cEth
```

##  Ether retrieve

Ether is subsequently retrieved at the point of withdrawal.

```solidity
271   //Ether retrieved only at the point of withdrawal:
272   CEther cEthToken = CEther("0x4ddc2d193948926d02f9b1fe9e1daa0718270ed5"); //contract address, the cEth contract address
273   uint256 redeemResult = cEthToken.redeem(_amount); //num Tokens to redeem

275   // REDEEM_ERROR_CODES
276   emit MyLog("If this is not 0, there was an error", redeemResult);
277   require(redeemResult == 0, "redeemResult error"); //uint 0=success, otherwise a failure
```