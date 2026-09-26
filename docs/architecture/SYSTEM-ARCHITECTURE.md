# System Architecture

## Pattern

Modular Monolith.

## Layers

1. Presentation
2. Application
3. Domain
4. Infrastructure

## Runtime

Browser -> Next.js -> Application/Domain -> Supabase

## Presentation

React Server Components by default.
Client Components only when interaction/state requires them.

## Application

Use cases:
- createExpense
- createIncome
- createTransfer
- createAccount
- createBudget
- createGoal
- addGoalContribution
- generateReport

## Domain

Financial invariants live here and are tested independently.

## Infrastructure

Supabase Auth, PostgreSQL, Storage, and SSR session integration.

## Principle

The UI must not become the source of truth for financial rules.
