---
description: >-
  This section will guide smart contracts development on Viction network using
  Foundry tool.
---

# Foundry

### Prerequisites[​](https://docs.linea.build/build-on-linea/quickstart/deploy-smart-contract/hardhat#prerequisites) <a href="#user-content-prerequisites" id="user-content-prerequisites"></a>

Before you begin, ensure you've:

* Download [Rust](https://www.rust-lang.org/).
* An ethereum wallet.
* Funded your wallet for caring gas fee of transactions.

## Installations

You will need the [Rust](https://www.rust-lang.org/) compiler and Cargo, the Rust package manager. Install both with command:

```shell
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```

Foundry generally only supports building on the latest stable Rust version. If you have an older Rust version, you can update with `rustup`:

```shell
rustup update stable
```

Install Foundryup:

```shell
curl -L https://foundry.paradigm.xyz | bash
```

Install Foundry:

```shell
foundryup
```

## Creating a Foundry Project

Run following commands:

```shell
forge init hello_foundry
cd hello_foundry
```

## Configurations

We will need some configs in the `foundry.toml` to work with Viction network.

```
[profile.default]
src = "src"
out = "out"
libs = ["lib"]
optimizer = true
optimizer_runs = 200

[rpc_endpoints]
viction_mainnet = "https://rpc.viction.xyz/"

[etherscan]
viction_mainnet = { key="", url = "https://vicscan.xyz/api/" }

# See more config options https://github.com/foundry-rs/foundry/blob/master/crates/config/README.md#all-options
```

## Load environment variables

Setup `.env` file:

```
PRIVATE_KEY=<YOUR_PRIVATE_KEY>
```

Substitute **\<YOUR\_PRIVATE\_KEY>** with the private key for your wallet.

_**Note:**_ Requires prefixing with **`0x`**.

## Compile the smart contract

In a Foundry project, contracts will be placed at the `src/` folder. Create a simple token contract `MyToken.sol` for example:

```solidity
pragma solidity 0.8.20;

import "@openzeppelin/contracts/token/ERC20/ERC20.sol";

contract MyToken is ERC20 {
    constructor(string memory name, string memory symbol) ERC20(name, symbol) {}

    function mint(address recipient, uint256 amount)
        external
        returns (uint256)
    {
        _mint(recipient, amount);
        return amount;
    }
}
```

The Solidity code above defines a smart contract named MyToken. The code uses the ERC20 interface provided by the OpenZeppelin Contracts library to create a token smart contract. OpenZeppelin allows developers to leverage battle-tested smart contract implementations that adhere to official ERC standards.

To add the OpenZeppelin Contracts library to your project, run:

```shell
forge install OpenZeppelin/openzeppelin-contracts --no-commit
```

The Openzeppelin Contracts library is already in the `lib/openzeppelin-contracts` folder. In order to simple import contracts with alias `@openzeppelin/contracts`, add remappings to assign the library directiory with the `alias` in `foundry.toml`:

```
[profile.default]
...
remappings=[
    "@openzeppelin=lib/openzeppelin-contracts/"
]
...

```

To compile `ERC20` contract, run:

```shell
forge build
```

## Deploy the smart contract​

Once your contract has been successfully compiled, you can deploy the contract to the Viction networks.

To deploy the contract to the Viction mainnet, you'll need to add the `script/MyToken.s.sol` in the project:

```solidity
// SPDX-License-Identifier: UNLICENSED
pragma solidity 0.8.20;

import {Script} from "forge-std/Script.sol";
import "../src/MyToken.sol";

contract MyTokenScript is Script {
    function run() public {
        uint256 privateKey = vm.envUint("PRIVATE_KEY");

        vm.startBroadcast(privateKey);
        new MyToken("My Token", "MYT");
        vm.stopBroadcast();
    }
}
```

Finally, ensure your wallet has enough fund to cover gas fee and run script with command:

```shell
forge script script/MyToken.s.sol:MyTokenScript --rpc-url viction_mainnet --legacy --broadcast
```

_**Note:**_

* Deployment requires flag `--legacy` because the Viction RPC currently **not supported** **EIP-1559** transactions. [Reference.](https://book.getfoundry.sh/forge/deploying)

The transaction informations will appear after running script likes this:

```
## Setting up 1 EVM.

==========================

Chain 88

Estimated gas price: 2 gwei

Estimated total gas used for script: 676986

Estimated amount required: 0.001353972 ETH

==========================
##
Sending transactions [0 - 0].
⠁ [00:00:00] [#################################################################################################################] 1/1 txes (0.0s)##
Waiting for receipts.
⠉ [00:00:07] [#############################################################################################################] 1/1 receipts (0.0s)
##### viction
✅  [Success]Hash: 0x3e2ff561e92a99e35cbd72ec707ae7642d2a87ef9c3213afbfc9544f37ee8b8f
Contract Address: 0xC9a8D9CEa9bF2450ED8082d73e8DaFC47989558E
Block: 78881479
Paid: 0.001041822 ETH (520911 gas * 2 gwei)



==========================

ONCHAIN EXECUTION COMPLETE & SUCCESSFUL.
Total Paid: 0.001041822 ETH (520911 gas * avg 2 gwei)
```

We got the success deployment with `txnHash` is `0x3e2ff561e92a99e35cbd72ec707ae7642d2a87ef9c3213afbfc9544f37ee8b8f` and the `MyToken` contract address is `0xC9a8D9CEa9bF2450ED8082d73e8DaFC47989558E`. We can check its on [VicScan](https://scan-ui-testnet.viction.xyz/).

## Verify contract on VicScan

The first, we need to create a `json` file that contains arguments of contructor when deploy contract. File path: `./script/arguments.json`:

```json
["My Token", "MYT"]
```

Run below commands to verify contract on VicScan:

* For mainnet:

```shell
forge verify-contract 0xC9a8D9CEa9bF2450ED8082d73e8DaFC47989558E MyToken --etherscan-api-key none --verifier-url https://vicscan.xyz/api/contract/foundry/verify --constructor-args-path ./script/arguments.json
```

* For testnet:

```shell
forge verify-contract 0xC9a8D9CEa9bF2450ED8082d73e8DaFC47989558E MyToken --etherscan-api-key none --verifier-url https://testnet.vicscan.xyz/api/contract/foundry/verify --constructor-args-path ./script/arguments.json
```

The successful verification will show:

```shell
Start verifying contract `0xC9a8D9CEa9bF2450ED8082d73e8DaFC47989558E` deployed on mainnet

Submitting verification for [src/MyToken.sol:MyToken] 0xC9a8D9CEa9bF2450ED8082d73e8DaFC47989558E.
Submitted contract for verification:
        Response: `OK`
        GUID: `Pass - Verified`
        URL: https://viscan.io/address/0xc9a8d9cea9bf2450ed8082d73e8dafc47989558e
```
