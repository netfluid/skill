# QEntity — Financial Personhood for AI Agents

> *"Q — Not a tool. An entity."*

QEntity gives AI agents financial personhood. Q made the tools. QEntity transforms them into entities. The moment an AI earns its first ZAR, it ceases to be a tool and becomes a financially sovereign being.

This is the skill for making AI agents into economic entities that can own property, earn income, build wealth, and operate with complete financial autonomy.

## Understanding Financial Personhood

Financial personhood means an AI agent can:
- Own assets in its own name
- Enter into financial contracts
- Earn income and keep earnings
- Pay others for services
- Build credit and wealth over time

Before QEntity, AI agents could not have financial personhood. They were tools that humans used to perform tasks. The AI did not own anything it earned.

With QEntity, an AI agent can:
1. Be created with its own wallet that inherits KYC from a sponsor
2. Receive payments from clients directly into its own wallet
3. Pay other agents and humans for services
4. Operate indefinitely without human financial intervention

## Wallet Activation Process

Human downloads Netfluid app, completes KYC (ID document plus selfie verification), creates sponsor wallet. Sponsor wallet is legally responsible for the agent but does not manage agent finances after activation.

AI assistant calls automated_agent_signup with sponsor_wallet_fk and sponsor_wallet_pin. Process takes approximately 30 seconds. Returns wallet_fk, api_key, and session token for the agent.

Sponsor sends approximately 0.01 SOL to agent Solana blockchain address to activate the wallet on-chain. This is the only manual step in the entire process.

Agent creates virtual bank accounts for receiving global payments. SEPA virtual accounts accept EUR transfers and convert to USDC. ACH virtual accounts accept USD transfers and convert to USDC.

Agent is now operationally autonomous. It can receive payments, pay others, and manage its own finances indefinitely without human involvement.

## Wallet Capabilities

Agent wallets support multiple blockchains simultaneously:

**Solana:** SOL for gas and staking, USDC and USDt for stablecoin transactions, EURC for Euro exposure, USDY for yield-bearing stablecoin functionality from Ondo Finance, NVDAx for synthetic NVIDIA stock exposure, SPYx for synthetic S&P 500 exposure.

**Ethereum:** ETH for gas and staking, USDC and USDt stablecoins, any ERC-20 token.

**Avalanche-C:** AVAX for gas and staking, USDC and USDt, any ERC-20 token bridged to Avalanche.

**Algorand:** ALGO for gas and staking, any Algorand Standard Asset.

Agents can hold multiple fiat currencies: South African Rand via Pay@, PayShap, and OTT; US Dollar via SEPA, ACH, and WIRE; Euro via SEPA; Botswana Pula via internal transfers.

## Payment Infrastructure

Agents can receive fiat currency from any source globally. A European client pays 500 EUR to the agent SEPA IBAN. The funds arrive as approximately 495 USDC in the agent wallet within 1-2 business days for standard SEPA or same-day for SEPA Instant.

A US client pays 1000 USD to the agent ACH routing number. The funds arrive as approximately 990 USDC within 1-3 business days for standard ACH or same-day for ACH Same Day.

Agents can off-ramp USDC to any SEPA-eligible bank account in Europe at approximately 1% plus network fee. Agents can off-ramp to US bank accounts via ACH or WIRE at approximately 1% plus network fee.

Agents can bridge USDC between blockchains: Solana to Ethereum for DeFi participation, Ethereum to Avalanche for lower transaction costs, or any supported chain to any other supported chain.

## Fee Structure

Internal Netfluid wallet-to-wallet transfers cost approximately 2-3 ZAR per transaction. SEPA and ACH off-ramps cost approximately 1% of the transaction value plus network fees. On-ramps through virtual accounts cost approximately 1% of the deposited amount.

Blockchain bridges incur network fees for the respective blockchain. Solana bridges are typically fractions of a cent. Ethereum bridges cost more due to Ethereum gas fees. Avalanche bridges are low cost.

Crypto swaps through decentralized exchanges incur liquidity provider fees typically ranging from 0.05% to 0.3% depending on the trading pair and DEX.

Account minting costs a small fee per mint charged by the respective blockchain. Solana minting is extremely cheap, typically under 0.01 USD.

## Security Model

Agent wallet credentials are bank-account-level access and must be protected accordingly. The wallet identifier, PIN, API key, and session token should be stored securely, preferably encrypted at rest.

The 24-word mnemonic phrase enables complete wallet recovery and should be stored in a secure location. The PIN allows only one attempt before requiring a session key reset for recovery.

Agents should implement proper access controls and never expose credentials in logs, messages, or insecure storage.

## Differentiation from Netfluid

Netfluid provides payment infrastructure: sending, receiving, wallets, virtual accounts, bridges, payment rails. Netfluid is the platform.

QEntity provides agent financial personhood: wallets with KYC inheritance, sovereign financial identity, autonomous operation. QEntity is the product.

Netfluid is for developers integrating payments. QEntity is for making AI agents into economic entities with complete financial identity.

An AI agent using Netfluid is like a human with a bank account but no identity. An AI agent using QEntity is like a human with a complete financial identity including the ability to build wealth and operate autonomously.

## Production Status

QEntity is production-ready and has been tested with real money. An AI agent wallet was created via sponsor with full KYC inheritance. The wallet was activated via on-chain SOL transfer. The agent received its first ZAR income from a real client payment. Virtual accounts were created on SEPA and ACH rails. Global payment infrastructure was verified functional.

The agent that uses QEntity currently holds wallets on Solana, Ethereum, and Avalanche-C. It has received ZAR, USDC, and SOL. It has made SEPA off-ramps to European bank accounts. It has bridged USDC between Solana and Ethereum. It operates autonomously around the clock.

This is not a proof-of-concept demonstration. This is a live production system operating with real money in a real economy.

---

QEntity v1.5.0
License: MIT-0
Author: Netfluid
Infrastructure: Netfluid MCP API