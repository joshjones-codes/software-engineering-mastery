# The Path — Year 1, in order

The single merged sequence. **Each row is one weekend**: the *Build* column is Saturday
afternoon (spine module), the *Read* column is Saturday morning (CS foundations —
the books). Follow it top to bottom; don't look further ahead than the current row.

Rules of the path:

- **Numbers are sequence, not calendar.** Skip a weekend and everything slides — nothing
  breaks, nothing is "behind."
- A module taking an extra weekend is normal (the estimates are guesses). Stay on it
  until its mastery checklist passes, then move to the next row.
- Rows marked ⚪ are optional — skip freely, return whenever.
- **Don't read ahead of the build, don't build ahead of the read.** The pairing is the
  method: theory in the morning, production in the afternoon, and neither blocks the other.

| Wknd | Build (Saturday PM) | Read (Saturday AM) |
|---|---|---|
| 1 | [1.1 API Design Fundamentals](curriculum/spine/01-production-backend/01-api-design-fundamentals.md) | *Code* ch. 1–4 · [F1.1](curriculum/foundations/01-how-computers-work/01-codes-and-binary.md) |
| 2 | [1.2 Validation & Error Handling](curriculum/spine/01-production-backend/02-validation-and-error-handling.md) | *Code* ch. 5–9 · finish [F1.1](curriculum/foundations/01-how-computers-work/01-codes-and-binary.md) |
| 3 | [1.3 Authentication](curriculum/spine/01-production-backend/03-authentication.md) (1 of 2) | *Code* ch. 10–12 · [F1.2](curriculum/foundations/01-how-computers-work/02-logic-gates-and-circuits.md) |
| 4 | 1.3 Authentication (2 of 2) | *Code* ch. 13–14 · finish F1.2 |
| 5 | [1.4 Authorization & RBAC](curriculum/spine/01-production-backend/04-authorization-and-rbac.md) | *Code* ch. 15–18 · [F1.3](curriculum/foundations/01-how-computers-work/03-memory-and-the-cpu.md) |
| 6 | [1.5 Pagination, Filtering & Sorting](curriculum/spine/01-production-backend/05-pagination-filtering-sorting.md) | *Code* ch. 19–22 · finish F1.3 |
| 7 | [1.6 Rate Limiting](curriculum/spine/01-production-backend/06-rate-limiting-and-abuse-protection.md) | *Code* ch. 23–25 · [F1.4](curriculum/foundations/01-how-computers-work/04-machine-code-to-high-level.md) |
| 8 | [1.7 Configuration & Secrets](curriculum/spine/01-production-backend/07-configuration-and-secrets.md) | *Code* ch. 26–28 · finish F1.4 — **book 1 done** 📕 |
| 9 | [1.8 Structured Logging](curriculum/spine/01-production-backend/08-structured-logging.md) | *Grokking* · [F2.1 Big-O](curriculum/foundations/02-programming-and-algorithms/01-complexity-and-big-o.md) |
| 10 | [1.9 API Versioning & Evolution](curriculum/spine/01-production-backend/09-api-versioning-and-evolution.md) | [F2.2 Arrays, Lists, Stacks, Queues](curriculum/foundations/02-programming-and-algorithms/02-arrays-lists-stacks-queues.md) |
| 11 | [1.10 API Keys & Service Auth](curriculum/spine/01-production-backend/10-api-keys-and-service-auth.md) | [F2.3 Hash Tables](curriculum/foundations/02-programming-and-algorithms/03-hash-tables.md) — build your own HashMap |
| 12 | [1.11 Multi-Tenancy](curriculum/spine/01-production-backend/11-multi-tenancy.md) (1 of 2) | [F2.4 Recursion, Sorting, Searching](curriculum/foundations/02-programming-and-algorithms/04-recursion-sorting-searching.md) |
| 13 | 1.11 Multi-Tenancy (2 of 2) | [F2.5 Trees & Graphs](curriculum/foundations/02-programming-and-algorithms/05-trees-and-graphs.md) (1 of 2) |
| 14 | [1.12 Webhooks](curriculum/spine/01-production-backend/12-webhooks.md) | F2.5 Trees & Graphs (2 of 2) |
| 15 | [1.13 Health Checks & Graceful Shutdown](curriculum/spine/01-production-backend/13-health-checks-and-graceful-shutdown.md) — **Stage 1 done** 🏁 | [F2.6 Heaps, LRU, Bloom Filters](curriculum/foundations/02-programming-and-algorithms/06-heaps-lru-bloom-filters.md) — the LRU returns in Stage 3 |
| 16 | [2.1 SQL Mastery](curriculum/spine/02-databases/01-sql-mastery.md) (1 of 2) | ⚪ [F2.7 DP & Greedy](curriculum/foundations/02-programming-and-algorithms/07-dynamic-programming-and-greedy.md) (1 of 2) |
| 17 | 2.1 SQL Mastery (2 of 2) | ⚪ F2.7 (2 of 2) — **book 2 done** 📗 |
| 18 | [2.2 Indexes & Query Optimization](curriculum/spine/02-databases/02-indexes-and-query-optimization.md) (1 of 2) | *OSTEP* · [F3.1 Processes & Threads](curriculum/foundations/03-operating-systems/01-processes-and-threads.md) (1 of 2) |
| 19 | 2.2 Indexes (2 of 2) | F3.1 (2 of 2) |
| 20 | [2.3 Transactions & Isolation](curriculum/spine/02-databases/03-transactions-and-isolation.md) (1 of 2) | [F3.2 Scheduling](curriculum/foundations/03-operating-systems/02-scheduling.md) |
| 21 | 2.3 Transactions (2 of 2) | [F3.3 Memory Management](curriculum/foundations/03-operating-systems/03-memory-management.md) (1 of 2) |
| 22 | [2.4 Data Modeling & Constraints](curriculum/spine/02-databases/04-data-modeling-and-constraints.md) | F3.3 (2 of 2) |
| 23 | [2.5 Migrations](curriculum/spine/02-databases/05-migrations.md) | [F3.4 Concurrency Primitives](curriculum/foundations/03-operating-systems/04-concurrency-primitives.md) (1 of 2) |
| 24 | [2.6 Connection Pooling](curriculum/spine/02-databases/06-connection-pooling.md) | F3.4 (2 of 2) — worker pool build; pays off at wknd 34 |
| 25 | [2.7 Replication & Read Replicas](curriculum/spine/02-databases/07-replication-and-read-replicas.md) (1 of 2) | [F3.5 Filesystems](curriculum/foundations/03-operating-systems/05-filesystems.md) — why databases fsync |
| 26 | 2.7 Replication (2 of 2) | [F3.6 Node.js Runtime Internals](curriculum/foundations/03-operating-systems/06-nodejs-runtime-internals.md) (1 of 2) |
| 27 | [2.8 Audit Tables & Soft Deletes](curriculum/spine/02-databases/08-audit-tables-and-soft-deletes.md) — the immutable audit trail | F3.6 (2 of 2) — **book 3 done** 📘 |
| 28 | ⚪ [2.9 NoSQL & Alternative Models](curriculum/spine/02-databases/09-nosql-and-alternative-models.md) — **Stage 2 done** 🏁 | *Networking* · [F4.1 TCP & UDP](curriculum/foundations/04-networking/01-transport-tcp-udp.md) (1 of 2) |
| 29 | [3.1 Caching Strategies](curriculum/spine/03-caching/01-caching-strategies.md) (1 of 2) | F4.1 (2 of 2) |
| 30 | 3.1 Caching Strategies (2 of 2) | [F4.2 DNS](curriculum/foundations/04-networking/02-dns.md) |
| 31 | [3.2 Redis in Practice](curriculum/spine/03-caching/02-redis-in-practice.md) | [F4.3 HTTP/1.1 → 3](curriculum/foundations/04-networking/03-http-from-1-to-3.md) (1 of 2) |
| 32 | [3.3 HTTP & CDN Caching](curriculum/spine/03-caching/03-http-and-cdn-caching.md) | F4.3 (2 of 2) — raw-socket HTTP server |
| 33 | ⚪ [3.4 Distributed Caching](curriculum/spine/03-caching/04-distributed-caching.md) — **Stage 3 done** 🏁 | [F4.4 TLS & Certificates](curriculum/foundations/04-networking/04-tls-and-certificates.md) |
| 34 | [4.1 Background Jobs & Workers](curriculum/spine/04-async-systems/01-background-jobs-and-workers.md) (1 of 2) | [F4.5 Proxies, LBs & WebSockets](curriculum/foundations/04-networking/05-proxies-lbs-websockets.md) — **book 4 done** 📙 |
| 35 | 4.1 Background Jobs (2 of 2) | *DDIA* · [F5.1 Storage Engines](curriculum/foundations/05-data-intensive-systems/01-storage-engines.md) (1 of 2) |
| 36 | [4.2 Queues & Message Brokers](curriculum/spine/04-async-systems/02-queues-and-message-brokers.md) (1 of 3) — build a queue from scratch | F5.1 (2 of 2) — tiny KV store |
| 37 | 4.2 Queues (2 of 3) | [F5.2 Encoding & Schema Evolution](curriculum/foundations/05-data-intensive-systems/02-encoding-and-schema-evolution.md) |
| 38 | 4.2 Queues (3 of 3) | [F5.3 Replication](curriculum/foundations/05-data-intensive-systems/03-replication.md) (1 of 2) |
| 39 | [4.3 Retries, Backoff & DLQs](curriculum/spine/04-async-systems/03-retries-backoff-and-dlqs.md) | F5.3 (2 of 2) |
| 40 | [4.4 Idempotency](curriculum/spine/04-async-systems/04-idempotency.md) | [F5.4 Partitioning](curriculum/foundations/05-data-intensive-systems/04-partitioning.md) |
| 41 | [4.5 Scheduling & Cron](curriculum/spine/04-async-systems/05-scheduling-and-cron.md) | [F5.5 Transactions & Consistency](curriculum/foundations/05-data-intensive-systems/05-transactions-and-consistency.md) (1 of 3) — DDIA's hardest, best chapters |
| 42 | [4.6 Pub/Sub & Event Fanout](curriculum/spine/04-async-systems/06-pub-sub-and-event-fanout.md) — the core domain action becomes an event | F5.5 (2 of 3) |
| 43 | [4.7 Realtime: WebSockets & SSE](curriculum/spine/04-async-systems/07-realtime-websockets-and-sse.md) (1 of 2) | F5.5 (3 of 3) |
| 44 | 4.7 Realtime (2 of 2) | [F5.6 Batch & Stream Processing](curriculum/foundations/05-data-intensive-systems/06-batch-and-stream-processing.md) (1 of 2) |
| 45 | [4.8 Notification Systems](curriculum/spine/04-async-systems/08-notification-systems.md) (1 of 2) | F5.6 (2 of 2) — **book 5 done** 📕📗📘📙📔 |
| 46 | 4.8 Notifications (2 of 2) | breathe — or start *Release It!* for Stage 5 |
| 47 | [4.9 Billing & Subscriptions](curriculum/spine/04-async-systems/09-billing-and-subscriptions.md) (1 of 2) | — |
| 48 | 4.9 Billing (2 of 2) — **Stage 4 done** 🏁 **YEAR 1 COMPLETE** | — |

## What Year 1 gets you

All five foundation books read *and applied*. The lab product built right: consistent API,
auth/RBAC, multi-tenant, indexed and migrated properly, cached, fully event-driven with
queues, retries, DLQs, idempotency, notifications, and billing. Every core capability in
the [Systems Catalog](SYSTEMS_CATALOG.md) through "background job system" — built, not
just read about. That's the interview story from Response 2, made real.

## The interview detour 🎯

Job-hunt pressure doesn't wait for the path. When interviews are live, **pause the path**
and run the frontend interview sequence — you're strongest here, so it converts fastest:

1. [FE 1.3 JavaScript Internals](curriculum/frontend/01-browser-platform/03-javascript-internals.md)
2. [FE 2.1 Rendering & Reconciliation](curriculum/frontend/02-react-internals/01-rendering-and-reconciliation.md)
3. [FE 4.1 Browser Rendering Pipeline](curriculum/frontend/04-rendering-and-performance/01-browser-rendering-pipeline.md)
4. [FE 4.2 Frontend Performance](curriculum/frontend/04-rendering-and-performance/02-frontend-performance.md)

Then resume the path where you left off. Everything already completed on the path is
system-design interview ammunition from row 1.

## Year 2

Stages 5–8 (distributed systems → storage/search/analytics → infrastructure → AI) plus
the rest of the frontend track. **Deliberately not scheduled yet** — sequencing it now
would be planning theater. When wknd 48 arrives, Year 1's actual pace writes Year 2's
path in an hour.
