# Bento.Fun

Bento.Fun is a decentralized binary options and prediction markets platform built on **BNB Smart Chain (BSC)**. The platform enables users to create, own, trade, and participate in real-time prediction markets (called "duels") with binary outcomes, using USDC or custom conviction tokens.

<img width="1884" height="899" alt="Screenshot 2026-01-14 at 22 49 43" src="https://github.com/user-attachments/assets/dd5a5591-6fe7-4f30-ba81-7d391f8ac0dc" />

## 🚀 Active Development Status

**Bento.Fun is under active development** with regular updates, feature additions, and improvements. The project demonstrates continuous development activity through:

- ✅ **Recent Mainnet Deployment**: Successfully deployed on BNB Smart Chain Mainnet (January 2026)
- ✅ **Multiple Testnet Deployments**: Active testing on BSC Testnet with multiple iterations
- ✅ **Continuous Contract Upgrades**: Diamond pattern contracts with modular facet architecture
- ✅ **Active Feature Development**: Phase 1 implementation complete with public/private markets, invitation system, referral system, contest period, and automated settlement
- ✅ **Regular Security Updates**: Ongoing security improvements and optimizations
- ✅ **Production-Ready Services**: 9 core services actively maintained and deployed

**Development Activity Indicators:**
- Recent contract deployments on BNB Smart Chain (2025-2026)
- Active codebase with 1000+ files across 9 packages
- Comprehensive documentation and technical guides
- Regular contract upgrades and optimizations
- Multi-signature wallet integration for secure governance

## Project Overview

Bento.Fun consists of several interconnected services that work together to provide a seamless binary options/prediction market experience:

### Core Components

1. **Frontend (Port 3000)**
   - Next.js 16 application providing the main user interface
   - Real-time price updates and duel participation
   - Smart wallet integration via Alchemy Account Kit
   - Responsive design for both desktop and mobile users
   - Support for public and private markets

2. **Backend (Port 3004)**
   - Express.js API server handling core business logic
   - User authentication and session management
   - MongoDB database with Prisma ORM
   - Integration with blockchain networks
   - WebSocket support for real-time updates

3. **Timer Logic (Port 3001)**
   - Manages the timing of prediction rounds
   - Handles round transitions and state management
   - WebSocket-based real-time updates
   - Ensures fair and synchronized duel periods
   - Automated settlement and threshold checking

4. **Invite Service (Port 3009)**
   - Manages user invitations and access control
   - Prisma-based database for user management
   - Invitation code generation and validation
   - User onboarding flow for private markets

5. **Admin Dashboard (Port 3002)**
   - Administrative interface for platform management
   - User management and monitoring
   - System statistics and analytics
   - Platform configuration and settings
   - Withdrawal approval system

6. **Curator Dashboard (Port 3003)**
   - Curator interface for league management
   - Market approval and moderation
   - League-specific analytics

7. **Pricing Engine (Python/Flask)**
   - LS-LMSR (Liquidity-Sensitive Logarithmic Market Scoring Rule) algorithm
   - Real-time probability and price calculations
   - Supabase (PostgreSQL) database integration
   - WebSocket support for live price feeds

8. **Telegram Bot**
   - Admin and curator notifications
   - System alerts and monitoring
   - User engagement features

9. **Smart Contracts (Solidity)**
   - Diamond Pattern (EIP-2535) architecture for modular, upgradeable contracts
   - Core market creation and betting logic
   - Automated settlement and payouts
   - P2P bet trading marketplace
   - Multi-signature wallet for secure governance
   - Deployed on BNB Smart Chain mainnet and testnet

### Key Features

- **Permissionless Market Creation**: Anyone can create prediction markets instantly
- **Public & Private Markets**: Support for both public markets and invite-only private markets
- **Real-time Pricing**: Dynamic option pricing based on liquidity using LS-LMSR algorithm
- **Smart Wallet Integration**: Email/social login via Alchemy Account Kit (ERC-4337)
- **Binary Prediction Markets & Versus Duels**: Simple YES/NO outcomes and versus duels with scheduled start/end times
- **Automated Settlement**: Bot-driven lifecycle management with contest period
- **Portfolio Tracking**: View positions, history, and P&L
- **Leaderboard**: Global rankings by profit
- **Diamond Pattern Contracts**: Modular, upgradeable smart contract architecture

### Technology Stack

- **Frontend**: Next.js 16, React 19, TailwindCSS, Alchemy Account Kit (Smart Wallets), Viem 2.29.2, Wagmi, Zustand
- **Backend**: Express.js, TypeScript, MongoDB, Prisma ORM, JWT, WebSocket
- **Smart Contracts**: Solidity ^0.8.30, Diamond Pattern (EIP-2535), Hardhat
- **Blockchain**: BNB Smart Chain (BSC)
- **Pricing Engine**: Python 3.x, Flask, NumPy, SciPy, Supabase (PostgreSQL)
- **Real-time**: WebSocket, Socket.IO
- **Database**: MongoDB, PostgreSQL (Supabase)
- **Tools**: Hardhat, Multi-Signature Wallet
- **Package Manager**: pnpm

This monorepo contains all the services for the Bento.Fun ecosystem, managed using pnpm workspaces.

## Services and Ports

| Service            | Port | Description                                     |
| ------------------ | ---- | ----------------------------------------------- |
| Frontend           | 3000 | Next.js application for the main user interface |
| Backend            | 3004 | Express.js API server                           |
| Timer Logic        | 3001 | Timer service for managing game rounds          |
| Invite Service     | 3009 | Invite-only system with Prisma database         |
| Admin Dashboard    | 3002 | Next.js application for admin interface         |
| Curator Dashboard  | 3003 | Next.js application for curator interface       |
| Pricing Engine     | 5001 | Python/Flask service for market pricing         |
| Telegram Bot       | 80   | Telegram bot for admin/curator notifications (webhook mode, configurable) |

## Supported Networks

Bento.Fun is **deployed on BNB Smart Chain**:

### Mainnet

- **BNB Smart Chain Mainnet** (Chain ID: 56)
  - RPC: https://bsc-dataseed.binance.org/
  - USDC: `0x8AC76a51cc950d9822D68b83fE1Ad97B32Cd580d`
  - Diamond: `0x53A16B43703F0573c5518B3C1427083E1a381d3e`

### Testnet

- **BNB Smart Chain Testnet** (Chain ID: 97)
  - RPC: https://data-seed-prebsc-1-s1.binance.org:8545/
  - USDC: `0xcA12689B79F053aeF20e3Dace505A545BCf76C78`
  - Diamond: `0xd419a76aD1D5a3407487A1e5A28bbfe287FC8Bef`

## Contract Addresses

### BNB Smart Chain Mainnet

| Contract                | Address                                      |
| ----------------------- | -------------------------------------------- |
| Diamond (Core)          | `0x53A16B43703F0573c5518B3C1427083E1a381d3e` |
| BENTO USDC              | `0x8AC76a51cc950d9822D68b83fE1Ad97B32Cd580d` |
| BentoAdminFacet         | `0x4b89fF0A6ec3F15e363f2b1e8Aa668968707d63e` |
| BentoCoreFacet          | `0x8ac8ba3763Cb31F0A3D1168c6946F21fddE3FCca` |
| BentoViewFacet          | `0x79CBC4F261B05e1104913537960126BC2037FE80` |
| BentoSettlementFacet    | `0xa4a180B55CdE859215F4cBdb58d97DCB66e3443f` |
| OwnershipFacet          | `0x55710dEc234C5383B04c17eF96Ff7301F809A727` |
| DiamondCutFacet         | `0x9E033185144448793ed12FA27b69C3358CF5e431` |
| DiamondLoupeFacet       | `0x1390b7Bfe21E7F56A41130784f909CE6E93C220c` |
| DiamondInit             | `0xe84332A6e1cBa131CBCdc616aC27c29dc42a3974` |

### BNB Smart Chain Testnet

| Contract                | Address                                      |
| ----------------------- | -------------------------------------------- |
| Diamond (Core)          | `0xd419a76aD1D5a3407487A1e5A28bbfe287FC8Bef` |
| BENTO USDC              | `0xcA12689B79F053aeF20e3Dace505A545BCf76C78` |
| BentoAdminFacet         | `0x36Dacaa07Ff6A5C76183A08d5a0E43d0A1315689` |
| BentoCoreFacet          | `0xCF16D9Fc723C1fc5753E6177615815Ece3EAd5D4` |
| BentoViewFacet          | `0x0fCb4574964d2F26a7f0f38131B5d7A7A6723db4` |
| BentoSettlementFacet    | `0x6D0A49a384C149a141E9FF9B64f3b042956FB702` |
| OwnershipFacet          | `0x4dA61b80106b4F8EC51DeE8B1D563CE541C00dD2` |
| DiamondCutFacet         | `0xD63e197bF8617AB1099a356465dAb11379855129` |
| DiamondLoupeFacet       | `0xA1c3D3Ad0c3213daF414902485843b044D024C01` |
| DiamondInit             | `0x18dA3b94c5Ebd562855A303743E247a2431d7DE3` |

## Prerequisites

- Node.js >= 18.0.0
- pnpm >= 8.0.0 (package manager)
- Python 3.x (for pricing engine)
- Virtual environment for Python services
- MongoDB (for backend)
- PostgreSQL/Supabase (for pricing engine)

## Getting Started

```bash
git clone https://github.com/Bentodotfun/bento.fun
cd bento.fun
```

### 1. Install Dependencies

```bash
pnpm install
```

### 2. Set Up Python Virtual Environment for Pricing Engine

```bash
# Navigate to pricing-engine directory
cd packages/pricing-engine

# Remove existing virtualenv if any
rm -rf virtualenv

# Create a new virtual environment using system Python
python3 -m venv virtualenv

# Activate the virtual environment
source virtualenv/bin/activate

# Your prompt should now show (virtualenv) at the beginning
# Verify you're in the virtual environment (should show path to virtualenv's python)
which python3
# Should show something like: /Users/your-username/path/to/bento.fun/packages/pricing-engine/virtualenv/bin/python3

# Install requirements (now safe to install as we're in virtualenv)
pip3 install -r requirements.txt

# Deactivate virtual environment when done
deactivate

# Return to root directory
cd ../..
```

**Note:** If you encounter any issues or conflicts with Homebrew-installed Python3, follow these steps before setting up the virtual environment:

```bash
# Uninstall Python3 and pip3 from Homebrew (if any)
brew uninstall python3
brew uninstall pip3

# Remove Python framework files
sudo rm -rf /opt/homebrew/opt/python@3.13
sudo rm -rf /opt/homebrew/Frameworks/Python.framework

# Remove pip configuration files
rm -rf ~/.pip
rm -rf ~/.config/pip
rm -rf /opt/homebrew/share/pip

# Clean up Homebrew
brew cleanup

# Verify Python3 is now using system version
which python3
```

### 3. Set Up Environment Variables

Update `.env` files in respective services:

```bash
# Frontend
cd packages/frontend
cp .env.example .env
# Update all variables in .env file, especially:
# - NEXT_PUBLIC_DIAMOND_BSC (BNB Smart Chain mainnet)
# - NEXT_PUBLIC_DIAMOND_BSC_TESTNET (BSC testnet)
# - NEXT_PUBLIC_BENTO_USDC_BSC
# - NEXT_PUBLIC_BENTO_USDC_BSC_TESTNET

# Backend
cd ../backend
cp .env.example .env
# Update all variables in .env file, including:
# - MongoDB connection string
# - Blockchain RPC URLs (especially BSC)
# - JWT secrets
# - AWS S3 credentials (if using)

# Timer Logic
cd ../timer-logic
cp .env.example .env
# Update all variables in .env file

# Invite Service
cd ../invite-service
cp .env.example .env
# Update all variables in .env file

# Admin Dashboard
cd ../admin-dashboard
cp .env.example .env
# Update all variables in .env file

# Curator Dashboard
cd ../curator-dashboard
cp .env.example .env
# Update all variables in .env file

# Pricing Engine
cd ../pricing-engine
cp .env.example .env
# Update all variables in .env file, including:
# - Supabase connection details
# - Blockchain RPC URLs

# Contracts
cd ../contracts
cp .env.example .env
# Update all variables in .env file, especially:
# - QUICKNODE_API_KEY_BSC_MAINNET
# - QUICKNODE_API_KEY_BSC_TESTNET
# - Private keys for deployment
cd ../..
```

### 4. Initialize Databases

```bash
# Backend - Generate Prisma client and push schema
pnpm backend-prisma

# Pricing Engine - Set up Supabase/PostgreSQL database
# Follow instructions in packages/pricing-engine/docs/
```

### 5. Start Services

For each package, navigate to its directory, install dependencies, and start the development server:

```bash
# Frontend (Next.js) - Port 3000
cd packages/frontend
pnpm install
pnpm run dev

# Backend (Express) - Port 3004
cd packages/backend
pnpm install
cd src
npx prisma generate
npx prisma db push
pnpm run start

# Timer Logic - Port 3001
cd packages/timer-logic
pnpm install
pnpm run dev

# Invite Service - Port 3009
cd packages/invite-service
npx prisma generate
npx prisma db push
pnpm install
pnpm run build
pnpm run dev

# Admin Dashboard - Port 3002
cd packages/admin-dashboard
pnpm install
pnpm run dev

# Curator Dashboard - Port 3003
cd packages/curator-dashboard
pnpm install
pnpm run dev

# Pricing Engine - Port 5001
cd packages/pricing-engine
source virtualenv/bin/activate
pip3 install -r requirements.txt
python3 pricing.py

# Telegram Bot
cd packages/telegram-bot
pnpm install
pnpm run dev
```

## Development

### Frontend (Next.js)

- Located in `packages/frontend`
- Uses Next.js 16 with App Router
- TailwindCSS for styling
- Alchemy Account Kit for smart wallet integration
- Viem and Wagmi for blockchain interactions

### Backend (Express)

- Located in `packages/backend`
- Express.js server with TypeScript
- MongoDB database with Prisma ORM
- JWT authentication
- WebSocket support for real-time updates

### Timer Logic

- Located in `packages/timer-logic`
- Manages game rounds and timing
- WebSocket communication
- Automated settlement and threshold checking

### Invite Service

- Located in `packages/invite-service`
- Prisma ORM for database
- Express.js server
- Requires `prisma generate` before running

### Admin Dashboard

- Located in `packages/admin-dashboard`
- Next.js application
- Admin interface for managing the platform

### Curator Dashboard

- Located in `packages/curator-dashboard`
- Next.js application
- Curator interface for league management

### Pricing Engine

- Located in `packages/pricing-engine`
- Python-based service using Flask
- LS-LMSR algorithm for dynamic pricing
- Requires virtual environment
- Supabase (PostgreSQL) database

### Smart Contracts

- Located in `packages/contracts`
- Solidity ^0.8.30
- Diamond Pattern (EIP-2535) architecture
- Hardhat for development and deployment
- Multi-signature wallet for upgrades
- Deployed on BNB Smart Chain

## Smart Contract Architecture

Bento.Fun uses the **Diamond Pattern (EIP-2535)** for modular, upgradeable smart contracts:

- **Diamond**: Main proxy contract
- **Facets**: Modular contract components
  - `BentoCoreFacet`: Core market creation and betting logic
  - `BentoViewFacet`: View functions and data queries
  - `BentoAdminFacet`: Admin operations
  - `BentoSettlementFacet`: Market resolution and payouts
  - `OwnershipFacet`: Ownership management
  - `DiamondCutFacet`: Facet upgrades
  - `DiamondLoupeFacet`: Facet inspection
  - `DiamondInit`: Initialization contract for Diamond setup

All contract upgrades are managed through a multi-signature wallet for security.

## BNB Chain Deployment

Bento.Fun is **actively deployed and maintained on BNB Smart Chain**:

### Mainnet Deployment
- **Network**: BNB Smart Chain (Chain ID: 56)
- **Status**: ✅ Live and Active
- **Primary Contract**: `0x53A16B43703F0573c5518B3C1427083E1a381d3e`

### Testnet Deployment
- **Network**: BNB Smart Chain Testnet (Chain ID: 97)
- **Status**: ✅ Active Development
- **Primary Contract**: `0xd419a76aD1D5a3407487A1e5A28bbfe287FC8Bef`

### Configuration Evidence

The project explicitly targets BNB Smart Chain through:

1. **Hardhat Configuration**: `bscMainnet` and `bscTestnet` networks configured with Chain IDs 56 and 97
2. **Contract Addresses**: Dedicated contract deployments on BSC mainnet and testnet
3. **Frontend Configuration**: BSC network configuration in contract config files
4. **RPC Endpoints**: BSC-specific RPC URLs in environment variables
5. **USDC Addresses**: BSC-specific USDC token addresses configured

## Troubleshooting

### Port Conflicts

If you encounter port conflicts, you can kill the process using:

```bash
# For port 3000 (Frontend)
lsof -i :3000 | grep LISTEN | awk '{print $2}' | xargs kill -9

# For port 3004 (Backend)
lsof -i :3004 | grep LISTEN | awk '{print $2}' | xargs kill -9

# For port 5001 (Pricing Engine)
lsof -i :5001 | grep LISTEN | awk '{print $2}' | xargs kill -9
```


### Python Virtual Environment Issues

If you have issues with the Python virtual environment:

```bash
cd packages/pricing-engine
rm -rf virtualenv
python3 -m venv virtualenv
source virtualenv/bin/activate
pip3 install -r requirements.txt
```

### Contract Deployment Issues

For contract deployment issues:

```bash
cd packages/contracts
# Ensure .env file has correct RPC URLs and private keys
# For BSC Mainnet: QUICKNODE_API_KEY_BSC_MAINNET
# For BSC Testnet: QUICKNODE_API_KEY_BSC_TESTNET
```

## Project Structure

```
bento.fun/
├── packages/
│   ├── contracts/           # Solidity smart contracts (Diamond pattern)
│   ├── backend/             # Express.js API server
│   ├── frontend/            # Next.js user application (port 3000)
│   ├── admin-dashboard/     # Next.js admin panel (port 3002)
│   ├── curator-dashboard/   # Next.js curator panel (port 3003)
│   ├── timer-logic/         # Timer bot service (port 3001)
│   ├── pricing-engine/      # Python pricing service
│   ├── telegram-bot/         # Telegram bot integration
│   └── invite-service/      # Invitation management
├── docs/                    # Documentation
├── final-docs/              # Final documentation
├── scripts/                 # Utility scripts
└── pnpm-workspace.yaml      # pnpm workspace configuration
```

## Contributing

We welcome contributions! Please see our contributing guidelines for more information.

## License

GNU General Public License

## Links

- **Website**: [bento.fun](https://bento.fun)
- **Documentation**: See `docs/` and `final-docs/` directories
- **Smart Contracts**: `packages/contracts/`
- **BNB Chain Explorer**: [View on BscScan](https://bscscan.com/address/0x53A16B43703F0573c5518B3C1427083E1a381d3e)

---

**Note**: This project is actively developed and deployed on BNB Smart Chain. For the latest updates and deployment information, please refer to the contract addresses section above or check the `packages/contracts/constants/networkMapping.json` file.
