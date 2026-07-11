# Distributed Systems

Staff-level thinking: what happens when there is more than one machine and any of them can fail.

| Module | Tier | Effort | Covers |
|---|---|---|---|
| [Distributed Systems Fundamentals](01-distributed-systems-fundamentals.md) | 🔴 must | ~2 wknds | fallacies of distributed computing, failure modes, CAP/PACELC |
| [Consistency Models](02-consistency-models.md) | 🔴 must | ~2 wknds | strong vs eventual, causal, linearizability, read-your-writes |
| [Time & Clocks](03-time-and-clocks.md) | 🟡 should | ~1 wknd | wall vs monotonic clocks, NTP drift, logical/vector clocks, timezone traps |
| [Outbox & Transactional Messaging](04-outbox-and-transactional-messaging.md) | 🔴 must | ~2 wknds | dual-write problem, outbox pattern, CDC intuition |
| [Sagas & Distributed Transactions](05-sagas-and-distributed-transactions.md) | 🟡 should | ~2 wknds | why 2PC hurts, compensating actions, orchestration vs choreography |
| [Event Sourcing & CQRS](06-event-sourcing-and-cqrs.md) | 🟡 should | ~2 wknds | events as source of truth, projections, replay, when NOT to use it |
| [Consensus & Leader Election](07-consensus-and-leader-election.md) | 🟡 should | ~2 wknds | Raft walkthrough, quorums, split brain |
| [Distributed Locks](08-distributed-locks.md) | 🟡 should | ~1 wknd | lease-based locks, fencing tokens, Redlock controversy |
| [Resilience Patterns](09-resilience-patterns.md) | 🔴 must | ~2 wknds | timeouts, circuit breakers, bulkheads, backpressure, load shedding |
| [Delivery Guarantees](10-delivery-guarantees.md) | 🟡 should | ~1 wknd | at-most/at-least/exactly-once, consumer offset management |
| [Offline-First & Sync](11-offline-first-and-sync.md) | 🟡 should | ~2–3 wknds | sync queues, conflict resolution, CRDT intuition — SlipCheck field crews with no signal |
| [Service Discovery & Load Balancing](12-service-discovery-and-load-balancing.md) | ⚪ nice | ~1 wknd | L4 vs L7, health-based routing, discovery mechanisms |
