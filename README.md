# The Profit - Malayalam News Portal Backend (Supabase / Postgres)

Postgres database schema, migrations, RLS security policies, and seed data for The Profit News Portal.

## Architecture & Schema
- Postgres 15+ on Supabase (ap-south-1 Mumbai)
- 37 news categories (20 top-level + 17 sub-categories)
- Full-text search with `pg_trgm` and `to_tsvector`
- Row-Level Security (RLS) on all 22 tables
- Razorpay payments and memberships webhook table

## Getting Started
```bash
# Install Supabase CLI
brew install supabase/tap/supabase

# Start local Supabase
supabase start

# Run migrations & seed data
supabase db reset
```

## Repository Structure
- `supabase/migrations/0001_init.sql`: Core schema, RLS policies, indexing, triggers
- `supabase/migrations/0002_auth_webhooks.sql`: Auth hooks & webhook idempotency
- `supabase/seed.sql`: 37 categories tree & default subscription plans
- `supabase/seed-articles.sql`: Test news articles
