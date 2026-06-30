# HiveOS Setup Guide

This guide will help you set up WarpMiner on HiveOS to mine FusionLayer (FXL).

> ⚠️ **BETA Testing:** WarpMiner HiveOS integration is currently in testing. Please be aware that:
>
> - Some issues may occur.
> - Your feedback is valuable and helps us improve the integration.

---

## Add FXL Wallet in HiveOS

1. Go to **Wallets**.
2. Click **Add Wallet**.
3. Fill in the following:
   - **Coin:** Enter `FXL` and click **Create "FXL"**
   - **Address:** Your FXL wallet address.
   - **Name:** Choose any name for your wallet (e.g. `wallet-1`).

---

## Create a Flight Sheet

1. Go to **Flight Sheets**.
2. Configure the following:
   - **Coin:** `FXL`
   - **Wallet:** Select your FXL wallet (e.g. `wallet-1`)
   - **Pool:** `Configure in miner`
   - **Miner:** `Custom`

---

### Custom Miner Configuration

Fill in the following fields:

- **Miner name:**
  ```
  WarpMiner
  ```

- **Installation URL:**
  ```
  https://github.com/0xFusionLayer/WarpMiner-HiveOS/releases/download/v2.0.0/warpminer.tar.gz
  ```

- **Hash algorithm:**
  ```
  FusionHash
  ```

- **Wallet and worker template:**
  ```
  %WAL%.%WORKER_NAME%
  ```

- **Pool URL:**
  ```
  stratum+tcp://<POOL_HOST>:<PORT>
  ```

---

## Apply the Flight Sheet

1. Save the Flight Sheet.
2. Assign it to your worker.
3. Start mining.

If everything is configured correctly, WarpMiner will connect to the selected pool and begin mining FXL.

---

## Support

If you encounter any issues or need assistance, please open an issue on GitHub or ask in the FusionLayer community channels.
