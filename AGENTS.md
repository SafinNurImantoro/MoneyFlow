# MoneyFlow Agent Instructions

## Mission

Build MoneyFlow according to the repository documentation. Prefer correctness, security, simplicity, and maintainability over speed.

## Mandatory Reading

Before changing code, read:

1. README.md
2. docs/product/PRD.md
3. docs/architecture/SYSTEM-ARCHITECTURE.md
4. docs/architecture/DATABASE-DESIGN.md
5. docs/architecture/SECURITY.md
6. docs/engineering/TESTING-STRATEGY.md
7. relevant ADR files

## Rules

- Never invent product requirements when documentation already defines them.
- Never expose service_role or secret keys to the browser.
- Never trust user_id supplied by the client for authorization.
- Authorization identity comes from the authenticated session.
- Every user-owned table must be protected by RLS.
- Do not disable RLS to fix an application bug.
- Do not use user-editable user_metadata for authorization.
- Do not store financial amounts as floating point.
- Amounts must be positive. Transaction type determines whether the amount adds or subtracts.
- Transfers are separate from income/expense.
- A transfer must not change total wealth.
- Source and destination accounts must differ.
- Archived accounts/categories cannot be used for new records.
- Goals and goal contributions do not automatically move money between accounts.
- Budget usage is calculated from transactions, not stored as an authoritative mutable counter.
- Preserve historical transactions when accounts/categories are archived.
- Receipt storage is private.
- Do not add AI to MVP unless the product scope is explicitly changed.
- Do not deploy production while local/staging quality gates are failing.

## Code Style

- TypeScript strict mode.
- Prefer small, composable modules.
- Validate external input with Zod.
- Keep financial business rules in domain/application logic, not UI components.
- Prefer server-side data access for sensitive operations.
- Use accessible semantic HTML.
- Avoid unnecessary client components.
- Keep components focused.

## Database

Schema changes must use migrations.
Never edit production manually as the normal workflow.
Every schema change needs:
- migration
- constraints
- relevant indexes
- RLS policy review
- tests
- documentation update when behavior changes

## Testing

For financial logic, write unit tests first.
For database authorization, write integration/security tests.
For critical user flows, write Playwright E2E tests.

## Git

Use:
- main
- develop
- feature/*
- fix/*

Commit prefixes:
- feat:
- fix:
- test:
- refactor:
- docs:
- chore:

## Stop Conditions

Stop and ask for clarification if a requested change conflicts with:
- financial invariants
- security model
- RLS ownership
- product scope
- documented architecture
