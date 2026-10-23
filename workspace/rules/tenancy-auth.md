# Rules — tenancy and authentication

- Authentication is owned by the auth setup in `auth.ts` (Auth.js with the Prisma
  adapter). Do not hand-roll sessions, tokens or password storage.
- Every request resolves the current tenant from the session; a user may act only
  on tenants they belong to. The tenant is never taken from a client-sent header,
  cookie or body field.
- Authorization uses the role on the membership (`owner`, `admin`, `member`,
  `viewer`); checks live in `lib/permissions.ts` and are called from Server Actions
  and route handlers.
- Secrets live in environment variables only: `.env.local` in development, the
  hosting platform's secret store in production. Never commit `.env*` files and
  never reference secrets in `next.config.*`.
- Webhook endpoints verify the provider signature before reading the body.
