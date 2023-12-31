---
description: >-
  In this guide, we take a look at different token standards on the Viction
  platform.
---

# Standards & Specification

## **Overview**

In every blockchain ecosystem the token functions as the central element of a new type of economy. A token standard defines a set of rules that governs its issuance and use.

You may be familiar with ERC (Ethereum Request for Comments), which is a technical standard used for smart contracts on the Ethereum. This terminology is the origin of TRC tokens - the equivalent of ERC on Viction.

### **Fungible and Non-fungible token**

There are two token standards on Viction so far: VRC25 and VRC725. These token standards can be divided into two different categories: fungible and non-fungible tokens. Fungible tokens are all equal and divisible, non-fungible tokens (NFTs) are all distinct and non-divisible.

Fungible tokens are interchangeable and can be divided into smaller token units like VIC. The fungible token standard VRC25 as digital assets used to offer access to products and/or services on a platform. Non-fungible tokens of the type VRC725 are those that represent a unique asset, like a certificate or a collectible in-game item. The table below compares the differences between three types of token standards on Viction.

|                                                 | **VRC25**                | **VRC725**        |
| ----------------------------------------------- | ------------------------ | ----------------- |
| **Divisibility**                                | **Divisible**            | **Non-Divisible** |
| **Technical requirements for Dapp integration** | **Moderate**             | **Moderate**      |
| **Technical requirements for exchange listing** | **Moderate**             | **N/A**           |
| **Transaction Fee**                             | **In Transaction Token** | **In VIC**        |

### **VRC25 - Gas-less transaction experience**

VRC25 is an token standard similar to ERC20 plus the ability to let token holders to pay transaction fee using the token itself. Without having store VIC inside their wallet, user can still transfer the token or delegate it to someone. This will create a better experience for non-web3 user when using the ecosystem.

VRC25 also have an expanded use to enable any smart-contract to have transaction fee sponsor for users of their contract.

### **VRC725- Non-fungible token**

Non-fungible tokens (NFTs) are all distinct and special. Every token is rare, with unique characteristics, its own metadata and special attributes. Most of the time when people think about NFT, they refer to the successful CryptoKitties game as the standard for crypto-collectibles. However, there are many other applications for VRC725 tokens.

{% content-ref url="vrc25-specification.md" %}
[vrc25-specification.md](vrc25-specification.md)
{% endcontent-ref %}

{% content-ref url="vrc725-specification.md" %}
[vrc725-specification.md](vrc725-specification.md)
{% endcontent-ref %}
