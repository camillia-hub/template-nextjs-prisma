# Next.js + Prisma SaaS — Camillia workspace template

A Camillia Community Hub workspace template for teams building a multi-tenant SaaS
on Next.js App Router, Prisma and PostgreSQL.

## What's inside

The `workspace/` directory is the template's `.workspace` contract tree:

```
workspace/
  README.md                     workspace overview and agent navigation guide
  rules/
    app-router.md               Server Components, Server Actions, caching rules
    data-access.md              Prisma-only access, migrations, tenant filters
    tenancy-auth.md             authentication, sessions, roles, secrets
  conventions/
    naming.md                   route segments, files, models, branches
    testing.md                  Vitest, database tests, Playwright
    commits.md                  conventional commits and PR rules
  repositories/
    app.md                      monorepo descriptor: layout, pnpm commands
  business/
    glossary.md                 SaaS vocabulary skeleton
    rules.md                    numbered business rules skeleton
  architecture/
    components.md               system components and responsibilities
    decisions/README.md         ADR format and decision log
    decisions/0001-nextjs-prisma-monolith.md
  technical/constraints/
    versions.md                 pinned toolchain versions, Node runtime constraint
  ui/
    map.md                      App Router route map by shell and role
```

## How to use

Install from the Camillia Community Hub, then create a workspace from this
template. Camillia installs the `workspace/` tree as the new workspace's
`.workspace` contract: the agent reads these rules, conventions, repository
descriptors and docs skeletons before every task. After installation, replace the
`<Product>` placeholders, point the repository descriptor at your real repo and
adjust the pinned versions to your stack.

## License

MIT — see [LICENSE](LICENSE).
