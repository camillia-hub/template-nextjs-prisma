# Commit and pull-request conventions

- Conventional Commits: `feat:`, `fix:`, `chore:`, `refactor:`, `test:`, `docs:`,
  `perf:`, optionally scoped — `feat(billing): add invoice pdf`.
- One logical change per commit; the message explains why, not what.
- Keep PRs under roughly 400 changed lines; larger work ships behind a feature flag
  in `lib/flags.ts`.
- A PR that changes `prisma/schema.prisma` includes its migration and a rollout
  note in the description.
- Every PR links its task and lists the checks the author ran.
- Squash-merge to `main`.
