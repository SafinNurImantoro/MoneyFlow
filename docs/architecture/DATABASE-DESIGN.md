# Database Design

All IDs use UUID.

All timestamps use timestamptz.
Money uses bigint integer minor units. For IDR, one stored unit represents one rupiah.

## profiles

id UUID PK -> auth.users.id
full_name text
avatar_url text nullable
created_at timestamptz
updated_at timestamptz

## accounts

id UUID PK
user_id UUID FK auth.users
name text
type text CHECK bank/cash/ewallet/other
currency_code text
opening_balance bigint CHECK >= 0
is_active boolean
created_at
updated_at

## categories

id UUID PK
user_id UUID FK auth.users
name text
type text CHECK income/expense
icon text nullable
color text nullable
is_active boolean
created_at
updated_at

## transactions

id UUID PK
user_id UUID FK auth.users
account_id UUID FK accounts
category_id UUID FK categories
type text CHECK income/expense
amount bigint CHECK > 0
transaction_date date
description text nullable
created_at
updated_at

## transfers

id UUID PK
user_id UUID FK auth.users
source_account_id UUID FK accounts
destination_account_id UUID FK accounts
amount bigint CHECK > 0
transfer_date date
description text nullable
created_at
updated_at
CHECK source != destination

## budgets

id UUID PK
user_id UUID FK auth.users
category_id UUID FK categories
period_start date
period_end date
amount bigint CHECK > 0
created_at
updated_at
CHECK period_start <= period_end

## financial_goals

id UUID PK
user_id UUID FK auth.users
name text
type text CHECK savings/purchase
target_amount bigint CHECK > 0
target_date date nullable
status text CHECK active/completed/archived
created_at
updated_at

## goal_contributions

id UUID PK
goal_id UUID FK financial_goals
amount bigint CHECK > 0
contribution_date date
note text nullable
created_at

## receipts

id UUID PK
transaction_id UUID FK transactions
storage_path text UNIQUE
file_name text
mime_type text
file_size bigint
created_at

## reminders

id UUID PK
user_id UUID FK auth.users
type text
title text
description text nullable
reminder_at timestamptz
repeat_rule text nullable
is_enabled boolean
created_at
updated_at

## user_preferences

user_id UUID PK -> auth.users
currency_code text
language text
theme text
hide_balances boolean
created_at
updated_at

## Balance Formula

opening_balance
+ income
- expense
- transfer_out
+ transfer_in

Transactions and transfers are authoritative financial records.
