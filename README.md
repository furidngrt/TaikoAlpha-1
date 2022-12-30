<p align="center"><img height="150" height="auto" src="https://user-images.githubusercontent.com/63885192/210028418-e15f2938-cb58-468f-8711-7375d66a038a.png"></p>

# Alpha-1 Testnet Guide

###  Deploy a contract
```
curl -L https://foundry.paradigm.xyz | bash
```

```
source /root/.bashrc
```

```
foundryup
```

Select 1 Proceed with installation (default)
```
curl https://sh.rustup.rs -sSf | sh
```

```
docker pull ghcr.io/foundry-rs/foundry:latest
```

```
forge init --template https://github.com/foundry-rs/forge-template hello_template
```

```
cd hello_template
```

```
forge build
```

```
forge test
```

```
forge create --legacy --rpc-url https://l2rpc.a1.taiko.xyz --private-key <your_private_key> src/Contract.sol:Contract
```

Paste transaction hash here https://l2explorer.a1.taiko.xyz




### Run a node

First request a faucet here before proceeding to the next step.

https://l2faucet.a1.taiko.xyz Taiko (A1 Testnet)
<p>
https://l1faucet.a1.taiko.xyz Ethereum (Taiko's Private L1)

install Dcoker
```
sudo apt autoremove docker* container* -y
```

```
sudo apt install jq curl wget tar zip unzip -y
```

```
curl -sSL https://get.docker.com | bash -
```

```
sudo curl -SL https://github.com/docker/compose/releases/download/v2.14.2/docker-compose-linux-x86_64 -o /usr/local/bin/docker-compose
```

```
sudo ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose
```

```
sudo chmod +x /usr/local/bin/docker-compose /usr/bin/docker-compose
```

```
sudo systemctl restart docker.service
```

```
```

Install
```
git clone https://github.com/taikoxyz/simple-taiko-node.git
```

```
cd simple-taiko-node
```

```
cp .env.sample .env
```

```
nano .env
```

Change ENABLE_PROPOSER=false to ENABLE_PROPOSER=true
<p>
In L1_PROPOSER_PRIVATE_KEY=enter your Private Key
<p>
In L2_SUGGESTED_FEE_RECIPIENT=enter your address

Run Node
```
sudo docker-compose up -d
```

check logs
```
sudo docker-compose logs -f
```
