# SaaS workspace: Next.js + Prisma + PostgreSQL

This workspace builds **<Product>**, a multi-tenant SaaS application:

- `app` — a Next.js 15 (App Router) + Prisma 6 + PostgreSQL 16 monorepo that
  contains the web app, its Server Actions, the database schema and the email
  worker (see `repositories/app.md`).

## How the agent should navigate this workspace

Read in this order before your first task:

1. `rules/` — mandatory rules: `app-router.md` (where code runs), `data-access.md`
   (how the database is touched) and `tenancy-auth.md` (who may do what). Rules win
   over conventions when they conflict.
2. `conventions/` — naming, testing and commit style.
3. `repositories/app.md` — the monorepo layout and every build/test command. Run
   the quick check listed there before you call a change done.
4. `business/` — the SaaS vocabulary (`glossary.md`) and numbered business rules
   (`rules.md`); use these exact terms in code and copy.
5. `architecture/components.md` and `architecture/decisions/` — the system shape
   and the ADR log; add an ADR when you change something structural.
6. `technical/constraints/versions.md` — pinned versions and the Node-runtime
   constraint Prisma imposes.
7. `ui/map.md` — the App Router route map; keep it in sync when routes change.

When a task teaches you a durable fact about the domain, record it in
`business/glossary.md` or `business/rules.md` — not only in the task paper.
