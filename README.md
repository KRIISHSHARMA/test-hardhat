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
- select `Create an empty hardhat.config.js`
- When Hardhat is run, it searches for the closest hardhat.config.js file starting from the current working directory. This file normally lives in the root of your project and an empty hardhat.config.js is enough for Hardhat to work. The entirety of your setup is contained in this file.
![image](https://github.com/KRIISHSHARMA/test-hardhat/assets/86760658/46dfac60-be4e-4b8c-9286-7d02f714dbc8)

- installing Plugin In this tutorial we are going to use hardhat's recommended plugin, `@nomicfoundation/hardhat-toolbox`, which has everything you need for developing smart contracts.

```
npm install --save-dev @nomicfoundation/hardhat-toolbox
```
- also add this line in `hardhat.config.js`

![image](https://github.com/KRIISHSHARMA/test-hardhat/assets/86760658/44967c31-0e8f-4ea8-bf6c-da013996b05f)

# Writing and Compiling Contracts 
- Write a simple Contract











