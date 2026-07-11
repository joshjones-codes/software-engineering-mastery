# Production Backend

Turn CRUD into production software. Everything here is also senior-interview material — this stage pays off in the current job search.

| Module | Tier | Effort | Covers |
|---|---|---|---|
| [API Design Fundamentals](01-api-design-fundamentals.md) | 🔴 must | ~1 wknd | resource modeling, URL design, HTTP semantics, status codes, error shapes, REST vs RPC vs GraphQL |
| [Validation & Error Handling](02-validation-and-error-handling.md) | 🔴 must | ~1 wknd | validate at boundaries, Zod schemas shared FE/BE, error taxonomy, problem+json |
| [Authentication](03-authentication.md) | 🔴 must | ~2 wknds | sessions vs JWT, password hashing, token rotation, OAuth/OIDC basics, MFA |
| [Authorization & RBAC](04-authorization-and-rbac.md) | 🔴 must | ~1 wknd | RBAC vs ABAC, permission models, enforcement layers, deny-by-default |
| [Pagination, Filtering & Sorting](05-pagination-filtering-sorting.md) | 🔴 must | ~1 wknd | offset vs cursor pagination, stable sort keys, filter grammars |
| [Rate Limiting & Abuse Protection](06-rate-limiting-and-abuse-protection.md) | 🔴 must | ~1 wknd | token bucket, sliding window, per-tenant limits, 429 semantics |
| [Configuration & Secrets](07-configuration-and-secrets.md) | 🟡 should | ~1 wknd | 12-factor config, env layering, secret hygiene, config validation at boot |
| [Structured Logging](08-structured-logging.md) | 🔴 must | ~1 wknd | log levels, structured JSON logs, correlation IDs, PII redaction |
| [API Versioning & Evolution](09-api-versioning-and-evolution.md) | 🟡 should | ~1 wknd | backwards compatibility, additive change, deprecation policy, contract tests |
| [API Keys & Service Auth](10-api-keys-and-service-auth.md) | 🟡 should | ~1 wknd | key issuance/hashing, scopes, machine-to-machine auth |
| [Multi-Tenancy](11-multi-tenancy.md) | 🔴 must | ~2 wknds | isolation models (row/schema/db), tenant context propagation, Postgres RLS, noisy neighbors |
| [Webhooks](12-webhooks.md) | 🟡 should | ~1 wknd | signatures, retries with backoff, delivery history, replay — the Stripe model |
| [Health Checks & Graceful Shutdown](13-health-checks-and-graceful-shutdown.md) | 🟡 should | ~1 wknd | liveness vs readiness, draining, SIGTERM handling |
