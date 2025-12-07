# 🌍 CrossBorderX – Instant Global FX Transfers Using Crypto Rails (Walletless)

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
✅ **Low Fees** – Avoid intermediary bank and forex conversion fees - ~0.1%–0.3% backend fees (liquidity, gas, swap). 
✅ **Walletless UX** - user doesn’t hold crypto, no MetaMask, no private keys  
✅ **Transparent & Auditable** – Every transaction is visible on the blockchain.  
✅ **Compliance-Ready** – Includes a KYC placeholder for future AML/KYC integration, fiat on/off-ramp checks.  
✅ **Built for FinTech Innovation** – A proof-of-concept for next-generation remittance startups.

---

## 🏗️ Architecture

# CrossBorderX Architecture

## System Overview

CrossBorderX is a blockchain-based cross-border remittance platform enabling seamless INR to GBP transfers using cryptocurrency as a settlement layer.

---

## Architecture Diagram

```
┌──────────────────────────────────────────┐
│               User (INR)                 │
└───────────────────┬──────────────────────┘
                    ▼
┌──────────────────────────────────────────┐
│        Payment Gateway (INR Pay-In)      │
│     Razorpay • PayU • Stripe             │
└───────────────────┬──────────────────────┘
                    ▼
┌──────────────────────────────────────────┐
│            CrossBorderX Backend          │
├──────────────────────────────────────────┤
│ • FX Engine (INR → USDT)                 │
│ • Smart Contracts (Swap, Transfer)       │
│ • Liquidity Pool Manager (USDT ↔ GBP)    │
│ • Compliance Engine (KYC / AML)          │
│ • Swap Router (USDT → GBP)               │
└───────────────────┬──────────────────────┘
                    ▼
┌──────────────────────────────────────────┐
│      Blockchain Network (Settlement)     │
│        Polygon • Solana                  │
│   (USDT Transfer & Swap Execution)       │
└───────────────────┬──────────────────────┘
                    ▼
┌──────────────────────────────────────────┐
│           GBP Liquidity Partner          │
├──────────────────────────────────────────┤
│ • DEX: Uniswap • Orca                    │
│ • CEX: Kraken • Coinbase • Binance UK    │
└───────────────────┬──────────────────────┘
                    ▼
┌──────────────────────────────────────────┐
│      UK Banking Partner (FPS Off-Ramp)   │
│      ClearBank • Modulr • Paynetics      │
└───────────────────┬──────────────────────┘
                    ▼
┌──────────────────────────────────────────┐
│       Receiver’s UK Bank Account (GBP)   │
└──────────────────────────────────────────┘

```

---

## ⚙️ Tech Stack

| **Layer**                           | **Tools / Services**                                                                                     |
| ----------------------------------- | -------------------------------------------------------------------------------------------------------- |
| **Frontend**                        | React.js • Next.js • TypeScript • TailwindCSS                                                            |
| **Backend (API)**                   | Node.js • Express.js / NestJS • WebSockets • REST / gRPC                                                 |
| **Blockchain Interaction**          | Ethers.js • Web3.js • Viem                                                                               |
| **Smart Contracts**                 | Solidity • Hardhat • OpenZeppelin • Foundry (optional)                                                   |
| **Blockchain Network**              | Polygon PoS / zkEVM                                                                                      |
| **Stablecoins**                     | USDT • USDC                                                                                              |
| **Liquidity Layer**                 | Uniswap V3 • Custom liquidity pool contracts • 1inch Routing (optional)                                  |
| **Oracle / FX Rates**               | Chainlink Price Feeds • Custom FX API                                                                    |
| **Custody / Wallet Infrastructure** | Fireblocks • Circle APIs • Self-custodial hot wallet service (backend-managed keys)                      |
| **Fiat On/Off-Ramp**                | On/Off-Ramp Partner (Transak / Onmeta / Circle) • UK FPS payout partner (ClearBank / Modulr / Paynetics) |
| **KYC/AML**                         | Sumsub • Chainalysis KYT (transaction monitoring)                                                        |
| **Database**                        | PostgreSQL • Redis (caching/queues)                                                                      |
| **Infrastructure**                  | Docker • Kubernetes • Load Balancer • NGINX • Cloudflare                                                 |
| **Cloud Provider**                  | AWS / GCP / Azure (EC2, Lambda, S3, RDS)                                                                 |
| **Monitoring & Logging**            | Prometheus • Grafana • ELK Stack • Sentry                                                                |
| **CI/CD**                           | GitHub Actions • Docker Hub • Terraform                                                                  |


---
## 🔄 How the Transfer Works (Walletless Flow)

1️⃣ **User Initiates Transfer** - User enters INR → GBP and pays via UPI/Bank Transfer.
2️⃣ **Backend Custody (No Wallet for User)** - Backend stores INR in a custodial balance under their verified profile.
3️⃣ **Convert INR → USDT (Backend Only)** - Backend mints/purchases USDT via exchange or OTC partner.
4️⃣ **Blockchain Settlement** - USDT sent instantly on a high-speed chain (Polygon/Base/Solana).
5️⃣ **Liquidity Pool Swap** - USDT → GBP-stablecoin using low-slippage LP.
6️⃣ **Off-Ramp to UK Bank** - GBP → UK bank via Faster Payments System (FPS). (USER CHOICE) - ⏱️ Usually minutes depending on bank.
7️⃣ **Receiver gets GBP in Bank** - Receiver never interacts with crypto.

---

## 💸 Cost Breakdown

| Component               | Cost (Approx)     |
| ----------------------- | ----------------- |
| Blockchain gas fees     | $0.01 – $0.05     |
| DEX swap fee            | 0.05% – 0.30%     |
| Off-ramp withdrawal fee | ~£1 – £2          |
| Compliance/KYC cost     | negligible per tx |

### ⭐ Total Backend Cost: 0.1% – 0.3% 
This is much lower than traditional payment rails.

## 💡 Smart Contract Overview

**Contract Name:** `CrossBorderRemittance.sol`

### Functions
| **Function**                                                        | **Description**                                                   |
| ------------------------------------------------------------------- | ----------------------------------------------------------------- |
| `sendRemittance(address recipient, uint256 amount)`                 | Transfers USDT/USDC from CrossBorderX to backend/receiver wallet. |
| `swapStablecoin(address tokenIn, address tokenOut, uint256 amount)` | Routes swap between stablecoins using DEX liquidity pool.         |
| `getLiquidity(address token)`                                       | Returns current liquidity available for swaps.                    |
| `addLiquidity(address token, uint256 amount)`                       | Adds tokens to internal liquidity pool.                           |
| `withdrawLiquidity(address token, uint256 amount)`                  | Admin function to manage operational liquidity.                   |
| `getExchangeRate(address tokenIn, address tokenOut)`                | Gets on-chain oracle FX rate (Chainlink).                         |
| `estimateFees(uint256 amount)`                                      | Returns estimated gas + liquidity fees for the user.              |
| `pause()`                                                           | Emergency pause for contract security.                            |
| `unpause()`                                                         | Unpauses contract.                                                |
| `setAdmin(address newAdmin)`                                        | Updates admin for contract operations.                            |


---

## 🧠 This is a conceptual flow and will evolve significantly as the project progresses.

