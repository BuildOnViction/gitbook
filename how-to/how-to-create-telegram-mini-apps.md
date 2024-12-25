---
description: This guide will show you how to create Telegram Mini Apps on Viction
---

# How to create Telegram Mini Apps

## **What are Telegram Mini Apps?**

**Telegram Mini Apps** are lightweight web apps that run inside Telegram chats. They allow developers to create social experiences, games, marketplaces, and other services that tap into Telegram’s features and \~1B audience globally.

### Mini App type

There are two main types of Mini Apps:

#### **Inline Apps**

Inline Apps show up as results when a user types the bot’s username followed by a query. The user taps an app result to launch the Mini App. Inline Apps are great for:

* Search experiences
* Quick interactions
* Discovering new content

#### **Direct Link Apps**

Users can open a Direct Link App just by tapping a link. Direct Link Apps are aware of the current chat context and support shared, collaborative experiences. Direct Link Apps are ideal for:

* Social experiences
* Games
* Productivity tools
* And more

### Core Infrastructure

1. A Telegram-supported wallet: which allows developers to embed web3 wallet into their games. You might refer to the following that support Viction

* Particle Network
* Ramper
* Wallet Connect

\*\* Wallet bot could serve managing your assets without switching between apps outside of Telegram:\*

* WalletX
* Coin98 (coming soon)

1. A Webapp to link to Telegram
2. A Telegram Bot to redirect users to the Webapp
3. Payments - via crypto/Telegram Stars

## Integration

### 1. Create a Telegram Bot

#### Generate a private Telegram Bot

Visit the **@BotFather** bot (developed by Telegram’s core team) and enter **/newbot** to create a new bot. You will receive an API token for your bot. Keep this token private as it will allow you to control your bot.

#### Connect the Webapp to your Bot

Use the **/newapp** command in the **@BotFather** bot by selecting your bot. Provide details such as the app name, description, photo, etc. Finally, enter the URL of your webapp. Your mini app will now appear in the Telegram app and can be launched by users.

#### **Additional Capabilities**

Mini apps opened from a direct link have limited capabilities. They cannot read or send messages on behalf of the user. However, they support cooperative and multiplayer features within the current chat context. Users must redirect to inline mode to actively pick a result in order to send messages.

Mini apps are powerful tools for creating fully-fledged web services, team collaborations, multiplayer games, and more. The possibilities are endless.

### 2. **Register a Game with @GameBot**

The first step is to register your game with @BotFather. Send the /newgame command to @BotFather, and provide the required details including:

* The title and description of your game
* A cover photo
* The message text a user will see when starting a game
* The URL of your Mini App

### 3. Deploy your smart contracts and assets

Viction provide a all-in-one development platform for web3 telegram games to enable seamless game deployment with ease

1. Web3 wallet
2. Management dashboard
3. Audited contract templates for games
4. Game Engine SDK
5. Embedded Marketplace
6. In-game purchase

…Guide by steps from Sequence/Thirdweb/Elympics…

### 4. Using Telegram Stars for in-game purchase

Stars can ONLY be acquired through **in-app purchases** via Apple and Google or [PremiumBot](https://t.me/premiumbot), then spent on **digital products** offered by bots – from **e-books** and **online courses** to items in [Telegram games](https://core.telegram.org/bots#host-games).

Walkthrough [**Bot Payments API for Digital Goods and Services**](https://core.telegram.org/bots/payments-stars)

\*\* There is no current option to enable purchasing Stars using $VIC or other assets on Viction\*

You will find the necessary methods for building your payment implementation in the [Payments Section of the Bot API Manual](https://core.telegram.org/bots/api#payments).

In short, you must:

* Send an invoice via [sendInvoice](https://core.telegram.org/bots/api#sendinvoice) (`currency`: “XTR”)
* Await an [Update](https://core.telegram.org/bots/api#update) with the field `pre_checkout_query`
* Approve or cancel the order via [answerPreCheckoutQuery](https://core.telegram.org/bots/api#answerprecheckoutquery)
* Await an [Update](https://core.telegram.org/bots/api#update) with the field `successful_payment`
* Store the [SuccessfulPayment](https://core.telegram.org/bots/api#successfulpayment)’s `telegram_payment_charge_id` – it may be needed to issue a refund in the future
* Deliver the goods and services purchased by the user

> You may find that some API methods for Payments request a provider\_token. This parameter is only needed for sales of physical goods and services – for digital ones, you can leave it empty.

#### **Step-by-Step Process**

> See Bot API: Payments for the complete list of available methods and objects. Be sure to provide the proper set of parameters to account for the type of goods you are selling, differentiating between digital and physical orders.

#### **1. Create Invoice**

The user contacts `@merchantbot` and requests to purchase something. The bot forms an invoice message with a description of the goods or service and amount to be paid (expressed in Telegram Stars). There are two ways of creating an invoice:

#### **A. Bot Invoice**

Use the [sendInvoice](https://core.telegram.org/bots/api#sendinvoice) method to generate an invoice and send it to a chat. You can pass an empty string as the _provider\_token_ parameter, since the invoice is for digital goods and services.

Remember to specify `XTR` in the `currency` field, since all sales of **digital goods and services** are carried out exclusively in Telegram Stars.

#### **B. Inline Invoice**

If `@merchantbot` supports [inline mode](https://core.telegram.org/bots/inline), you can use [inputInvoiceMessageContent](https://core.telegram.org/bots/api#inputinvoicemessagecontent) to allow users to share invoices for your goods and services to their one-on-one chats with friends, or to their groups and channels. These invoices will have a **Pay button** that can be used multiple times.

#### **2. Choose Forwarding Behavior**

There are two ways for handling **forwarded copies** of your invoices, controlled by the parameter _start\_parameter_ in the [sendInvoice](https://core.telegram.org/bots/api#sendinvoice) method.

* **A. Multi-chat invoice.** Forwarded copies show a **Pay button**, which multiple users can press and attempt to pay for the goods or services. [Inline invoices](https://core.telegram.org/bots/payments-stars#b-inline-invoice) are always multi-chat invoices.
* **B. Single-chat invoice.** Invoice can only be paid from the chat to which it was sent, _forwarded copies_ show a **URL button** with a deep link to the bot. The deep link can be used to generate a similar invoice in the chat with the bot, to show an error message, or for other purposes. [More info on Deep Linking »](https://core.telegram.org/bots#deep-linking)

If a _single-chat invoice_ is sent to the chat with `@merchantbot`, it can only be paid **once**. If a _single-chat invoice_ is sent to any other chat, it can be paid **many times** by many users.

> To get a better understanding of how this works, try toggling the “Pay from Forwards” parameter when creating invoices with our demo @ShopBot.

Regardless of whether or not the **Pay** button is available in an invoice, the merchant bot always has the power to decide whether or not to accept new payments for a particular invoice.

#### **3. Pre-Checkout**

The user purchases Stars from Telegram (if necessary), then presses the pay button. At this moment the Bot API sends an [Update](https://core.telegram.org/bots/api#update) with the field _pre\_checkout\_query_ that contains all the available information about the order to the bot.

Your bot must reply using [answerPrecheckoutQuery](https://core.telegram.org/bots/api#answerprecheckoutquery) within **10 seconds** after receiving this update or the transaction is canceled.

The bot may return an error if it can't process the order for any reason. We highly recommend specifying a reason for failure to complete the order in human readable form (e.g. _"Sorry, we're all out of rubber duck digital posters! Would you be interested in a cast iron bear digital poster instead?"_). Telegram will display this reason to the user.

> Warning: It is critical to make sure your bot only accepts multiple payments when the order can be processed correctly. This is especially important if you are using multi-chat, inline or single-chat, multi-use invoices.

#### **4. Checkout**

If the bot confirms the order and the payment is successful, the API will send a receipt message of the type [_successful\_payment_](https://core.telegram.org/bots/api#message) from the user. Once your bot receives this message, it should proceed with sending the digital goods or services purchased by the user.

> Warning: You must always check that you received a successful\_payment update before delivering the goods or services purchased by the user – simply answering a pre\_checkout\_query does not guarantee a successful order or payment.

If the message was sent to any other chat, the **Pay button** remains and can be used again. It is up to the merchant bot whether to actually accept multiple payments.

### 5. Share your game

Once registered, your game will receive a shareable game URL and a game code which players can enter to launch the game. You can share this URL and code on your website, social media, and within Telegram chats to spread your game to other players.
