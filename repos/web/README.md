# {{ projectName }} — Web

Next.js 15 (App Router) + Prisma 6 + PostgreSQL 16 monorepo for
**{{ projectName }}**: the web app, its Server Actions, the database schema and
the email worker.

## Layout

- `app/` — routes, layouts, Server Actions
- `prisma/` — schema and migrations
- `lib/` — data access, auth, tenancy helpers
- `tests/` — Vitest and Playwright suites

## Commands

```bash
pnpm install
pnpm dev
pnpm build
pnpm test
pnpm prisma migrate dev
```

The workspace contract (`repositories/app.md`) lists the build rules and the
quick checks the agent runs before calling a change done.
