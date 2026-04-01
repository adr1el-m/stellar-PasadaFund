<div align="center">
  <img src="frontend/public/readme/jeepney.png" alt="PasadaFund Banner" width="100%">
  
  # 🚛 PasadaFund
  
  **Stellar Route Resilience Protocol**
  
  [![Soroban](https://img.shields.io/badge/Soroban-v22.0.0-df4b37?style=for-the-badge&logo=rust&logoColor=white)](https://soroban.stellar.org/)
  [![React](https://img.shields.io/badge/React-v18.3.1-61dafb?style=for-the-badge&logo=react&logoColor=black)](https://react.dev/)
  [![Stellar](https://img.shields.io/badge/Stellar-Testnet-black?style=for-the-badge&logo=stellar&logoColor=white)](https://stellar.org/)
  [![License: MIT](https://img.shields.io/badge/License-MIT-green.svg?style=for-the-badge)](https://opensource.org/licenses/MIT)

  ---
  
  *PasadaFund is a decentralized mission-governed protocol designed to protect the route continuity of Jeepney and Tricycle transport groups in the Philippines against fuel price shocks through transparent, community-governed reserve management.*
  
  [**Explore the dApp**](https://stellar-pasada-fund.vercel.app/) • [**View Contract**](https://stellar.expert/explorer/testnet/contract/CCLVGF3AR5WGDZF4RWMLVXTIBH3YBXOV3CLAWXNB73NSKXJDHE62WMAJ) • [**Report a Bug**](https://github.com/adr1el-m/stellar-PasadaFund/issues)

</div>

## 📖 Overview

In the Philippines, the transport sector is highly vulnerable to global fuel volatility. **PasadaFund** transforms this vulnerability into resilience by leveraging **Soroban Smart Contracts** to manage a community-funded XLM reserve pool. 

Through on-chain governance, transport cooperatives and contributors can propose and vote on support requests (fuel subsidies, maintenance relief, etc.), ensuring every Peso—or Stroop—is accounted for and disbursed to verified beneficiaries.

### 🌟 Key Vision
- **Transparency**: Every contribution and disbursement is permanently etched on the Stellar ledger.
- **Democratic Governance**: Members who contribute to the reserve gain the right to vote on community support requests.
- **Stroop-Safe Precision**: Financial operations utilize high-precision arithmetic to ensure stability across the protocol.

## 🚀 Deployment Status (Testnet)

![Contract ID](frontend/public/readme/contractId.png)

| Component | Value |
| :--- | :--- |
| **Contract ID** | `CCLVGF3AR5WGDZF4RWMLVXTIBH3YBXOV3CLAWXNB73NSKXJDHE62WMAJ` |
| **Admin Wallet** | `GCOLFCAVXCQ6PEVYVFI64WKVDBELGPDROK76L5QQCA3AWHTNPRDSKEWB` |
| **Native XLM SAC** | `CDLZFC3SYJYDZT7K67VZ75HPJVIEUVNIXF47ZG2FB2RMQQVU2HHGCYSC` |
| **Network** | Stellar Testnet |

## 🎥 Proof of Operation

[![Demo Video](https://img.shields.io/badge/Demo%20Video-Watch%20Now-black?style=for-the-badge&logo=youtube&logoColor=ff0000)](frontend/public/readme/Demo.mp4)

### Platform Snapshots

| Landing Page | Dashboard Overview |
| :---: | :---: |
| ![Landing](frontend/public/readme/LandingPage.png) | ![Dashboard](frontend/public/readme/1.png) |
| **Proposal Governance** | **Transaction History** |
| ![Proposals](frontend/public/readme/2.png) | ![Activity](frontend/public/readme/3.png) |

### Complete User Flow

| Initiate Contribution | Enter Amount & Confirm |
| :---: | :---: |
| ![Wallet Connection](frontend/public/readme/connectingFreighterWallet.png) | ![Reserve Deposit](frontend/public/readme/ContributingToPool.png) |
| **Transaction Confirmation** | **Contribution Reflected in Stellar Expert** |
| ![Confirm Txn](frontend/public/readme/Successful\ transaction\(pool\ contribution\).png) | ![Explorer Confirmation](frontend/public/readme/theContibutionreflected.png) |

## 🛠️ Core Features

- **XLM Reserve Pool**: A real-time, on-chain treasury audited via `soroban_sdk::token::Client`.
- **Contribution-Activated Governance**: Contribution to the pool triggers automatic protocol membership.
- **Decentralized Support Requests**: Proposers can submit support tickets with custom titles, amounts, and recipient addresses.
- **Member-Weighted Threshold**: Requires a minimum of **2 member votes** for proposal approval, preventing single-actor dominance.
- **Fail-Safe RPC & UX**: 
  - Dual RPC fallback for maximum dashboard uptime.
  - Glassmorphic UI with skeleton loading states and success confetti.
  - Unified activity feed merging on-chain events with local transaction logs.

## 🏗️ Technical Architecture

### Tech Stack
- **Smart Contracts**: `Rust`, `Soroban SDK` (no-std environment)
- **Frontend**: `React 18`, `TypeScript`, `Vite`
- **Styling**: `Vanilla CSS` (Modern Glassmorphism Design System)
- **Stellar Integration**: `@stellar/freighter-api`, `@stellar/stellar-sdk`
- **Deployment**: `Vercel` (Frontend), `Stellar CLI` (Contracts)

### Project Structure
```text
.
├── contracts/pasadafund/   # Soroban Rust Source
├── frontend/src/           # React TypeScript UI
│   ├── lib/stellar.ts      # Core Soroban Client Logic
│   └── App.tsx             # Main Dashboard & Governance UI
└── vercel.json             # Root-level Vercel Deployment Config
```

## ✅ Contract Test Verification

![All Tests Passing](frontend/public/readme/contractTest.png)

All core business logic is verified through comprehensive unit and integration tests:
- ✓ Contribution mechanism with treasury updates
- ✓ Multi-member proposal voting with threshold enforcement
- ✓ Secure fund transfers to verified recipients

## 💻 Local Development

### 1. Requirements
- [Rust & Cargo](https://rustup.rs/)
- [Stellar CLI](https://developers.stellar.org/docs/build/smart-contracts/getting-started/setup#install-the-stellar-cli)
- Node.js (v18+)

### 2. Smart Contract Setup
```bash
cd contracts/pasadafund
cargo test          # Run the comprehensive test suite
stellar contract build
```

### 3. Frontend Setup
```bash
cd frontend
cp .env.example .env # Configure your Contract IDs
npm install
npm run dev
```

## ⚖️ Governance Model

1. **Contribute**: Users deposit XLM to become protocol members.
2. **Propose**: Any member can submit a Support Request for a specific bounty/subsidy.
3. **Vote**: Members vote on active proposals. A threshold of 2 votes is required.
4. **Execute**: Once approved, the admin or members can trigger the disbursement, transferring XLM from the contract directly to the recipient's wallet.

## 🤝 Maintainer

<div align="center">
  <img src="frontend/public/readme/adriel.jpg" alt="Adriel Magalona" style="border-radius: 50%; border: 4px solid #df4b37; width: 140px; height: 140px; object-fit: cover;">
  <br>
  <h3>Adriel Magalona</h3>
  <p>Full-Stack Developer & Blockchain Enthusiast</p>
  
  <a href="https://www.linkedin.com/in/adr1el/">
    <img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn">
  </a>
  <a href="https://github.com/adr1el-m">
    <img src="https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white" alt="GitHub">
  </a>
</div>

---

<div align="center">
  Built with ❤️ during the 2026 Build on Stellar Bootcamp
</div>
