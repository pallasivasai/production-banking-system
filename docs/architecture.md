# Banking System Architecture

## Current backend
- Supabase Auth for identity and sessions
- PostgreSQL for relational data
- Row Level Security for user-scoped access
- PostgreSQL function for atomic transfers
- Realtime-ready account and transaction tables
- GitHub as the source-control repository

## Core tables
- `banking_profiles`: application profile and role metadata
- `bank_accounts`: fictional bank accounts and balances
- `bank_transactions`: immutable-style transaction records with idempotency keys

## Transfer design
The `transfer_money` function locks both account rows, validates authorization/status/currency/balance, applies the debit and credit together, and records one transaction. The idempotency key prevents accidental duplicate processing.

## Security
- Client side must use a publishable Supabase key only.
- RLS is enabled on banking tables.
- Secret/service keys must never be shipped to the browser.
- Sensitive transfer logic is kept in database/server-side code rather than trusting client-side balance updates.

## Next implementation stages
1. Seed fictional test accounts through controlled server-side setup.
2. Add a protected Edge Function for transfer requests if needed by the frontend boundary.
3. Build React authentication and dashboard.
4. Subscribe to Realtime account/transaction changes.
5. Add automated tests and CI.
6. Add observability and operational documentation.
