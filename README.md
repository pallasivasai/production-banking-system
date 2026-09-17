# Production Banking System

A free, hands-on production-style banking learning project built with React, Supabase PostgreSQL, Auth, Realtime, RLS and Edge Functions.

## Goals
- Learn secure relational database design
- Implement authenticated banking operations
- Practice atomic money transfers and transaction history
- Use Row Level Security (RLS)
- Use Supabase Realtime for live balance/transaction updates
- Build server-side business logic with Edge Functions
- Maintain schema with SQL migrations
- Connect everything to GitHub with reproducible development workflows

## Planned architecture
```text
React + Vite
     |
Supabase Auth
     |
PostgreSQL + RLS
     |
Edge Functions
     |
Realtime + Audit Logs
```

## Development rules
- No real banking or payment credentials.
- Use fictional users and balances only.
- Never commit secrets, `.env` files, service-role/secret keys, or passwords.
- Client applications use publishable keys with RLS enabled.
- Sensitive server-side operations stay in Edge Functions.

## Current Supabase project
The learning project is connected to the existing Supabase project used for database practice. Existing `emp` and `lop_attendance` tables are preserved and will not be repurposed for banking data.

## Roadmap
1. Database schema
2. Auth and profiles
3. Accounts and balances
4. Atomic transfers
5. Transaction ledger
6. RLS security
7. Realtime updates
8. Audit logging
9. Edge Functions
10. Frontend dashboard
11. Testing and documentation
