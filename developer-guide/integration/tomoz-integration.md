---
description: TomoZ is the runtime feature to perform gas-less transaction with VRC25 token
---

# TomoZ integration

### How it works

* TomoZ enables gas-less transaction for VRC25 by requiring the owner to deposit VIC to VRC25Issuer contract. So when there is transaction call to VRC25 token, the gas fee will be paid by the owner. Please note that internal call to VRC25 token won't be gas-sponsored.
* The owner of VRC25 token must call `apply` function of `VRC25Issuer` contract at [0x8c0faeb5c6bed2129b8674f262fd45c4e9468bee](https://tomoscan.io/address/0x8c0faeb5c6bed2129b8674f262fd45c4e9468bee) after deployment in order to register for TomoZ. If a contract didn't register TomoZ yet, the transaction fee must be paid by the user who perform the transaction.
* When the VIC for the VRC25 token is exhausted, user will pay gas for it normally unless the owner deposit more VIC.

### Requirement

* Smart-contract that meet [VRC25 Specification](../standards-and-specification/trc25-specification.md).
* 10 VIC for first time registration.

### How to apply

The owner of VRC25 token must call `apply` function of `VRC25Issuer` contract at [0x8c0faeb5c6bed2129b8674f262fd45c4e9468bee](https://tomoscan.io/address/0x8c0faeb5c6bed2129b8674f262fd45c4e9468bee).

The [source code](https://github.com/BuildOnViction/trc25/raw/main/contracts/tests/VRC25Issuer.sol) and [ABI](https://github.com/BuildOnViction/trc25/raw/main/metadata/VRC25Issuer.json) for VRC25Issuer contract can be found in [trc25 repository](https://github.com/BuildOnViction/trc25/).

