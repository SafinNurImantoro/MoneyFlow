# API Specification

## Auth

POST /api/auth/register
POST /api/auth/login
POST /api/auth/logout
GET /api/auth/me
POST /api/auth/forgot-password

## Accounts

GET /api/accounts
POST /api/accounts
GET /api/accounts/:id
PATCH /api/accounts/:id
POST /api/accounts/:id/archive

## Categories

GET /api/categories
POST /api/categories
PATCH /api/categories/:id
POST /api/categories/:id/archive

## Transactions

GET /api/transactions
POST /api/transactions
GET /api/transactions/:id
PATCH /api/transactions/:id
DELETE /api/transactions/:id

Query filters:
type, account_id, category_id, start_date, end_date, search.

## Transfers

GET /api/transfers
POST /api/transfers
GET /api/transfers/:id

## Dashboard

GET /api/dashboard?period=YYYY-MM

## Budgets

GET /api/budgets
POST /api/budgets
GET /api/budgets/:id
PATCH /api/budgets/:id
DELETE /api/budgets/:id

## Goals

GET /api/goals
POST /api/goals
GET /api/goals/:id
PATCH /api/goals/:id
POST /api/goals/:id/contributions
POST /api/goals/:id/complete

## Reports

GET /api/reports/monthly
GET /api/reports/categories
GET /api/reports/cash-flow

## Errors

{
  "error": {
    "code": "INVALID_AMOUNT",
    "message": "Amount must be greater than zero."
  }
}

## Rules

- Validate all external input.
- Authenticate before user-owned reads/writes.
- Never accept client-provided user_id as authority.
- Use idempotency for critical create operations where duplicate submission is possible.
- Keep financial mutations atomic.
