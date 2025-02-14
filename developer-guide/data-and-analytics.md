# Data and analytics

## Introduction

As the network usage expands, the volume of valuable on-chain data will significantly increase. With this rapid data growth, the task of calculating and aggregating this information to generate reports or power a decentralized application (dApp) can become increasingly time-consuming and resource-intensive.

By utilizing established data providers, developers can accelerate their development processes, achieve more accurate results, and minimize the efforts required for ongoing maintenance. This approach allows development teams to focus on delivering the core functionalities of their projects, rather than getting bogged down by the complexities of data management. Leveraging these external data solutions ensures that teams can efficiently harness the wealth of on-chain data, driving innovation and enhancing the performance and reliability of their dApps.

## Prerequisites

To effectively use block explorers within the context of data analytics, it is essential to grasp their basic concepts. **Block explorers** provide a user-friendly interface for accessing and navigating blockchain data, which is crucial for extracting meaningful insights.

Additionally, gaining a solid understanding of indexing is important, as indexes significantly enhance system design by optimizing data retrieval processes. Indexes allow for faster and more efficient queries, which is particularly beneficial in handling large volumes of blockchain data.



From an architectural standpoint, it is also beneficial to understand the fundamentals of **APIs (Application Programming Interfaces)** and **REST (Representational State Transfer)**. Even a theoretical knowledge of these concepts can be invaluable. **APIs** enable different software applications to communicate with each other, while **REST** is a widely-used architectural style for designing networked applications. Together, they play a crucial role in developing robust and scalable systems for blockchain data analytics. Familiarity with these concepts will provide a solid foundation for leveraging block explorers and data indexing effectively in your projects.



## SubQuery Network <a href="#subquery-network" id="subquery-network"></a>

SubQuery is a premier data indexing service that provides developers with fast, reliable, decentralized, and customizable APIs tailored for their Web3 projects. By leveraging SubQuery, developers gain access to rich, indexed data from over 100+ ecosystems, including **Viction**. This enables them to create intuitive and immersive user experiences. The SubQuery Network ensures the resilience and decentralization of your applications by offering a robust infrastructure network. With SubQuery's comprehensive blockchain developer toolkit, you can focus on building the next generation of Web3 applications without the need to invest time and resources into developing a custom backend for data processing activities. This empowers developers to innovate and deploy unstoppable applications efficiently and effectively.

One of SubQuery's significant competitive advantages is its capability to aggregate data not only within a single blockchain but also across multiple blockchains, all within a single project. This cross-chain data aggregation enables developers to create advanced, feature-rich analytics dashboards and multi-chain block explorers. By consolidating data from various blockchains, SubQuery allows for comprehensive insights and real-time analytics, providing a unified view of blockchain activities. This functionality is particularly valuable for developers looking to build sophisticated tools and applications that require seamless integration and analysis of data from multiple blockchain networks, thereby enhancing the overall user experience and utility of their Web3 projects.



To get started, use the [Viction starter](https://github.com/subquery/ethereum-subql-starter/tree/main/Viction/viction-starter) and begin indexing Viction blockchain data in minutes. It is advised to first start with the [quick start guide](https://academy.subquery.network/indexer/quickstart/quickstart.html). Otherwise, further information may be obtained [here](https://academy.subquery.network/).



## Goldsky Subgraph

Goldsky is the go-to data indexer for web3 builders, offering high-performance subgraph hosting and realtime data replication pipelines.

Goldsky provides a completely backwards-compatible subgraph indexing solution. The core of the indexing uses exactly the same WASM processing layer, but in addition, Goldsky offers:

* a rewritten RPC layer, autoscaling query layer, and storage optimizations to improve reliability (99.9%+ uptime) and performance (up to 6x faster)
* webhooks support out-the-box to enable notifications, messaging, and other push-based use cases
* support for custom EVM chains so you can index your own rollup or private blockchain seamlessly

You can query Viction blocks easily using this endpoint

[https://api.goldsky.com/api/public/project\_cld6kdj9u539w0htd50sbeqyz/subgraphs/viction-blocks/1.0/gn](https://api.goldsky.com/api/public/project_cld6kdj9u539w0htd50sbeqyz/subgraphs/viction-blocks/1.0/gn)



## The Graph

Getting historical data on a smart contract can be frustrating when you’re building a dApp. [The Graph](https://thegraph.com/) provides an easy way to query smart contract data through APIs known as subgraphs. The Graph’s infrastructure relies on a decentralized network of indexers, enabling your dapp to become truly decentralized.

### Quick Start[​](https://docs.fuse.io/developers/subgraphs#quick-start)

These subgraphs only take a few minutes to set up and get running. To get started, follow these three steps:

1. Initialize your subgraph project
2. Deploy & Publish
3. Query from your dapp

Pricing: All developers receive 100,000 free queries per month on the decentralized network. After these free queries, you only pay based on usage at $2 for every 100,000 queries.

Here’s a step-by-step walkthrough:

### 1. Initialize your subgraph project[​](https://docs.fuse.io/developers/subgraphs#1-initialize-your-subgraph-project)

#### Create a subgraph on Subgraph Studio⁠[​](https://docs.fuse.io/developers/subgraphs#create-a-subgraph-on-subgraph-studio)

Go to the [Subgraph Studio](https://thegraph.com/studio/) and connect your wallet. Once your wallet is connected, you can begin by clicking “Create a Subgraph”. It is recommended to use Title Case: “Subgraph Name Chain Name.”

![Create a Subgraph](https://lh7-rt.googleusercontent.com/docsz/AD_4nXec0i1XMpKLaNsJKKxKIE2CksezUDgJVNzYhte_meraAOr8YlLqG9YryTYc6dlEmEume_fhXAIdqruBUCITAZcJTzw2WwHGucq6UsotS4oIZUeIEyIGDK-UASG3Zifypzz9aM5h?key=ZR7I2qHpTceitGesCDnDjg4E)

You will then land on your subgraph’s page. All the CLI commands you need will be visible on the right side of the page:

![CLI commands](https://lh7-rt.googleusercontent.com/docsz/AD_4nXduXmDd9YeX1g3fbTxXpzc1glbPQJKxb2Weo4atzNSzidZFoTU6vQgkjGxFyNWORQ8SLeu1OoSdtqvQjpmgVFDDjZt5gbAa716isMAQRoxKbXvVJYBO9gtrPI9XbUhPmJlQRGOEhw?key=ZR7I2qHpTceitGesCDnDjg4E)

#### Install the Graph CLI⁠[​](https://docs.fuse.io/developers/subgraphs#install-the-graph-cli)

On your local machine run the following:

`npm install -g @graphprotocol/graph-cli`

#### Initialize your Subgraph⁠[​](https://docs.fuse.io/developers/subgraphs#initialize-your-subgraph)

You can copy this directly from your subgraph page to include your specific subgraph slug:

`graph init <SUBGRAPH_SLUG>`

You’ll be prompted to provide some info on your subgraph like this:

![cli sample](https://lh7-rt.googleusercontent.com/docsz/AD_4nXe_aM9tHEhv3E_IbROEt80-QVTIOn3Ei3_Hci6qywQuOztCvb1c93M_aqSVgwr2Wmst6B4o5gd_wcInMSm24j1rx0vboZblz_smTtsu3dHW06u5WP8Bo34x62U1cxfwFaoUziF2cg?key=ZR7I2qHpTceitGesCDnDjg4E)

Simply have your contract verified on the block explorer and the CLI will automatically obtain the ABI and set up your subgraph. The default settings will generate an entity for each event.

### 2. Deploy & Publish[​](https://docs.fuse.io/developers/subgraphs#2-deploy--publish)

#### Deploy to Subgraph Studio⁠[​](https://docs.fuse.io/developers/subgraphs#deploy-to-subgraph-studio)

First run these commands:

`$ graph codegen`

`$ graph build`

Then run these to authenticate and deploy your subgraph. You can copy these commands directly from your subgraph’s page in Studio to include your specific deploy key and subgraph slug:

`$ graph auth <DEPLOY_KEY>`

`$ graph deploy <SUBGRAPH_SLUG>`

You will be asked for a version label. You can enter something like v0.0.1, but you’re free to choose the format.

#### Test your subgraph⁠[​](https://docs.fuse.io/developers/subgraphs#test-your-subgraph)

You can test your subgraph by making a sample query in the playground section. The Details tab will show you an API endpoint. You can use that endpoint to test from your dapp.

![Playground](https://lh7-rt.googleusercontent.com/docsz/AD_4nXfFIngodCrLIYreEz-K-0t-HA-BpC0CN7Akomckev34aqh16nmKtkaik_5mwFF_TZoAMk5YOg-oMNiWNf4tr8Nrzvr6vZRvU2rqbk2km03ygiWYkNX8ZDUNxw0fi5gNdbdSBYKYNw?key=ZR7I2qHpTceitGesCDnDjg4E)

#### Publish Your Subgraph to The Graph’s Decentralized Network[​](https://docs.fuse.io/developers/subgraphs#publish-your-subgraph-to-the-graphs-decentralized-network)

Once your subgraph is ready to be put into production, you can publish it to the decentralized network. On your subgraph’s page in Subgraph Studio, click on the Publish button:

![publish button](https://lh7-rt.googleusercontent.com/docsz/AD_4nXf4STljAjkXLSj8XzVtP3YP8kXtQYQ1NEsB1yWMyqZsIiHpTLaLYCY07Tmp0mYRn8unKIF7WTFJAFov3VGEfULHMM6tpxKnHAlaPtPV-maRWp6hn1Nvg6FsNCfjWwDzEvJR87A2RA?key=ZR7I2qHpTceitGesCDnDjg4E)

Before you can query your subgraph, Indexers need to begin serving queries on it. In order to streamline this process, you can curate your own subgraph using GRT.

When publishing, you’ll see the option to curate your subgraph. As of May 2024, it is recommended that you curate your own subgraph with at least 3,000 GRT to ensure that it is indexed and available for querying as soon as possible.

![Publish screen](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdp47H91K3_BJ7bhPzWWh8IiGSaUuN6FzW7L1yLOp8b25AgkXe8bF6x4r6qJPFHc0cMgsoViSoWicXiv6gvnqr8zapgENQGYh6AZHIlAZsyaxj-tpQ70vdxP5ke3WLoAR-X6ZWvvQ?key=ZR7I2qHpTceitGesCDnDjg4E)

Note: The Graph's smart contracts are all on Arbitrum One, even though your subgraph is indexing data from Ethereum, BSC or any other [supported chain](https://thegraph.com/docs/en/developing/supported-networks/).

### 3. Query your Subgraph[​](https://docs.fuse.io/developers/subgraphs#3-query-your-subgraph)

Congratulations! You can now query your subgraph on the decentralized network!

For any subgraph on the decentralized network, you can start querying it by passing a GraphQL query into the subgraph’s query URL which can be found at the top of its Explorer page.

Here’s an example from the [CryptoPunks Ethereum subgraph](https://thegraph.com/explorer/subgraphs/HdVdERFUe8h61vm2fDyycHgxjsde5PbB832NHgJfZNqK) by Messari:

![Query URL](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcj6_nq8W5X7AoIdOXbs2Dh4nzAg0x3SNdqRuSLNqV1YloNMr2amiDk1-J7a-C0wRPLF3r0fdwkjzY2arBcwwTBswpMXJ165rx_Q00XaouaigA1eJJh9nW9yp5Bx8nVKeFITiYM?key=ZR7I2qHpTceitGesCDnDjg4E)

The query URL for this subgraph is:

[https://gateway-arbitrum.network.thegraph.com/api/\*\*\[api-key\]\*\*/subgraphs/id/HdVdERFUe8h61vm2fDyycHgxjsde5PbB832NHgJfZNqK](https://gateway-arbitrum.network.thegraph.com/api/**\[api-key]**/subgraphs/id/HdVdERFUe8h61vm2fDyycHgxjsde5PbB832NHgJfZNqK)

Now, you simply need to  fill in your own API Key to start sending GraphQL queries to this endpoint.

#### Getting your own API Key[​](https://docs.fuse.io/developers/subgraphs#getting-your-own-api-key)

![API keys](https://lh7-rt.googleusercontent.com/docsz/AD_4nXe4LCeMfSqlCQPcJrDjxP3k459imR8knwvWxpxFrhLBs1GZbn12I4n5VWncEGnsvEzV-DaWnzGGDCNsysUB2rFsEb7UWCfAChtTN6EuY1sRgu9P0ZZpAVc2IRrywcnkA5b8oF5pCg?key=ZR7I2qHpTceitGesCDnDjg4E)

In Subgraph Studio, you’ll see the “API Keys” menu at the top of the page. Here you can create API Keys.

### Appendix[​](https://docs.fuse.io/developers/subgraphs#appendix)

#### Sample Query[​](https://docs.fuse.io/developers/subgraphs#sample-query)

This query shows the most expensive CryptoPunks sold.

`{`

&#x20;`trades(orderBy: priceETH, orderDirection: desc) {`

&#x20;  `priceETH`

&#x20;  `tokenId`

&#x20;`}`

`}`

Passing this into the query URL returns this result:

`{`

&#x20;`"data": {`

&#x20;  `"trades": [`

&#x20;    `{`

&#x20;      `"priceETH": "124457.067524886018255505",`

&#x20;      `"tokenId": "9998"`

&#x20;    `},`

&#x20;    `{`

&#x20;      `"priceETH": "8000",`

&#x20;      `"tokenId": "5822"`

&#x20;    `},`

`//      ...`

💡 Trivia: Looking at the top sales on [CryptoPunks website](https://cryptopunks.app/cryptopunks/topsales) it looks like the top sale is Punk #5822, not #9998. Why? Because they censor the flash-loan sale that happened.

#### Sample code[​](https://docs.fuse.io/developers/subgraphs#sample-code)

`const axios = require("axios");`\


``const graphqlQuery = `{``

&#x20;`trades(orderBy: priceETH, orderDirection: desc) {`

&#x20;  `priceETH`

&#x20;  `tokenId`

&#x20;`}`

``}`;``

`const queryUrl =`

&#x20;`"https://gateway-arbitrum.network.thegraph.com/api/[api-key]/subgraphs/id/HdVdERFUe8h61vm2fDyycHgxjsde5PbB832NHgJfZNqK";`



`const graphQLRequest = {`

&#x20;`method: "post",`

&#x20;`url: queryUrl,`

&#x20;`data: {`

&#x20;  `query: graphqlQuery,`

&#x20;`},`

`};`



`// Send the GraphQL query`

`axios(graphQLRequest)`

&#x20;`.then((response) => {`

&#x20;  `// Handle the response here`

&#x20;  `const data = response.data.data;`

&#x20;  `console.log(data);`

&#x20;`})`

&#x20;`.catch((error) => {`

&#x20;  `// Handle any errors`

&#x20;  `console.error(error);`

&#x20;`});`

#### Additional resources:[​](https://docs.fuse.io/developers/subgraphs#additional-resources)

* To explore all the ways you can optimize & customize your subgraph for a better performance, read more about [creating a subgraph here](https://thegraph.com/docs/en/developing/creating-a-subgraph/).
* For more information about querying data from your subgraph, read more [here](https://thegraph.com/docs/en/querying/querying-the-graph/).
