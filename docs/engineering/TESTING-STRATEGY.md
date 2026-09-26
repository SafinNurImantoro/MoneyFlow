# Testing Strategy

## Unit

Test pure financial calculations and validation.

Mandatory:
- balance formula
- budget percentage
- goal percentage
- transaction validation
- transfer validation

## Integration

Test:
- database constraints
- RLS
- ownership
- transaction CRUD
- transfer atomicity
- receipt access
- report queries

## E2E

Critical flows:
1. Register/login
2. Onboarding
3. Add account
4. Add expense
5. Add income
6. Transfer
7. Edit/delete transaction
8. Create budget
9. Create goal
10. Add contribution
11. Upload receipt
12. Export report
13. Sign out

## Quality Commands

pnpm lint
pnpm typecheck
pnpm test
pnpm test:e2e
pnpm build

## Financial Invariants

- income increases balance
- expense decreases balance
- transfer leaves total wealth unchanged
- goal contribution does not change account balance
- budget does not change account balance
- editing/deleting transaction recalculates balance
- cross-user access fails
