---
description: This guide will show you how to verify gas sponsored transactions
---

# How to verify gas sponsored transactions

## Background <a href="#background" id="background"></a>

As the current status of VRC25 standard, a few partner or users had been issued the token successfully. However, they are unable to regconize whether their transactions had been applied for ZeroGas or not. Hence this article is a guidance for how can they ensure that they applied the ZeroGas successfully.

## Prerequisite <a href="#prerequisite" id="prerequisite"></a>

* Assumed that the Token had been applied succesfully. If the token had not been created or not event apply it. Then kindly follow the guidance as here: [https://docs.viction.xyz/developer-guide/integration/vic-zerogas-integration](https://docs.viction.xyz/developer-guide/integration/vic-zerogas-integration)
* If the token had been issue via **VicIssuer**, then you can follow this guidance:[How to issue token, apply ZeroGas & testing on Viction Blockchain Testnet](https://coin98.atlassian.net/wiki/spaces/TT/pages/268075011)

## Getting Started <a href="#getting-started" id="getting-started"></a>

As the following image, the. user issued the token successfully. However, they know how to rectify whether the transaction is zero gas or not.

New Issued Token contract: [https://testnet.vicscan.xyz/address/0x4ff96908a19a2AF0E70404eF6Bc0925C0e43700A#code](https://testnet.vicscan.xyz/address/0x4ff96908a19a2AF0E70404eF6Bc0925C0e43700A#code)

VicIssuer Apply Tx: [https://testnet.vicscan.xyz/tx/0xde1aa5624aa5ab025b2b65c0a5c278b3791e930d79aaa3fedfb74d01aa133cba](https://testnet.vicscan.xyz/tx/0xde1aa5624aa5ab025b2b65c0a5c278b3791e930d79aaa3fedfb74d01aa133cba)

Step to verify with the example Tx:  [![](https://testnet.vicscan.xyz/favicon-dark.svg)VIC Scan - The most intuitive Viction explorer](https://testnet.vicscan.xyz/tx/0xf0ea48e8f8e0d02595ccb64821e0fc89ce06c284c976ea552490fc326483c19b)

In the example Tx we would notice a few following detail:

* **Tx Type**: Gas Sponsored
* **Sender** : 0xCc48C437020B17D881C719Ff53DF4e56022Fb61A&#x20;
* **Receiver**: 0xaa3984428fe62211c6485165c30584507175B3fb
* **Fee Payer (Token contract address)**: 0x4ff96908a19a2AF0E70404eF6Bc0925C0e43700A

<figure><img src="../.gitbook/assets/image (150).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (153).png" alt=""><figcaption></figcaption></figure>

As we can see, The Fee payer now is neither **Sender** or **recepient.** It is the token contract address, which means that the token had been **registered** for ZeroGas successfully.

For further testing, you can vist the **VRCIssuer** **contract** to figure whether the token is registered or not & the amout of sponsored fund is remaining by querying the token address.

**Testnet**: [https://testnet.vicscan.xyz/address/0x8c0faeb5c6bed2129b8674f262fd45c4e9468bee](https://testnet.vicscan.xyz/address/0x8c0faeb5c6bed2129b8674f262fd45c4e9468bee)

**Mainnet**: [https://www.vicscan.xyz/address/0x8c0faeb5c6bed2129b8674f262fd45c4e9468bee](https://www.vicscan.xyz/address/0x8c0faeb5c6bed2129b8674f262fd45c4e9468bee)

<figure><img src="../.gitbook/assets/image (155).png" alt=""><figcaption></figcaption></figure>

