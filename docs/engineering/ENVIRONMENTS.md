# Environments

## Local

Purpose: development and automated testing.

Database: local Supabase.
Data: disposable seed data.

## Staging

Purpose: production-like QA.

Database: dedicated Supabase staging project.
Data: synthetic/non-sensitive test data.

## Production

Purpose: real user data.

Database: dedicated Supabase production project.
Secrets: production-only.
Backups and recovery verified.

## Rule

Never point local development at production.
