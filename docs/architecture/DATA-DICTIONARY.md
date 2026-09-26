# Data Dictionary

| Field | Meaning |
|---|---|
| opening_balance | Balance at the moment an account is created |
| amount | Positive financial quantity |
| transaction.type | income or expense |
| transfer | Movement between two owned accounts |
| is_active | Whether an account/category can be used for new records |
| target_amount | Goal target |
| contribution | Progress record, not an account transfer |
| period_start/end | Budget calculation window |
| hide_balances | UI privacy preference |
| storage_path | Private receipt object path |

## Money

Use integer bigint for IDR. Never use floating point for stored financial amounts.

## Dates

Use date for transaction/budget/goal dates.
Use timestamptz for event/audit timestamps.
