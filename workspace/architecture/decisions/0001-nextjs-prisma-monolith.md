# ADR-0001: Next.js App Router monolith with Prisma and PostgreSQL

- Status: accepted
- Date: 2026-01-15

## Context

The SaaS needs fast product iteration with a small team, server-rendered marketing
pages and a rich authenticated app, without operating a separate API service on day
one.

## Decision

One Next.js App Router monolith holds UI, Server Actions and integrations. Prisma
over PostgreSQL 16 is the only data path. Background work (email) runs as a small
worker in the same repository, fed by a transactional outbox table.

## Consequences

One deployment unit, one type system end to end, minimal operational surface.
When a subsystem outgrows the monolith it is extracted along the `lib/` boundaries,
starting with the worker.
