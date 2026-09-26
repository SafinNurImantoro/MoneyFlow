# Database Migration Workflow

1. Change schema locally.
2. Create a migration using the installed Supabase CLI workflow.
3. Review SQL.
4. Run locally.
5. Run tests.
6. Review constraints.
7. Review indexes.
8. Review RLS.
9. Run database security advisors where available.
10. Apply to staging.
11. Test staging.
12. Apply to production only after approval.

Migration files are version-controlled.
Never rely on undocumented manual production edits.
