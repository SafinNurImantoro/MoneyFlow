# Testing Matrix

| Feature | Unit | Integration | E2E | Priority |
|---|---|---|---|---|
| Auth | Yes | Yes | Yes | P0 |
| Accounts | Yes | Yes | Yes | P0 |
| Categories | Yes | Yes | Yes | P0 |
| Expense | Yes | Yes | Yes | P0 |
| Income | Yes | Yes | Yes | P0 |
| Transfer | Yes | Yes | Yes | P0 |
| Balance | Yes | Yes | Yes | P0 |
| Budget | Yes | Yes | Yes | P1 |
| Goals | Yes | Yes | Yes | P1 |
| Receipt | - | Yes | Yes | P1 |
| Reports | Yes | Yes | Yes | P1 |
| Reminders | Yes | Yes | Yes | P2 |

## Security Tests

- user A cannot read user B account
- user A cannot modify user B transaction
- user A cannot access user B receipt
- client cannot assign another user_id
- archived account rejected for new transaction
- archived category rejected for new transaction
