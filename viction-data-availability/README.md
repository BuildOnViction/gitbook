---
description: >-
  Viction's Data Availability (DA) represents a groundbreaking initiative to
  enhance this aspect of blockchain technology.
---

# Viction Data Availability

## Introduction

Every monolithic blockchain, which is a blockchain where all functions—such as consensus, data availability, and transaction execution—are integrated within a single protocol, includes a data availability layer. This layer ensures that all the necessary data for validating and verifying transactions is accessible to all network participants.

Viction's Data Availability (DA) represents a groundbreaking initiative to enhance this aspect of blockchain technology. By modularizing the data availability layer, Viction decouples it from the core Viction blockchain. This means that instead of being an inseparable part of the Viction blockchain, the DA layer is designed as a separate, standalone module.

This modular DA layer can be utilized as a roll-up solution by developers building on other blockchain networks. Roll-ups are a scalability technique that processes transactions off the main blockchain (off-chain) and then posts the transaction data back to the main blockchain. This reduces the computational load on the main blockchain while still benefiting from its security features.

By offering its DA layer as a modular component, Viction provides an efficient, scalable, and secure way for other blockchains to manage their data availability needs. This pioneering approach not only enhances the scalability of individual blockchains but also promotes interoperability and flexibility across the broader blockchain ecosystem.

## Viction DA Infrastructure diagram



<figure><img src="../.gitbook/assets/Screenshot 2024-08-07 at 11.29.52.png" alt=""><figcaption><p>Viction DA infrastructure diagram</p></figcaption></figure>

**Viction DA** takes advantage of AWS CloudFormation, a powerful service specifically designed to manage and provision AWS infrastructure using code. This approach allows us to define their cloud resources in simple text files, which can then be used to automatically and consistently create and manage those resources.&#x20;

By utilizing AWS CloudFormation, **Viction DA** ensures a deployment model that is highly scalable, meaning it can handle increased load without performance issues. It is also highly reliable, providing a stable and consistent environment, and automated, reducing the need for manual intervention and minimizing the risk of human error. This results in an efficient and effective way to manage cloud resources, ensuring that the infrastructure can grow and adapt as needed.

## System components context diagram

<figure><img src="../.gitbook/assets/Screenshot 2024-08-08 at 18.19.36.png" alt=""><figcaption><p>Viction DA - System component context diagram</p></figcaption></figure>

This describes the system components that we develop and how it connects to external components.

* Users initiate transactions on the Layer 2 (L2) blockchain.
* The L2 blockchain/ DA client submits the block data to the Viction DA service.
* Viction DA compresses the data, generates unique commitments and IDs, and returns these IDs. These IDs are used to retrieve the original data and associated proofs.
* The L2 blockchain sends the IDs back to Viction (Rollup Tx).
* Light nodes/ users can use these IDs to fetch the corresponding commitments and proofs from Viction DA.
* Light nodes/ users utilize the commitments and proofs to validate the authenticity and integrity of the data.



