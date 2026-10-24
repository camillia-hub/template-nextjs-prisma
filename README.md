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

Two payload areas have special meaning to the product rather than to the
workspace tree: `template.json` declares the expected repositories (see
[Template contract](#template-contract)), and `repos/` carries the seed
content the wizard applies to them (`web`).

## How to use

Install from the Camillia Community Hub, then create a workspace from this
template. Camillia installs the `workspace/` tree as the new workspace's
`.workspace` contract: the agent reads these rules, conventions, repository
descriptors and docs skeletons before every task. Where the workspace files
carry `{{ projectName }}` or `{{ orgName }}` tokens, they are substituted with
your project and organization names when the template is applied — no manual
placeholder hunt. After installation, point the repository descriptor at your
real repo and adjust the pinned versions to your stack.

## Template contract

`template.json` declares the repositories this product is made of; the
workspace wizard walks each one and offers to **create** a fresh repo at your
git provider or **load** an existing one:

| Key | Label | Description | Required | Override default |
|---|---|---|---|---|
| `web` | Web application | Next.js SaaS application | yes | no |

Seed content for each repo lives under `repos/<key>/` (a starter README and
`.gitignore`). Applying a seed to a repo that already has content requires the
"authorize content override" choice in the wizard; before anything is
overwritten the current branch heads are tagged
`camillia-backup/template-<yyyyMMdd-HHmmss>`, so existing work is never lost.

Replacement tokens — `{{ orgName }}`, `{{ projectName }}` and `{{ projectId }}`
— are substituted across all workspace-bound files at apply time. See the
[extension guidelines](https://github.com/camillia-hub/extension-guidelines)
for the full template contract.

## License

MIT — see [LICENSE](LICENSE).
