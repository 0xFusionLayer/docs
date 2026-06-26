# Running a FusionLayer Node

This guide explains how to download, install, and run an official FusionLayer (`fxl`) node.

---

## Download

Download the latest prebuilt binaries from the official releases page:

https://github.com/0xFusionLayer/fxl-node/releases

Alternatively, you may build the node from source if you prefer.

---

## Start the Node

Run the executable:

```bash
./fxl
```

The node will automatically begin connecting to peers and syncing the FusionLayer blockchain.

---

## Troubleshooting

### Permission Denied

If you receive:

```text
Permission denied
```

Make the binary executable:

```bash
chmod +x fxl
```

Then run it again:

```bash
./fxl
```

---

# Hardware Requirements

## Minimum

- 4+ CPU Cores
- 8 GB RAM
- 1 TB Free Storage (Mainnet Sync)
- 8 Mbit/sec Internet Connection

> **Note**
>
> FusionLayer is designed for modern 64-bit processors. Older CPU architectures may fail to start the node or experience unexpected crashes.

---

# Network Ports

The node uses three primary ports.

All ports are configurable.

| Flag | Default | Purpose |
|------|---------|---------|
| `--port` | `30303` | Peer-to-peer networking |
| `--http.port` | `8545` | JSON-RPC HTTP API |
| `--ws.port` | `8546` | WebSocket API |

Example:

```bash
./fxl --port 30303 --http --http.port 8545 --ws --ws.port 8546
```

You may replace these values with any available ports.

---

# Port Descriptions

## P2P Port (`--port`)

Used for peer-to-peer communication with other FusionLayer nodes.

Default:

```text
30303
```

This port should be accessible through your firewall if you want your node to accept incoming peer connections.

---

## HTTP RPC (`--http.port`)

Used for JSON-RPC over HTTP.

Default:

```text
8545
```

Enable HTTP with:

```bash
--http
```

---

## WebSocket RPC (`--ws.port`)

Used for WebSocket connections.

Default:

```text
8546
```

Enable WebSocket support with:

```bash
--ws
```

---

# Security

When exposing RPC interfaces on a public network:

- Only enable the APIs you actually need.
- Configure your firewall appropriately.
- Avoid exposing administrative APIs to the public Internet.
- Restrict HTTP/WebSocket access whenever possible.

---

# Helpful Flags

Display all available options:

```bash
./fxl --help
```

Check the client version:

```bash
./fxl version
```

---

# Additional Resources

Website

https://fusionlayer.org

Explorer

https://fusionscan.net

GitHub

https://github.com/0xFusionLayer

Releases

https://github.com/0xFusionLayer/fxl-node/releases
