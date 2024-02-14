# Chain Data Snapshots

### Overview

For a node to join the network and work with other nodes, it must sync data with other nodes first. Overtime, the data to be synchronized will increased and the process will take several days to weeks, even months.

To help node operators to catchup with network quickly, we create a snapshot for Viction mainnet every Friday. The snapshot consists of 2 parts that must be downloaded and extracted for a node to synchronize properly.

* TomoX**:** `https://snapshot.viction.xyz/TOMOX_DATA.tar`
* Chain Data: `https://snapshot.viction.xyz/CHAIN_DATA.tar`

We also have checksum information to verify downloaded files are correct.

* TomoX**:** `https://snapshot.viction.xyz/TOMOX_DATA.tar.sha1`
* Chain Data**:** `https://snapshot.viction.xyz/CHAIN_DATA.tar.sha1`

### Example

This example demonstrates how to use the snapshot files with the assumption that the node has been stopped and node data is stored at the following path: `/var/lib/docker/volumes/viction_mainnet/_data/data`

<pre class="language-bash"><code class="lang-bash"><strong># set dir
</strong>VIC_DATA_DIR="/var/lib/docker/volumes/viction_mainnet/_data/data"
TMP_DIR="/tmp"
<strong>
</strong><strong># download the files to /tmp folder
</strong>wget -c https://snapshot.viction.xyz/TOMOX_DATA.tar -O $TMP_DIR/TOMOX_DATA.tar
wget -c https://snapshot.viction.xyz/CHAIN_DATA.tar -O $TMP_DIR/CHAIN_DATA.tar

# remove existing data
rm -r $VIC_DATA_DIR/tomox
rm -r $VIC_DATA_DIR/tomo

# create new dir for extraction
mkdir -p $VIC_DATA_DIR/tomox
<strong>mkdir -p $VIC_DATA_DIR/tomo/chaindata
</strong>
# extract the file
tar xvf $TMP_DIR/TOMOX_DATA.tar -C $VIC_DATA_DIR/tomox
tar xvf $TMP_DIR/CHAIN_DATA.tar -C $VIC_DATA_DIR/tomo/chaindata
</code></pre>

### **Notes**

* At the time of this writing, the size of the snapshot files are nearly 800GB, please make sure that you have enough free space to store the files and the extracted contents.
* The file CHAIN\_DATA.tar is over 750GB at the time of writing and will take a long time to download and extract. You can use the following command to perform those operations in background:

```bash
# download the file
wget -bqc https://snapshot.viction.xyz/CHAIN_DATA.tar -O $TMP_DIR/CHAIN_DATA.tar
```

<pre class="language-bash"><code class="lang-bash"># extract the file
<strong>nohup tar xvf $TMP_DIR/CHAIN_DATA.tar -C $VIC_DATA_DIR/tomo/chaindata &#x26;
</strong></code></pre>
