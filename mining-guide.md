# FXL Mining Guide

This guide explains how to mine FXL using **WarpMiner**, covering both **Solo Mining** and **Pool Mining**.

---

# Prerequisites

## Wallet

To receive mining rewards, you'll need an FXL address.

FusionLayer is EVM-compatible, so you can use **MetaMask** or any other Ethereum-compatible wallet.

If you haven't added the FusionLayer network to your wallet yet, use the network configuration available at:

https://fusionlayer.org/metamask/

Once the network is added, create or import an account and use its address for mining rewards.

---

## FXL Node (Solo Mining Only)

Solo mining requires a running FusionLayer node.

Setup guide:

https://github.com/0xFusionLayer/docs/blob/main/run-a-node.md

---

## WarpMiner

Download the official GPU miner from:

https://github.com/0xFusionLayer/warpminer

You may either:

- Download the latest prebuilt binaries
- Clone the repository and build from source

Ensure the executable has permission to run.

---

# Solo Mining

Solo mining means your local FusionLayer node generates new blocks using your GPU miner.

## 1. Start Your FXL Node

Launch your node with WebSocket and mining enabled:

```bash
./fxl --ws --mine --miner.etherbase 0xYourWalletAddress
```

### Parameters

| Flag | Description |
|------|-------------|
| `--ws` | Enables the WebSocket server. |
| `--mine` | Starts mining on the node. |
| `--miner.etherbase` | Address that receives block rewards. |

### Optional

Specify a custom WebSocket port:

```bash
--ws.port 8546
```

Enable the required APIs:

```bash
--ws.api admin,personal,eth,net,web3,miner
```

---

## External Miner Connections

If your miner is running on another machine, allow remote WebSocket connections:

```bash
--ws.addr 0.0.0.0 --ws.origins "*"
```

These options make the node listen on all interfaces and accept external WebSocket connections.

---

## 2. Start WarpMiner

Connect WarpMiner to your node:

```bash
./warpminer -user=username -pass=password -pool=ws://localhost:8546
```

### Parameters

| Option | Description |
|--------|-------------|
| `-user` | Any username. |
| `-pass` | Any password. |
| `-pool` | WebSocket endpoint of your FusionLayer node. |

Example:

```text
ws://localhost:8546
```

or

```text
ws://192.168.1.50:8546
```

Mining rewards are sent to the address specified by:

```text
--miner.etherbase
```

---

# Pool Mining

Pool mining connects directly to a mining pool instead of your own node.

Example:

```bash
./warpminer -user=YOUR_WALLET -pass=x -pool=stratum://pool_address
```

Replace:

```text
pool_address
```

with the pool's actual Stratum endpoint.

Depending on the pool:

- `-user` is usually your wallet address.
- `-pass` is often ignored or set to `x`.

Refer to your chosen pool's documentation for the correct connection details.

---

# Troubleshooting

## Miner Cannot Connect

Verify that:

- Your FusionLayer node is running.
- WebSocket is enabled.
- The correct WebSocket port is being used.
- Required APIs are enabled.
- Firewall rules allow the connection.

For pool mining, verify:

- Pool address is correct.
- Username and password follow the pool's requirements.

---

## No Mining Rewards

For solo mining:

- Verify the `--miner.etherbase` address.
- Ensure your node is fully synchronized.
- Confirm WarpMiner is connected to your node.

For pool mining:

- Verify your wallet address.
- Check the pool dashboard for worker activity.

---

# Additional Resources

FXL Node

https://github.com/0xFusionLayer/fxl-node

WarpMiner

https://github.com/0xFusionLayer/warpminer

Website

https://fusionlayer.org

---

Happy Mining! ⛏️
