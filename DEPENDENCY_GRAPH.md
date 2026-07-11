# Dependency Graph

What unlocks what. Edges mean "genuinely easier if you've done the source first" —
not bureaucratic gating. `must`-tier modules within a stage are the real gate;
`should`/`nice` can be back-filled any time.

## Spine stages

```mermaid
flowchart TD
    S1["1 · Production Backend<br/>auth · RBAC · pagination · rate limiting · multi-tenancy"]
    S2["2 · Databases<br/>indexes · transactions · migrations · replication"]
    S3["3 · Caching<br/>strategies · Redis · CDN"]
    S4["4 · Async Systems<br/>queues · retries · idempotency · notifications · billing"]
    S5["5 · Distributed Systems<br/>consistency · outbox · sagas · resilience · offline sync"]
    S6["6 · Storage, Search & Analytics<br/>uploads · pipelines · search · events"]
    S7["7 · Infrastructure<br/>Linux · containers · AWS · observability · IaC"]
    S8["8 · AI Systems<br/>RAG · agents · MCP · evals"]

    S1 --> S2 --> S3 --> S4 --> S5
    S4 --> S6
    S5 --> S7
    S6 --> S7
    S7 --> S8
    S4 -. "agents need queues & idempotency" .-> S8
```

## Foundations pairing (read alongside, not before)

```mermaid
flowchart LR
    F1["Code (Petzold)<br/>how computers work"]
    F2["Grokking Algorithms<br/>+ data structures"]
    F3["OSTEP<br/>operating systems · Node runtime"]
    F4["Networking Top-Down"]
    F5["DDIA<br/>data-intensive systems"]

    F1 --> F2 --> F3 --> F4 --> F5

    F1 -. "pairs with" .-> P1["Spine 1–2"]
    F2 -. "pairs with" .-> P1
    F3 -. "pairs with" .-> P2["Spine 3–4"]
    F4 -. "pairs with" .-> P3["Spine 4–5"]
    F5 -. "pairs with" .-> P4["Spine 5–6"]
```

## Frontend track entry points

```mermaid
flowchart TD
    FE1["Browser Platform<br/>HTML/CSS/JS internals"]
    FE2["React Internals"]
    FE3["Application Architecture"]
    FE4["Rendering & Performance"]
    FE5["Design Systems"]
    FE6["Offline & Device APIs"]
    FE7["Testing"]
    FE8["FE Infrastructure"]

    FE1 --> FE2 --> FE3
    FE1 --> FE4
    FE3 --> FE5
    FE3 --> FE6
    FE3 --> FE7
    FE2 --> FE8

    S5x["Spine 5.11<br/>Offline-First & Sync"] -. "backend half of" .-> FE6
```

**Interview-priority path** (senior FE roles, relevant now):
JavaScript Internals → Rendering & Reconciliation → Browser Rendering Pipeline → Frontend Performance.

## Cross-track edges worth knowing

| Before | Makes this much easier |
|---|---|
| OSTEP concurrency primitives | Background jobs & workers (Spine 4.1) |
| Node.js runtime internals | Realtime/WebSockets, streams, backpressure everywhere |
| Networking: TCP & HTTP | Rate limiting, load balancing, WebSockets, K8s networking |
| DDIA replication/partitioning | Spine 5 (distributed systems) — read them together |
| Queues + idempotency (Spine 4) | Billing, webhooks, agents (tool retries are retries) |
| Storage engines (DDIA ch. 3) | Indexes & query optimization (Spine 2.2) |
| Hash tables + LRU (Foundations 2) | Caching stage — you'll have built the core structure |
