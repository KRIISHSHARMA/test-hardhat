# Setting up env

## Installing Node.js 
```
curl -fsSL https://deb.nodesource.com/setup_20.x | sudo -E bash -
sudo apt-get install -y nodejs
```
## In case of error in libnode file (remove file , install dependencies , upgrade node , remove unwanted elements)

```
sudo apt remove libnode-dev
sudo apt install -f
sudo apt upgrade nodejs
sudo apt autoremove
```

## Installing Hardhat using npm inside a dir 

- initialize an npm project
```
npm init
```
- Now we can install Hardhat
```
npm install --save-dev hardhat
```
- In the same directory where you installed Hardhat run:
```
npx hardhat init
```
- Select `Create a hardhat.config.js`
- When Hardhat is run, it searches for the closest hardhat.config.js file starting from the current working directory. This file normally lives in the root of your project and an empty hardhat.config.js is enough for Hardhat to work. The entirety of your setup is contained in this file.
![Screenshot from 2024-03-29 15-50-46](https://github.com/KRIISHSHARMA/test-hardhat/assets/86760658/ad0e2413-970d-452d-835d-01871ec21882)


# Writing and Compiling Contracts 
- Make a Token.sol (or file with any name) and wirte a basic contact in it
- To compile the contract run `npx hardhat compile` in your terminal.
  
![Screenshot from 2024-03-29 15-56-44](https://github.com/KRIISHSHARMA/test-hardhat/assets/86760658/72234f0d-8bd3-4370-876d-16eeed709d28)

## Issues i faced while compiling
 - No file to compile error after cmd `npx hardhat compile`
 - Solution :
    1. Make sure that the solidity version in `hardhat.config.js` is the same as in Token.sol or any solidity file you create
    2. Move your Sol file to a `contract` folder 

# Testing The Contract
- "Writing automated tests when building smart contracts is of crucial importance, as your user's money is what's at stake".
- "To test our contract, we are going to use Hardhat Network, a local Ethereum network designed for development. It comes built-in with Hardhat, and it's used as the default network. You don't need to setup anything to use it."
- "going to use ethers.js to interact with the Ethereum contract we built in the previous section, and we'll use Mochas our test runner."
- create file Token.js
- run the follwoing cmd
```
npx hardhat test
```
![Screenshot from 2024-03-29 16-10-00](https://github.com/KRIISHSHARMA/test-hardhat/assets/86760658/f70cb594-315c-48b2-aa5e-9f57ca1be1b5)

# Deploying to a live network (hardhat)
- In Hardhat Ignition, deployments are defined through Ignition Modules
- Ignition modules are expected to be within the ./ignition/modules directory.
- If aleady not made , make new directory ignition inside the project root's directory, then, create a directory named modules inside of the ignition directory
- new directory ignition inside the project root's directory, then, create a directory named modules inside of the ignition directory
- Make Token.js inside same directory
``` sh
const { buildModule } = require("@nomicfoundation/hardhat-ignition/modules");

const TokenModule = buildModule("TokenModule", (m) => {
  const token = m.contract("Token");

  return { token };
});

module.exports = TokenModule;
```
