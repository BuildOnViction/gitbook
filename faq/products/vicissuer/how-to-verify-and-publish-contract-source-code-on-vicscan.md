# How to Verify & Publish Contract Source Code on VicScan

## Issue a token on VicIssuer <a href="#issue-a-token-on-vic-issuer" id="issue-a-token-on-vic-issuer"></a>

To issue a token on VicIssuer, ensure you've completed the preceding steps. Once done, proceed to the final step outlined below. For detailed guidance, refer to the instructions [here ](./)

<figure><img src="../../../.gitbook/assets/Screenshot 2024-05-30 at 00.41.17.png" alt="" width="563"><figcaption></figcaption></figure>

Ensure that all detail is correct then click on the **Issue Token** button. <mark style="color:yellow;">**The code here is only displayed in this step**</mark>. Hence It is recommended that you copy & store it to your file. So you can use it to perform the contract verification later on.

{% hint style="warning" %}
**If you didn't copy the source code here, there is no way for you to go back to copy it again**
{% endhint %}

<figure><img src="../../../.gitbook/assets/Screenshot 2024-05-30 at 00.41.56 (1).png" alt="" width="563"><figcaption></figcaption></figure>

Allow the connection to the site, then confirm the deployment of a new contract via the wallet pop-up. Once completed, a success pop-up will be displayed.

<div>

<figure><img src="../../../.gitbook/assets/Screenshot 2024-05-30 at 00.44.23.png" alt=""><figcaption></figcaption></figure>

 

<figure><img src="../../../.gitbook/assets/Screenshot 2024-05-30 at 00.44.55.png" alt=""><figcaption></figcaption></figure>

</div>

**View** the contract at the dashboard of **VicIssuer**. Click on the contract address to view on explorer

<figure><img src="../../../.gitbook/assets/Screenshot 2024-05-30 at 00.45.15.png" alt=""><figcaption></figcaption></figure>

## Verify & Publish Contract Source Code on VicScan

**Step 1:** Click on the **Contract** tab & click on **Verify & Publish** button

<figure><img src="../../../.gitbook/assets/Screenshot 2024-05-30 at 00.46.55.png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/Screenshot 2024-05-30 at 00.48.01.png" alt=""><figcaption></figcaption></figure>

**Step 2:** Fill in the following information

* **Contract Address**: **Fetched** the contract address **automatically**
* **Contract Name**: If you create a **token** via **Viction Issuer** then the name should be
  * **MyVRC25Mintable** for **Reissueable** token (selected when issuing)
  * **MyVRC25** for **Non-reissueable** token
* **Complier:** Select the compiler version **v0.7.6** for verifying the **contract is issued** from **VicIssuer**
* **Optimization:** Default is **No**. Refer: [![](https://cdn.sstatic.net/Sites/ethereum/Img/favicon.ico?v=40dede55262c)'Runs (Optimizer) ' and 'Optimization' while verifying source code on Etherscan](https://ethereum.stackexchange.com/questions/64172/runs-optimizer-and-optimization-while-verifying-source-code-on-etherscan)
*   Click on the “**Add Solidity Source Code**“ to input the source code.

    * **File name** can be any thing without **space** or **special characters**.
    * **Solidity Source Code**: Copy & paste your source code from the VicIssuer screen.&#x20;



    <figure><img src="../../../.gitbook/assets/Screenshot 2024-05-30 at 00.52.59.png" alt=""><figcaption></figcaption></figure>

**Step 3:** The Contract is verified successfully

<figure><img src="../../../.gitbook/assets/Screenshot 2024-05-30 at 00.55.52.png" alt=""><figcaption></figcaption></figure>
