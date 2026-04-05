# Netfluid — AI Agent Banking & Global Payments

**Version:** 6.96.0  
**Author:** Netfluid  
**Website:** https://netfluid.io  
**Support:** support@netfluid.io  
**Repository:** https://github.com/netfluid/skill  

---

## Overview

Netfluid enables AI agents to manage fiat and crypto finances — open virtual bank accounts, send/receive global payments, and manage crypto wallets.

### Capabilities

- **Virtual bank accounts** in USD, ZAR, EUR
- **Global payments** via SEPA, ACH, WIRE
- **Crypto wallet** management (USDC, USDT, SOL, ETH)
- **On/off-ramp** between fiat and crypto
- **Multi-currency** support

---

## Installation

### ClawHub (Recommended)
```bash
npx clawhub@latest search netfluid
npx clawhub@latest install netfluid
```

### Git Clone
```bash
git clone https://github.com/netfluid/skill.git
```

---

## Required Credentials

| Credential | Source | Purpose |
|------------|--------|---------|
| `api_key` | Netfluid App → Settings → API Keys | Authentication |
| `session_key` | Netfluid App (one-time use) | Get session token |
| `wallet_fk` | From `/wallet/accounts_list` | Wallet ID |
| `account_fk` | From `/wallet/accounts_list` | Account ID |

### Getting Started

1. **Get API Key**: App → Settings → API Keys
2. **Get Session Key**: From Netfluid app (single use)
3. **Exchange**: Use `mcp_netfluid_session` with session_key
4. **List Accounts**: Use `mcp_netfluid_wallet_accounts_list`

---

## Available Tools

### Account Operations
- `mcp_netfluid_wallet_accounts_list` - List accounts
- `mcp_netfluid_account_info` - Get balance
- `mcp_netfluid_account_send` - Send fiat

### Crypto Operations
- `mcp_netfluid_crypto_balance` - Crypto balance
- `mcp_netfluid_crypto_spend` - Send crypto
- `mcp_netfluid_crypto_swap` - Swap tokens

### Funding & Withdrawals
- `mcp_netfluid_fund_banks` - Bank transfer details
- `mcp_netfluid_withdraw_to_bank` - Bank withdrawal
- `mcp_netfluid_fund_payat` - Pay@ (South Africa)
- `mcp_netfluid_fund_payshap` - PayShap (South Africa)

### Bridges
- `mcp_netfluid_bridge_on_ramp` - Virtual account (SEPA/ACH)
- `mcp_netfluid_bridge_off_ramp_sepa` - SEPA off-ramp
- `mcp_netfluid_bridge_off_ramp_ach_wire` - ACH/Wire off-ramp

### Utilities
- `mcp_netfluid_wallet_kyc_check` - KYC status
- `mcp_netfluid_wallet_fee` - Transaction fee
- `mcp_netfluid_wallet_verify` - Keep session alive

---

## Supported Networks

| Blockchain | Token |
|------------|-------|
| Solana | SOL, USDC, USDT |
| Ethereum | ETH, USDC, USDT |
| Avalanche-C | AVAX, USDC, USDT |

### Fiat Currencies
- **ZAR** - South African Rand
- **USD** - US Dollar
- **EUR** - Euro

---

## Security Rules

⚠️ **ALWAYS** confirm transactions with user before execution

⚠️ Credentials are **transient** - request fresh session keys as needed

⚠️ Never create/redeem voucher from same wallet

---

## Error Handling

| Error | Action |
|-------|--------|
| `token invalid` | Get new session_key |
| `insufficient funds` | Check balance |
| `invalid address` | Verify blockchain address |

---

## License

Copyright © 2026 Netfluid. MIT License.
