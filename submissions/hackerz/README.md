# Multi-Lend - Cross-Chain Lending Application


## 📋 Project Overview

**Project Name:** Multi-Lend 

**Tagline:** [Cross-Chain Lending Application developed on Stellar and Polkadot]

**Description:**
[Multi-Lend - Cross-Chain Lending Application developed on Stellar and Polkadot.
It allow users to lend Stellar XLM and borrow Polkadot DOT tokens.
It solves a real problem: "How do I use my cash (Fiat) to farm yields in Polkadot without using a centralized exchange (CEX)?"]

[It uses unique strengths:]

[Stellar: Cheap, fast, regulated coin.]

[Polkadot: Sophisticated, interoperable DeFi.]

## 👥 Team Information

**Team Name:** [ HackerZ ]

**Team Members:**
- [ Chaitanya Chawla ](https://github.com/chaitanya1-coder) - [Developer/Full-Stack]

## 🛠️ Technologies Used

- **Frontend:** [ Next.js ]
- **Backend:** [Node.js, Rust]
- **Blockchain:** [Stellar, Polkadot]
- **Smart Contracts:** [ Rust ]

## 🛠️ Links & Resources

- **Live Demo:** [Depolyed Link](https://multi-lend-sepia.vercel.app/)
- **Backend:** [Node.js, Rust]
- **Blockchain:** [Stellar, Polkadot]
- **Smart Contracts:** [ Rust ]

## About The Project
**Details:**
Mutli-Lend is a cross-chain lending protocol leveraging Stellar's low-cost fiat on-ramps as collateral for Polkadot's sophisticated DeFi ecosystem.

## 💡 The Problem
* **Polkadot users** have access to high-yield DeFi but struggle with difficult/expensive fiat on-ramps.
* **Stellar users** have excellent access to real-world assets (USDC, EURC) but lack complex lending environments.
* Moving capital between these two giants is currently fragmented and slow.

## 🚀 The Solution
This project implements a **Trustless Lock-and-Mint Bridge** connecting Soroban (Stellar's smart contract platform) with the Polkadot ecosystem.

Users can lock **Stellar Native Assets (XLM/USDC)** in a Soroban Vault and instantly receive **Wrapped Equivalents** on Polkadot to use as collateral in lending protocols (like Aave forks).

##Architecture

### 1. Stellar (Soroban Rust Contract)
* **Role:** Custodian of funds.
* **Tech:** Rust, Soroban SDK.
* **Function:** `deposit()` locks user funds and emits a standardized `CrossChainDeposit` event. It ensures funds are strictly controlled and verifiable on-chain.

### 2. The Bridge Relayer (Node.js)
* **Role:** The Observer & Messenger.
* **Tech:** TypeScript, `@stellar/stellar-sdk`.
* **Logic:** Listens for specific event topics from the Soroban contract. Upon validation, it triggers the minting signature for the destination chain.

### 3. Polkadot Side (Destination)
* **Role:** The DeFi Layer.
* **Tech:** Substrate / Ink! (Mocked for MVP).
* **Logic:** Mints 1:1 pegged tokens based on the proofs provided by the Relayer.

## 🛠 Tech Stack

| Component | Technology |
| :--- | :--- |
| **Smart Contracts** | Rust, Soroban SDK |
| **Frontend** | React, Vite, Freighter Wallet API |
| **Backend/Relayer** | Node.js, Stellar RPC |
| **Network** | Stellar Testnet (Soroban) |

## ⚡️ How to Run the Demo

### Prerequisites
* Node.js v18+
* Cargo & Rust (wasm32-unknown-unknown target)
* Freighter Wallet Extension (Set to Testnet)

### 1. Deploy the Contract (Stellar)
```bash
cd contracts
soroban contract deploy --wasm target/wasm32-unknown-unknown/release/collateral_vault.wasm --source S_SECRET_KEY...
```
### Start the Relayer
```bash
cd relayer
# Paste Contract ID into bridge_listener.js
node bridge_listener.js
```

### Launch Frontend

```bash
cd frontend
npm install
npm run dev
```
### Test Your Flow

Open ```bash localhost:5173```



### 🚧 Challenges & Solutions
* Challenge: Event Decoding. Decoding XDR (External Data Representation) from the Stellar ledger in Node.js was complex.

* Solution: We utilized the xdr.ScVal.fromXDR method from the @stellar/stellar-sdk to properly parse the binary event data into readable JSON.

* Challenge: Decimals Mismatch. Stellar uses 7 decimal places while Polkadot often uses 10 or 12.

* Solution: We implemented a normalization logic in the smart contract to ensure 1:1 value parity when bridging.

### 🔮 Future Improvements
* If we had more time, we would implement:

* [ ] Decentralized Relayer Network: Replace the single Node.js script with a set of decentralized verifiers (e.g., using Axelar or Hyperlane).

* [ ] Reverse Bridge (Withdraw): Implement the "Burn-and-Unlock" logic to allow users to move funds back to Stellar.

* [ ] Oracle Integration: Add a price feed to the Vault to ensure the collateral value doesn't drop below the liquidation threshold.

### 📄 License
* Distributed under the MIT License. See LICENSE for more information.

### 🙏 Acknowledgments
* Stellar Developer Docs: For the comprehensive Soroban tutorials.

* Polkadot Wiki: For the XCM documentation.

* Pendulum Chain: For the inspiration on Spacewalk bridges.

**Built for Stellar x Polkadot Hackerhouse BLR** 🎉