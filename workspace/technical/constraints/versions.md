# Version constraints

| Component | Pinned version | Notes |
| --- | --- | --- |
| Node.js | 22 LTS | `.nvmrc` and CI. |
| Next.js | 15.x | App Router with React Server Components. |
| React | 19.x | Ships with Next.js 15. |
| TypeScript | 5.9.x | `strict: true`. |
| Prisma | 6.x | Client and CLI versions move together. |
| PostgreSQL | 16 | Same major version in dev, preview and production. |
| pnpm | 9.x | Lockfile committed; CI uses `pnpm install --frozen-lockfile`. |

Hosting constraint: the app deploys as a Node.js server (not the edge runtime)
because Prisma needs Node APIs. Node is the default runtime for every route; do not
switch a route to the edge runtime without removing its Prisma imports first.
