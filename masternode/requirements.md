---
description: Hardware specification for running a Viction Mainnet node.
---

# Requirements

### General System Specs <a href="#hardware" id="hardware"></a>

Minimum requirements

* CPU: 2 cores
* RAM: 8 GB
* SSD: 1 TB
* Network: 10 Mb/s

Full node requirements

* CPU: 4 cores
* RAM: 16 GB
* SSD: 1 TB
* Network: 25 Mb/s

Masternode requirements

* CPU: 8 cores
* RAM: 16 GB
* SSD: 1 TB
* Network: 25 Mb/s

Archive node requirements

* CPU: 16-64 cores
* RAM: 32 GB
* SSD: 4 TB
* Network: 25 Mb/s

The requirements above are for typical workload and cannot cover all workloads. These are good starting points to adjust node specifications to fit with your workload.

{% hint style="info" %}
As of December 2024, the size of blockchain data is:

* Full node: 900 GB
* Archive node: 3743 GB
{% endhint %}

### Recommendation

We recommend using popular cloud providers as their reliability and uptime are close to 100%. These servers would be a good starting point:

* **Amazon EC2**: C5 instance
* **DigitalOcean**: CPU optimized droplet 16GB/8vCPU
* **Google Cloud Engine**: n2d-standard-8

Setting up a Masternode Candidate on a low specs machine might result in poor performances, significantly impacting owner's rewards and the chain performance.

{% hint style="info" %}
Notice

A Masternode has a certain number of tasks to process (validations, block creations, etc.) over time. Your Masternode should be able to process all the tasks that are designated to it, or the rewards will be negatively impacted. However, overpowered technical specifications of the Masternode will not result in greater rewards.
{% endhint %}

### Maintenance <a href="#maintenance" id="maintenance"></a>

All IT systems require maintenance.

It is of the owner's responsibility to ensure regular maintenance, and that the node has enough:

* Disk space to store the new blockchain data.
* Processing power to keep the chain operating at optimal speed.
* Monitoring to be able to react quickly in case of a problem occurring.
* Security measures like firewalling, OS security patching, SSH via keypairs, etc.

This is a non-exhaustive list.
