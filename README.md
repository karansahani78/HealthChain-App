# Karan: Health Records Management System Using Blockchain

## Introduction
The aim of this framework is to implement blockchain technology for EHR (Electronic Health Records) and provide secure storage of electronic records by defining granular access rules for users. Additionally, the framework addresses scalability issues faced by blockchain technology through the use of off-chain storage. This system offers the benefits of scalability, security, and integrity for EHRs, leveraging blockchain technology.

<!-- TABLE OF CONTENTS -->
## Table of Contents

- [Installation](#installation)
  - [Node modules](#node-modules)
  - [Ganache](#ganache)
  - [IPFS](#ipfs)
  - [Local server](#local-server)
  - [Metamask](#metamask)
- [Getting the dApp running](#getting-the-dapp-running)
  - [Configuration](#configuration)
    - [Ganache](#1-ganache)
    - [IPFS](#2-ipfs)
    - [Metamask](#3-metamask)
  - [Smart Contract](#smart-contract)
    - [Starting your local development blockchain](#1-starting-your-local-development-blockchain)
- [Running the dApp](#running-the-dapp)
  - [Connecting Metamask to our local blockchain](#1-connecting-metamask-to-our-local-blockchain)
  - [Starting IPFS](#2-starting-ipfs)
  - [Starting a local server](#3-starting-a-local-server)

## Installation

The project requires NodeJS and npm to work. Instructions to install all other dependencies are given below.

### Node modules

1. Move to the project directory and open it in your terminal.
2. Run `npm install` to install project dependencies.

### Ganache

1. Go to [Ganache homepage](https://truffleframework.com/ganache) and download.
2. If you are on Linux, you must have received a `.appimage` file. Follow installation instructions available [here](https://itsfoss.com/use-appimage-linux/).

### IPFS

1. Go to the [GitHub page](https://github.com/ipfs/ipfs-desktop) of IPFS and install IPFS Desktop.

### Local server

1. Install Node lite-server by running the following command on your terminal: `npm install -g lite-server`.

### Metamask

1. Metamask is a browser extension available for Google Chrome, Mozilla Firefox, and Brave Browser.
2. Go to [Metamask](http://metamask.io/) and add it to your browser.

## Getting the dApp running

### Configuration

#### 1. Ganache
- Open Ganache and click on settings in the top right corner.
- Under **Server** tab:
  - Set Hostname to `127.0.0.1`
  - Set Port Number to `8545`
  - Enable Automine
- Under **Accounts & Keys** tab:
  - Enable Autogenerate HD Mnemonic

#### 2. IPFS
- Open your terminal and run `ipfs init`.
- Then run:
ipfs config --json API.HTTPHeaders.Access-Control-Allow-Origin "['*']"
ipfs config --json API.HTTPHeaders.Access-Control-Allow-Credentials "['true']"
ipfs config --json API.HTTPHeaders.Access-Control-Allow-Methods "['PUT', 'POST', 'GET']"

> Note: If you face any issues with the above command on Windows, try using Command Prompt and escape sequences or Git Bash.

#### 3. Metamask
- After installing Metamask, click on the Metamask icon in your browser.
- Click on **TRY IT NOW** if there is an announcement about a new version of Metamask.
- Continue and accept all the terms and conditions.
- Stop when Metamask asks you to create a new password. We will come back to this after deploying the contract in the next section.

### Smart Contract

1. Install Truffle using `npm install truffle -g`.
2. Compile Contracts using `truffle compile`.

#### 1. Starting your local development blockchain
- Open Ganache and configure it as mentioned above.

1. Open a new Terminal and deploy contracts using `truffle migrate`.
2. Copy the deployed contract address to `src/app.js`.

![Ganache Contract Address](https://raw.githubusercontent.com/SuyashMore/SwasthyaChain/master/images/ganace-contracct.png)

```js
// app/src/app.js  line number 11
var agentContractAddress = '0x75E115394aacC7c6063E593B9292CB9417E4cbeC';




If you change the contents of any contract, replace the existing deployment using truffle migrate --reset.
Note: Resetting the contract will change the contract address, which needs to be updated in src/app.js.

Running the dApp
1. Connecting Metamask to our local blockchain
Connect Metamask to localhost:8485.
Click on Import Account.

Select any account from Ganache and copy the private key to import the account into Metamask.

2. Starting IPFS
Start the IPFS Desktop Application.
3. Start a local server
Open a new terminal window and navigate to /YOUR_PROJECT_DIRECTORY/app/.
Run npm start.
Open localhost:3000 in your browser.
That's it! The dApp is up and running locally.
