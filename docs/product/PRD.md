# Product Requirements Document

## 1. Product

MoneyFlow

## 2. Problem

Personal financial records are often scattered across notes, chat messages, banking apps, or memory. Users need one place to understand money coming in, money going out, where money is stored, spending limits, and savings targets.

## 3. Target User

Primary: individual users managing personal finances.

Initial product owner/use case: Safin as a real user and portfolio project.

## 4. Goals

- Record expense in seconds.
- Record income easily.
- Track multiple money locations.
- Track transfers without double-counting.
- Understand current and monthly cash flow.
- Set budgets.
- Track savings/purchase goals.
- Attach receipts.
- Generate reports.
- Protect private financial data.

## 5. Non-goals for MVP

- Bank account synchronization.
- Investment portfolio management.
- Debt management.
- OCR receipt extraction.
- AI categorization.
- Financial advice/recommendations.
- Multi-user household finance.
- Complex accounting.
- Recurring transactions as a core MVP feature.

## 6. Accounts

Examples:
- SeaBank
- Dompet
- Toples

Supported types:
- bank
- cash
- ewallet
- other

Accounts are archived rather than normally deleted.

## 7. Transactions

Types:
- income
- expense

Amount must be > 0.

## 8. Transfers

Transfer has:
- source account
- destination account
- amount
- date
- description

Transfer is not an expense.

## 9. Budget

Budget is a spending limit.

Status:
- <80% normal
- 80-99% warning
- >=100% exceeded

Transactions remain allowed after exceeding budget.

## 10. Goals

Types:
- savings
- purchase

Goal tracks progress only. Goal contribution does not automatically move money.

## 11. Receipts

Attach image/reference to a transaction. Private storage.

## 12. Reminders

Types:
- bill
- budget
- goal
- recurring_transaction
- general

## 13. Dashboard

Must show:
- total balance
- income this month
- expense this month
- net cash flow
- budget summary
- goals
- recent transactions
- quick add

## 14. Success Metrics

- A user can record a simple expense with minimal interaction.
- Balance remains mathematically consistent after transaction changes.
- No cross-user data access.
- Critical E2E flows pass.
- App works on mobile and desktop.
- PDF report is generated correctly.
