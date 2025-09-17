# Chain Data Snapshots

## Overview

For a node to join the network and work with other nodes, it must sync data with other nodes first. Overtime, the data to be synchronized will increased and the process will take several days to weeks, even months.

## Download

Snapshots for mainnet are available for both full node and archive node:

* Full node: [https://snapshot.viction.xyz/VICTION\_FULL\_DATA.tar.zst](https://snapshot.viction.xyz/VICTION_FULL_DATA.tar.zst)
* Full node mirror: [https://chain-snapshots.tforce.dev/viction/vic\_main\_full.tar.zst](https://chain-snapshots.tforce.dev/viction/vic_main_full.tar.zst)
* Archive node: [https://snapshot.viction.xyz/VICTION\_ARCHIVE\_DATA.tar.zst](https://snapshot.viction.xyz/VICTION_ARCHIVE_DATA.tar.zst)
* Archive node mirror: [https://chain-snapshots.tforce.dev/viction/vic\_main\_archive.tar.zst](https://chain-snapshots.tforce.dev/viction/vic_main_archive.tar.zst)&#x20;

{% hint style="info" %}
As of September 2025, the size after extraction for full node and archive node are 1014G and 4161G respectively.
{% endhint %}

To download the file, it's recommended to use **wget** or **aria2**.

```sh
# donwload using wget
wget -P /tmp https://snapshot.viction.xyz/VICTION_FULL_DATA.tar.zst

# download using aria2
aria2c -c -d /tmp https://snapshot.viction.xyz/VICTION_FULL_DATA.tar.zst
```

## How to use

The snapshot is compressed using zstandard for balancing between speed and compression.

After downloaded the file to `/tmp/VICTION_FULL_DATA.tar.zst`, to extract the file to a directory, say `/data/victionchain`, please run this command:

<pre class="language-sh"><code class="lang-sh"><strong># create destination directory
</strong>mkdir /data/viction

# extract the archive
tar -xvf /tmp/VICTION_FULL_DATA.tar.zst -C /data/victionchain
</code></pre>

After extraction, the datadir should look like this:

<figure><img src="../.gitbook/assets/viction_data_dir.jpg" alt=""><figcaption></figcaption></figure>

### Notes

To download and extract the file in background, in Linux host can use `nohup` for this purpose.

```sh
# donwload using wget
wget -b -P /tmp -o /tmp/VICTION_FULL_DATA.tar.zst.txt https://snapshot.viction.xyz/VICTION_FULL_DATA.tar.zst

# download using aria2
nohup aria2c -c -d /tmp https://snapshot.viction.xyz/VICTION_FULL_DATA.tar.zst > /tmp/VICTION_FULL_DATA.tar.zst.txt 2>&1 &

# extract the file
mkdir /data/victionchain
nohup tar -xvf /tmp/VICTION_FULL_DATA.tar.zst -C /data/victionchain > nohup.txt 2>&1 &
```
