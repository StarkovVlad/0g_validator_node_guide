# 0g_validator_node_guide

![0G-bg-2](https://github.com/user-attachments/assets/33c09ed1-3199-4f14-9a24-d473511c7c01)

<h1 align=center>💗Validator Node💗</h1>

## Hardware Requirement

```bash
- Memory: 64 GB
- CPU: 8 cores
- Disk: 1 TB NVME SSD
- Bandwidth: 100 MBps for Download / Upload
```

## Install 0gchaind via CLI
```bash
git clone -b v0.2.3 https://github.com/0glabs/0g-chain.git
./0g-chain/networks/testnet/install.sh
source ~/.profile
```

## Set Chain ID
```bash
0gchaind config chain-id zgtendermint_16600-2
```

## Initialize Node
```bash
0gchaind init <your_validator_name> --chain-id zgtendermint_16600-2
```

## Genesis & Seeds
### Copy the Genesis File
```bash
sudo apt install -y unzip wget
rm ~/.0gchain/config/genesis.json
wget -P ~/.0gchain/config https://github.com/0glabs/0g-chain/releases/download/v0.2.3/genesis.json
0gchaind validate-genesis
```

### Add Seeds
$HOME/.0gchain/config/config.toml. The format of the config.toml file is as follows:
```toml
[p2p]

# ...

# Comma separated list of seed nodes to connect to
seeds = "<node-id>@<ip>:<p2p port>"
```

seed = `81987895a11f6689ada254c6b57932ab7ed909b6@54.241.167.190:26656,010fb4de28667725a4fef26cdc7f9452cc34b16d@54.176.175.48:26656,e9b4bc203197b62cc7e6a80a64742e752f4210d5@54.193.250.204:26656,68b9145889e7576b652ca68d985826abd46ad660@18.166.164.232:26656
`

## Start TestNet
```bash
0gchaind start
```

