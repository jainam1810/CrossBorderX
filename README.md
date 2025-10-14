# 🌍 CrossBorderX – Crypto-Powered Global Money Transfer

> **Transfer any currency across borders within seconds using stablecoins and blockchain liquidity pools.**

## 🚀 Overview

**CrossBorderX** is a prototype for instant, low-cost, cross-border money transfers built on blockchain.  
Instead of relying on traditional SWIFT banking rails, this project uses **stablecoins (e.g., USDT/USDC)** and **decentralized liquidity pools** to move value globally in seconds.

Example flow:
> A user in Mumbai sends ₹10,000 INR to a friend in London → the amount is converted into USDT → transferred via blockchain → swapped into GBP using a liquidity pool → instantly available in the receiver’s wallet.

This project demonstrates how **crypto rails can replace outdated banking networks** to achieve instant remittance with minimal fees.

---

## 🧩 Features

✅ **Instant Transfers** – Send any amount across borders using stablecoins within seconds.  
✅ **Low Fees** – Avoid intermediary bank and forex conversion fees.  
✅ **Liquidity Pool Swaps** – Automatic conversion between currencies via Uniswap-style pools.  
✅ **Transparent & Auditable** – Every transaction is visible on the blockchain.  
✅ **Compliance-Ready** – Includes a KYC placeholder for future AML/KYC integration.  
✅ **Built for FinTech Innovation** – A proof-of-concept for next-generation remittance startups.

---

## 🏗️ Architecture

USER (Metamask or any other wallet)
│
▼
Frontend (React + Ethers.js)
│
▼
Smart Contracts (Solidity + Hardhat)
│
▼
Polygon Mumbai Testnet / Uniswap Pool

---

## ⚙️ Tech Stack

| Layer | Tools |
|-------|-------|
| **Frontend** | React.js, Ethers.js |
| **Smart Contracts** | Solidity, Hardhat |
| **Blockchain** | Polygon Mumbai Testnet |
| **Wallet** | MetaMask |
| **Node Provider** | Alchemy / Infura |
| **DEX / Liquidity** | Uniswap (Testnet Integration) |

---

## 🪙 Example Transaction Flow

1️⃣ **User Inputs** – Sender enters amount and target currency (e.g., INR → GBP).  
2️⃣ **Stablecoin Conversion** – INR is converted into USDT (simulation).  
3️⃣ **Blockchain Transfer** – USDT sent via Polygon network to receiver’s wallet.  
4️⃣ **Liquidity Pool Swap** – USDT swapped into GBP-equivalent token (simulated).  
5️⃣ **Instant Receipt** – Receiver gets funds in GBP wallet.

---

## 💡 Smart Contract Overview

**Contract Name:** `CrossBorderRemittance.sol`

### Functions
| Function | Description |
|-----------|-------------|
| `sendRemittance(address recipient, uint amount)` | Transfers stablecoins to recipient |
| `swapStablecoin(address tokenA, address tokenB, uint amount)` | Swaps between tokens using liquidity pool |
| `getExchangeRate(address tokenA, address tokenB)` | Fetches simulated FX rate |
| `addLiquidity(address token, uint amount)` | Adds tokens to the liquidity pool |

---

## 🧠 Conceptual Flow

