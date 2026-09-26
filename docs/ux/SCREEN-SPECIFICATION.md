# Screen Specification

## Auth

### Login
Purpose: authenticate.
Components: email, password, submit, forgot password, register link.
States: loading, validation error, auth error, success.

### Register
Fields: full name, email, password, confirmation.
Validation: email format, password strength, matching confirmation.

### Forgot Password
Field: email.
States: loading, submitted, error.

## Onboarding

Currency -> first account -> opening balance -> optional additional accounts -> dashboard.

## Home

Must show:
- greeting
- period
- total balance
- income
- expense
- net cash flow
- quick actions
- budget summary
- goal summary
- recent transactions

## Transactions

Features:
- search
- type filter
- account filter
- category filter
- date filter
- list
- detail
- edit
- delete

## Add Transaction

Shared fields:
- amount
- category
- account
- date
- description
- receipt for expense

## Accounts

List account cards and total balance.
Actions:
- create
- edit
- archive
- view detail

## Goals

Goal card:
- name
- type
- current
- target
- progress
- target date

Goal detail:
- contribution
- history
- complete

## Budgets

Budget card:
- category
- used
- limit
- percentage
- status

## Reports

Show:
- income
- expense
- net cash flow
- category breakdown
- monthly trend
- PDF export

## Settings

Profile, appearance, currency, notifications, categories, accounts, security, data/export.

## Required UI States

Every data screen must define:
- loading
- empty
- success
- validation error
- server error
- unauthorized/forbidden
- retry
