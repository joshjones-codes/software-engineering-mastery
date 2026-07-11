# Async Systems

The biggest conceptual leap: work that happens later, elsewhere, and sometimes twice.

| Module | Tier | Effort | Covers |
|---|---|---|---|
| [Background Jobs & Workers](01-background-jobs-and-workers.md) | 🔴 must | ~2 wknds | job lifecycle, worker pools, concurrency limits, graceful shutdown |
| [Queues & Message Brokers](02-queues-and-message-brokers.md) | 🔴 must | ~2–3 wknds | build a queue from scratch; SQS vs RabbitMQ vs Kafka vs Redis Streams; ordering |
| [Retries, Backoff & DLQs](03-retries-backoff-and-dlqs.md) | 🔴 must | ~1 wknd | exponential backoff, jitter, dead-letter queues, poison messages |
| [Idempotency](04-idempotency.md) | 🔴 must | ~1 wknd | idempotency keys, dedup, why exactly-once is a lie you engineer around |
| [Scheduling & Cron](05-scheduling-and-cron.md) | 🟡 should | ~1 wknd | distributed cron, drift, overlap locks, missed-run policy |
| [Pub/Sub & Event Fanout](06-pub-sub-and-event-fanout.md) | 🟡 should | ~1 wknd | one event, many consumers; decoupling; event contracts |
| [Realtime: WebSockets & SSE](07-realtime-websockets-and-sse.md) | 🟡 should | ~2 wknds | connection lifecycle, presence, scaling stateful connections |
| [Notification Systems](08-notification-systems.md) | 🟡 should | ~2 wknds | the classic system: multi-channel, preferences, batching, digests |
| [Billing & Subscriptions](09-billing-and-subscriptions.md) | 🟡 should | ~2 wknds | Stripe webhooks done right, idempotent processing, metering, dunning |
