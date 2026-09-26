# Base Wallet Tracker

A wallet intelligence dashboard concept for tracking addresses, token balances, transfers, and activity on Base.

## Project Goal

This project is designed as a Base-first wallet analytics dashboard. The focus is not trading signals; the focus is reading wallet behavior clearly: what changed, which contracts were touched, which tokens moved, and whether an address looks active, dormant, experimental, or high-risk.

## What It Explores

- Wallet transaction history
- Token balances and movement
- Address labels and watchlists
- Base explorer/RPC data patterns
- Practical wallet analytics UI

## Core Data Model

```txt
Wallet
  address
  label
  first_seen_at
  last_seen_at
  tags[]

Transaction
  hash
  block_number
  timestamp
  from
  to
  value
  method_id
  status

TokenBalance
  token_address
  symbol
  decimals
  raw_balance
  formatted_balance
  last_updated_at
```

## Planned Views

- Wallet overview
- Recent transactions
- Token exposure
- Contract interactions
- Activity timeline

## Technical Approach

1. Validate wallet addresses before any RPC/API call.
2. Fetch latest native ETH balance from Base RPC.
3. Resolve recent transactions through explorer or indexer APIs.
4. Normalize token balances by decimals.
5. Group activity by contract, token, and time window.
6. Present high-signal summaries before raw tables.

## UI Sections

| Section | Purpose |
| --- | --- |
| Overview | Balance, last activity, tx count, risk notes |
| Tokens | Token exposure and recent changes |
| Activity | Chronological transfers and contract calls |
| Contracts | Contracts touched by the wallet |
| Watchlist | Saved addresses for repeated checks |

## Roadmap

- Base RPC balance reader
- Address watchlist
- ERC-20 token table
- Recent transaction timeline
- Contract interaction grouping
- CSV export for wallet research

## Stack

- TypeScript
- React / Next.js
- Base RPC or explorer API
- Tailwind CSS

## Status

Learning build. Designed to become a clean dashboard for on-chain wallet reading.
