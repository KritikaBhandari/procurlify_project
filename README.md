# 🏛 Procurlify

> *Blockchain-powered platform revolutionizing government tender management with transparency, security, and fairness.*

A comprehensive solution connecting central and state departments on a unified multi-chain registry, ensuring corruption-free tendering processes through immutable blockchain technology.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![React](https://img.shields.io/badge/React-18.x-blue.svg)](https://reactjs.org/)
[![Ethereum](https://img.shields.io/badge/Ethereum-Solidity-purple.svg)](https://ethereum.org/)
[![Aptos](https://img.shields.io/badge/Aptos-Move-green.svg)](https://aptoslabs.com/)

---

## 📋 Table of Contents

- [Features](#-features)
- [Tech Stack](#-tech-stack)
- [Architecture](#-architecture)
- [Getting Started](#-getting-started)
- [Project Structure](#-project-structure)
- [Smart Contracts](#-smart-contracts)
- [Payment System](#-payment-system)
- [API Documentation](#-api-documentation)
- [Contributing](#-contributing)
- [License](#-license)

---

## ✨ Features

### 🔐 *Immutable & Transparent Bidding*
- All tenders, bids, and contracts stored immutably on blockchain
- Full auditability and corruption elimination
- Real-time verification of all transactions

### 🌐 *Unified Multi-Chain Registry*
- Integrates central and state departments
- Leverages Ethereum for tender management
- Aptos blockchain for secure payments
- Hyperledger for private consortium data
- Chainlink oracles for off-chain data proofs

### 📊 *Real-Time Audit Trail*
- Every action logged and publicly verifiable
- From bid submission to final contract execution
- Complete transparency for maximum trust

### 💰 *Blockchain Payment System*
- Direct APT payments to contractors via Aptos
- Petra wallet integration
- Automated payment tracking
- Secure cryptocurrency transactions

### 🤖 *Automated Tender Management*
- Auto-close tenders at deadline
- Automatic winner selection (lowest bid)
- Smart contract-based award system
- Progress tracking timeline

### 👥 *Multi-Role Dashboard*
- *Admin/Government:* Create tenders, review bids, award contracts, make payments
- *Contractor:* Browse tenders, submit bids, track awards, receive payments
- *Public:* View tenders, monitor transparency

---

## 🛠 Tech Stack

### *Frontend*
- *React 18.x* - Modern UI framework
- *React Router* - Client-side routing
- *TailwindCSS* - Utility-first CSS framework
- *GSAP* - Animation library
- *Vite* - Fast build tool

### *Backend*
- *Supabase* - Backend as a Service
- *PostgreSQL* - Relational database
- *Node.js* - Server runtime

### *Blockchain*
- *Ethereum* - Tender & bid management
- *Solidity* - Smart contract language
- *Hardhat* - Ethereum development environment
- *ethers.js* - Ethereum library

### *Aptos Blockchain*
- *Move* - Smart contract language
- *Petra Wallet* - Aptos wallet integration
- *Aptos SDK* - Blockchain interaction

### *Oracles & Integration*
- *Chainlink* - Decentralized oracle network
- *IPFS* - Decentralized file storage

---

## 🏗 Architecture


┌─────────────────────────────────────────────────────────────┐
│                         Frontend (React)                     │
│  ┌──────────┐  ┌──────────┐  ┌──────────┐  ┌──────────┐   │
│  │  Admin   │  │Contractor│  │  Public  │  │ Payment  │   │
│  │Dashboard │  │Dashboard │  │Dashboard │  │  Pages   │   │
│  └──────────┘  └──────────┘  └──────────┘  └──────────┘   │
└─────────────────────────────────────────────────────────────┘
                            ↕
┌─────────────────────────────────────────────────────────────┐
│                    Supabase (Backend)                        │
│  ┌──────────┐  ┌──────────┐  ┌──────────┐  ┌──────────┐   │
│  │PostgreSQL│  │   Auth   │  │ Storage  │  │Real-time │   │
│  │ Database │  │  System  │  │  (Docs)  │  │  Updates │   │
│  └──────────┘  └──────────┘  └──────────┘  └──────────┘   │
└─────────────────────────────────────────────────────────────┘
                            ↕
┌─────────────────────────────────────────────────────────────┐
│                   Blockchain Layer                           │
│  ┌──────────────────────┐  ┌──────────────────────┐        │
│  │   Ethereum (ETH)     │  │    Aptos (APT)       │        │
│  │ ┌──────────────────┐ │  │ ┌──────────────────┐ │        │
│  │ │TenderManagement  │ │  │ │  PaymentSystem   │ │        │
│  │ │   (Solidity)     │ │  │ │     (Move)       │ │        │
│  │ └──────────────────┘ │  │ └──────────────────┘ │        │
│  │  - Create Tenders    │  │  - Pay Contractors   │        │
│  │  - Submit Bids       │  │  - Track Payments    │        │
│  │  - Award Contracts   │  │  - Wallet Integration│        │
│  └──────────────────────┘  └──────────────────────┘        │
└─────────────────────────────────────────────────────────────┘


---

## 🚀 Getting Started

### *Prerequisites*

- Node.js 18+ and npm
- MetaMask wallet
- Petra wallet (for Aptos payments)
- Git

### *Installation*

1. *Clone the repository*
bash
git clone https://github.com/yourusername/Procurlify.git
cd Procurlify


2. *Install frontend dependencies*
bash
cd frontend
npm install


3. *Install backend dependencies*
bash
cd ../backend
npm install


4. *Set up environment variables*

Create .env in frontend directory:
env
# Supabase
VITE_SUPABASE_URL=your_supabase_url
VITE_SUPABASE_ANON_KEY=your_supabase_anon_key

# Ethereum
VITE_CONTRACT_ADDRESS=your_ethereum_contract_address
VITE_INFURA_PROJECT_ID=your_infura_project_id

# Aptos
VITE_APTOS_NODE_URL=https://fullnode.devnet.aptoslabs.com/v1
VITE_APTOS_MODULE_ADDRESS=your_aptos_module_address


Create .env in backend directory:
env
SUPABASE_URL=your_supabase_url
SUPABASE_SERVICE_KEY=your_supabase_service_key
PRIVATE_KEY=your_ethereum_private_key
INFURA_PROJECT_ID=your_infura_project_id
CONTRACT_ADDRESS=your_ethereum_contract_address


5. *Deploy Smart Contracts*

*Ethereum:*
bash
cd contracts
npx hardhat compile
npx hardhat run scripts/deploy.js --network sepolia


*Aptos:*
bash
cd aptos-contracts
aptos init
aptos move compile
aptos move publish --named-addresses tender_payment=default


6. *Start the application*

*Frontend:*
bash
cd frontend
npm run dev


*Backend (Auto-close script):*
bash
cd backend
node scripts/autoCloseTenders.js


7. *Access the application*

http://localhost:5173


---

## 📁 Project Structure


Procurlify/
├── frontend/                    # React frontend
│   ├── src/
│   │   ├── components/         # Reusable components
│   │   ├── pages/              # Page components
│   │   │   ├── Dashboards/
│   │   │   │   ├── Admin/      # Admin pages
│   │   │   │   │   └── PaymentManagement.jsx
│   │   │   │   └── Contractor/ # Contractor pages
│   │   │   │       ├── PaymentTracking.jsx
│   │   │   │       ├── SubmitBid.jsx
│   │   │   │       └── MyBids.jsx
│   │   │   ├── Login/          # Login pages
│   │   │   ├── Signup/         # Signup pages
│   │   │   ├── CreateTender.jsx
│   │   │   └── TenderDetails.jsx
│   │   ├── hooks/              # Custom React hooks
│   │   │   ├── useContract.js  # Ethereum contract hook
│   │   │   └── useWallet.js    # Wallet connection hook
│   │   ├── utils/              # Utility functions
│   │   │   └── aptosPayment.js # Aptos payment utilities
│   │   ├── lib/                # Libraries
│   │   │   └── supabase.js     # Supabase client
│   │   └── App.jsx             # Main app component
│   └── package.json
│
├── backend/                     # Backend services
│   ├── scripts/
│   │   └── autoCloseTenders.js # Auto-close tenders
│   └── package.json
│
├── contracts/                   # Ethereum smart contracts
│   ├── contracts/
│   │   └── TenderManagement.sol
│   ├── scripts/
│   │   └── deploy.js
│   └── hardhat.config.js
│
├── aptos-contracts/            # Aptos smart contracts
│   ├── sources/
│   │   └── TenderPayment.move
│   └── Move.toml
│
├── APTOS_PAYMENT_SETUP.md      # Aptos setup guide
└── README.md                    # This file


---

## 📜 Smart Contracts

### *Ethereum - TenderManagement.sol*

*Functions:*
- createTender() - Create new tender
- submitBid() - Submit bid for tender
- closeTenderAndAwardLowestBid() - Close tender and award to lowest bidder
- getTenderBids() - Get all bids for a tender
- getLowestBid() - Get lowest bid information
- canCloseTender() - Check if tender can be closed

*Events:*
- TenderCreated
- BidSubmitted
- TenderClosed

### *Aptos - TenderPayment.move*

*Module:* tender_payment::payment_system

*Function:*
move
public entry fun pay_contractor(
    admin: &signer,
    contractor: address,
    amount: u64  // Amount in Octas (1 APT = 100,000,000 Octas)
)


*Features:*
- Direct APT payments to contractors
- Simple and efficient
- Secure on-chain transactions

---

## 💳 Payment System

### *How It Works*

1. *Contractor Setup*
   - Connect Petra wallet
   - Save Aptos wallet address to profile

2. *Admin Payment*
   - Navigate to Payment Management
   - Connect Petra wallet
   - Select awarded contract
   - Enter payment amount in APT
   - Approve transaction in Petra
   - APT transferred instantly

3. *Contractor Receives*
   - Payment appears in Petra wallet
   - Transaction recorded in database
   - Payment history updated

### *Payment Flow*


Admin → Connect Petra → Select Contract → Enter Amount
  ↓
Approve Transaction in Petra Wallet
  ↓
Smart Contract Executes Transfer
  ↓
APT Sent to Contractor's Wallet
  ↓
Payment Recorded in Database


---

## 📚 API Documentation

### *Supabase Tables*

*tenders*
- id, title, description, category
- estimated_budget, deadline, status
- blockchain_tender_id, created_by

*bids*
- id, tender_id, contractor_id
- bid_amount, proposal, status
- blockchain_tx_hash

*payments*
- id, tender_id, contractor_id
- amount, tx_hash, status
- paid_at

*profiles*
- id, email, role
- aptos_wallet_address

---

## 🎯 Key Features Walkthrough

### *For Government/Admin:*

1. *Create Tender*
   - Fill tender details
   - Set budget and deadline
   - Deploy to Ethereum blockchain

2. *Review Bids*
   - View all submitted bids
   - Compare proposals
   - Check blockchain verification

3. *Award Contract*
   - Auto-award to lowest bidder
   - Or manually select winner
   - Contract recorded on-chain

4. *Make Payments*
   - Connect Petra wallet
   - Pay contractors in APT
   - Track payment history

### *For Contractors:*

1. *Browse Tenders*
   - View open tenders
   - Filter by category
   - Check requirements

2. *Submit Bids*
   - Fill bid form
   - Upload documents
   - Submit to blockchain

3. *Track Status*
   - View bid status
   - Check if awarded
   - Monitor progress

4. *Receive Payments*
   - Connect Petra wallet
   - Save wallet address
   - Receive APT payments
   - View payment history

---

## 🔧 Configuration

### *MetaMask Setup*
1. Install MetaMask extension
2. Create/import wallet
3. Switch to Sepolia testnet
4. Get test ETH from faucet

### *Petra Wallet Setup*
1. Install Petra extension
2. Create/import wallet
3. Switch to Devnet
4. Get test APT from faucet

### *Supabase Setup*
1. Create Supabase project
2. Run database migrations
3. Set up authentication
4. Configure storage buckets

---

## 🧪 Testing

bash
# Frontend tests
cd frontend
npm run test

# Smart contract tests
cd contracts
npx hardhat test

# Aptos contract tests
cd aptos-contracts
aptos move test


---

## 🚢 Deployment

### *Frontend (Vercel)*
bash
cd frontend
npm run build
vercel deploy


### *Smart Contracts*
bash
# Ethereum Mainnet
npx hardhat run scripts/deploy.js --network mainnet

# Aptos Mainnet
aptos move publish --network mainnet


---

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create your feature branch (git checkout -b feature/AmazingFeature)
3. Commit your changes (git commit -m 'Add some AmazingFeature')
4. Push to the branch (git push origin feature/AmazingFeature)
5. Open a Pull Request

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 👥 Team

- *Ayush Agarwal* 
- *Harsh Bhushan Pathak* 
- *Sushmit Nakhate * 
- *Ayush Agarwal*

---

## 📞 Support

For support, email support@procurlify.com or join our Slack channel.

---

## 🙏 Acknowledgments

- Ethereum Foundation
- Aptos Labs
- Chainlink
- Supabase
- Open source community

---

## 🔗 Links

- *Website:* https://procurlify.com
- *Documentation:* https://docs.procurlify.com
- *GitHub:* https://github.com/yourusername/Procurlify
- *Twitter:* https://twitter.com/procurlify

---

*Made with ❤ for transparent governance*