# MoneyFlow Blueprint

MoneyFlow adalah aplikasi personal finance management yang dirancang untuk penggunaan pribadi sekaligus portfolio project.

## Status

**Blueprint: FINAL v1.0**

Blueprint ini menjadi sumber kebenaran sebelum implementasi kode.

## Product Goal

Membuat pencatatan pemasukan, pengeluaran, transfer, budget, dan target keuangan menjadi cepat, jelas, aman, dan nyaman digunakan dari mobile maupun desktop.

## Core Stack

- Next.js 16
- React
- TypeScript
- Tailwind CSS 4
- shadcn/ui
- Supabase PostgreSQL
- Supabase Auth
- Supabase Storage
- @supabase/ssr
- Zod
- React Hook Form
- Recharts
- Vitest
- Playwright
- pnpm
- GitHub
- Vercel untuk production

## Architecture

Modular Monolith.

Browser -> Next.js -> Application/Domain -> Supabase

## Development Order

1. Local setup
2. Auth
3. Accounts
4. Categories
5. Transactions
6. Transfers
7. Dashboard
8. Budgets
9. Goals
10. Receipts
11. Reports/PDF
12. Reminders
13. Full testing
14. Security review
15. Staging
16. Production

## Environment Rule

Localhost first. Jangan deploy production sebelum local dan staging lulus quality gate.

## Source of Truth

- Financial facts berasal dari transactions/transfers.
- Account balance dihitung dari opening balance + income - expense - transfer out + transfer in.
- Budget dan goal tidak mengubah saldo account.
- RLS adalah authorization boundary database.
