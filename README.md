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
- Select `Create a JavaScript project`
- When Hardhat is run, it searches for the closest hardhat.config.js file starting from the current working directory. This file normally lives in the root of your project and an empty hardhat.config.js is enough for Hardhat to work. The entirety of your setup is contained in this file.

# Writing and Compiling Contracts 
- In your /contracts directory, go ahead and delete the Lock.sol that Hardhat includes for you by default
- Run create a sol file
- for example creating a faucet contract

# Adding Testfile structure 
- building unit test for the contract
- In the /test folder, clean and rename the sample file included by Hardhat either from Lock.js to FaucetTests.js as Lock.js is the unit test for already made Lock.sol contract that we deleted
- create a test file to test your contract











