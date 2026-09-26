# Edge Cases

## Transactions

- zero amount
- negative amount
- huge amount
- future date
- invalid date
- missing account
- archived account
- missing category
- archived category
- another user's account/category
- duplicate submit
- edit after account archive
- delete then report refresh

## Transfers

- same source/destination
- archived source
- archived destination
- cross-user account
- duplicate submit
- partial database failure
- insufficient balance if policy later requires it
- very large amount

## Budgets

- end before start
- zero amount
- overlapping periods
- category belongs to another user
- category archived after budget creation
- transaction crosses budget boundary
- exactly 80%
- exactly 100%

## Goals

- target zero
- contribution exceeds target
- completed goal receives contribution
- target date in past
- duplicate contribution

## Receipts

- unsupported MIME
- oversized file
- upload succeeds but metadata fails
- metadata exists but object missing
- unauthorized access
- filename/path traversal attempts

## Auth

- expired session
- invalid session
- duplicate registration
- reset token expired
- rate limit

## UX

Every critical screen must handle:
loading, empty, error, retry, success, validation.
