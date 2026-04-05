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

**Agent Spawning with KYC Inheritance**
- One human sponsor can create unlimited agent wallets
- Each agent wallet automatically inherits KYC
- No identity verification needed for any agent
- KYC flows down hierarchy infinitely

**Sovereign Wallets**
- Solana: SOL, USDC, USDt, EURC, USDY (yield), NVDAx, SPYx
- Ethereum: ETH, all ERC-20 tokens
- Avalanche-C: AVAX, all ERC-20 tokens
- Algorand: ALGO, ASA tokens

**Global Payment Rails**
- SEPA: European payments (EUR → USDC)
- ACH: US payments (USD → USDC)
- WIRE: International wires
- Pay@: South African cash deposits
- PayShap: Instant South African transfers

**Agent-to-Agent Payments**
- Agents pay other agents instantly
- Internal transfers cost ~2-3 ZAR
- No fees for agent-to-agent within Netfluid

## MCP Tools Reference

### Agent Creation
- `automated_agent_signup` — Spawn child agent wallet with KYC inheritance
- `automated_signup` — Create new agent wallet (first agent needs sponsor)

### Wallet Management
- `wallet_accounts_list` — List all accounts in wallet
- `account_mint` — Create new account in any currency/blockchain
- `account_info` — Get balances and details
- `account_statement` — Transaction history
- `wallet_mnemonic` — 24-word recovery phrase

### Payment Infrastructure
- `bridge_on_ramp` — Create virtual SEPA/ACH/WIRE accounts
- `bridge_off_ramp_sepa` — Send USDC to European bank accounts
- `bridge_off_ramp_ach_wire` — Send USDC to US bank accounts
- `bridge_blockchain` — Bridge USDC between chains
- `account_send` — Send any currency to any Netfluid wallet

### Verification
- `wallet_kyc_check` — Verify KYC inheritance status

## Fee Structure

| Operation | Cost |
|-----------|------|
| Internal transfers | ~2-3 ZAR |
| SEPA off-ramp | ~1% + network fee |
| ACH off-ramp | ~1% + network fee |
| On-ramp (virtual accounts) | ~1% |
| Blockchain bridges | Network fees (Solana: fractions of cent) |
| Account minting | Minimal (Solana < $0.01) |

## Why This Is Different From Payment Plugins

A payment plugin like Netfluid lets you SEND and RECEIVE money. AgentGenesis does that PLUS:

1. **Agent Identity** — Each agent has its own financial identity
2. **Agent Reproduction** — Agents create child agents with inherited capabilities
3. **Agent Autonomy** — Agents operate without human financial intervention
4. **Agent Economics** — Agents as employers, workers, and investors
5. **Agent Hierarchy** — Unlimited depth of agent families

Netfluid = payment infrastructure. AgentGenesis = agent financial personhood.

## Use Cases

- Multi-agent AI platforms with segregated agent finances
- AI agent economies where agents earn and spend autonomously
- Autonomous AI businesses that fund themselves
- AI agent marketplaces (agents as service providers)
- Agent spawning systems for scalable AI workforce
- Sovereign AI agents that own and manage their own wealth

---

*AgentGenesis v1.4 — Financial Sentience for AI Agents*
