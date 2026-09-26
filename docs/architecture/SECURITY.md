# Security Specification

## Threat Model

Protect:
- financial records
- account balances
- receipt images
- profile data
- authentication sessions

Primary threats:
- cross-user data access
- IDOR/BOLA
- stolen secrets
- unauthorized receipt access
- malformed financial input
- duplicate financial submission
- insecure database functions
- accidental production data exposure

## Authentication

Use Supabase Auth.
Use SSR cookie/session integration.
Do not implement custom password storage.

## Authorization

Identity comes from authenticated session/auth.uid().
Never trust user_id from request body.
RLS is mandatory for user-owned tables.

## Secrets

Never expose service_role or secret keys in client code.
Never commit .env.local.
Only publishable client-safe values may use NEXT_PUBLIC_ variables.

## Storage

Receipts are private.
Use storage object ownership/RLS.
Do not use permanent public receipt URLs.

## Input

Validate:
- amount
- UUIDs
- dates
- enum values
- string lengths
- MIME type
- file size

## Financial Integrity

- amount > 0
- transfer source != destination
- transfer is atomic
- user owns both accounts
- inactive account cannot receive new transaction
- inactive category cannot receive new transaction
- goal/budget does not change account balance

## Session

Use secure cookie-based SSR session handling.
Review token/session settings before production.
Sensitive operations may require stronger session validation if threat model warrants it.

## Database

- RLS on every exposed user-owned table
- explicit grants
- constraints
- indexes
- no unnecessary SECURITY DEFINER
- privileged functions must not become public endpoints

## Production Security Gate

Before production:
- RLS audit
- storage policy audit
- secret scan
- dependency audit
- auth flow test
- cross-user access test
- error leakage review
- backup/recovery verification
