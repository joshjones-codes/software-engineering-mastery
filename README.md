# Software Engineering Mastery

A multi-year, first-principles curriculum for going from senior full-stack engineer to
systems engineer — built in public, one weekend at a time, with
[SlipCheck](https://slipcheck.pro) as the production laboratory.

**This is not a list of technologies to learn.** It's a map of the *problems* that
technologies exist to solve. Docker is one implementation of *containers*. Kafka is one
implementation of *distributed messaging*. Redis is one implementation of *caching*.
The curriculum teaches the concept; the tool is a detail.

## The premise

CRUD web development is being commoditized. What stays valuable is the ability to
design, build, and operate systems that keep working under scale, failure, and changing
requirements — and to explain *why* they're built the way they are. That ability is
built the same way it always has been: one deeply-understood concept at a time,
practiced against a real product with real users.

## How this repo works

```
ROADMAP.md            ← the map: 142 modules, 5 tracks, tiered must/should/nice
DEPENDENCY_GRAPH.md   ← what unlocks what
SYSTEMS_CATALOG.md    ← the ~50 reusable systems every mature SaaS is built from
curriculum/           ← one file per module (stubs until reached, authored when reached)
handbook/             ← MY accumulated knowledge — one chapter per COMPLETED module
reading/              ← the book sequence and how it pairs with the build track
templates/            ← the module template every authored module follows
progress/             ← one line per completed module
```

The **curriculum** is the map. The **handbook** is the territory — it only contains
chapters for modules I've actually completed, written in my own words with my own
diagrams, mistakes, and benchmarks. The curriculum was designed up front; the handbook
cannot be.

## The weekend loop

Every module runs the same cycle:

```
Read  →  Build  →  Integrate  →  Reflect  →  Teach
```

- **Read** — Saturday morning: the module's reading + current book chapters ([reading/](reading/README.md))
- **Build** — Saturday afternoon: the smallest version that works, from scratch
- **Integrate** — into SlipCheck, when it genuinely solves a product problem
- **Reflect** — handwritten notebook first, then a [handbook](handbook/README.md) chapter
- **Teach** — the handbook chapter, lightly edited, becomes a public post

A module is done when I can answer, without notes:

1. Why does this exist? What problem does it solve?
2. How would a naive solution fail?
3. How would I implement it myself?
4. Where does SlipCheck use it (or why doesn't it)?
5. How would I explain the tradeoffs in a Staff-level interview?

## The tracks

| Track | What | Cadence |
|---|---|---|
| [Spine](curriculum/spine/README.md) | 73 build modules in 8 stages, backend → distributed → infra → AI | primary — in order |
| [Foundations](curriculum/foundations/README.md) | 28 reading modules across 5 books | Saturday mornings, parallel |
| [Frontend](curriculum/frontend/README.md) | 21 depth modules — browser, React internals, performance | interleaved when relevant |
| [Practices](curriculum/practices/README.md) | 10 habits | every module, from day 1 |
| [Advanced](curriculum/advanced/README.md) | 10 areas | years 2+ — deliberately unplanned |

## Rules I hold myself to

1. **One module at a time.** The roadmap is a map, not a to-do list. 142 modules is not
   a wall to stare at — it's proof I never have to wonder what's next.
2. **Concepts before tools.** No module is "learn X framework."
3. **Build before adopting.** Write the toy version before installing the real one.
4. **Everything ties back to SlipCheck** when it honestly can. Production pressure is
   the best teacher.
5. **Every six months: one project designed with no AI architecture help.** AI as
   reviewer, not architect. That's the internalization test.
6. **Skipping a weekend is fine.** The streak that matters is measured in months.

## Where I'm starting from

~5 years professional full-stack (React/Next.js, Node, TypeScript, PostgreSQL, AWS),
currently building SlipCheck — a compliance SaaS for snow-removal contractors.
Strong at shipping products; this curriculum is about understanding the layer beneath
everything I ship.

**Start here → [Module 1: API Design Fundamentals](curriculum/spine/01-production-backend/01-api-design-fundamentals.md)**
