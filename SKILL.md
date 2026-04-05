Version: 6.96.0
# Netfluid — AI Agent Banking & Global Payments

**Purpose**: Enable AI agents to manage fiat and crypto finances - open bank accounts, send/receive global payments, manage crypto wallets
**Installation**: Clone https://github.com/netfluid/skill or install via ClawHub

---

## What This Skill Does

Netfluid gives AI agents financial capabilities:

- Open **virtual bank accounts** in USD, ZAR, EUR
- Send/receive **global payments** via SEPA, ACH, WIRE
- Manage **crypto wallets** (USDC, USDT, SOL, ETH)
- **On/off-ramp** between fiat and crypto
- Operate **24/7**

---

## 🔴 MANDATORY: Always ask for confirmation before executing any transaction

---

## Credentials Required

| Parameter | Source | Description |
|-----------|--------|-------------|
| `api_key` | Netfluid app → Settings → API Keys | Your API key |
| `token` | From session_key via `/session` | Session token (15 min TTL) |
| `wallet_fk` | From `/wallet/accounts_list` | Wallet ID |
| `account_fk` | From `/wallet/accounts_list` | Account ID |

**Note**: Credentials are used only for API calls, never stored permanently.

---

## Quick Start

### Step 1: Get Session Token
```python
# User provides session_key from Netfluid app
session_key = "netfluid_xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx"
# Call mcp_netfluid_session(session_key=session_key)
# Returns: {"token": "xxx...", "wallet_fk": 123, "expires_in": 900}
```

### Step 2: List Accounts
```python
mcp_netfluid_wallet_accounts_list(
    api_key="your_api_key",
    token="session_token",
    wallet_fk=123
)
# Returns: [{"account_fk": 12345, "account_address": "xxx", "currency": "ZAR", "type": "fiat"}]
```

### Step 3: Check Balance
```python
mcp_netfluid_account_info(
    api_key="your_api_key",
    token="session_token",
    account_fk=12345
)
# Returns: {"balance": 100.00, "account_address": "xxx"}
```

---

## Account Operations

### List Accounts
```python
mcp_netfluid_wallet_accounts_list(
    api_key="your_api_key",
    token="session_token",
    wallet_fk=123
)
```

### Account Balance
```python
mcp_netfluid_account_info(
    api_key="your_api_key",
    token="session_token",
    account_fk=12345
)
# Returns: {"balance": 100.00, "available": 100.00}
```

### Crypto Balance
```python
mcp_netfluid_crypto_balance(
    api_key="your_api_key",
    token="session_token",
    account_fk=12345
)
# Returns: {"tokens": {"USDC": 1.0}, "native": {"SOL": 0.1}}
```

### Send Fiat (Internal Transfer)
```python
mcp_netfluid_account_send(
    api_key="your_api_key",
    token="session_token",
    account_fk=12345,
    destination="recipient_account_address",
    amount=10.00,
    note="Payment"
)
```

---

## Crypto Operations

### Send Crypto
```python
mcp_netfluid_crypto_spend(
    api_key="your_api_key",
    token="session_token",
    account_fk=12345,
    asset_id="EPjFWdd5AufqSSqeM2qN1xzybapC8G4wEGGkZwyTDt1v",  # USDC on Solana
    destination="recipient_blockchain_address",
    amount=1.0,
    note="Transfer"
)
```

### Swap Tokens
```python
mcp_netfluid_crypto_swap(
    api_key="your_api_key",
    token="session_token",
    account_fk=12345,
    digital_asset_fk=1,  # From /crypto/digitalassets
    to_digital_asset_fk=2,
    amount=5.0
)
```

### List Supported Assets
```python
mcp_netfluid_crypto_digitalassets(api_key="your_api_key")
```

---

## Fund Account

### Bank Transfer
```python
mcp_netfluid_fund_banks(
    api_key="your_api_key",
    token="session_token",
    account_fk=12345
)
# Returns bank details with reference number
```

### Card Deposit
```python
# Step 1: Quote
mcp_netfluid_fund_card_quote(
    api_key="your_api_key",
    token="session_token",
    wallet_fk=123,
    account_fk=12345,
    amount=100
)

# Step 2: Execute (after user confirms)
mcp_netfluid_fund_card_recharge(
    api_key="your_api_key",
    token="session_token",
    wallet_fk=123,
    account_fk=12345,
    wallet_card_id="card_id",
    amount=100
)
```

### Pay@ (South Africa)
```python
mcp_netfluid_fund_payat(
    api_key="your_api_key",
    token="session_token",
    account_fk=12345,
    amount=100,
    reference="Payment"
)
```

### PayShap (South Africa - Instant)
```python
mcp_netfluid_fund_payshap(
    api_key="your_api_key",
    token="session_token",
    account_fk=12345
)
```

---

## Withdraw

### To Bank Account
```python
# Step 1: Save Bank Account
mcp_netfluid_wallet_rba(
    api_key="your_api_key",
    token="session_token",
    wallet_fk=123,
    beneficiary="Name",
    bank="Bank",
    iban="XX000000000000000000",
    swift="BANKXXXX",
    email="email@example.com",
    address_street="Street 1",
    address_city="City",
    address_zip="12345",
    countryISO2="XX"
)

# Step 2: Withdraw
mcp_netfluid_withdraw_to_bank(
    api_key="your_api_key",
    token="session_token",
    account_fk=12345,
    rba_fk=1,
    amount=50
)
```

### To OTT (South Africa)
```python
mcp_netfluid_withdraw_to_ott(
    api_key="your_api_key",
    token="session_token",
    account_fk=12345,
    quote_id="quote_id",
    mobile="27xxxxxxxxx"
)
```

---

## Bridges (Virtual Accounts)

### List Bridges
```python
mcp_netfluid_bridge_list(
    api_key="your_api_key",
    token="session_token",
    wallet_fk=123,
    account_fk=12345,
    transfer_type="on-ramp"
)
```

### Create On-Ramp (Virtual Account)
```python
mcp_netfluid_bridge_on_ramp(
    api_key="your_api_key",
    token="session_token",
    wallet_fk=123,
    account_fk=12345,
    blockchain="solana",
    address="your_solana_address",
    source_rail="sepa",
    currency="usdc"
)
```

### Create Off-Ramp
```python
# SEPA (Europe)
mcp_netfluid_bridge_off_ramp_sepa(
    api_key="your_api_key",
    token="session_token",
    wallet_fk=123,
    account_fk=12345,
    account_owner="Name",
    iban="DE00000000000000000000",
    iso3_country="DEU",
    iban_bic="BANKXXXX",
    entity_type="individual",
    address_line="Street 1",
    address_city="Berlin",
    address_state="Berlin",
    address_zipcode="10115",
    address_iso3_country="DEU",
    first_name="John",
    last_name="Doe"
)

# ACH/Wire (USA)
mcp_netfluid_bridge_off_ramp_ach_wire(
    api_key="your_api_key",
    token="session_token",
    wallet_fk=123,
    account_fk=12345,
    account_owner="Name",
    account_number="123456789",
    routing_number="123456789",
    address_line="123 Main St",
    address_city="New York",
    address_state="NY",
    address_zipcode="10001",
    address_iso3_country="USA"
)
```

### Cross-Chain Bridge
```python
mcp_netfluid_bridge_blockchain(
    api_key="your_api_key",
    token="session_token",
    wallet_fk=123,
    account_fk=12345,
    blockchain="ethereum",
    address="0x...",
    currency="usdc"
)
```

---

## Utilities

### Session Management
```python
# Keep session alive
mcp_netfluid_wallet_verify(
    api_key="your_api_key",
    token="session_token",
    wallet_fk=123
)
```

### KYC Status
```python
mcp_netfluid_wallet_kyc_check(
    api_key="your_api_key",
    token="session_token",
    wallet_fk=123
)
```

### Transaction Fee
```python
mcp_netfluid_wallet_fee(
    api_key="your_api_key",
    token="session_token",
    wallet_fk=123,
    amount=100
)
```

---

## Error Handling

| Error | Meaning | Action |
|-------|---------|--------|
| `token invalid` | Session expired | Get new session_key |
| `insufficient funds` | Balance low | Check balance |
| `invalid address` | Wrong address | Verify with `/crypto/verify` |
| `account locked` | Account paused | Contact support |

---

## Supported Networks

| Blockchain | Native Token | Stablecoins |
|------------|-------------|------------|
| Solana | SOL | USDC, USDT |
| Ethereum | ETH | USDC, USDT |
| Avalanche-C | AVAX | USDC, USDT |

### Fiat Currencies
- **ZAR** - South African Rand
- **USD** - US Dollar  
- **EUR** - Euro

---

## Security Notes

- Credentials are transient - request fresh session keys as needed
- All transactions require user confirmation
- Operations are logged by Netfluid API
- Recovery phrases are display-only, never transmitted
