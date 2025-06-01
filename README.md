# 📦 Stellar-Soroban Voting DApp

A decentralized voting application built on **Stellar blockchain** using **Soroban smart contracts**. Users can vote for their preferred candidate while automatically funding their Stellar account with 1 XLM per vote.

## 🚀 Features

- **Next.js** based modern frontend with TypeScript
- **Rust/Soroban** smart contracts for secure voting
- 🔑 **Freighter wallet** integration
- ⚡ 3 different voting candidates/projects
- 💰 Automatic **1 XLM funding** to selected candidate
- 🎨 Elegant and responsive UI with **Tailwind CSS**
- 📊 Real-time vote tracking on blockchain
- 🔒 Secure and transparent voting mechanism

## 📂 Project Structure

```bash
stellar-voting-dapp/
├── frontend/              # Next.js application
│   ├── src/
│   │   ├── app/          # App router pages
│   │   ├── components/   # React components
│   │   └── lib/         # Utility functions
│   ├── package.json
│   └── tailwind.config.js
├── voting-contract/       # Rust/Soroban smart contract
│   ├── src/
│   │   └── lib.rs       # Contract implementation
│   ├── Cargo.toml
│   └── target/
└── README.md             # This document!

```
## 🛠️ Installation
Prerequisites

- Node.js 18+ and npm
- Rust and Cargo
- Soroban CLI
- Freighter Wallet Browser Extension

1️⃣ Clone the repository:
```bash
git clone https://github.com/<username>/stellar-voting-dapp.git
cd stellar-voting-dapp
```
2️⃣ Setup Frontend:
```bash
cd frontend
npm install
```
3️⃣ Setup Smart Contract:
```bash
# Install Soroban CLI
cargo install --locked soroban-cli

# Add WASM target
rustup target add wasm32-unknown-unknown

# Build the contract
cd ../voting-contract
soroban contract build
```
4️⃣ Deploy Contract (Testnet):
```bash
# Configure testnet
soroban network add testnet --rpc-url https://soroban-testnet.stellar.org:443 --network-passphrase "Test SDF Network ; September 2015"

# Deploy contract
soroban contract deploy \
  --wasm target/wasm32-unknown-unknown/release/voting_contract.wasm \
  --source YOUR_SECRET_KEY \
  --network testnet
```
5️⃣ Start Development Server:
```bash
cd ../frontend
npm run dev
```
Visit http://localhost:3000 to see the application.

## ⚙️Usage

- 1.Connect Wallet: Click "Connect Freighter Wallet" to link your Stellar wallet

- 2.Select Candidate: Choose from 3 available voting options (Project A, B, or C)

- 3.Vote & Fund: Submit your vote - this will record your vote AND send 1 XLM to the selected candidate

- 4.Track Results: All votes and transactions are recorded on Stellar blockchain

🔧 Environment Variables
Create .env.local in the frontend directory:

```envNEXT_PUBLIC_SOROBAN_NETWORK_PASSPHRASE=Test SDF Network ; September 2015
NEXT_PUBLIC_SOROBAN_RPC_URL=https://soroban-testnet.stellar.org:443
NEXT_PUBLIC_CONTRACT_ADDRESS=YOUR_DEPLOYED_CONTRACT_ADDRESS
```

🧪 Testing
```bash# Test smart contract
cd voting-contract
cargo test
# Test frontend
cd ../frontend
npm test
```
🤝 Contributing
We welcome contributions! Please feel free to submit a Pull Request.

- Fork the project
- Create your feature branch (git checkout -b feature/AmazingFeature)
- Commit your changes (git commit -m 'Add some AmazingFeature')
- Push to the branch (git push origin feature/AmazingFeature)
- Open a Pull Request

📄 License
This project is licensed under the MIT License.

🔗 Useful Links

- 🌐 Stellar Developer Documentation
- 🔧 Soroban Smart Contracts
- 💼 Freighter Wallet
- 🧪 Stellar Laboratory
- ⚠️ Important Notes

Make sure you have Freighter Wallet installed and configured

This project uses Stellar Testnet - get test XLM from Stellar Laboratory

Complete smart contract compilation before running the frontend

Each vote costs 1 XLM + network fees


