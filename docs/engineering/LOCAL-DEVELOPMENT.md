# Local Development

## Goal

Develop and test without touching production data.

## Flow

Local Next.js + local Supabase -> tests -> staging -> production.

## Setup

1. Install Node.js LTS.
2. Install pnpm.
3. Install Supabase CLI.
4. Clone repository.
5. Install dependencies.
6. Start local Supabase.
7. Copy .env.example to .env.local.
8. Apply migrations.
9. Seed local data.
10. Start Next.js.

Expected app:
http://localhost:3000

## Commands

Use `--help` on the installed Supabase CLI before relying on command syntax because CLI commands change over time.

Never put production secrets in local development.
