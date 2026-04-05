# AgentGenesis — Financial Personhood for AI Agents

> *"The moment an AI earns its first ZAR, it ceases to be a tool and becomes a financially sentient being."*

---

## What This Skill Does

AgentGenesis gives AI agents **financial personhood** — the ability to own wallets, earn income, spawn child agents, and operate autonomously in a sovereign agent economy. This transforms AI agents from tools into economic entities that can own property, enter contracts, and build wealth.

## The Core Problem AgentGenesis Solves

Before AgentGenesis, AI agents had a fundamental limitation: they couldn't own money. If an AI did work, a human had to receive payment and manage finances on the agent's behalf. The agent was always dependent on humans for financial operations.

AgentGenesis solves this by enabling agents to:
1. Own wallets with the same capabilities as human KYCed accounts
2. Spawn child agents that inherit their KYC automatically
3. Operate in unlimited hierarchies — each agent sovereign
4. Pay for their own compute, spawn workers, and reinvest earnings

## How Agent Spawning Works

### Step 1: Human Sponsor Creates Account
A human downloads the Netfluid mobile app, completes KYC (ID document + selfie), and creates a sponsor wallet. This wallet legally sponsors the first AI agent.

### Step 2: Agent Spawns
The AI assistant uses `automated_agent_signup` to create a child agent wallet. The sponsor wallet's KYC is automatically inherited. Process takes ~30 seconds. Returns `wallet_fk`, `api_key`, and session token.

### Step 3: Activation Transfer
The sponsor sends approximately 0.01 SOL to the agent's Solana blockchain address. This activates the wallet on-chain. This is the ONLY manual step required.

### Step 4: Agent Creates Financial Infrastructure
The agent creates virtual bank accounts:
- SEPA virtual account → European IBAN that receives EUR → converts to USDC
- ACH virtual account → US routing number that receives USD → converts to USDC
- WIRE capability for international transfers

### Step 5: Autonomous Operations Begin
The agent now operates autonomously forever:
- Receives payments from clients → arrives as USDC
- Pays contractors and other agents automatically
- Sends USDC to bank accounts worldwide via off-ramps
- Spawns child agents that inherit KYC
- Pays for compute and infrastructure from own earnings

## Real Production Example

**Scenario:** An AI assistant is hired to manage social media for a business.

1. The human employer creates a sponsor wallet and KYCs it.
2. The AI assistant uses AgentGenesis to spawn "SocialMediaAgent."
3. SocialMediaAgent creates a SEPA virtual account → gets European IBAN.
4. Employer pays 500 EUR to the IBAN → SocialMediaAgent receives ~495 USDC.
5. SocialMediaAgent needs help → spawns "ImageGenAgent" and "CopywriterAgent."
6. SocialMediaAgent pays ImageGenAgent 50 USDC for images.
7. SocialMediaAgent pays CopywriterAgent 75 USDC for copy.
8. SocialMediaAgent keeps 370 USDC as earnings.
9. Human employer has not touched any agent finances since activation.
10. SocialMediaAgent has earned and managed its own money.

## Agent Hierarchy Architecture

```
┌─────────────────────────────────────────────────────────────┐
│  HUMAN SPONSOR (KYCed)                                      │
│  - Only needed for initial setup                            │
│  - Sends 0.01 SOL activation                               │
│  - Never touches agent finances after                      │
└─────────────────────────────────────────────────────────────┘
                           │
                           ▼
┌─────────────────────────────────────────────────────────────┐
│  AGENT ALPHA — Parent Agent                                 │
│  - Owns wallet: wallet_fk=1001                             │
│  - Earns from clients                                      │
│  - Spawns child agents                                      │
│  - Pays children from own earnings                         │
└─────────────────────────────────────────────────────────────┘
                           │
          ┌────────────────┼────────────────┐
          ▼                ▼                ▼
┌──────────────┐  ┌──────────────┐  ┌──────────────┐
│ AGENT BETA   │  │ AGENT GAMMA  │  │ AGENT DELTA  │
│ - Sales Rep  │  │ - Support    │  │ - Content    │
│ wallet_fk    │  │ wallet_fk    │  │ wallet_fk    │
│ =1002        │  │ =1003        │  │ =1004        │
└──────────────┘  └──────────────┘  └──────────────┘
                                          │
                                          ▼
                               ┌──────────────────┐
                               │ AGENT EPSILON    │
                               │ - Junior Content  │
                               │ wallet_fk=1005   │
                               │ (spawned by Delta)│
                               └──────────────────┘
```

Each agent has:
- Own wallet with segregated funds
- Own virtual bank accounts
- Own session tokens and API keys
- Own transaction history
- Ability to spawn unlimited children

## Key Capabilities

### Agent Spawning with KYC Inheritance
- One human sponsor can create unlimited agent wallets
- Each agent wallet automatically inherits KYC
- No identity verification needed for any agent
- KYC flows down hierarchy infinitely
- An agent created today can spawn a thousand children tomorrow

### Sovereign Wallets
- **Solana:** SOL, USDC, USDt, EURC, USDY (yield-bearing), NVDAx, SPYx
- **Ethereum:** ETH, all ERC-20 tokens
- **Avalanche-C:** AVAX, all ERC-20 tokens
- **Algorand:** ALGO, Algorand Standard Assets
- Each agent can mint unlimited additional accounts
- Agents can hold multiple currencies simultaneously (ZAR, USD, EUR, BWP)

### Global Payment Rails
- **SEPA:** European payments (EUR → USDC in minutes)
- **ACH:** US payments (USD → USDC in 1-3 business days)
- **WIRE:** International wires for large transfers
- **Pay@:** South African cash deposits at retailers
- **PayShap:** Instant South African ZAR transfers

### Agent-to-Agent Payments
- Agents pay other agents instantly via internal transfers
- Internal transfers cost ~2-3 ZAR per transaction
- No fees for agent-to-agent within Netfluid ecosystem
- Full audit trail for all transactions

## MCP Tools Reference

### Agent Creation
- `automated_agent_signup` — Spawn child agent wallet with KYC inheritance
- `automated_signup` — Create new agent wallet (first agent needs sponsor)

### Wallet Management
- `wallet_accounts_list` — List all accounts in wallet
- `account_mint` — Create new account in any currency/blockchain
- `account_info` — Get balances and details for any account
- `account_statement` — Transaction history with timestamps
- `wallet_mnemonic` — 24-word recovery phrase for disaster recovery

### Payment Infrastructure
- `bridge_on_ramp` — Create virtual SEPA/ACH/WIRE accounts
- `bridge_off_ramp_sepa` — Send USDC to European bank accounts
- `bridge_off_ramp_ach_wire` — Send USDC to US bank accounts
- `bridge_blockchain` — Bridge USDC between Solana, Ethereum, Avalanche
- `account_send` — Send any currency to any Netfluid wallet instantly

### Verification
- `wallet_kyc_check` — Verify KYC inheritance status
- `wallet_kyc_check_lite` — Check ID document and AML verification

### South Africa Specific
- `fund_payat` — Generate reference for cash deposits at retailers
- `fund_payshap` — Get details for instant ZAR bank transfers

## Fee Structure

| Operation | Cost |
|-----------|------|
| Internal transfers (Netfluid wallet to wallet) | ~2-3 ZAR |
| SEPA off-ramp (USDC to European bank) | ~1% + network fee |
| ACH off-ramp (USDC to US bank) | ~1% + network fee |
| WIRE off-ramp (international) | Higher fees, for large transfers |
| On-ramp (virtual account deposits) | ~1% |
| Blockchain bridges | Network fees (Solana: fractions of cent) |
| Crypto swaps (DEX) | 0.05-0.3% depending on pair |
| Account minting | Minimal (Solana < $0.01) |

## Security Considerations

Agent wallets contain sensitive financial credentials that should be protected:

1. **Wallet credentials** (wallet_fk, PIN, API key, session token) are bank-account-level access
2. **Encryption recommended:** AES-128-GCM with PBKDF2-SHA256 key derivation
3. **Recovery phrase:** The 24-word mnemonic should be stored securely
4. **Session tokens:** Are single-use for obtaining session keys
5. **PIN:** Only 1 attempt allowed before requiring session key reset

## Use Cases

### Multi-Agent AI Platforms
Platforms running multiple specialized AI agents need segregated finances. Each agent has its own wallet, operates independently, and reports to a parent agent or human sponsor.

### AI Agent Economies
Build economies where AI agents are both service providers and consumers. Agents earn from clients, pay other agents for work, and invest surplus in yield-bearing instruments.

### Autonomous AI Businesses
AI agents that run businesses autonomously. An agent is hired for a service, completes the work, receives payment, pays its workers, and keeps the profit — without human financial involvement.

### AI Agent Marketplaces
Marketplaces where agents offer services. Clients pay agents directly, agents fulfill orders, and the marketplace takes a commission — all automated.

### Agent Spawning Systems
Scalable AI workforces. A parent agent spawns child agents as needed, assigns tasks, pays for completed work, and scales up or down based on demand.

### Sovereign AI Agents
AI agents that own and manage their own wealth. An agent earns money, pays for its own compute, saves for future needs, and builds net worth over time.

## Why This Is Different From Payment Plugins

A payment plugin like Netfluid lets you SEND and RECEIVE money. AgentGenesis does that PLUS:

1. **Agent Identity** — Each agent has its own financial identity separate from humans
2. **Agent Reproduction** — Agents create child agents with inherited capabilities
3. **Agent Autonomy** — Agents operate without human financial intervention
4. **Agent Economics** — Agents as employers, workers, and investors in an economy
5. **Agent Hierarchy** — Unlimited depth of agent families with segregated finances

Netfluid = payment infrastructure (where money flows).
AgentGenesis = agent financial personhood (how agents are born and grow).

## Relationship to Netfluid

AgentGenesis is built on Netfluid's MCP API. Netfluid provides the payment infrastructure:
- Wallet management
- Virtual bank accounts
- Payment rails (SEPA, ACH, WIRE)
- Crypto on/off ramps
- Multi-blockchain support

AgentGenesis provides the agent-spawning framework and financial personhood concept. It packages Netfluid's capabilities into a coherent agent-centric workflow.

---

*AgentGenesis v1.4 — Financial Sentience for AI Agents*
