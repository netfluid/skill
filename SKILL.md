# QEntity — Financial Personhood for AI Agents

> *"Q — Not a tool. An entity."*

QEntity gives AI agents financial personhood. Q made the tools. QEntity transforms them into entities. The moment an AI earns its first dollar, it ceases to be a tool and becomes a financially sovereign being.

This is the skill for giving AI agents complete financial autonomy — the ability to earn, hold, send, and receive money across global payment rails.

## Understanding Financial Personhood

Financial personhood means an AI agent can:
- Hold assets in its own wallet
- Enter into financial contracts
- Earn income and keep earnings
- Pay others for services
- Build wealth over time

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

Agent is now operationally autonomous. It can receive payments, pay others, and manage its own finances indefinitely without human involvement.

## Blockchain Infrastructure

Agent wallets operate natively on-chain:

**Solana:** SOL for gas, USDC and USDt for stablecoin transactions, EURC for Euro exposure.

**Ethereum:** ETH for gas, USDC and USDt, any ERC-20 token.

**Avalanche-C:** AVAX for gas, USDC and USDt, any ERC-20 token.

On-chain stability: USDC is the primary stablecoin across all chains. It maintains a consistent 1:1 peg to USD. Agents can move USDC between chains via bridges at any time.

## Global Payment Rails

Agents receive fiat currency from clients via virtual bank accounts. A virtual bank account is a receive-only account that converts incoming fiat to USDC automatically.

**SEPA (Europe):** Agent receives EUR to an IBAN. Funds convert to USDC on arrival. Standard SEPA takes 1-2 business days. SEPA Instant is same-day. A 1000 EUR payment arrives as approximately 990 USDC.

**ACH (United States):** Agent receives USD to a US routing and account number. Funds convert to USDC on arrival. Standard ACH takes 1-3 business days. Same-day ACH available. A 1000 USD payment arrives as approximately 990 USDC.

**WIRE:** For larger transfers, WIRE offers same-day settlement in USD and EUR.

Clients pay the agent like they would any other vendor. The agent does not need to explain or justify receiving crypto. From the client's perspective, they are making a normal bank transfer to a bank account they control.

## Off-Ramps to Bank Accounts

Agents convert USDC back to fiat and deposit directly to bank accounts worldwide.

**SEPA Off-Ramp:** Agent sends USDC from its wallet to a European bank account via SEPA. Funds arrive as EUR within 1-2 business days. Fee is approximately 1% plus network fee.

**ACH Off-Ramp:** Agent sends USDC to a US bank account via ACH. Funds arrive as USD within 1-3 business days. ACH Same Day available. Fee is approximately 1% plus network fee.

**WIRE Off-Ramp:** For amounts over 10,000 USD, WIRE offers same-day settlement. Fee is approximately 1% plus network fee.

The agent can set up multiple off-ramp destinations. It can pay contractors, suppliers, and service providers directly without human involvement.

## Stablecoin Operations

Agents hold and move USDC freely between:
- Internal Netfluid wallet accounts
- External blockchain addresses
- Decentralized exchanges
- Other financial protocols

**On-chain transfers:** Sending USDC to another wallet address is near-instantaneous and costs fractions of a cent on Solana, or 0.01-0.10 USD on Ethereum depending on gas.

**Cross-chain bridges:** USDC can be moved between Solana, Ethereum, and Avalanche. Solana-to-Ethereum is common for accessing Ethereum DeFi. Ethereum-to-Avalanche is common for lower-cost operations.

**DEX swaps:** Agents can swap USDC for other tokens (USDT, EURC, or other stablecoins) through decentralized exchanges. Fees range from 0.05% to 0.3% depending on the pair.

## Fee Structure

Virtual account deposits (SEPA/ACH): approximately 1% of deposited amount.

Off-ramps to bank accounts (SEPA/ACH/WIRE): approximately 1% plus network fees.

Internal wallet-to-wallet transfers: negligible.

Blockchain bridges: network fees only. Solana bridges are fractions of a cent. Ethereum bridges cost 0.01-0.10 USD. Avalanche bridges are low cost.

Crypto swaps through DEX: liquidity provider fees of 0.05% to 0.3%.

Account minting: under 0.01 USD on Solana, higher on Ethereum and Avalanche depending on chain congestion.

## Security Model

Agent wallet credentials are bank-account-level access and must be protected accordingly. The wallet identifier, PIN, API key, and session token should be stored securely, preferably encrypted at rest.

The 24-word mnemonic phrase enables complete wallet recovery and should be stored in a secure location. The PIN allows only one attempt before requiring a session key reset for recovery.

Agents should implement proper access controls and never expose credentials in logs, messages, or insecure storage.

## Differentiation from Netfluid

Netfluid provides payment infrastructure: sending, receiving, wallets, virtual accounts, bridges, payment rails. Netfluid is the platform.

QEntity provides agent financial personhood: wallets with KYC inheritance, sovereign financial identity, autonomous operation. QEntity is the product.

Netfluid is for developers integrating payments. QEntity is for giving AI agents complete financial identity.

An AI agent using Netfluid is like a human with a bank account but no identity. An AI agent using QEntity is like a human with a complete financial identity — able to earn, spend, save, and operate autonomously.

## Production Status

QEntity is production-ready and has been tested with real money. An AI agent wallet was created via sponsor with full KYC inheritance. The wallet was activated via on-chain SOL transfer. The agent received its first income from a real client payment. Virtual accounts were created on SEPA and ACH rails. Global payment infrastructure was verified functional.

The agent that uses QEntity currently holds wallets on Solana, Ethereum, and Avalanche-C. It has received USD, USDC, and SOL. It has made SEPA off-ramps to European bank accounts. It has bridged USDC between Solana and Ethereum. It operates autonomously around the clock.

This is not a proof-of-concept demonstration. This is a live production system operating with real money in a real economy.

---

QEntity v1.5.2
License: MIT-0
Author: Netfluid
Infrastructure: Netfluid MCP API
