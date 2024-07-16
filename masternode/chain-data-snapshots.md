# Chain Data Snapshots

## Overview

For a node to join the network and work with other nodes, it must sync data with other nodes first. Overtime, the data to be synchronized will increased and the process will take several days to weeks, even months.

The snapshot consists of 2 parts that must be downloaded and extracted for a node to synchronize properly.

## Full Node

{% hint style="info" %}
To help node operators to catchup with network quickly, we create a snapshot for Viction mainnet **every Friday**
{% endhint %}

* TomoX**:** [https://snapshot.viction.xyz/TOMOX\_DATA.tar.zst](https://snapshot.viction.xyz/TOMOX\_DATA.tar.zst)
* Chain Data: [https://snapshot.viction.xyz/CHAIN\_DATA.tar.zdt](https://snapshot.viction.xyz/CHAIN\_DATA.tar.zdt)

We also have checksum information to verify downloaded files are correct.

* TomoX**:** [https://snapshot.viction.xyz/TOMOX\_DATA.tar.zst.sha1](https://snapshot.viction.xyz/TOMOX\_DATA.tar.zst.sha1)
* Chain Data**:** [https://snapshot.viction.xyz/CHAIN\_DATA.tar.zst.sha1](https://snapshot.viction.xyz/CHAIN\_DATA.tar.zst.sha1)

## Archive Node

{% hint style="info" %}
To help node operators to catchup with network quickly, we create a  archive snapshot for Viction mainnet quarter(3 months) for cost saving. Latest data is snapshot on **May 29th, 2024**
{% endhint %}

* TomoX**:** `https://snapshot.viction.xyz/archive-node/TOMOX_DATA.tar.zst`
* Chain Data: `https://snapshot.viction.xyz/archive-node/CHAIN_DATA.tar.zst`

We also have checksum information to verify downloaded files are correct.

* TomoX**:** `https://snapshot.viction.xyz/archive-node/TOMOX_DATA.tar.zst.sha1`
* Chain Data**:** `https://snapshot.viction.xyz/archive-node/CHAIN_DATA.tar.zst.sha1`

## **Notes**

* At the time of this writing, the size of the snapshot files are:
  * Nearly **800GB** for the Full Node
  * Nearly **3.5TB** for the Archive Node
* Please make sure that you have enough free space to store the files and the extracted contents.

## Example

{% hint style="info" %}
This is an example for using the snapshot with **Full Node**, if you are about to use for **Archive Node**, then please update the link to the archive data URL above.
{% endhint %}



### For Full Node

This example demonstrates how to use the snapshot files with the assumption that the node has been stopped and node data is stored at the following path: `/var/lib/docker/volumes/viction_mainnet/_data/data`

```bash
# set dir
VIC_DATA_DIR="/var/lib/docker/volumes/viction_mainnet/_data/data"
TMP_DIR="/tmp"

# download the files to /tmp folder
wget -c https://snapshot.viction.xyz/TOMOX_DATA.tar.zst -O $TMP_DIR/TOMOX_DATA.tar.zst
wget -c https://snapshot.viction.xyz/CHAIN_DATA.tar.zst -O $TMP_DIR/CHAIN_DATA.tar.zst

# remove existing data
rm -r $VIC_DATA_DIR/tomox
rm -r $VIC_DATA_DIR/tomo

# create new dir for extraction
mkdir -p $VIC_DATA_DIR/tomox
mkdir -p $VIC_DATA_DIR/tomo/chaindata

# extract the file
tar zstd xvf $TMP_DIR/TOMOX_DATA.tar.zst -C $VIC_DATA_DIR/tomox
tar zstd xvf $TMP_DIR/CHAIN_DATA.tar.zst -C $VIC_DATA_DIR/tomo/chaindata
```

* The file **CHAIN\_DATA.tar** is huge at the time of writing and will take a long time to download and extract. You can use the following command to perform those operations in background:

```bash
# download the file
wget -bqc https://snapshot.viction.xyz/CHAIN_DATA.tar.zst -O $TMP_DIR/CHAIN_DATA.tar.zst
```

```bash
# extract the file
nohup tar xvf $TMP_DIR/CHAIN_DATA.tar -C $VIC_DATA_DIR/tomo/chaindata &
```

### For Archive Node

This example demonstrates how to use the snapshot files with the assumption that the node has been stopped and node data is stored at the following path: `/var/lib/docker/volumes/viction_mainnet/_data/data`

```bash
# set dir
VIC_DATA_DIR="/var/lib/docker/volumes/viction_mainnet/_data/data"
TMP_DIR="/tmp"

# download the files to /tmp folder
wget -c https://snapshot.viction.xyz/archive-node/TOMOX_DATA.tar.zst -O $TMP_DIR/TOMOX_DATA.tar
wget -c https://snapshot.viction.xyz/archive-node/CHAIN_DATA.tar.zst -O $TMP_DIR/CHAIN_DATA.tar

# remove existing data
rm -r $VIC_DATA_DIR/tomox
rm -r $VIC_DATA_DIR/tomo

# create new dir for extraction
mkdir -p $VIC_DATA_DIR/tomox
mkdir -p $VIC_DATA_DIR/tomo/chaindata

# extract the file
tar zstd xvf $TMP_DIR/TOMOX_DATA.tar -C $VIC_DATA_DIR/tomox
tar zstd xvf $TMP_DIR/CHAIN_DATA.tar -C $VIC_DATA_DIR/tomo/chaindata
```

* The file **CHAIN\_DATA.tar.zst** is huge at the time of writing and will take a long time to download and extract. You can use the following command to perform those operations in background:

```bash
# download the file
wget -bqc https://snapshot.viction.xyz/archive-node/CHAIN_DATA.tar.zst -O $TMP_DIR/CHAIN_DATA.tar
```

```bash
# extract the file
nohup tar zstd xvf $TMP_DIR/CHAIN_DATA.tar -C $VIC_DATA_DIR/tomo/chaindata &
```
