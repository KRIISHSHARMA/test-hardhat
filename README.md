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

# Writing and Compiling Contracts 
## Issues i faced 
 - No file to compile error after cmd `npx hardhat commit`
 - Solution :
    1. Make sure that the solidity version in `hardhat.config.js` is the same as in Token.sol or any solidity file you create
    2. Move your Sol file to a `contract` folder 
