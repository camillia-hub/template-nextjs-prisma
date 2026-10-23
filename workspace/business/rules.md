# Business rules

- BR-1 All tenant data is isolated; no feature may read or write across tenants.
- BR-2 Only `owner` may manage billing or delete the tenant; `owner` and `admin`
  manage members.
- BR-3 `free` tenants are limited to 3 seats and 100 projects; limits are enforced
  server-side.
- BR-4 Plan upgrades apply immediately; downgrades apply at the end of the paid
  period.
- BR-5 Deleting a tenant schedules data erasure after a 30-day grace period; the
  erasure job is run by operations outside the application.
- BR-6 Every billing-relevant change (plan, seats) writes an audit log entry.
