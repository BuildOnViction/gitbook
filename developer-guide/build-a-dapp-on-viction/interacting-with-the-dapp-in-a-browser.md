# Interacting with the Dapp in a browser

Now we’re ready to use our Dapp!

### Install and configure MetaMask <a href="#id-4986" id="id-4986"></a>

1. Install the [MetaMask browser extension](https://metamask.io/) in Chrome or FireFox.
2. Once installed, you’ll see the MetaMask fox icon next to your address bar. Click the icon and MetaMask will open up.
3. Create a New password. Then, write down the Secret Backup Phrase and accept the terms. By default, MetaMask will create a new Ethereum address for you.

<img src="https://miro.medium.com/max/1828/1*tV2bQfZ2vVhvpOOwKY0Y5g.png" alt="" data-size="original">

_Initiating MetaMask_

4\. Now we’re connected to the Ethereum network, with a brand new wallet with 0 ETH.

5\. Let’s now connect MetaMask to Viction (testnet). Click the menu with the “Main Ethereum Network” and select **Custom RPC**. Use the [Networks data from Viction](../../how-to/how-to-connect-to-viction-network/metamask.md) (testnet) and click **Save**

![](https://miro.medium.com/max/60/1\*Dm4qhGJOjnolRwxX-VN94w.png?q=20) ![](https://miro.medium.com/max/1424/1\*Dm4qhGJOjnolRwxX-VN94w.png)

_Connecting MetaMask to Viction (testnet)_

6\. The network name at the top will switch to say “Viction testnet”. Now that we are on Viction network we can import Viction wallets.

We could use the VIC wallet we created previously, but better **let’s create a new VIC wallet** and add a few VIC tokens — _you know how to do it_.

7\. Once you have created your new VIC wallet, **copy the private key**. Back to MetaMask, click on the top-right circle and select **Import Account.** Paste the private key and _voilà_! Your VIC wallet is loaded in MetaMask

![](https://miro.medium.com/max/60/1\*AjEHidU-h0Ae0CXTsQUJ5Q.png?q=20) ![](https://miro.medium.com/max/1298/1\*AjEHidU-h0Ae0CXTsQUJ5Q.png)

_Importing a wallet_

### Using the Dapp <a href="#id-9432" id="id-9432"></a>

If you want to get started with your dApp quickly or see what this whole project looks like with a frontend, you can use Hardhat's[ boilerplate repo](https://github.com/NomicFoundation/hardhat-boilerplate).

The first things you need to do are cloning this repository and installing its dependencies:

```bash
git clone https://github.com/NomicFoundation/hardhat-boilerplate.git
cd hardhat-boilerplate
npm install
```

### **Front End App**

In `frontend` you'll find a simple app that allows the user to do two things:

* Check the connected wallet's balance.
* Send tokens to an address.

It's a separate npm project and it was created using `create-react-app`, so this means that it uses webpack and babel.

```bash
npx hardhat node
```

Once installed, let's run Hardhat's testing network:

```bash
npx hardhat run scripts/deploy.js --network localhost
```

Then, on a new terminal, go to the repository's root folder and run this to deploy your contract:

```bash
npx hardhat run scripts/deploy.js --network localhost
```

Finally, we can run the frontend with:

```bash
cd frontend
npm install
npm start
```

Open [http://localhost:3000/](http://localhost:3000/) to see your Dapp. You will need to have [Coinbase Wallet](https://www.coinbase.com/wallet) or [Metamask](https://metamask.io/) installed and listening to`localhost 8545.`([Example](https://github.com/c98tristan/gitbook-Viction/blob/master/developer-guide/building-dapp-on-Viction/develop-a-simple-web3-frontend-to-interact-with-the-contract/interacting-with-the-dapp-in-a-browser.md#4986))
