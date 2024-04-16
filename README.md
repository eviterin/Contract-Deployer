# Contract Deployer

This project lets you deploy a smart contract to an EVM chain. 
Supported chains are Base Mainnet, Base Sepolia and localhost. However, support for  additional chains can be added by modifying `hardhat.config.js`.

This is a very trimmed down version of [Hardhat's boilerplate repo](https://github.com/NomicFoundation/hardhat-boilerplate).

## Setup
### Prerequisites
[Install Node.js](https://nodejs.org/en/download/package-manager)

### Clone and Install
```
git clone https://github.com/eviterin/Contract-Deployer.git
cd Contract-Deployer
npm install 
```

### Wallet

Add your private key to the `.env` file. 
Make sure that the wallet has at least 0.001 Eth on the chain that you will deploy on. 

## Run

Compiles `Lock.sol`, deploys it to the Base Sepolia chain, and then writes to the contract.

The `Lock.sol` contract locks the funds up until the date specified during its deployment. The `showcase.js` script deploys this contract with the parameter set to 10 seconds in the future. 

```shell
npx hardhat compile
npx hardhat run scripts/showcase.js --network base-sepolia
```

Expected output:
```
Lock deployed to: [contract address]
Attempting to withdraw
Withdraw failed (expected)
Sleeping for 15 seconds
Attempting to withdraw again
Withdraw successful (expected)
```
