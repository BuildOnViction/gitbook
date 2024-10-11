---
description: >-
  Viction VRRF, which stands for Verifiable Relatively Random Function, is a
  pseudo-random number generator that is both verifiable and provably fair.
---

# VRRF

## Get Started

In decentralized blockchain, random number generator (RNG) is essential recipe in developing application, especially in gaming application. Verifiable Random Function (VRF) in the recent years become a familiar concept for smart contract developers. In an effort to create a lightweight solution for smart contract developers to get random numbers, Viction Team is pleased to intro VRRF, a pseudo-random number generator.

With simplicity in mind, VRRF is designed as pseudo-random number generator, which is not perfect in term of probability distribution, but still extremely hard to be manipulated. In exchange for the absent of true random, VRRF enable calling smart-contracts to get random number with lighting fast speed and within one transaction only.

VRRF is an ideal solution for application that isn't too strict on probability distribution but still want to have a manipulation-resistant number to use as source of random number for the application itself. All the processes are fully on-chain and simple APIs make it easier to integration into any application.

## Features

VRRF creates a pseudo-random number based on mathematical and cryptographic techniques. Every request call to VRRF and its result will be processed and stored by the blockchain. Therefore, they are protected from being modified or controlled by any one party, including oracle operators, miners, users, or creators of smart contracts.

**Verifiable**: The random number created by VRRF is deterministic, with the same set of inputs, will result in the same output.

**Relatively**: This is where VRRF is different from other VRF solution. VRRF makes use of parts of previous result combined with many on-chain parameters and user inputted salt to feed into the random function. Because of this characteristic, _the order of calling VRRF in block can make the output more unpredictable_.

**Random**: The output of VRRF is presoudo-random and manipulation resistant number. With the length of 256-bit, it's sufficient for most applications' needs.

**Function**: At its heart is the function that utilized mathematical and cryptography techniques generate the random number.

## APIs

To integrate with VRRF, you will simply need to call `random(bytes32 salt)` function. Both of them return a 256-bit number, which is large enough to serve any application the developers may want.

```solidity
interface IVRRF {
  /**
   * @notice Get pseudo-random number base on provided seed
   * @param salt Random data as an additional input to harden the random
   */
  function random(bytes32 salt) external returns(bytes32);
}
```

The API is available at the following address in Viction:

* Mainnet: 0x53eDcf19e4fb242c9957CB449d2d4106fD760A7F
* Testnet: 0xDb14c007634F6589Fb542F64199821c3308A9d92

{% hint style="info" %}
For unit-testing, please implement a mock version of IVRRF in your test.
{% endhint %}

## Use cases

VRRF may be utilized to construct trustworthy smart contracts for any applications that are dependent on the possibility of unforeseen results:\
Responsibilities and resources are distributed at random. For instance, customer service members are assigned to any tickets or tele-sale support activities.

* By utilizing VRRF, it is possible to generate distinct attributes for NFTs, adding a touch of uniqueness to the minting process. Game Studio can use this to assign a unique set of characteristics through a randomized process.
* Developers have the ability to create more enjoyable blockchain games by using random results, which are unpredictable.
* Lottery system to select winners at random. With VRRF, users will be able to verify that each winner is picked using a random source that is not biased in any way.

## Cost

At Viction, we believed that the VRRF should be **free** and **accessible** to everyone. So, any user may utilize this feature to construct what they want while enjoying a frictionless journey to Web3.

## Notices

* Due to the fact that VRRF relies on the order of calling transaction, protocols who make use of VRRF must wait for a short period of time (say 8-10 seconds) before displaying random result to end-users to avoid issues related to block re-org.

