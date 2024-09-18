# How to troubleshoot when the node is up but couldn't begin to sync block

In general, as long as the node is operational, it will begin to sync new blocks. However, there were a few unknown behaviors that prevented the block from synchronizing. As a result, this instruction will be helpful in resolving the issue of blocks not synchronizing once the node has been powered up.

<figure><img src="../.gitbook/assets/photo_2024-09-18 23.27.08 (1).jpeg" alt=""><figcaption><p>Node is Up but unable to sync new blocks</p></figcaption></figure>

The reason can come from the P2P port (default **30303**) from the node had been blocked by the Firewall. &#x20;

* **Solution**:  Rectify  & Unblocked the port.
* If the case that the firewall had been opened for the port. Then please try to run the node with the add-on command  `--nat extip:111.111.111.111` with `111.111.111.111` is the IP address to connect with internet (external network) of that node.

In case you are running the node via Docker, then you need to:

* Open the port **30303** to internet for **TCP/UDP**
* Docker should use the network mode `host` instead of `bridge`

&#x20;**Incorrect** mapping port

```
      - "30343:30303"
      - "30343:30303/udp"
```

**Correct** mapping port

```
  - "30303:30303"
  - "30303:30303/udp"
```

The explanation for the network mode host is that Docker may use the port as long as it starts the container; it does not need to map to another port. This will result in improved performance as docker will no longer need to proxy traffic.

Example of the `docker start command`

```
networks:
  viction:
    ipam:
      driver: default
      config:
        - subnet: 10.0.155.0/24

services:
  geth:
    image: *****.dkr.ecr.ap-northeast-1.amazonaws.com/blockchain-vic:1ef07e87
    restart: unless-stopped
    stop_signal: SIGTERM
    stop_grace_period: 300s
    volumes:
      - /viction:/var/data
      - ./password:/app/password
    networks:
      - viction
    ports:
      - "8595:8545"
      - "30303:30303"
      - "30303:30303/udp"
    entrypoint:
      - /app/geth
      - --datadir=/var/data
      - --syncmode=full
      - --gcmode=full
      - --networkid=88
      - --announce-txs
      - --rpc
      - --rpccorsdomain=*
      - --rpcaddr=0.0.0.0
      - --rpcport=8545
      - --rpcvhosts=*
      - --rpcapi=db,eth,net,web3,personal,debug
      - --ws
      - --wsaddr=0.0.0.0
      - --wsport=8546
      - --wsorigins=*
      - --gasprice=250000000
      - --bootnodes=enode://fd3da177f9492a39d1e7ce036b05745512894df251399cb3ec565081cb8c6dfa1092af8fac27991e66b6af47e9cb42e02420cc89f8549de0ce513ee25ebffc3a@3.212.20.0:30303,enode://97f0ca95a653e3c44d5df2674e19e9324ea4bf4d47a46b1d8560f3ed4ea328f725acec3fcfcb37eb11706cf07da669e9688b091f1543f89b2425700a68bc8876@3.212.20.0:30301,enode://b72927f349f3a27b789d0ca615ffe3526f361665b496c80e7cc19dace78bd94785fdadc270054ab727dbb172d9e3113694600dd31b2558dd77ad85a869032dea@188.166.207.189:30301,enode://c8f2f0643527d4efffb8cb10ef9b6da4310c5ac9f2e988a7f85363e81d42f1793f64a9aa127dbaff56b1e8011f90fe9ff57fa02a36f73220da5ff81d8b8df351@104.248.98.60:30301
      - --mine
      - --keystore=/var/data/keystore
      - --password=/app/password
      - --unlock=*****
      - --verbosity=5
```

If you are looking for other bootnodes, please refer to this [link](https://docs.viction.xyz/developer-guide/deploy-on-viction/viction-mainnet#bootnodes)

More detail for using the docker to run a node in mainnet can be found at the readme file [here](https://github.com/BuildOnViction/victionchain?tab=readme-ov-file#run-docker)
