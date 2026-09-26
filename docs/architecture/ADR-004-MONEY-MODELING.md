# ADR-004: Money Modeling

Status: Accepted

Decision:
Store amounts as positive bigint integers. Transaction type determines direction.

Reason:
Avoid floating point errors and make financial invariants explicit.

Formula:
opening + income - expense - transfer_out + transfer_in
