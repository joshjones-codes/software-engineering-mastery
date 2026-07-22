# Systems Catalog

Every mature SaaS — Stripe, Shopify, Uber, Slack, GitHub — is assembled from a subset
of the same ~50 reusable backend capabilities. Different products, same underlying
systems. This catalog is the checklist: each capability mapped to the module that
teaches it, checked off when I've **built it once**.

Once you've built each of these once, every backend you ever encounter is a
recombination of familiar parts.

## Core application systems

| Capability | Module | Built |
|---|---|---|
| Authentication | Spine 1.3 | ☐ |
| Authorization (RBAC/ABAC) | Spine 1.4 | ☐ |
| User & org management, multi-tenancy | Spine 1.11 | ☐ |
| Settings & preferences | Spine 1.7 (config patterns) | ☐ |
| API keys & service auth | Spine 1.10 | ☐ |

## Communication systems

| Capability | Module | Built |
|---|---|---|
| Email pipeline | Spine 4.8 | ☐ |
| Push / SMS / in-app notifications | Spine 4.8 | ☐ |
| WebSockets & presence | Spine 4.7 | ☐ |
| Webhook platform (outbound, Stripe-style) | Spine 1.12 | ☐ |

## Data systems

| Capability | Module | Built |
|---|---|---|
| Search | Spine 6.5 | ☐ |
| Analytics / event pipeline | Spine 6.6 | ☐ |
| Audit logs (immutable) | Spine 2.8 | ☐ |
| Activity feeds | Spine 4.6 + 6.6 | ☐ |
| Reporting & warehouse exports | Spine 6.6 | ☐ |

## File systems

| Capability | Module | Built |
|---|---|---|
| File uploads (presigned, multipart) | Spine 6.1 | ☐ |
| Image processing pipeline | Spine 6.2 | ☐ |
| Document/PDF generation | Spine 6.3 | ☐ |
| CDN integration | Spine 3.3 | ☐ |

## Payment systems

| Capability | Module | Built |
|---|---|---|
| Billing, subscriptions, metering, dunning | Spine 4.9 | ☐ |
| Inbound webhook processing (idempotent) | Spine 4.4 + 4.9 | ☐ |

## Infrastructure systems

| Capability | Module | Built |
|---|---|---|
| Background jobs & workers | Spine 4.1 | ☐ |
| Queues | Spine 4.2 | ☐ |
| Job scheduler / cron | Spine 4.5 | ☐ |
| Distributed locks | Spine 5.8 | ☐ |
| Rate limiting | Spine 1.6 | ☐ |
| Caching | Spine 3.1–3.2 | ☐ |
| Feature flags | Practices: feature-flags | ☐ |
| Secrets & config management | Spine 1.7 + 7.7 | ☐ |

## Real-time systems

| Capability | Module | Built |
|---|---|---|
| GPS tracking / streaming telemetry | Spine 4.7 + 6.7 | ☐ |
| Live dashboards | Spine 4.7 | ☐ |
| Offline sync (field devices) | Spine 5.11 + FE 6.2 | ☐ |

## Reliability systems

| Capability | Module | Built |
|---|---|---|
| Health checks & graceful shutdown | Spine 1.13 | ☐ |
| Retries, backoff, DLQs | Spine 4.3 | ☐ |
| Idempotency | Spine 4.4 | ☐ |
| Circuit breakers & backpressure | Spine 5.9 | ☐ |
| Backups & disaster recovery | Spine 7.8 | ☐ |

## Security & observability

| Capability | Module | Built |
|---|---|---|
| MFA, session management | Spine 1.3 | ☐ |
| Encryption & key rotation | Spine 7.7 + Advanced: security | ☐ |
| Structured logging | Spine 1.8 | ☐ |
| Metrics, tracing, alerting | Spine 7.6 | ☐ |
| Error tracking | Spine 7.6 | ☐ |

---

## The reference build order

The spine's project sequencing — each capability lands when the lab product genuinely
needs it. The order below is the natural sequence for a field-service B2B SaaS (the
worked example used throughout the curriculum); most SaaS products follow it closely:

1. **Authentication & RBAC** — company roles, admin vs crew
2. **GPS tracking** — check-in verification (core product)
3. **File upload service** — site photos, presigned + compression
4. **Audit logging** — immutable compliance trail (the product IS the audit trail)
5. **Notification platform** — assignment alerts, weather triggers
6. **Background job system** — everything async goes through it
7. **Search** — employees, sites, events
8. **Analytics / event pipeline** — manager dashboards off the event stream, not prod DB
9. **Billing & subscriptions** — revenue
10. **Reporting / PDF generation** — the deliverable customers pay for
11. **Real-time map updates** — dispatch board goes live
12. **Webhook platform** — customers' systems subscribe to compliance events
13. **Multi-tenancy hardening** — RLS, isolation guarantees
14. **Observability** — traces across the whole event flow
15. **Feature flags** — safe rollout as customer count grows

The north-star architecture this converges on:

```
Employee checks in
      ↓
  publish event
      ↓
┌────────────────────────────────────────────┐
│ queue → GPS verification → weather lookup  │
│       → audit log (immutable)              │
│       → notifications (retry + DLQ)        │
│       → analytics stream                   │
│       → payroll export                     │
│       → manager dashboard (realtime)       │
└────────────────────────────────────────────┘
```

One action, many consumers, no coupling — and I can explain every tradeoff in it.
