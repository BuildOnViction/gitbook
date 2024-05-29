---
description: >-
  VicIssuer provides a friendly user interface and back-end mechanism to issue
  VRC20(deprecated) & VRC25 tokens in only a few steps.
---

# VicIssuer

Below are the most important features of [VicIssuer](https://issuer.viction.xyz/) that have made it a revolutionary tool:

* **User-Friendly Interface:** Issue a VRC20(deprecated) or VRC25 token in only a few steps.
* **No Coding Experience Required:** No prerequisite knowledge about smart contract programming is needed.
* **Token Customization Options:** Customize the token supply, token name, and minimum transaction fee through VicIssuer’s dashboard.

### **‌Know Your Token Type**

Before issuing your token on Viction, make sure you are aware of the available token types and the differences between them.

**VRC20(deprecated):** VRC20 is an equivalent token standard of ERC20 built on top of the Viction blockchain. VRC20 token holders would need to hold a small amount of VIC to cover extremely low transaction fees.

**VRC25:** VRC25 creates a frictionless experience for non-crypto users by allowing token holders to pay transaction fees by the token itself without having to hold any VIC in their wallet.

**Comparison Table**

|                                                 | **VRC20 (deprecated)** |                                        **VRC25**                                        |
| ----------------------------------------------- | :--------------------: | :-------------------------------------------------------------------------------------: |
| **Technical Requirements for Dapp Integration** |         **Low**        |                                       **Moderate**                                      |
| **Technical Requirements for Exchange Listing** |         **Low**        |                                       **Moderate**                                      |
| **Transaction Fees**                            |     **Native VIC**     | <p><strong>By token itself</strong></p><p><strong>(no need for native VIC)</strong></p> |

### ISSUE

**Step 1:** Go to [https://issuer.viction.xyz/](https://issuer.viction.xyz/) and click on **Issue New Token**.

<figure><img src="../../../.gitbook/assets/Screenshot 2023-11-26 at 00.41.26.png" alt=""><figcaption></figcaption></figure>

**Step 2:** Unlock your wallet by choosing one of the available methods.

<figure><img src="../../../.gitbook/assets/Screenshot 2023-11-26 at 00.44.53.png" alt=""><figcaption></figcaption></figure>

**Step 3:** Fill out the token information including Token Name, Token Symbol, Token Supply, Decimals, Token Type VRC20(deprecated) or VRC25, and whether or not it’s reissuable.

* The symbol of the token contract is the symbol by which the token contract should be known, for example, “MYT”. It is broadly equivalent to a stock ticker and limited to 5 characters in length.
* Decimals refer to how divisible a token can be, from 0 (not at all divisible) to 18 (pretty much continuous) and even higher if required. Technically speaking, the decimal value is the number of digits that come after the decimal place when displaying token values on-screen.
* Make sure to check out the differences between reissuable/ non-reissuable tokens, and VRC20(deprecated)/ VRC25 tokens by hovering on the information icon and clicking on the “Differences?” link.

<figure><img src="../../../.gitbook/assets/Screenshot 2023-11-26 at 00.50.40.png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/Screenshot 2023-11-26 at 00.51.13.png" alt=""><figcaption></figcaption></figure>

{% hint style="warning" %}
**Disclaimer:** The token issuance fee could vary depending on how much it costs to deploy the smart contract.
{% endhint %}

**Step 4:** VicIssuer will ask for the token’s information to confirm. Please check all the criteria carefully before clicking on the “Issue token” and wait for the contract to be deployed.

For VRC25 tokens, if you want to verify and publish the contract source code on VicScan, please copy the source code from the **Code review** section. You can refer to the guidance [here](how-to-verify-and-publish-contract-source-code-on-vicscan.md).

{% hint style="warning" %}
If you do not copy it at this stage, you will not be able to go back and copy it later
{% endhint %}

<figure><img src="../../../.gitbook/assets/Screenshot 2024-05-30 at 00.41.56 (2).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
**Note:** Any developer with some experience developing and deploying smart contracts can refer to our reference implementation of the [Standards & Specification](https://docs.viction.xyz/developer-guide/standards-and-specification) to make customizations to the deployed token contract.
{% endhint %}

### **THE STEPS BELOW ARE FOR VRC25 TOKENS ONLY**

**Step 5:** A notification is received when the token is successfully issued. Click “View detail” to check the token’s summary including number of holders, transactions, etc. For VRC25 tokens, choose **Apply to pay fee by token** for VIC ZeroGas integration.

**Step 6:** Once deployed, the issuer needs to agree that the fees for all transactions to the newly deployed token contract will be paid in terms of the issued token. Once the conditions are agreed upon, move to the next step by clicking “I understand”.

**Step 7:** The token issuer needs to deposit a minimum amount of 10 VIC. The deposit can’t be withdrawn. The VIC held in the deposit pool will be deducted to pay the Masternodes for processing transactions.

**Step 8:** Now the new VRC25 token can be used. Edit the transaction fee in the token itself. Change this number at any time during the operation period of the token.

**Step 9:** In the token management dashboard, there are buttons to interact with the tokens, such as transfer and deposit more VIC to pay for subsequent transaction fees. Don’t forget to regularly check the balance of the VRC25 deposit because transactions will not be processed if the remaining deposit is not enough to pay the transaction fees.

### **DONATE VIC FOR VRC25 TRANSACTION FEES**

If there are not enough VIC funds to pay for subsequent transaction fees, any token holders can deposit more VIC to the VicIssuer contract to continue making transactions.‌

Go to the **“Donate VRC-25 fee”** tab from VicIssuer’s homepage. Enter the name of the token to donate VIC to, then enter the donation amount. Considering that the transaction fee in Viction is near zero, 1 VIC can power thousands of transactions.

![](https://lh5.googleusercontent.com/PL-tz1-aPJlSOOaNlMBgj3He75quhYhHTv9DXzNAvlwlvfZ8iXD-XmznFiq7K5hFhtzqGP8GMBXcrvobrE8-MfNqtygA48BI7OnjY9DYY5v5Up1V9k0cd3QkkQfxTNG36VYWbdy3)
