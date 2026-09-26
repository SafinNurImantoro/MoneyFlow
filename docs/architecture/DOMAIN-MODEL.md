# Domain Model

## Entities

Profile
Account
Category
Transaction
Transfer
Budget
FinancialGoal
GoalContribution
Receipt
Reminder
UserPreference

## Relationships

User 1--N Accounts
User 1--N Categories
User 1--N Transactions
User 1--N Transfers
User 1--N Budgets
User 1--N Goals
Goal 1--N GoalContributions
Transaction 1--N Receipts
User 1--N Reminders
User 1--1 Preferences

## Key distinction

Transaction = income/expense.

Transfer = movement between owned accounts.

Budget = spending rule.

Goal = tracking target.

None of budget/goal contribution changes account balance automatically.
