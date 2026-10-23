# Testing conventions

- Vitest for unit and component tests, Testing Library for React components; tests
  live next to the unit they cover (`invoice.test.ts`, `InvoiceTable.test.tsx`).
- Database-touching tests run against a throwaway PostgreSQL schema via
  `pnpm test:db` and use the factories in `tests/factories/`.
- Every Server Action has at least one test for the happy path and one for an
  unauthorized caller.
- Playwright specs in `e2e/` cover the critical journeys: signup, invite member,
  create the core record, upgrade plan. They run in CI against a preview
  deployment.
- Before pushing: `pnpm lint`, `pnpm typecheck` and `pnpm test` pass, and
  `pnpm build` succeeds.
