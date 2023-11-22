---
description: >-
  VicIssuer provides a friendly user interface and back-end mechanism to issue
  TRC20 & TRC21 tokens in only a few steps.
---

# VicIssuer

Below are the most important features of [VicIssuer](https://issuer.viction.xyz/) that have made it a revolutionary tool:

* **User-Friendly Interface:** Issue a TRC20 or TRC21 token in only a few steps.
* **No Coding Experience Required:** No prerequisite knowledge about smart contract programming is needed.
* **Token Customization Options:** Customize the token supply, token name, and minimum transaction fee through VicIssuer’s dashboard.

**‌Know Your Token Type**

Before issuing your token on Viction, make sure you are aware of the available tokens types and the differences between them.

**TRC20:** TRC20 is an equivalent token standard of ERC20 built on top of the Viction blockchain. TRC20 token holders would need to hold a small amount of VIC to cover extremely low transaction fees.

**TRC21:** TRC21 creates a much frictionless experience for non-crypto users by allowing token holders to pay transaction fees by the token itself without having to hold any VIC in their wallet. \\

**Comparison Table**

|                                                 |    **TRC20**   |                                        **TRC21**                                        |
| ----------------------------------------------- | :------------: | :-------------------------------------------------------------------------------------: |
| **Technical Requirements for Dapp Integration** |     **Low**    |                                       **Moderate**                                      |
| **Technical Requirements for Exchange Listing** |     **Low**    |                                       **Moderate**                                      |
| **Transaction Fees**                            | **Native VIC** | <p><strong>By token itself</strong></p><p><strong>(no need for native VIC)</strong></p> |

### ISSUE

**Step 1:**

Go to [https://issuer.Viction.com/](https://issuer.viction.com/) and click on “Issue New Token”.

<div>

<img src="https://lh3.googleusercontent.com/ndCZhxRX0DduCHamfc5suwnVgXZQMFkSASLryG9M_C3m0XF7uHRPkjN-XqQ9HdWgMDllWsuqQPgLR1d8eiucYwxKtisx8wkoG_vkLF1eA7VdCEgMmMCrK0duv7h3u85CrpG1O_Zz" alt="">

 

<figure><img src="<../../.gitbook/assets/Screenshot_2 (2).png>" alt=""><figcaption></figcaption></figure>

</div>

**Step 2:**

Unlock your wallet by choosing one of the available methods.

<div>

<img src="https://lh5.googleusercontent.com/5i4cEou5twtRPvc8KlIDBUnYTUnOxqkdBsIGtdO3f1BI2wxNuhKDyPcbwPJP2g1iMY1386YvY1f-WH_BkTO5YXojnaIgRR1BmKCb72KcJNwg4lT2kktO7WCZWfq9EuU0YnTctulc" alt="">

 

<figure><img src="<../../.gitbook/assets/Screenshot_3 (2).png>" alt=""><figcaption></figcaption></figure>

</div>

**Step 3:**

Fill out the token information including Token Name, Token Symbol, Token Supply, Decimals, Token Type (TRC20 or TRC21), and whether or not it’s reissuable.

* The symbol of the token contract is the symbol by which the token contract should be known, for example, “MYT”. It is broadly equivalent to a stock ticker and limited to 5 characters in length.
* Decimals refer to how divisible a token can be, from 0 (not at all divisible) to 18 (pretty much continuous) and even higher if required. Technically speaking, the decimals value is the number of digits that come after the decimal place when displaying token values on-screen.
* Make sure to check out the differences between reissuable/ non-reissuable tokens, and TRC20/ TRC21 tokens by hovering on the information icon and clicking on the “Differences?” link.

<div>

<img src="https://lh4.googleusercontent.com/RccOJoSplATEnan10naKZ0PW-qrB-L_cOiJNpQFJBhLJH9ENCkRl77eKfqKQtrVd3B6pkElCrB7iOZCMokegoibCrwmIKMXsM3WljvPgFa7n7Nzxddct4sofZUEmaetbKYOB83TH" alt="">

 

<figure><img src="<../../.gitbook/assets/Screenshot_1 (2).png>" alt=""><figcaption></figcaption></figure>

</div>

<figure><img src="../../.gitbook/assets/Screenshot_2.png" alt=""><figcaption></figcaption></figure>

**Disclaimer:** The token issuance fee could vary depending on how much it costs to deploy the smart contract.

**Step 4:**

VicIssuer will ask for the token’s information to confirm. Please check all the criteria carefully before clicking on the “Issue token” and wait for the contract to be deployed.

**Note:** Any developer with some experience developing and deploying smart contracts can refer to our reference implementation of the [Standards & Specification](https://docs.viction.xyz/developer-guide/standards-and-specification) to make customizations to the deployed token contract.

**THE STEPS BELOW ARE FOR TRC21 TOKENS ONLY**

**Step 5:** A notification is received when the token is successfully issued. Click “View detail” to check the token’s summary including: number of holders, transactions, etc. For TRC21 tokens, choose “Apply to pay fee by token” for VIC ZeroGas integration.

![](https://lh6.googleusercontent.com/s8zaJXonmRhE2DW8G2pCESXg9p5OHfYGmZYmf7iO\_h9Km5ddMq2MPCq-PE1gyPlPSbqsSCHN0ES6sdL4lNanfr3RWk-L1iEivRQnmW4fOP2KEg5IV4hBgEUccX9fy5RhTLjNejbL)

**Step 6:** Once deployed, the issuer needs to agree that the fees for all transactions to the newly deployed token contract will be paid in terms of the issued token. Once the conditions are agreed, move to the next step by clicking “I understand”.

**Step 7:** The token issuer needs to deposit a minimum amount of 10 VIC. The deposit can’t be withdrawn. The VIC held in the deposit pool will be deducted to pay the Masternodes for processing transactions.

**Step 8:** Now the new TRC21 token can be used. Edit the transaction fee in the token itself. Change this number at any time during the operation period of the token.

![](https://lh6.googleusercontent.com/DgX6LNwhUIybgabf3K9iLpd\_DPYkgLrHHWlJ3RML8qPQoZa\_Dvp5rvaJ8c8ZOwnEfkcyRJtlUqYB5-PuY3X0pjdJglnFZ0-j9eL2Lb1QXdJaMmm7jUh526k9oyF-\_RHZUD-hG9Rd)

**Step 9:** In the token management dashboard, there are buttons to interact with the tokens, such as transfer and deposit more VIC to pay for subsequent transaction fees. Don’t forget to regularly check the balance of the TRC21 deposit because transactions will not be processed if the remaining deposit is not enough to pay the transaction fees.

![](https://lh3.googleusercontent.com/I2ffwVcBRRPCo43hFDXrc-9HXoXdzxQWJofCbR4R-VW342b0EChRjR3tcR3TP3tKu3s26v6MjP7NnGgJqVBvBBiEELNLj1W82UhSH6YZM6akbFLlGAoh6FAp5t77q4njg8DQyiqK)

**DONATE VIC FOR TRC21 TRANSACTION FEES**

If there are not enough VIC funds to pay for subsequent transaction fees, any token holders can deposit more VIC to the VicIssuer contract to continue making transactions.‌

Go to the **“Donate TRC-21 fee”** tab from VicIssuer’s homepage. Enter the name of the token to donate VIC to, then enter the donation amount. Considering that the transaction fee in Viction is near-zero, 1 VIC can power thousands of transactions.

![](https://lh5.googleusercontent.com/PL-tz1-aPJlSOOaNlMBgj3He75quhYhHTv9DXzNAvlwlvfZ8iXD-XmznFiq7K5hFhtzqGP8GMBXcrvobrE8-MfNqtygA48BI7OnjY9DYY5v5Up1V9k0cd3QkkQfxTNG36VYWbdy3)