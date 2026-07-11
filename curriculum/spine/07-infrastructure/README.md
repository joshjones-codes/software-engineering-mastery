# Infrastructure & Operations

Own the machine your code runs on and the path it takes to get there.

| Module | Tier | Effort | Covers |
|---|---|---|---|
| [Linux Fundamentals](01-linux-fundamentals.md) | 🔴 must | ~2 wknds | shell fluency, processes, permissions, systemd, signals, /proc |
| [Containers](02-containers.md) | 🔴 must | ~2 wknds | images, layers, namespaces/cgroups (what Docker actually is), Compose |
| [CI/CD](03-ci-cd.md) | 🔴 must | ~2 wknds | pipelines, environments, quality gates, rollbacks, deploy strategies |
| [Cloud Architecture (AWS)](04-cloud-architecture-aws.md) | 🔴 must | ~2–3 wknds | VPC, IAM, ALB, ECS vs Lambda, RDS, SQS/SNS/EventBridge — when each |
| [Infrastructure as Code](05-infrastructure-as-code.md) | 🟡 should | ~2 wknds | Terraform, state, drift, module design |
| [Observability](06-observability.md) | 🔴 must | ~2–3 wknds | metrics, distributed tracing, alerting, OpenTelemetry, intro SLOs |
| [Secrets Management](07-secrets-management.md) | 🟡 should | ~1 wknd | rotation, KMS, secret zero problem |
| [Backups & Disaster Recovery](08-backups-and-disaster-recovery.md) | 🟡 should | ~1 wknd | RPO/RTO, restore drills (a backup you haven't restored isn't a backup) |
| [Container Orchestration](09-container-orchestration.md) | 🟡 should | ~3–4 wknds | K8s concepts: scheduling, services, config, operators — orchestration first, kubectl second |
| [Cost Engineering](10-cost-engineering.md) | 🟡 should | ~1 wknd | unit economics, cost per feature, FinOps basics |
| [DNS, TLS & Domains in Practice](11-dns-tls-domains-in-practice.md) | 🟡 should | ~1 wknd | records, certs, renewal, propagation debugging |
