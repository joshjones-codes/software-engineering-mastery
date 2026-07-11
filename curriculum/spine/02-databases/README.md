# Databases

Go from 'uses Postgres' to understanding what the database is doing and why.

| Module | Tier | Effort | Covers |
|---|---|---|---|
| [SQL Mastery](01-sql-mastery.md) | 🔴 must | ~2 wknds | joins, aggregations, window functions, CTEs, EXPLAIN as a habit |
| [Indexes & Query Optimization](02-indexes-and-query-optimization.md) | 🔴 must | ~2 wknds | B-tree mechanics, composite/covering/partial indexes, reading query plans |
| [Transactions & Isolation](03-transactions-and-isolation.md) | 🔴 must | ~2 wknds | ACID, isolation levels, anomalies, optimistic vs pessimistic locking |
| [Data Modeling & Constraints](04-data-modeling-and-constraints.md) | 🔴 must | ~1 wknd | normalization vs denormalization, foreign keys, integrity in the DB not just the app |
| [Migrations](05-migrations.md) | 🔴 must | ~1 wknd | expand–contract, zero-downtime migrations, backfill strategies |
| [Connection Pooling](06-connection-pooling.md) | 🟡 should | ~1 wknd | pool sizing, serverless vs pooled, pgBouncer |
| [Replication & Read Replicas](07-replication-and-read-replicas.md) | 🟡 should | ~2 wknds | replication lag, read-your-writes, routing reads |
| [Audit Tables & Soft Deletes](08-audit-tables-and-soft-deletes.md) | 🟡 should | ~1 wknd | immutable history, temporal data, compliance-grade audit trails |
| [NoSQL & Alternative Models](09-nosql-and-alternative-models.md) | ⚪ nice | ~1 wknd | document/KV/wide-column, when relational stops fitting |
