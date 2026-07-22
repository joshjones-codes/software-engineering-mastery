# API Design Fundamentals

> **Track:** Spine · **Stage:** 1 — Production Backend · **Tier:** 🔴 must · **Effort:** ~1 wknd · **Status:** 📖 authored — start here
> **Prerequisites:** none — this is Module 1
> **Paired reading:** *Code* ch. 1–4 (Saturday morning — unrelated on purpose; it's the parallel track)

## Why does this exist?

An API is a *contract between strangers across time*. The consumer might be your own
frontend today, a mobile app next year, a customer's integration in year three — and
every one of them will depend on decisions you made before they existed. Bad API design
isn't a style problem; it's a **compounding cost problem**: every inconsistent endpoint
becomes something every future consumer must special-case, forever, because you can't
change a published contract without breaking someone.

The concept exists because two parties who can't coordinate in real time (your server
team and every current-and-future client) need a shared, stable, predictable language.
Everything in this module — resource modeling, status codes, error shapes — is just
mechanisms for making that language predictable.

## Mental model

**An API is a set of nouns (resources) that a small fixed set of verbs (HTTP methods)
act on.** The design work is almost entirely in choosing the nouns.

```
        the fixed verbs                 your nouns
  GET / POST / PATCH / DELETE   ×   /merchants /couriers /deliveries /photos
                    │
                    ▼
     predictable grid of behavior:
     if you know how ONE resource works,
     you know how ALL of them work
```

The test of a good API: a consumer who has seen two of your endpoints can correctly
*guess* the third. Predictability **is** the product.

## Vocabulary

- **Resource** — a noun worth addressing: `delivery`, not `completeDelivery`. Resources
  are things; behavior comes from methods applied to things.
- **Collection vs item** — `/deliveries` vs `/deliveries/:id`. Plural collections, always.
- **Idempotent** — calling it twice = calling it once (GET, PUT, DELETE; *not* POST).
  This word returns in Spine 4.4 with much higher stakes.
- **Safe** — no state change at all (GET, HEAD). Safe implies idempotent, not vice versa.
- **Representation** — the JSON is not the resource; it's one representation of it.
  This is why the same resource can appear with different shapes (list vs detail).
- **Contract** — everything a consumer can observe: paths, shapes, status codes,
  error formats, ordering. If they can observe it, they will depend on it
  ([Hyrum's Law](https://www.hyrumslaw.com/)).

## First principles: the naive solution

How past-me built APIs — endpoints named after UI actions, added in the order features
shipped:

```
POST /api/assignDelivery
GET  /api/getCourierDeliveries?courierId=7
POST /api/markDelivered
GET  /api/dashboardData
POST /api/uploadProofPhoto
```

Where it fails, precisely:

1. **Nothing is guessable.** Is it `getCourierDeliveries` or `deliveriesForCourier`?
   Every consumer memorizes every endpoint. The API surface grows O(features), and so
   does the documentation burden.
2. **`/dashboardData` couples the API to one screen.** When the dashboard changes, the
   endpoint changes — now the API versions at the speed of the UI. (This is the actual
   argument that produced GraphQL; see tradeoffs.)
3. **Verbs in URLs duplicate what HTTP already provides**, so error semantics drift:
   one endpoint returns `200 {"error": true}`, another `500` with HTML, depending on
   who wrote it and when.
4. **No consistent error shape** means every consumer writes per-endpoint error
   handling. This is the single most expensive failure in practice — clients end up
   with `catch { toast("Something went wrong") }` because parsing errors reliably is
   impossible.

The naive approach isn't wrong because it's ugly. It's wrong because **every
inconsistency is a permanent tax on every future consumer**.

## The industry solution

Resource-oriented design over plain HTTP semantics. The playbook, distilled from the
[Stripe](https://stripe.com/docs/api), [GitHub](https://docs.github.com/en/rest), and
[Google AIP](https://google.aip.dev/) API guidelines — three shops that publish theirs
precisely because consistency is the product:

**1. Model the nouns first.** Worked example — a last-mile delivery platform
(the example domain used throughout the curriculum):

```
merchants ─┬─ locations
           ├─ couriers
           └─ deliveries ──── proof-photos
              (courier × location × time)
```

**2. Uniform grid of operations:**

```
GET    /v1/deliveries           list (paginated, filterable)
POST   /v1/deliveries           create
GET    /v1/deliveries/:id       fetch one
PATCH  /v1/deliveries/:id       partial update
DELETE /v1/deliveries/:id       delete (or state transition — see below)
```

**3. Sub-resources only where the child can't exist alone:**
`/deliveries/:id/photos` — a proof-of-delivery photo of nothing is meaningless. But
deliveries get a top-level collection even though they belong to merchants, because the
product queries them across merchants ("all of today's deliveries"). **Access patterns,
not just ownership, decide the URL shape.**

**4. Status codes as contract, small fixed palette:** `200/201/204` success;
`400` malformed, `401` who are you, `403` not allowed, `404` doesn't exist *(also:
exists but you may not know that — return 404 not 403 for cross-tenant probes)*,
`409` conflict, `422` understood but invalid, `429` slow down, `5xx` our fault.

**5. One error envelope everywhere** (this module's highest-leverage decision):

```json
{
  "error": {
    "type": "validation_error",
    "message": "delivered_at must be in the past",
    "field": "delivered_at",
    "request_id": "req_8fk2j1"
  }
}
```

Machine-readable `type` for client logic, `message` for humans, `request_id` to join
against logs (pays off in Spine 1.8 and 7.6). RFC 9457 (*Problem Details*) is the
standardized version of this idea.

**6. State transitions as actions, not fake resources.** When something genuinely isn't
CRUD — completing a delivery, say — Stripe's convention:
`POST /v1/deliveries/:id/complete`. A verb, deliberately, marking "this is a
transition with rules," rather than pretending `PATCH {status: "complete"}` has no
side effects.

## Tradeoffs

- **REST-ish resources vs RPC:** resource design costs you expressiveness for
  predictability. Internal service-to-service calls often *should* be RPC (gRPC, Spine
  6.4 territory) — the uniform-interface argument is strongest at the *public* boundary
  where consumers are strangers.
- **vs GraphQL:** GraphQL solves real problems (per-view data shaping, N screens × M
  clients) at the cost of caching complexity, query cost control, and a heavier
  server. A product with one first-party web client is buying flexibility it doesn't
  need — GraphQL's benefits don't clear its costs there. *Knowing why you're NOT
  using something is the senior answer.*
- **Purity vs pragmatism:** a `/dashboard` aggregate endpoint is fine *as an explicit,
  named exception* (a "view resource") — the sin isn't the aggregate, it's the whole
  API being accidental aggregates.
- **When resource-orientation is the wrong choice:** genuinely action-centric domains
  (a calculation service), streaming, and batch pipelines. Fixed verbs fit poorly;
  don't force them.

## Build it

**Weekend project:** design-first, then implement, no framework magic.

1. Write `openapi.yaml` for the lab product's four core resources (the worked example
   uses `merchants`, `couriers`, `deliveries`, `proof-photos`) — *before* any code.
   Every endpoint, every status code, the error envelope, list/detail representations.
2. Implement two of them on **raw Node `http`** — no Express. Hand-roll: router,
   JSON body parsing with size limit, error envelope middleware, 405 for wrong
   methods (a detail frameworks hide).
3. Torture-test the contract: wrong method, malformed JSON, unknown fields, trailing
   slash, `Accept: text/html`, 10 MB body. Every response must still be the envelope.

What building on raw `http` teaches that Express hides: content-type negotiation is
your job, 405 vs 404 is a real decision, and "middleware" is just an array of
functions you fold over a request.

## Lab integration

Two paths, depending on what the lab looks like when you get here:

**Greenfield (the stronger version):** the contract exists before the first route does.
Write `ADR-001: API conventions` — the error envelope, resource naming, status-code
palette, pagination placeholder (Spine 1.5 fills it in) — and hold every route to it
from day one. You get the Stripe property (uniformity) for free, because there's
nothing to migrate.

**Brownfield:** the audit. An API that grew feature-by-feature — mixed conventions,
some routes returning `{ data }`, some bare objects, error shapes varying by
author-date — is exactly the naive solution above, and it's normal: it's what shipping
fast looks like. The integration is an **audit + ADR**, not a rewrite:

1. Inventory every route handler into a table: path, method, request/response shape,
   error shape, status codes used.
2. Write the same `ADR-001: API conventions`.
3. Migrate the two worst offenders to the convention; leave the rest for
   opportunistic migration (expand–contract discipline arrives properly in Spine 2.5).

Why it matters by scale:

- At **1 customer**: none of this matters. That's why brownfield APIs look the way they do.
- At **100 customers**: the first external integration request arrives ("can we pull
  your events into our system?") and the contract becomes a product surface.
- At **10,000**: you're Stripe — you publish your API guidelines because hundreds of
  integrations depend on your consistency, and versioning (Spine 1.9) is a
  full-time concern.

## System design exercise

*Design the public API for a last-mile delivery platform: merchants, couriers,
deliveries with GPS + photo proof-of-delivery, and enterprise merchants pulling
delivery reports. End customers tracking a package are read-only third parties;
merchants are read-write first parties.*

Work through: resource model, whose-view-is-it problems (a "delivery" to a merchant vs
to the end customer — does the customer see the courier's name? the merchant's cost?),
auth boundary (foreshadows 1.3/1.4), and what you'd version from day one.
Back-of-envelope: 2,000 couriers × 30 deliveries/day ≈ 60k writes/day — trivially
small (~0.7 rps average, maybe 20 rps lunch-rush peak), which is itself the design
insight: **this API's constraint is contract quality, not throughput.** Numbers before
architecture.

## Interview questions

1. **PUT vs PATCH vs POST?** — PUT replaces (idempotent), PATCH partially updates
   (not guaranteed idempotent), POST creates/acts (not idempotent). Idempotency is
   the load-bearing distinction: it determines what's safe to retry — which is why it
   returns with money attached in Spine 4.4.
2. **404 vs 403 for a resource in another tenant?** — 404. A 403 confirms existence;
   that's an information leak across a tenant boundary (GitHub does this for private
   repos).
3. **Where do actions that aren't CRUD go?** — `POST /resource/:id/verb` as an explicit
   state transition, or model the *result* as a resource (`POST /refunds` rather than
   `POST /payments/:id/refund` — Stripe chose the resource).
4. **Why is a consistent error shape more valuable than good error messages?** —
   Messages help humans once; shapes let every client handle every error
   programmatically forever. Consistency compounds, prose doesn't.
5. **When would you choose GraphQL?** — Many clients with divergent data needs per
   view (mobile + web + partners), willing to pay in caching complexity and query
   cost control. One first-party client = you're buying flexibility you don't need.

## Common mistakes

- Designing endpoints after screens (`/dashboardData`) — couples API lifetime to UI
  lifetime.
- Returning `200` with `{"success": false}` — breaks every HTTP-aware layer between
  the client and you (caches, proxies, monitoring, retry logic).
- `403` where `404` belongs across tenant boundaries (information leak).
- Nesting by ownership instead of access pattern (`/merchants/:id/locations/:id/deliveries/:id`
  — three IDs to fetch one thing that has a unique ID).
- Treating the error format as "we'll standardize it later." Later means after
  consumers have parsed all five accidental formats.
- Bikeshedding REST purity (HATEOAS debates) instead of shipping a boring, consistent
  contract. Stripe is not "RESTful"; Stripe is *predictable*.

## Reading

- [Stripe API reference](https://stripe.com/docs/api) — read it as a *design artifact*:
  notice what's identical across every resource.
- [Google AIPs](https://google.aip.dev/) — AIP-121 through AIP-135 are the distilled
  resource-design rules.
- RFC 9457 — Problem Details for HTTP APIs.
- [Hyrum's Law](https://www.hyrumslaw.com/) — why every observable behavior is contract.

## Mastery checklist

- [ ] Can explain the problem without naming a technology ("contract between strangers across time")
- [ ] Can draw the verbs × nouns grid from memory
- [ ] Wrote the OpenAPI spec before code — [link]
- [ ] Built two resources on raw Node `http` — [link]
- [ ] Lab: ADR-001 (API conventions) merged + first two resources living by it — [link]
- [ ] Wrote the handbook chapter — [link]
- [ ] Can answer all five interview questions cold

## Reflection

*(written after completion — see [handbook contract](../../../handbook/README.md))*
