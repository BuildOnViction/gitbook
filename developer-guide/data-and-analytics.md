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



## Goldsky Subgraph <a href="#subquery-network" id="subquery-network"></a>

Goldsky is the go-to data indexer for web3 builders, offering high-performance subgraph hosting and realtime data replication pipelines.

Goldsky provides a completely backwards-compatible subgraph indexing solution. The core of the indexing uses exactly the same WASM processing layer, but in addition, Goldsky offers:

* a rewritten RPC layer, autoscaling query layer, and storage optimizations to improve reliability (99.9%+ uptime) and performance (up to 6x faster)
* webhooks support out-the-box to enable notifications, messaging, and other push-based use cases
* support for custom EVM chains so you can index your own rollup or private blockchain seamlessly

You can query Viction blocks easily using this endpoint

[https://api.goldsky.com/api/public/project\_cld6kdj9u539w0htd50sbeqyz/subgraphs/viction-blocks/1.0/gn](https://api.goldsky.com/api/public/project_cld6kdj9u539w0htd50sbeqyz/subgraphs/viction-blocks/1.0/gn)

