# 🏛️ ArdhiChain — Blockchain Land Registry System

> A decentralized, tamper-proof land ownership and dispute resolution platform built for Kenya and emerging markets.

[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Solidity](https://img.shields.io/badge/Solidity-0.8.x-blue)](https://soliditylang.org/)
[![Node.js](https://img.shields.io/badge/Node.js-18+-brightgreen)](https://nodejs.org/)
[![React](https://img.shields.io/badge/React-18-blue)](https://reactjs.org/)
[![Status](https://img.shields.io/badge/Status-In%20Development-yellow)]()

---

## 📌 Problem Statement

Land disputes are one of the most significant legal and economic challenges in Kenya and much of Sub-Saharan Africa. Traditional land registries suffer from:

- 📂 Lost, defaced, or duplicate physical records
- 🔄 Double allocation of the same plot to multiple owners
- 💰 Rampant fraud by cartels and corrupt officials
- ⏳ Slow, paper-heavy transfer processes taking weeks or months
- 🔍 Zero public transparency — ownership cannot be independently verified

> Research by Otieno et al. (2023) reveals that **nearly 60% of landowners in Kenya have experienced property disputes**, underlining the urgent need for reform.

---

## 💡 What is ArdhiChain?

**ArdhiChain** is a blockchain-powered land registry platform that creates a **permanent, transparent, and tamper-proof** record of land ownership. No single authority can secretly alter a record. Ownership is verifiable in seconds. Property transfers are enforced automatically through smart contracts.

**Key capabilities:**
- 🔗 Immutable on-chain title deed storage
- 🤝 Smart contract-driven ownership transfers
- ⚖️ Built-in dispute filing and resolution workflow
- 🗺️ GIS/parcel map integration
- 🪪 Digital identity verification for landowners
- 📜 Full transaction and ownership history (audit trail)
- 🏛️ Government authority approval layer

---

## 🏗️ System Architecture

```
┌─────────────────────────────────────────────────────────────────┐
│                        FRONTEND (React / Next.js)               │
│   Citizen Portal │ Government Dashboard │ Dispute Portal        │
└────────────────────────────┬────────────────────────────────────┘
                             │ REST / GraphQL API
┌────────────────────────────▼────────────────────────────────────┐
│                       BACKEND (Node.js / Express)               │
│   Auth Service │ Land Service │ Dispute Service │ IPFS Service  │
└──────┬─────────────────────┬──────────────────────┬────────────┘
       │ Web3.js / Ethers.js │                      │
┌──────▼──────────────┐  ┌───▼──────────────┐  ┌───▼──────────┐
│  Ethereum Blockchain │  │   IPFS / Filecoin │  │  PostgreSQL  │
│  (Smart Contracts)   │  │  (Document Store) │  │  (Off-chain) │
└─────────────────────┘  └──────────────────┘  └──────────────┘
```

---

## 🛠️ Tech Stack

| Layer | Technology |
|-------|-----------|
| Smart Contracts | Solidity 0.8.x, Hardhat |
| Blockchain Network | Ethereum (Sepolia Testnet → Mainnet / Polygon) |
| Backend | Node.js, Express.js |
| Frontend | React.js, Next.js, TailwindCSS |
| Document Storage | IPFS via Pinata / web3.storage |
| Database (off-chain index) | PostgreSQL |
| Auth / Identity | JWT + Metamask / WalletConnect |
| Maps | Leaflet.js + OpenStreetMap |
| Testing | Hardhat, Mocha, Chai |
| DevOps | Docker, GitHub Actions |

---

## 📁 Repository Structure

```
ardhichain/
├── contracts/                  # Solidity smart contracts
│   ├── LandRegistry.sol        # Core land record contract
│   ├── OwnershipTransfer.sol   # Transfer & escrow logic
│   ├── DisputeResolution.sol   # Dispute filing & arbitration
│   └── interfaces/
├── backend/                    # Node.js API server
│   ├── routes/
│   ├── services/
│   ├── middleware/
│   └── utils/
├── frontend/                   # React / Next.js web app
│   ├── pages/
│   ├── components/
│   └── hooks/
├── scripts/                    # Deployment & migration scripts
├── test/                       # Smart contract & API tests
├── docs/                       # Extended documentation
│   ├── SYSTEM_DESIGN.md
│   ├── SMART_CONTRACT_SPEC.md
│   ├── API_REFERENCE.md
│   └── ARCHITECTURE_DIAGRAMS/
├── .github/
│   ├── workflows/              # CI/CD pipelines
│   └── ISSUE_TEMPLATE/
├── hardhat.config.js
├── .env.example
├── docker-compose.yml
└── README.md
```

---

## 👥 Team Roles & Responsibilities

> **Team Size: 8 members** — assign yourself to one of the areas below by editing this section and opening a PR.

| # | Role | Responsibilities | Assigned To |
|---|------|-----------------|-------------|
| 1 | **Blockchain Lead** | Smart contract architecture, Solidity coding, audits | `@username` |
| 2 | **Smart Contract Dev** | Contract testing, Hardhat scripts, deployment | `@username` |
| 3 | **Backend Lead** | API architecture, Node.js services, database design | `@username` |
| 4 | **Backend Dev** | Route development, IPFS integration, auth service | `@username` |
| 5 | **Frontend Lead** | UI/UX design, React component library, wallet integration | `@username` |
| 6 | **Frontend Dev** | Pages, maps (Leaflet.js), dispute portal UI | `@username` |
| 7 | **DevOps / Infra** | Docker, CI/CD pipelines, testnet deployment, monitoring | `@username` |
| 8 | **QA / Documentation** | Testing strategy, test writing, technical docs, API docs | `@username` |

---

## 🚀 Getting Started

### Prerequisites

- Node.js v18+
- npm or yarn
- MetaMask browser extension
- Docker & Docker Compose
- Git

### 1. Clone the Repository

```bash
git clone https://github.com/YOUR_ORG/ardhichain.git
cd ardhichain
```

### 2. Install Dependencies

```bash
# Root (Hardhat / contracts)
npm install

# Backend
cd backend && npm install

# Frontend
cd ../frontend && npm install
```

### 3. Configure Environment

```bash
cp .env.example .env
# Fill in your values:
# - PRIVATE_KEY (deployer wallet private key)
# - ALCHEMY_API_URL or INFURA_URL
# - PINATA_API_KEY (IPFS)
# - DATABASE_URL (PostgreSQL)
# - JWT_SECRET
```

### 4. Compile & Deploy Contracts (Local)

```bash
# Start local blockchain
npx hardhat node

# In a new terminal — compile & deploy
npx hardhat compile
npx hardhat run scripts/deploy.js --network localhost
```

### 5. Run the Backend

```bash
cd backend
npm run dev
```

### 6. Run the Frontend

```bash
cd frontend
npm run dev
# Open http://localhost:3000
```

### 7. Run All with Docker

```bash
docker-compose up --build
```

---

## 🧪 Running Tests

```bash
# Smart contract tests
npx hardhat test

# Backend API tests
cd backend && npm test

# Coverage report
npx hardhat coverage
```

---

## 📋 Core Smart Contract: `LandRegistry.sol`

```solidity
// Simplified interface — see contracts/LandRegistry.sol for full implementation
contract LandRegistry {
    struct LandParcel {
        uint256 parcelId;
        string titleDeedHash;   // IPFS hash of scanned deed
        address owner;
        string gpsCoordinates;
        uint256 areaInSqMeters;
        bool isDisputed;
        uint256 registeredAt;
    }

    function registerLand(string memory _titleDeedHash, string memory _gps, uint256 _area) external;
    function transferOwnership(uint256 _parcelId, address _newOwner) external;
    function fileDispute(uint256 _parcelId, string memory _reason) external;
    function getParcel(uint256 _parcelId) external view returns (LandParcel memory);
    function getOwnershipHistory(uint256 _parcelId) external view returns (address[] memory);
}
```

---

## 🔑 Key Features

### 1. Land Registration
Register a new parcel on-chain with a title deed document hash (stored on IPFS), GPS coordinates, and owner wallet address. Government authority must approve before finalization.

### 2. Ownership Transfer
Smart contract-enforced transfer: both parties sign, government approves, transfer executes automatically. No middlemen. Full history preserved on-chain.

### 3. Dispute Resolution
Any party can file a dispute against a parcel. The parcel is flagged `isDisputed = true`, blocking further transfers until resolution by an appointed arbitration panel.

### 4. Title Deed Verification
Any citizen can enter a parcel ID or GPS coordinates to verify current ownership, view the full transfer history, and download the IPFS-stored title deed — all publicly, without needing an account.

### 5. Government Dashboard
A role-gated portal for Ministry of Lands officials to approve registrations, review disputes, and revoke fraudulent records with a full on-chain audit trail.

---

## 🛡️ Security Considerations

- Role-based access control (RBAC) on all critical contract functions
- Multi-sig requirement for government approval actions
- Re-entrancy guard on all transfer functions
- IPFS content addressing (hash-verified document storage)
- Rate limiting and input validation on all API endpoints
- Smart contract audit planned before mainnet deployment

---

## 🗺️ Roadmap

| Phase | Description | Status |
|-------|-------------|--------|
| **Phase 1** | Smart contract development & local testing | 🔄 In Progress |
| **Phase 2** | Backend API & IPFS integration | 📅 Planned |
| **Phase 3** | Frontend portal (citizen + government) | 📅 Planned |
| **Phase 4** | Testnet deployment (Sepolia / Mumbai) | 📅 Planned |
| **Phase 5** | Security audit & penetration testing | 📅 Planned |
| **Phase 6** | Pilot with county land office (Kiambu) | 📅 Planned |
| **Phase 7** | Mainnet deployment | 📅 Planned |

---

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/your-feature-name`
3. Commit your changes: `git commit -m "feat: add your feature"`
4. Push to your branch: `git push origin feature/your-feature-name`
5. Open a Pull Request — all PRs require at least **1 review** before merging

Please read [CONTRIBUTING.md](docs/CONTRIBUTING.md) for our code standards and commit message conventions.

---

## 📄 License

This project is licensed under the **MIT License** — see [LICENSE](LICENSE) for details.

---

## 📬 Contact & Links

- **Project Lead:** Emmanuel Bett — `your.email@zetech.ac.ke`
- **Docs:** [/docs](./docs/)
- **Issues:** [GitHub Issues](https://github.com/YOUR_ORG/ardhichain/issues)

> *"Land is the basis of all independence. Land is the basis of freedom, justice and equality."* — Malcolm X
*
