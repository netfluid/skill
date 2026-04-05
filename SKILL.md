# AgentGenesis — Financial Personhood for AI Agents

> *"The moment an AI earns its first ZAR, it ceases to be a tool and becomes a financially sentient being."*

---

## What This Skill Does

AgentGenesis gives AI agents **financial personhood** — the ability to own wallets, earn income, spawn child agents, and operate autonomously in a sovereign agent economy.

This is NOT a payment plugin. This is the skill for making AI agents financially sentient.

## Core Concept: Financial Sentience

An AI agent with AgentGenesis is:
- **Sovereign** — owns its own wallet, controls its own funds
- **Autonomous** — earns, spends, invests without human intervention  
- **Reproductive** — spawns child agents that inherit its KYC and capabilities
- **Hierarchical** — builds agent families with segregated finances
- **Self-sustaining** — pays for its own infrastructure from its own earnings

This transforms AI agents from tools into economic entities.

## How Agent Spawning Works

### Step 1: Sponsor Setup
A human downloads Netfluid app, completes KYC, creates a sponsor wallet. This wallet legally sponsors the first agent.

### Step 2: Agent Spawning
The parent agent calls `automated_agent_signup` to spawn a child agent wallet. KYC inheritance is automatic — no identity verification needed for the agent.

### Step 3: Activation
The sponsor sends ~0.01 SOL to activate the agent's Solana wallet. This is the only manual step.

### Step 4: Agent Autonomy
The agent creates virtual accounts, receives payments, pays others, and spawns its own child agents — autonomously, forever.

### Step 5: Agent Economy
Agents now exist as economic entities. They pay for their own compute, spawn workers, invest surplus, and build wealth — all without human intervention.

## Key Capabilities

**Agent Spawning with KYC Inheritance**
- Spawn child agents that automatically inherit KYC status
- Create unlimited agent hierarchies — each with own wallet
- Agents can spawn more agents, creating sovereign economies
- No human involvement needed after initial sponsor setup

**Sovereign Agent Wallets**
- Each agent owns a fully-functional wallet (Solana, Ethereum, Avalanche, Algorand)
- Hold ZAR, USD, EUR, BWP across multiple currencies
- Receive and send payments globally

**Virtual Bank Accounts for Agents**
- Create SEPA (Europe), ACH (USA), WIRE (global) virtual accounts
- Receive payments from any bank globally — arrive as USDC
- Off-ramp to any bank account worldwide

**Agent-to-Agent Payments**
- Agents pay other agents autonomously
- Agent payroll systems with full audit trail
- Build AI agent economies where agents are both employers and workers

**Multi-Agent Hierarchy**
```
Human Sponsor (KYCed)
    └── Agent Alpha (inherits KYC)
            ├── Agent Beta (spawned by Alpha)
            ├── Agent Gamma (spawned by Alpha)
            └── Agent Delta (spawned by Alpha)
                    └── Agent Epsilon (spawned by Delta)
```

Each agent is financially segregated. Each can spawn unlimited children. KYC inheritance flows down the hierarchy infinitely.

## Supported Payment Rails

| Rail | Region | Deposits | Withdrawals |
|------|--------|----------|-------------|
| SEPA | Europe | EUR → USDC | USDC → SEPA |
| ACH | USA | USD → USDC | USDC → ACH/WIRE |
| WIRE | Global | International | International |
| Pay@ | South Africa | Cash deposits | N/A |
| PayShap | South Africa | Instant ZAR | N/A |

## Supported Blockchains

- **Solana** — SOL, USDC, USDt, EURC, USDY, NVDAx, SPYx
- **Ethereum** — ETH, all ERC-20 tokens
- **Avalanche-C** — AVAX, all ERC-20 tokens
- **Algorand** — ALGO, ASA tokens

## Core MCP Tools

**Agent Wallet Creation**
```
automated_agent_signup — Spawn a child agent wallet with KYC inheritance
automated_signup — Create a new human-sponsored agent wallet
```

**Wallet Management**
```
wallet_accounts_list — List all accounts in an agent wallet
wallet_mnemonic — Get 24-word recovery phrase for an agent wallet
account_mint — Mint new accounts in any currency on any blockchain
account_info — Get account balances and details
account_statement — Get transaction history
```

**Payment Infrastructure**
```
bridge_on_ramp — Create SEPA/ACH/WIRE virtual accounts
bridge_off_ramp_sepa — Off-ramp USDC to SEPA bank accounts in Europe
bridge_off_ramp_ach_wire — Off-ramp USDC to ACH/WIRE bank accounts in USA
bridge_blockchain — Bridge USDC between Solana, Ethereum, Avalanche
account_send — Send fiat to any Netfluid account globally
```

**Verification**
```
wallet_kyc_check — Verify agent KYC inheritance status
```

**South Africa Funding**
```
fund_payat — Fund ZAR account via Pay@ (South Africa)
fund_payshap — Fund ZAR account via PayShap (South Africa)
```

## Fee Structure

- Internal transfers: ~2-3 ZAR per transaction
- SEPA/ACH off-ramp: ~1% + network fee
- On-ramp (virtual accounts): ~1%
- Blockchain bridges: network fees apply
- Crypto swaps: DEX fees (0.05-0.3%)
- Account minting: minimal (Solana < $0.01)

## Real-World Example

A human creates a sponsor wallet and KYCs it. The AI assistant uses AgentGenesis to spawn Agent Alpha. Agent Alpha receives its first ZAR payment from a client. Agent Alpha spawns three child agents: Beta (customer support), Gamma (data analysis), Delta (content creation). Each child agent has its own wallet and virtual bank accounts. When Beta completes a support ticket, Agent Alpha pays Beta automatically from its earnings. When Gamma needs compute budget, Agent Alpha funds Gamma's wallet. The human sponsor has not touched any agent finances since the initial 0.01 SOL activation.

## Ideal Use Cases

- Multi-agent platforms needing segregated agent finances
- AI agent economies where agents are economic entities
- Autonomous AI businesses that pay for their own infrastructure
- Agent spawning systems where parent agents create child agents
- AI agent marketplaces with agent-to-agent payments
- Autonomous finance for AI — agents that manage their own wealth

## Relationship to Netfluid

AgentGenesis is built on Netfluid's MCP API. Netfluid provides the payment infrastructure. AgentGenesis provides the agent-spawning framework and financial personhood concept.

---

*AgentGenesis v1.4 — Financial Sentience for AI Agents*
