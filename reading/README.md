# Reading

## The spine sequence (in order, one at a time)

A deliberate progression — each book answers the question the previous one raises:

| # | Book | Question it answers | Pairs with |
|---|---|---|---|
| 1 | **Code** — Charles Petzold (2nd ed) | What *is* a computer? | Spine 1–2 · [Foundations 1](../curriculum/foundations/01-how-computers-work/README.md) |
| 2 | **Grokking Algorithms** — Aditya Bhargava | How do we solve problems on one? | Spine 2 · [Foundations 2](../curriculum/foundations/02-programming-and-algorithms/README.md) |
| 3 | **Operating Systems: Three Easy Pieces** — Arpaci-Dusseau ([free online](https://pages.cs.wisc.edu/~remzi/OSTEP/)) | How does one machine actually run programs? | Spine 3–4 · [Foundations 3](../curriculum/foundations/03-operating-systems/README.md) |
| 4 | **Computer Networking: A Top-Down Approach** — Kurose & Ross (selected chapters) | How do machines talk? | Spine 4–5 · [Foundations 4](../curriculum/foundations/04-networking/README.md) |
| 5 | **Designing Data-Intensive Applications** — Martin Kleppmann | How do thousands of machines work together? | Spine 5–6 · [Foundations 5](../curriculum/foundations/05-data-intensive-systems/README.md) |

**How to read:** 1–2 chapters per weekend, Saturday morning, notebook open. Summarize
each chapter in my own words before moving on. Don't rush — *Code* especially is about
building intuition, not coverage. Don't get stuck on every transistor either: the goal
is the abstraction-layer mental model, not CPU design.

## Shelf 2 — pulled in by specific stages

| Book | When |
|---|---|
| *The Algorithm Design Manual* — Skiena (selected chapters) | after Grokking, as reference |
| *Release It!* — Michael Nygard | Spine 5 (resilience patterns) |
| *System Design Interview vol 1–2* — Alex Xu | practice alongside Spine 4+, as drills not as source |
| *Building Microservices* — Sam Newman | Spine 5 → Advanced: architecture |
| *Understanding Distributed Systems* — Roberto Vitillo | lighter DDIA companion, Spine 5 |
| *Terraform: Up & Running* — Yevgeniy Brikman | Spine 7.5 |
| *Staff Engineer* — Will Larson | Advanced: staff engineering (not before) |

## Frontend shelf

| Resource | When |
|---|---|
| web.dev performance & rendering guides | FE 4 |
| *JavaScript: The New Toys* / *You Don't Know JS Yet* | FE 1.3 |
| React docs "under the hood" + JSConf Fiber talks | FE 2 |
| Every Layout (every-layout.dev) | FE 1.2 |

## Rules

- **One spine book at a time.** Supplements are allowed; parallel spine books are not.
- AWS/K8s/tool docs are read while building, never as "reading."
- Papers (Raft, Dynamo, Kafka, Spanner) enter at Spine 5 — one paper per module max.
