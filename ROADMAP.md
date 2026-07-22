# Roadmap

The full catalog — **142 modules** across five tracks. This is a **map, not a to-do list**:
the unit of progress is always *one module*, and the only module that matters is the current one.

**For the actual order to work in, use [PATH.md](PATH.md)** — Year 1 weekend by weekend,
spine builds and CS-foundations reading already interleaved. This file is the full territory;
PATH.md is the route through it.

## How the tracks interleave

- **[Spine](curriculum/spine/README.md)** (73 modules) — the primary track. Weekend builds, driven by the lab product. Work it in order.
- **[Foundations](curriculum/foundations/README.md)** (28 modules) — Saturday-morning reading alongside the spine. *Code* → *Grokking* → *OSTEP* → *Networking* → *DDIA*.
- **[Frontend](curriculum/frontend/README.md)** (21 modules) — interleave when interview-relevant or product-relevant; you're already strong here, this adds depth.
- **[Practices](curriculum/practices/README.md)** (10 habits) — woven into every module from day one. Never a phase.
- **[Advanced](curriculum/advanced/README.md)** (10 areas) — years 2+. Don't plan these yet.

## Tiers

- 🔴 **must** — gates progress; core mental models
- 🟡 **should** — build when the lab product or interviews demand it; don't skip forever
- ⚪ **nice** — genuinely optional; curiosity-driven

Effort estimates assume the weekend loop: Read → Build → Integrate → Reflect → Teach.

---


## Spine — The Build Track


### Production Backend

Turn CRUD into production software. Everything here is also senior-interview material — this stage pays off in the current job search.

| Module | Tier | Effort | Covers |
|---|---|---|---|
| [API Design Fundamentals](curriculum/spine/01-production-backend/01-api-design-fundamentals.md) | 🔴 must | ~1 wknd | resource modeling, URL design, HTTP semantics, status codes, error shapes, REST vs RPC vs GraphQL |
| [Validation & Error Handling](curriculum/spine/01-production-backend/02-validation-and-error-handling.md) | 🔴 must | ~1 wknd | validate at boundaries, Zod schemas shared FE/BE, error taxonomy, problem+json |
| [Authentication](curriculum/spine/01-production-backend/03-authentication.md) | 🔴 must | ~2 wknds | sessions vs JWT, password hashing, token rotation, OAuth/OIDC basics, MFA |
| [Authorization & RBAC](curriculum/spine/01-production-backend/04-authorization-and-rbac.md) | 🔴 must | ~1 wknd | RBAC vs ABAC, permission models, enforcement layers, deny-by-default |
| [Pagination, Filtering & Sorting](curriculum/spine/01-production-backend/05-pagination-filtering-sorting.md) | 🔴 must | ~1 wknd | offset vs cursor pagination, stable sort keys, filter grammars |
| [Rate Limiting & Abuse Protection](curriculum/spine/01-production-backend/06-rate-limiting-and-abuse-protection.md) | 🔴 must | ~1 wknd | token bucket, sliding window, per-tenant limits, 429 semantics |
| [Configuration & Secrets](curriculum/spine/01-production-backend/07-configuration-and-secrets.md) | 🟡 should | ~1 wknd | 12-factor config, env layering, secret hygiene, config validation at boot |
| [Structured Logging](curriculum/spine/01-production-backend/08-structured-logging.md) | 🔴 must | ~1 wknd | log levels, structured JSON logs, correlation IDs, PII redaction |
| [API Versioning & Evolution](curriculum/spine/01-production-backend/09-api-versioning-and-evolution.md) | 🟡 should | ~1 wknd | backwards compatibility, additive change, deprecation policy, contract tests |
| [API Keys & Service Auth](curriculum/spine/01-production-backend/10-api-keys-and-service-auth.md) | 🟡 should | ~1 wknd | key issuance/hashing, scopes, machine-to-machine auth |
| [Multi-Tenancy](curriculum/spine/01-production-backend/11-multi-tenancy.md) | 🔴 must | ~2 wknds | isolation models (row/schema/db), tenant context propagation, Postgres RLS, noisy neighbors |
| [Webhooks](curriculum/spine/01-production-backend/12-webhooks.md) | 🟡 should | ~1 wknd | signatures, retries with backoff, delivery history, replay — the Stripe model |
| [Health Checks & Graceful Shutdown](curriculum/spine/01-production-backend/13-health-checks-and-graceful-shutdown.md) | 🟡 should | ~1 wknd | liveness vs readiness, draining, SIGTERM handling |

### Databases

Go from 'uses Postgres' to understanding what the database is doing and why.

| Module | Tier | Effort | Covers |
|---|---|---|---|
| [SQL Mastery](curriculum/spine/02-databases/01-sql-mastery.md) | 🔴 must | ~2 wknds | joins, aggregations, window functions, CTEs, EXPLAIN as a habit |
| [Indexes & Query Optimization](curriculum/spine/02-databases/02-indexes-and-query-optimization.md) | 🔴 must | ~2 wknds | B-tree mechanics, composite/covering/partial indexes, reading query plans |
| [Transactions & Isolation](curriculum/spine/02-databases/03-transactions-and-isolation.md) | 🔴 must | ~2 wknds | ACID, isolation levels, anomalies, optimistic vs pessimistic locking |
| [Data Modeling & Constraints](curriculum/spine/02-databases/04-data-modeling-and-constraints.md) | 🔴 must | ~1 wknd | normalization vs denormalization, foreign keys, integrity in the DB not just the app |
| [Migrations](curriculum/spine/02-databases/05-migrations.md) | 🔴 must | ~1 wknd | expand–contract, zero-downtime migrations, backfill strategies |
| [Connection Pooling](curriculum/spine/02-databases/06-connection-pooling.md) | 🟡 should | ~1 wknd | pool sizing, serverless vs pooled, pgBouncer |
| [Replication & Read Replicas](curriculum/spine/02-databases/07-replication-and-read-replicas.md) | 🟡 should | ~2 wknds | replication lag, read-your-writes, routing reads |
| [Audit Tables & Soft Deletes](curriculum/spine/02-databases/08-audit-tables-and-soft-deletes.md) | 🟡 should | ~1 wknd | immutable history, temporal data, compliance-grade audit trails |
| [NoSQL & Alternative Models](curriculum/spine/02-databases/09-nosql-and-alternative-models.md) | ⚪ nice | ~1 wknd | document/KV/wide-column, when relational stops fitting |

### Caching

The first real scaling tool — and the first real consistency problem.

| Module | Tier | Effort | Covers |
|---|---|---|---|
| [Caching Strategies](curriculum/spine/03-caching/01-caching-strategies.md) | 🔴 must | ~2 wknds | cache-aside, write-through/behind, TTL, invalidation, stampede protection |
| [Redis in Practice](curriculum/spine/03-caching/02-redis-in-practice.md) | 🔴 must | ~1 wknd | data structures, atomic operations, eviction policies, pub/sub |
| [HTTP & CDN Caching](curriculum/spine/03-caching/03-http-and-cdn-caching.md) | 🟡 should | ~1 wknd | Cache-Control, ETags, stale-while-revalidate, CDN behavior |
| [Distributed Caching](curriculum/spine/03-caching/04-distributed-caching.md) | ⚪ nice | ~1 wknd | consistent hashing, hot keys, cache topology |

### Async Systems

The biggest conceptual leap: work that happens later, elsewhere, and sometimes twice.

| Module | Tier | Effort | Covers |
|---|---|---|---|
| [Background Jobs & Workers](curriculum/spine/04-async-systems/01-background-jobs-and-workers.md) | 🔴 must | ~2 wknds | job lifecycle, worker pools, concurrency limits, graceful shutdown |
| [Queues & Message Brokers](curriculum/spine/04-async-systems/02-queues-and-message-brokers.md) | 🔴 must | ~2–3 wknds | build a queue from scratch; SQS vs RabbitMQ vs Kafka vs Redis Streams; ordering |
| [Retries, Backoff & DLQs](curriculum/spine/04-async-systems/03-retries-backoff-and-dlqs.md) | 🔴 must | ~1 wknd | exponential backoff, jitter, dead-letter queues, poison messages |
| [Idempotency](curriculum/spine/04-async-systems/04-idempotency.md) | 🔴 must | ~1 wknd | idempotency keys, dedup, why exactly-once is a lie you engineer around |
| [Scheduling & Cron](curriculum/spine/04-async-systems/05-scheduling-and-cron.md) | 🟡 should | ~1 wknd | distributed cron, drift, overlap locks, missed-run policy |
| [Pub/Sub & Event Fanout](curriculum/spine/04-async-systems/06-pub-sub-and-event-fanout.md) | 🟡 should | ~1 wknd | one event, many consumers; decoupling; event contracts |
| [Realtime: WebSockets & SSE](curriculum/spine/04-async-systems/07-realtime-websockets-and-sse.md) | 🟡 should | ~2 wknds | connection lifecycle, presence, scaling stateful connections |
| [Notification Systems](curriculum/spine/04-async-systems/08-notification-systems.md) | 🟡 should | ~2 wknds | the classic system: multi-channel, preferences, batching, digests |
| [Billing & Subscriptions](curriculum/spine/04-async-systems/09-billing-and-subscriptions.md) | 🟡 should | ~2 wknds | Stripe webhooks done right, idempotent processing, metering, dunning |

### Distributed Systems

Staff-level thinking: what happens when there is more than one machine and any of them can fail.

| Module | Tier | Effort | Covers |
|---|---|---|---|
| [Distributed Systems Fundamentals](curriculum/spine/05-distributed-systems/01-distributed-systems-fundamentals.md) | 🔴 must | ~2 wknds | fallacies of distributed computing, failure modes, CAP/PACELC |
| [Consistency Models](curriculum/spine/05-distributed-systems/02-consistency-models.md) | 🔴 must | ~2 wknds | strong vs eventual, causal, linearizability, read-your-writes |
| [Time & Clocks](curriculum/spine/05-distributed-systems/03-time-and-clocks.md) | 🟡 should | ~1 wknd | wall vs monotonic clocks, NTP drift, logical/vector clocks, timezone traps |
| [Outbox & Transactional Messaging](curriculum/spine/05-distributed-systems/04-outbox-and-transactional-messaging.md) | 🔴 must | ~2 wknds | dual-write problem, outbox pattern, CDC intuition |
| [Sagas & Distributed Transactions](curriculum/spine/05-distributed-systems/05-sagas-and-distributed-transactions.md) | 🟡 should | ~2 wknds | why 2PC hurts, compensating actions, orchestration vs choreography |
| [Event Sourcing & CQRS](curriculum/spine/05-distributed-systems/06-event-sourcing-and-cqrs.md) | 🟡 should | ~2 wknds | events as source of truth, projections, replay, when NOT to use it |
| [Consensus & Leader Election](curriculum/spine/05-distributed-systems/07-consensus-and-leader-election.md) | 🟡 should | ~2 wknds | Raft walkthrough, quorums, split brain |
| [Distributed Locks](curriculum/spine/05-distributed-systems/08-distributed-locks.md) | 🟡 should | ~1 wknd | lease-based locks, fencing tokens, Redlock controversy |
| [Resilience Patterns](curriculum/spine/05-distributed-systems/09-resilience-patterns.md) | 🔴 must | ~2 wknds | timeouts, circuit breakers, bulkheads, backpressure, load shedding |
| [Delivery Guarantees](curriculum/spine/05-distributed-systems/10-delivery-guarantees.md) | 🟡 should | ~1 wknd | at-most/at-least/exactly-once, consumer offset management |
| [Offline-First & Sync](curriculum/spine/05-distributed-systems/11-offline-first-and-sync.md) | 🟡 should | ~2–3 wknds | sync queues, conflict resolution, CRDT intuition — field crews and mobile users with no signal |
| [Service Discovery & Load Balancing](curriculum/spine/05-distributed-systems/12-service-discovery-and-load-balancing.md) | ⚪ nice | ~1 wknd | L4 vs L7, health-based routing, discovery mechanisms |

### Storage, Search & Analytics

Files, documents, and turning operational data into questions you can answer.

| Module | Tier | Effort | Covers |
|---|---|---|---|
| [Object Storage & Uploads](curriculum/spine/06-storage-search-analytics/01-object-storage-and-uploads.md) | 🔴 must | ~2 wknds | presigned URLs, multipart, checksums, lifecycle policies — every product with user uploads lands here |
| [File Processing Pipelines](curriculum/spine/06-storage-search-analytics/02-file-processing-pipelines.md) | 🟡 should | ~2 wknds | async image processing, thumbnails, EXIF/GPS extraction, virus scanning |
| [Document Generation](curriculum/spine/06-storage-search-analytics/03-document-generation.md) | 🟡 should | ~1 wknd | PDF reports, templating, async generation — invoices, reports, exports |
| [Data Formats & Serialization](curriculum/spine/06-storage-search-analytics/04-data-formats-and-serialization.md) | 🟡 should | ~1 wknd | JSON vs Protobuf vs Avro, schema evolution, compression |
| [Search](curriculum/spine/06-storage-search-analytics/05-search.md) | 🟡 should | ~2 wknds | inverted indexes, tokenization, relevance, Postgres FTS before dedicated engines |
| [Analytics Pipelines](curriculum/spine/06-storage-search-analytics/06-analytics-pipelines.md) | 🟡 should | ~2 wknds | event collection, ETL/ELT, columnar storage, reading off the event stream not prod DB |
| [Stream Processing](curriculum/spine/06-storage-search-analytics/07-stream-processing.md) | ⚪ nice | ~2 wknds | windows, watermarks, stateful processing |

### Infrastructure & Operations

Own the machine your code runs on and the path it takes to get there.

| Module | Tier | Effort | Covers |
|---|---|---|---|
| [Linux Fundamentals](curriculum/spine/07-infrastructure/01-linux-fundamentals.md) | 🔴 must | ~2 wknds | shell fluency, processes, permissions, systemd, signals, /proc |
| [Containers](curriculum/spine/07-infrastructure/02-containers.md) | 🔴 must | ~2 wknds | images, layers, namespaces/cgroups (what Docker actually is), Compose |
| [CI/CD](curriculum/spine/07-infrastructure/03-ci-cd.md) | 🔴 must | ~2 wknds | pipelines, environments, quality gates, rollbacks, deploy strategies |
| [Cloud Architecture (AWS)](curriculum/spine/07-infrastructure/04-cloud-architecture-aws.md) | 🔴 must | ~2–3 wknds | VPC, IAM, ALB, ECS vs Lambda, RDS, SQS/SNS/EventBridge — when each |
| [Infrastructure as Code](curriculum/spine/07-infrastructure/05-infrastructure-as-code.md) | 🟡 should | ~2 wknds | Terraform, state, drift, module design |
| [Observability](curriculum/spine/07-infrastructure/06-observability.md) | 🔴 must | ~2–3 wknds | metrics, distributed tracing, alerting, OpenTelemetry, intro SLOs |
| [Secrets Management](curriculum/spine/07-infrastructure/07-secrets-management.md) | 🟡 should | ~1 wknd | rotation, KMS, secret zero problem |
| [Backups & Disaster Recovery](curriculum/spine/07-infrastructure/08-backups-and-disaster-recovery.md) | 🟡 should | ~1 wknd | RPO/RTO, restore drills (a backup you haven't restored isn't a backup) |
| [Container Orchestration](curriculum/spine/07-infrastructure/09-container-orchestration.md) | 🟡 should | ~3–4 wknds | K8s concepts: scheduling, services, config, operators — orchestration first, kubectl second |
| [Cost Engineering](curriculum/spine/07-infrastructure/10-cost-engineering.md) | 🟡 should | ~1 wknd | unit economics, cost per feature, FinOps basics |
| [DNS, TLS & Domains in Practice](curriculum/spine/07-infrastructure/11-dns-tls-domains-in-practice.md) | 🟡 should | ~1 wknd | records, certs, renewal, propagation debugging |

### AI Systems

Applied AI engineering on top of everything above — agents and RAG are distributed systems with a model in the loop.

| Module | Tier | Effort | Covers |
|---|---|---|---|
| [Embeddings & Vector Search](curriculum/spine/08-ai-systems/01-embeddings-and-vector-search.md) | 🔴 must | ~2 wknds | embedding models, similarity, pgvector before dedicated DBs, hybrid search |
| [RAG Systems](curriculum/spine/08-ai-systems/02-rag-systems.md) | 🔴 must | ~2 wknds | chunking, retrieval quality, reranking, citations, when RAG is the wrong tool |
| [Agents & Tool Use](curriculum/spine/08-ai-systems/03-agents-and-tool-use.md) | 🔴 must | ~2–3 wknds | agent loops, function calling, sandboxing, failure modes, human-in-the-loop |
| [MCP](curriculum/spine/08-ai-systems/04-mcp.md) | 🟡 should | ~1 wknd | build an MCP server over the lab product's data |
| [Evals](curriculum/spine/08-ai-systems/05-evals.md) | 🔴 must | ~2 wknds | golden sets, LLM-as-judge, regression testing prompts like code |
| [Context Engineering & Memory](curriculum/spine/08-ai-systems/06-context-engineering-and-memory.md) | 🟡 should | ~2 wknds | context budgets, summarization, memory architectures |
| [Prompting & Model Routing](curriculum/spine/08-ai-systems/07-prompt-engineering-and-model-routing.md) | 🟡 should | ~1 wknd | prompt caching, cost/latency tiers, structured output |
| [Inference & Serving](curriculum/spine/08-ai-systems/08-inference-and-serving.md) | ⚪ nice | ~2 wknds | tokens/sampling, batching, quantization intuition, latency budgets |

## Foundations — The Read Track


### How Computers Work

Book: *Code* (Petzold, 2nd ed). Builds the abstraction-layer mental model everything else sits on.

| Module | Tier | Effort | Covers |
|---|---|---|---|
| [Codes & Binary](curriculum/foundations/01-how-computers-work/01-codes-and-binary.md) | 🔴 must | ~2 wknds | Code ch. 1–9 · number systems, bits, bytes, hex · build: binary/hex converter |
| [Logic Gates & Circuits](curriculum/foundations/01-how-computers-work/02-logic-gates-and-circuits.md) | 🔴 must | ~2 wknds | Code ch. 10–14 · boolean logic, gates, adders · build: logic gate simulator |
| [Memory & the CPU](curriculum/foundations/01-how-computers-work/03-memory-and-the-cpu.md) | 🔴 must | ~2 wknds | Code ch. 15–22 · flip-flops, RAM, CPU execution · build: simulate an 8-bit adder |
| [Machine Code to High-Level Languages](curriculum/foundations/01-how-computers-work/04-machine-code-to-high-level.md) | 🟡 should | ~2 wknds | Code ch. 23–28 · assembly, abstraction layers · build: toy stack VM |

### Programming & Algorithms

Books: *Grokking Algorithms*, then selected *Algorithm Design Manual* chapters. Build every structure once.

| Module | Tier | Effort | Covers |
|---|---|---|---|
| [Complexity & Big-O](curriculum/foundations/02-programming-and-algorithms/01-complexity-and-big-o.md) | 🔴 must | ~1 wknd | growth rates, time vs space, amortized analysis intuition |
| [Arrays, Lists, Stacks & Queues](curriculum/foundations/02-programming-and-algorithms/02-arrays-lists-stacks-queues.md) | 🔴 must | ~1 wknd | build: dynamic array + linked list from scratch |
| [Hash Tables](curriculum/foundations/02-programming-and-algorithms/03-hash-tables.md) | 🔴 must | ~1 wknd | hashing, collisions, resizing · build: your own HashMap |
| [Recursion, Sorting & Searching](curriculum/foundations/02-programming-and-algorithms/04-recursion-sorting-searching.md) | 🔴 must | ~1 wknd | quicksort/mergesort, binary search, recursion patterns |
| [Trees & Graphs](curriculum/foundations/02-programming-and-algorithms/05-trees-and-graphs.md) | 🔴 must | ~2 wknds | BFS/DFS, tries, shortest paths · build: a trie-backed autocomplete |
| [Heaps, LRU & Bloom Filters](curriculum/foundations/02-programming-and-algorithms/06-heaps-lru-bloom-filters.md) | 🟡 should | ~1 wknd | build: LRU cache + priority queue (both appear constantly in real systems) |
| [Dynamic Programming & Greedy](curriculum/foundations/02-programming-and-algorithms/07-dynamic-programming-and-greedy.md) | ⚪ nice | ~2 wknds | memoization, tabulation, greedy proofs intuition |

### Operating Systems

Book: *Operating Systems: Three Easy Pieces* (free online). Ends with the runtime you actually ship.

| Module | Tier | Effort | Covers |
|---|---|---|---|
| [Processes & Threads](curriculum/foundations/03-operating-systems/01-processes-and-threads.md) | 🔴 must | ~2 wknds | OSTEP virtualization chapters · fork/exec, threads vs processes |
| [Scheduling](curriculum/foundations/03-operating-systems/02-scheduling.md) | 🟡 should | ~1 wknd | context switching, schedulers, priority |
| [Memory Management](curriculum/foundations/03-operating-systems/03-memory-management.md) | 🔴 must | ~2 wknds | virtual memory, paging, stack vs heap — what your variables actually are |
| [Concurrency Primitives](curriculum/foundations/03-operating-systems/04-concurrency-primitives.md) | 🔴 must | ~2 wknds | locks, semaphores, condition variables, race conditions · build: worker pool with a thread-safe queue |
| [Filesystems](curriculum/foundations/03-operating-systems/05-filesystems.md) | 🟡 should | ~1 wknd | inodes, journaling, fsync — why databases care |
| [Node.js Runtime Internals](curriculum/foundations/03-operating-systems/06-nodejs-runtime-internals.md) | 🔴 must | ~2 wknds | event loop phases, libuv, streams & backpressure, worker threads — deep in YOUR runtime |

### Networking

Book: *Computer Networking: A Top-Down Approach* (selected chapters).

| Module | Tier | Effort | Covers |
|---|---|---|---|
| [Transport: TCP & UDP](curriculum/foundations/04-networking/01-transport-tcp-udp.md) | 🔴 must | ~2 wknds | handshakes, flow control, congestion, head-of-line blocking |
| [DNS](curriculum/foundations/04-networking/02-dns.md) | 🔴 must | ~1 wknd | resolution path, record types, TTLs, debugging with dig |
| [HTTP/1.1 → HTTP/3](curriculum/foundations/04-networking/03-http-from-1-to-3.md) | 🔴 must | ~2 wknds | build: tiny HTTP server on raw TCP sockets — then appreciate what frameworks do |
| [TLS & Certificates](curriculum/foundations/04-networking/04-tls-and-certificates.md) | 🔴 must | ~1 wknd | handshake, certificate chains, what the padlock actually proves |
| [Proxies, Load Balancers & WebSockets](curriculum/foundations/04-networking/05-proxies-lbs-websockets.md) | 🟡 should | ~1 wknd | reverse proxies, L4 vs L7, the WebSocket upgrade |

### Data-Intensive Systems

Book: *Designing Data-Intensive Applications*. Read slowly, across months, paired with spine stages 2–6.

| Module | Tier | Effort | Covers |
|---|---|---|---|
| [Storage Engines](curriculum/foundations/05-data-intensive-systems/01-storage-engines.md) | 🔴 must | ~2 wknds | DDIA ch. 3 · B-trees vs LSM trees · build: tiny append-only KV store |
| [Encoding & Schema Evolution](curriculum/foundations/05-data-intensive-systems/02-encoding-and-schema-evolution.md) | 🟡 should | ~1 wknd | DDIA ch. 4 · forward/backward compatibility |
| [Replication](curriculum/foundations/05-data-intensive-systems/03-replication.md) | 🔴 must | ~2 wknds | DDIA ch. 5 · leaders, followers, lag, multi-leader conflicts |
| [Partitioning](curriculum/foundations/05-data-intensive-systems/04-partitioning.md) | 🔴 must | ~1 wknd | DDIA ch. 6 · hash vs range, rebalancing, hot spots |
| [Transactions & Consistency](curriculum/foundations/05-data-intensive-systems/05-transactions-and-consistency.md) | 🔴 must | ~2–3 wknds | DDIA ch. 7–9 · the hardest and best chapters — take your time |
| [Batch & Stream Processing](curriculum/foundations/05-data-intensive-systems/06-batch-and-stream-processing.md) | 🟡 should | ~2 wknds | DDIA ch. 10–11 · dataflow thinking, event logs |

## Frontend — The Depth Track


### The Browser Platform

Master the platform itself — the layer under every framework.

| Module | Tier | Effort | Covers |
|---|---|---|---|
| [HTML Semantics & Accessibility](curriculum/frontend/01-browser-platform/01-html-semantics-and-accessibility.md) | 🔴 must | ~2 wknds | semantic structure, forms, focus management, dialogs, ARIA, keyboard navigation |
| [CSS Mastery](curriculum/frontend/01-browser-platform/02-css-mastery.md) | 🔴 must | ~2–3 wknds | grid, flexbox, stacking contexts, container queries, clamp(), logical properties · project: pixel-faithful Stripe-quality page |
| [JavaScript Internals](curriculum/frontend/01-browser-platform/03-javascript-internals.md) | 🔴 must | ~2–3 wknds | closures, prototype chain, event loop & microtasks, GC, iterators, proxies · build: event emitter, debounce/throttle, deep clone |
| [SVG & Canvas](curriculum/frontend/01-browser-platform/04-svg-and-canvas.md) | ⚪ nice | ~2 wknds | coordinate systems, paths, when SVG vs canvas — feeds dataviz and maps |

### React Internals

Not hooks — architecture. Know what React does with your code.

| Module | Tier | Effort | Covers |
|---|---|---|---|
| [Rendering & Reconciliation](curriculum/frontend/02-react-internals/01-rendering-and-reconciliation.md) | 🔴 must | ~2 wknds | Fiber, keys, render vs commit, memoization semantics · build: mini virtual DOM + your own useState |
| [Concurrent Rendering & Suspense](curriculum/frontend/02-react-internals/02-concurrent-rendering-and-suspense.md) | 🟡 should | ~2 wknds | transitions, scheduling, tearing, use() |
| [Server Components & Hydration](curriculum/frontend/02-react-internals/03-server-components-and-hydration.md) | 🔴 must | ~2 wknds | RSC model, streaming SSR, hydration cost — you ship Next.js; know what it's doing |

### Application Architecture

Where seniors separate themselves: structure, state, and data flow at app scale.

| Module | Tier | Effort | Covers |
|---|---|---|---|
| [State Management](curriculum/frontend/03-application-architecture/01-state-management.md) | 🔴 must | ~2 wknds | local vs server vs URL state, context performance, Zustand/Jotai tradeoffs |
| [Data Fetching & Caching](curriculum/frontend/03-application-architecture/02-data-fetching-and-caching.md) | 🔴 must | ~2 wknds | TanStack Query, optimistic updates, cache invalidation, request waterfalls |
| [Forms & Validation](curriculum/frontend/03-application-architecture/03-forms-and-validation.md) | 🟡 should | ~1 wknd | React Hook Form + Zod, schemas shared with the API layer |
| [Error, Loading & Offline UX](curriculum/frontend/03-application-architecture/04-error-loading-and-offline-ux.md) | 🟡 should | ~1 wknd | error boundaries, skeletons vs spinners, retry UX, empty states |

### Rendering & Performance

The pipeline, then the practice of making it fast.

| Module | Tier | Effort | Covers |
|---|---|---|---|
| [Browser Rendering Pipeline](curriculum/frontend/04-rendering-and-performance/01-browser-rendering-pipeline.md) | 🔴 must | ~2 wknds | layout → paint → composite, reflows, GPU layers, what triggers what |
| [Frontend Performance](curriculum/frontend/04-rendering-and-performance/02-frontend-performance.md) | 🔴 must | ~2–3 wknds | Core Web Vitals, bundle analysis, code splitting, virtualization, image strategy, web workers · project: make the lab app feel instant on mobile |

### Design Systems

Underrated senior skill — the difference between using a component library and owning a design system.

| Module | Tier | Effort | Covers |
|---|---|---|---|
| [Design Systems](curriculum/frontend/05-design-systems/01-design-systems.md) | 🟡 should | ~2–3 wknds | tokens, variants, composition & slots, accessible primitives, documentation · project: formalize the lab app's UI into a documented system |

### Offline & Device APIs

The browser capabilities that make offline-capable, device-aware field apps possible.

| Module | Tier | Effort | Covers |
|---|---|---|---|
| [Service Workers & PWA](curriculum/frontend/06-offline-and-device-apis/01-service-workers-and-pwa.md) | 🟡 should | ~2 wknds | caching strategies, installability, update lifecycle |
| [IndexedDB & Offline-First UI](curriculum/frontend/06-offline-and-device-apis/02-indexeddb-and-offline-first-ui.md) | 🟡 should | ~2 wknds | local persistence, sync queue UX, conflict surfacing — pairs with Spine 5.11 |
| [Device APIs](curriculum/frontend/06-offline-and-device-apis/03-device-apis.md) | 🟡 should | ~2 wknds | geolocation, camera, push notifications, background sync — offline inspection uploads |

### Frontend Testing

Confidence at the UI layer.

| Module | Tier | Effort | Covers |
|---|---|---|---|
| [Frontend Testing](curriculum/frontend/07-testing/01-frontend-testing.md) | 🟡 should | ~2 wknds | Testing Library, Playwright, Storybook, visual regression |

### Frontend Infrastructure

The tooling layer most product engineers never open.

| Module | Tier | Effort | Covers |
|---|---|---|---|
| [Bundlers & Build Tooling](curriculum/frontend/08-infrastructure/01-bundlers-and-build-tooling.md) | 🟡 should | ~2 wknds | Vite/webpack mental model, SWC, tree shaking, source maps |
| [Monorepos & Shared Packages](curriculum/frontend/08-infrastructure/02-monorepos-and-shared-packages.md) | ⚪ nice | ~2 wknds | pnpm workspaces, shared-ui/shared-types, versioning internal packages |

### Motion

Polish tier — pursue when it serves the product.

| Module | Tier | Effort | Covers |
|---|---|---|---|
| [Animation & Motion](curriculum/frontend/09-motion/01-animation-and-motion.md) | ⚪ nice | ~2 wknds | FLIP, spring physics, Framer Motion, shared layout transitions |

## Practices — Woven Into Every Module

| Doc | Territory |
|---|---|
| [Testing](curriculum/practices/testing.md) | the full family — unit → integration → E2E → property → load → chaos → contract — introduced progressively; every weekend build ships with tests |
| [Version Control & Git](curriculum/practices/version-control-and-git.md) | branching discipline, rebase fluency, bisect, meaningful history; internals arrive in Developer Tooling |
| [Security Mindset](curriculum/practices/security-mindset.md) | OWASP Top 10 as a per-module checklist, secure defaults, lightweight threat modeling |
| [Technical Writing](curriculum/practices/technical-writing.md) | ADRs, design docs, RFCs — every module reflection IS the practice; the handbook is the output |
| [Estimation](curriculum/practices/estimation.md) | back-of-envelope math, latency numbers every engineer should know, capacity sizing in every system-design exercise |
| [Observability Habits](curriculum/practices/observability-habits.md) | log/metric/trace something in every build from day one; the deep module is Spine 7.6 |
| [Domain Modeling](curriculum/practices/domain-modeling.md) | entities, invariants, state machines, ubiquitous language — modeling before coding |
| [Feature Flags & Experimentation](curriculum/practices/feature-flags-and-experimentation.md) | flag lifecycle, kill switches, gradual rollout, cleanup debt |
| [Privacy & Compliance](curriculum/practices/privacy-and-compliance.md) | PII handling, data minimization, retention, PIPEDA/GDPR — table stakes the moment a product holds GPS traces, photos, or employee data |
| [Cost Awareness](curriculum/practices/cost-awareness.md) | unit economics per feature — what does this endpoint/queue/bucket cost at 10× scale? |

## Advanced — Years 2+

| Doc | Territory |
|---|---|
| [Architecture](curriculum/advanced/architecture.md) | monolith → modular monolith → services, evolutionary architecture, migration planning, ADR-driven change |
| [Reliability Engineering](curriculum/advanced/reliability-engineering.md) | SLOs/SLIs, error budgets, incident response, postmortems, capacity planning, DR |
| [Performance Engineering](curriculum/advanced/performance-engineering.md) | profiling, benchmarking, load testing, memory behavior, concurrency tuning |
| [Security Engineering](curriculum/advanced/security-engineering.md) | cryptography in practice, PKI, OAuth/OIDC internals, key rotation, supply-chain security |
| [Database Internals](curriculum/advanced/database-internals.md) | query planners, MVCC, WAL, storage engine construction |
| [Developer Tooling](curriculum/advanced/developer-tooling.md) | Git internals, language servers, build systems, monorepo infrastructure, codegen, static analysis |
| [Platform Engineering](curriculum/advanced/platform-engineering.md) | internal developer platforms, golden paths, self-service infrastructure |
| [ML Systems](curriculum/advanced/ml-systems.md) | training/serving pipelines, GPU fundamentals, feature stores, inference optimization |
| [Staff Engineering](curriculum/advanced/staff-engineering.md) | technical strategy, RFC culture, mentoring, organizational design, influence without authority |
| [Specializations Menu](curriculum/advanced/specializations.md) | compilers, kernels, HPC, embedded, browsers, database engines, deep networking — pick ONE when the time comes |
