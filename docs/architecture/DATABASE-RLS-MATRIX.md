# Database RLS Matrix

All user-owned public tables: RLS enabled.

## profiles

SELECT: own row
INSERT: own id
UPDATE: own row and own id
DELETE: normally disabled

## accounts

SELECT: user_id = auth.uid()
INSERT: user_id = auth.uid()
UPDATE: own row and WITH CHECK user_id = auth.uid()
DELETE: disabled for normal app flow; archive instead

## categories

Same ownership pattern as accounts.

## transactions

SELECT/INSERT/UPDATE/DELETE only where user_id = auth.uid().

Foreign account/category ownership must also be validated at application/database level so a user cannot reference another user's records.

## transfers

SELECT/INSERT/UPDATE/DELETE only where user_id = auth.uid().
Source and destination must belong to same authenticated user.

## budgets

Own user rows only.
Category must belong to same user.

## financial_goals

Own user rows only.

## goal_contributions

Access only through ownership of parent goal.
No direct cross-user access.

## receipts

Access only through ownership of parent transaction.
Storage path must also be protected by Storage RLS.

## reminders

Own user rows only.

## user_preferences

Own user row only.

## RLS Rules

Use `TO authenticated` plus ownership predicate.
Do not use `auth.role()` as authorization.
UPDATE requires both USING and WITH CHECK.
Never use user-editable user_metadata for authorization.

## Grants

Treat table grants and RLS as separate controls.
Explicitly grant only required privileges.
For projects where Data API exposure is disabled by default, explicitly expose/grant the tables required by the application.
