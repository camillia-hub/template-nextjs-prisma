# Naming conventions

## Files and folders (App Router)

- Route segments are kebab-case (`app/billing/invoices/page.tsx`).
- Route files follow the Next.js conventions: `page.tsx`, `layout.tsx`,
  `loading.tsx`, `error.tsx`, `actions.ts`.
- Route-local code lives in private folders (`_components/`, `_lib/`); shared code
  lives in `components/`, `lib/` and `prisma/` at the repository root.
- Components are PascalCase (`InvoiceTable.tsx`); hooks are `useCamelCase.ts`;
  utilities are camelCase (`formatMoney.ts`).

## Database

- Models are PascalCase singular (`Invoice`); tables map to snake_case plural via
  `@@map("invoices")`; columns are camelCase mapped to snake_case.
- Enum values are lowercase snake_case.

## Git

- Branches: `<type>/<task-id>-<slug>` (`feat/231-invoice-export`).
- Commits and PR titles: Conventional Commits (see `conventions/commits.md`).
