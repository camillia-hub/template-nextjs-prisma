# Repository: app

| | |
| --- | --- |
| Name | `app` |
| Stack | Next.js 15 (App Router), React 19, TypeScript 5.9 (strict), Prisma 6, PostgreSQL 16 |
| Package manager | pnpm 9 on Node 22 |

## Layout

```
app/
  app/                  App Router routes, layouts, Server Actions
    (marketing)/        public pages
    (app)/              authenticated product shell
    api/                webhooks and external integrations only
  components/           shared UI components
  lib/                  db.ts, auth.ts, permissions.ts, flags.ts, utilities
  prisma/               schema.prisma, migrations/
  worker/               transactional email worker
  tests/                factories and database test setup
  e2e/                  Playwright specs
```

## Commands

| Task | Command |
| --- | --- |
| Install dependencies | `pnpm install` |
| Dev server (http://localhost:3000) | `pnpm dev` |
| Lint | `pnpm lint` |
| Type check | `pnpm typecheck` |
| Unit and component tests | `pnpm test` |
| Database tests | `pnpm test:db` |
| Create a migration | `pnpm prisma migrate dev --name <name>` |
| Apply migrations (deploy) | `pnpm prisma migrate deploy` |
| Production build | `pnpm build` |
| E2E tests | `pnpm e2e` |

Quick check before pushing:
`pnpm lint && pnpm typecheck && pnpm test && pnpm build`.
