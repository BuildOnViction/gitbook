---
description: >-
  This tutorial shows how easy it is to migrate a Dapp running on Ethereum to
  Viction in order to use the many unrivaled features and advantages that
  Viction has over Ethereum.
---

# Migrate Ethereum Dapp to Viction

## What’s a Dapp? <a href="#b85e" id="b85e"></a>

Dapps are built on smart contracts deployed onto the blockchain where platform serves as the back-end for the application. One of the most popular Dapps — Cryptokitties, is collectibles-style Dapp built on Ethereum. When we build a game with Ethereum, essentially, each game action and transaction is be stored on the Ethereum blockchain.

## What’s Viction? <a href="#d2b6" id="d2b6"></a>

In short, Viction is an innovative solution to blockchain scalability and functionality. Viction supports all EVM-compatible smart-contracts, which basically means that every Dapp run on Ethereum can be easily ported to Viction.

{% hint style="info" %}
_Every Dapp running on Ethereum can be easily ported to Viction!_
{% endhint %}

## Why should developers build Dapps on Viction? <a href="#0547" id="0547"></a>

> _Viction is a blockchain built for practical decentralized applications._

Remember CryptoKitties in 2017? A single Dapp brought the whole Ethereum blockchain to their knees. The network was congested, with endless waiting times for transaction confirmation and high transaction fees. Porting to Viction would seem a good idea for the cute kitties. Viction mainnet can process 2,000 TPS, which is 100x faster than the Ethereum blockchain, and for a fraction (1/1000) of the cost of Dapps on Ethereum. Furthermore, the whole Viction ecosystem is also quickly evolving, which makes it become an ideal platform for Dapp development.

For more information about Viction, please refer to our [website](http://Viction.com/).

## Introduction <a href="#7e29" id="7e29"></a>

In this tutorial, we will see how easy it is to migrate the [**TomoRPS**](https://tomorps.online/) (source code can be found [**here**](https://github.com/frogdevvn/tomorps-smartcontract) and [**here**](https://github.com/frogdevvn/tomorps-backend)) game from Ethereum to Viction in 1 hour.

The migration consists of 3 steps:

1. Remove some configs of Ethereum network and replace by Viction network in Truffle project.
2. Compile & deploy a smart contract to Viction networks.
3. Update old client and testing the game :)

Below is **Video** showing that TomoRPS was slow and had bad user experience because of the low performance of Ethereum.

{% embed url="https://vimeo.com/348170191" %}

## Remove some configs of Ethereum network and replace by Viction network in Truffle project <a href="#d654" id="d654"></a>

Take a look at our current truffle-config.js.

We have 2 configs for deploying the smart contract to Ropsten Testnet and Ethereum Mainnet.

```
var HDWalletProvider = require("truffle-hdwallet-provider");var mnemonic = "YOUR_MNEMONIC";module.exports = {
  // See <http://truffleframework.com/docs/advanced/configuration>
  // to customize your Truffle configuration!
  networks: {
    solc: {
      optimizer: {
        enabled: true,
        runs: 200
      }
    },
    development: {
      host: "127.0.0.1",
      port: 7545,
      network_id: "*" // Match any network id
    },
    ropsten: {
      // must be a thunk, otherwise truffle commands may hang in CI
      provider: () =>
        new HDWalletProvider(
          mnemonic,
          "https://ropsten.infura.io/v3/9b5040ea0b704bf18af87f7edb53a644"
        ),
      network_id: "3",
      gas: 5000000
    },
    mainnet: {
      // must be a thunk, otherwise truffle commands may hang in CI
      provider: () =>
        new HDWalletProvider(
          mnemonic,
          "https://mainnet.infura.io/v3/9be4a7a6a57a47eea40d6a37af2b2712"
        ),
      network_id: "1",
      gas: 5000000,
      gasPrice: 10000000000
    }
  }
};
```

To deploy the same contract onto Viction, let’s change the configuration to connect to the [Viction network.](../developer-guide/working-with-Viction/) Check [Viction Network document,](../developer-guide/working-with-Viction/) we can find all configs of Viction networks easily. The configuration change basically tells Truffle to connects to Viction and deploy the contract on it instead of Ethereum.

Finally, we have the updated truffle-config.js.

```
"use strict";
var HDWalletProvider = require("truffle-hdwallet-provider");
var mnemonic = "YOUR_MNEMONIC";
  
module.exports = {
  networks: {
    development: {
      provider: () => new HDWalletProvider(mnemonic, "http://127.0.0.1:8545"),
      host: "127.0.0.1",
      port: "8545",
      network_id: "*" // Match any network id
    },
    tomotestnet: {
      provider: () =>
        new HDWalletProvider(
          mnemonic,
          "https://testnet.tomochain.com",
          0,
          1,
          true,
          "m/44'/889'/0'/0/"
        ),
      network_id: "89",
      gas: 5000000,
      gasPrice: 10000000000000
    },
    tomomainnet: {
      provider: () =>
        new HDWalletProvider(
          mnemonic,
          "https://rpc.Viction.com",
          0,
          1,
          true,
          "m/44'/889'/0'/0/"
        ),
      network_id: "88",
      gas: 5000000,
      gasPrice: 10000000000000
    }
  },
  compilers: {
    solc: {
      settings: {
        evmVersion: "byzantium"
      }
    }
  }
};
```

## Compile & deploy a smart contract to Viction networks <a href="#6ac5" id="6ac5"></a>

Now, it’s a good time to compile the smart contract with Viction networks.

* Run command `truffle compile`
* Migrate the contract to Viction Testnet network:

`truffle migrate --network tomotestnet`

After a few seconds, the smart contract will be migrated successfully to Viction Testnet.

## Update client to interact with Viction smart contract <a href="#ab97" id="ab97"></a>

This is the easiest step. We only need to change old smart contract address to new address on Viction and update our client (text, icon, logon…) to match with Viction.

`ADDRESS_CONTRACT: “0xb7cEb47FbD0f6f98E16E681eb3933B7801a1ce43”`

You can go to [**VicScan Testnet** ](https://testnet.tomoscan.io/)to verify the contract deployment.

## Testing <a href="#b3ec" id="b3ec"></a>

Let’s get some faucet VIC from the [**faucet page**](https://faucet.testnet.tomochain.com/).

Connect MetaMask to Viction Testnet by following this [**guide**](https://github.com/BuildOnViction/docs/blob/game\_tutorials/get-started/wallet).

You can even play the game with [**TomoWallet**](broken-reference) through our built-in Dapp Browser, which provides the best user experience for gamers.

And enjoy the game running on Viction and taste how fast and cheap transactions on Viction are.

Below is the **video** showing how fast TomoRPS is on Viction.

{% embed url="https://vimeo.com/348143592" %}

## Conclusion <a href="#2a44" id="2a44"></a>

It will not be too difficult and won’t take much time to migrate your Dapps from Ethereum to Viction. Along with that Dapps running on Viction has many advantages in speed and cost. So don’t hesitate to bring your Dapps to Viction where you can make your Dapps great again.

[**Github**](https://github.com/BuildOnViction/docs/blob/game\_tutorials/docs/developers/migrate\_from\_ethereum.md)
