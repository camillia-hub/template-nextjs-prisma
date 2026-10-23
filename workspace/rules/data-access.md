# Rules — data access (Prisma + PostgreSQL)

- Prisma Client is the only database access path. No raw SQL except inside a
  migration file.
- `prisma/schema.prisma` is the source of truth. Schema changes always ship with a
  migration produced by `pnpm prisma migrate dev`; never hand-edit a migration
  after it has been applied anywhere.
- Every model carries `tenantId` except `Tenant` itself, and every query filters by
  the caller's tenant through the `forTenant` helper in `lib/db.ts`.
- Multi-write operations run inside `prisma.$transaction`.
- N+1 is a bug: use `include` and `select` deliberately; list pages must load in a
  constant number of queries.
- Migrations are additive within a release; drops land one release after the code
  stopped reading the column.
- One shared PrismaClient from `lib/db.ts`; never instantiate `PrismaClient` in
  feature code.
