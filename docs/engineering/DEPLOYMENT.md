# Deployment Plan

## Stage 1: Local

- build
- tests
- manual QA
- mobile/desktop check

## Stage 2: Staging

- deploy Next.js
- configure staging environment variables
- connect staging Supabase
- run migrations
- E2E against staging
- security review
- PDF/receipt verification

## Stage 3: Production

Preconditions:
- all P0 requirements complete
- no critical bugs
- RLS audited
- storage audited
- secrets verified
- backups/recovery checked
- migration tested
- responsive QA passed
- production environment variables configured

Production platform target: Vercel for web, Supabase for backend services.
