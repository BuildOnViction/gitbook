---
description: >-
  This guide explains how to connect OP Stack rollups with the Viction Data
  Availability (DA) Layer using the testnet on Viction as settlement.
---

# Simple Guide for Integrating OP Stack Rollup with Viction DA Layer

## Prerequisites and Initial Configuration

To initiate an OP Stack rollup, follow the steps provided in the [official documentation](https://docs.optimism.io/builders/chain-operators/tutorials/create-l2-rollup). OP Stack documentation covers all procedures necessary for deploying the rollup, however, please note that the following adjustments are necessary for switching the network to Viction testnet:

* **Change the Network Chain ID**: Modify the chain ID from Viction testnet
* Modify the Batcher’s Destination Viction Address: Update the batcher’s destination Viction address to separate transactions from the default destination address on the Viction network.

The above two updates can be made after creating the `getting-started.json` file.

## Service Configuration for DA Layer Integration <a href="#service-configuration-for-da-layer-integration" id="service-configuration-for-da-layer-integration"></a>

Once all OP services are started, proceed with the following steps:

**1. Start the Light Client:** Initialize the light client service, which will handle storing L2 transaction batch data to the DA Layer.

**2. Stop the Batcher Service:** Temporarily halt the batcher service to apply the necessary configuration changes.

**3. Update the Batcher Configuration:** Modify the `--l1-eth-rpc` parameter in the batcher’s configuration to point to the light client’s RPC URL.

**4. Resume the Batcher Service:** Resume the batcher service to continue processing transactions.

[As illustrated in the Light Client diagram](https://app.gitbook.com/o/T5NoFw3kpfO1sTCSR41o/s/J7KRTq1pTZaELn1mvmb2/\~/changes/11/glitchd-products/data-availability/da-layer-integration-case-studies), the light client performs the following functions:

* Stores L2 transaction batch data to the DA Layer.
* Saves versioned hashes on Viction.
* Returns the versioned hashes to the batcher.

## Testing the Integration <a href="#testing-the-integration" id="testing-the-integration"></a>

A test OP Stack L2 network is available for experimentation:

* **Chain ID:** 42444
* **L2 RPC Node:** [http://geth-l2-op-stack-rollup-dev-1161098553.eu-central-1.elb.amazonaws.com:8545/](http://geth-l2-op-stack-rollup-dev-1161098553.eu-central-1.elb.amazonaws.com:8545/)
* **Batcher transactions on the Viction network can be found at the following link:**

By comparing the initial transactions with subsequent ones, particularly focusing on the input size, it becomes evident that the input size is significantly smaller in later transactions. This reduction occurs because the transactions contain only the versioned hashes of the data stored on the DA layer.

By adhering to these steps and configurations, the integration of the DA Layer solution with an OP Stack rollup can be successfully accomplished. For any questions or issues, please consult the documentation or contact our team.
