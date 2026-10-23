# UI map

App Router routes of the `app` repository. Keep this file in sync when routes
change.

## Marketing shell — `app/(marketing)/`

| Route | Purpose |
| --- | --- |
| `/` | Landing page |
| `/pricing` | Plans and signup entry |

## Product shell — `app/(app)/` (requires membership)

| Route | Purpose | Role |
| --- | --- | --- |
| `/dashboard` | Tenant overview | member+ |
| `/projects` | Project list | member+ |
| `/projects/[projectId]` | Project detail | member+ |
| `/settings/members` | Membership management | admin+ |
| `/settings/billing` | Plan, seats, invoices | owner |

## API — `app/api/`

| Route | Purpose |
| --- | --- |
| `/api/webhooks/billing` | Billing provider events (signature-verified) |
