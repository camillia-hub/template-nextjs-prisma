# System components

```
+-------------------------------------------------+
| Next.js app (server + client components)        |
|  +- Server Components and Server Actions        |
|  +- Route handlers (webhooks, integrations)     |
+----------------------+--------------------------+
                       | Prisma
                       v
               +----------------+        +---------------+
               | PostgreSQL 16  |        | Email worker  | (transactional email)
               +----------------+        +---------------+
```

| Component | Where it lives | Responsibility |
| --- | --- | --- |
| Next.js app | `app` repository | UI, Server Actions, authentication, webhooks. |
| PostgreSQL | managed instance | System of record, reached only through Prisma. |
| Email worker | `worker/` in the same repo | Sends transactional email from the outbox table. |
| Billing provider | external SaaS | Subscriptions and invoices; events arrive by signature-verified webhook. |
