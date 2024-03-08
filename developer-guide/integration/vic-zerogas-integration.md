---
description: >-
  VIC ZeroGas is the runtime feature to perform gas-less transaction with VRC25
  token
---

# VIC ZeroGas integration

### How it works

* VIC ZeroGas enables gas-less transaction for VRC25 by requiring the owner to deposit VIC to VRC25Issuer contract. So when there is transaction call to VRC25 token, the gas fee will be paid by the owner. Please note that internal call to VRC25 token won't be gas-sponsored.
* The owner of VRC25 token must call `apply` function of `VRC25Issuer` contract at [https://www.vicscan.xyz/address/0x8c0faeb5c6bed2129b8674f262fd45c4e9468bee](https://www.vicscan.xyz/address/0x8c0faeb5c6bed2129b8674f262fd45c4e9468bee) after deployment in order to register for VIC ZeroGas. If a contract didn't register VIC ZeroGas yet, the transaction fee must be paid by the user who perform the transaction.
* When the VIC for the VRC25 token is exhausted, user will pay gas for it normally unless the owner deposit more VIC.

### Requirement

* Smart-contract that meet [VRC25 Specification](../standards-and-specification/vrc25-specification.md).
* 10 VIC for first time registration.

### How to apply (mainnet)

The owner of VRC25 token must call `apply` function of `VRC25Issuer` contract at&#x20;

[https://www.vicscan.xyz/address/0x8c0faeb5c6bed2129b8674f262fd45c4e9468bee](https://www.vicscan.xyz/address/0x8c0faeb5c6bed2129b8674f262fd45c4e9468bee)

### How to apply (testnet)

If your **test token** is deployed to the **testnet**, you also still can call the apply function of VRC25Issuer contract at the same address: [https://testnet.vicscan.xyz/address/0x8c0faeb5c6bed2129b8674f262fd45c4e9468bee](https://testnet.vicscan.xyz/address/0x8c0faeb5c6bed2129b8674f262fd45c4e9468bee)

The VIC testnet token can be found via faucet:  [https://faucet-testnet.viction.xyz/](https://faucet-testnet.viction.xyz/)

The VICIssuer testnet: [https://issuer-testnet.viction.xyz/](https://issuer-testnet.viction.xyz/)



The [source code](https://github.com/BuildOnViction/trc25/raw/main/contracts/tests/VRC25Issuer.sol) and [ABI](https://github.com/BuildOnViction/trc25/raw/main/metadata/VRC25Issuer.json) for VRC25Issuer contract can be found in [VRC25 repository](https://github.com/BuildOnViction/vrc25).
