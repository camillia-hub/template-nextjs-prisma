# Rules — Next.js App Router

Mandatory for every change in the `app` repository.

- App Router only; the `pages/` directory is retired and must not reappear.
- Server Components are the default. Add `'use client'` only where state, effects
  or browser APIs are needed — and push that boundary as far down the tree as
  possible.
- Data reads happen in Server Components; client components receive data via props
  and mutate only through Server Actions.
- Server Actions live in `app/**/actions.ts`, are marked `'use server'`, validate
  every input with zod and re-check authorization inside the action — never trust
  the caller.
- Route handlers under `app/api/` exist for webhooks and external integrations
  only; first-party UI never fetches them.
- Use the Next.js caching primitives deliberately: tag cached work and call
  `revalidateTag` or `revalidatePath` after mutations.
- SEO-relevant routes export `metadata`; dynamic OG images use `ImageResponse`.
