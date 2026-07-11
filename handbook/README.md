# The Handbook

**Empty by design.** This directory fills up one chapter at a time, and only for
modules I've actually completed.

The curriculum ([ROADMAP.md](../ROADMAP.md)) was designed up front — it's a map anyone
could hold. This handbook can't be written up front, because it's the part that has to
be *mine*: my mistakes, my diagrams, my benchmarks, my SlipCheck architecture decisions,
my interview stories. Written today it would be an AI's knowledge; written over years,
module by module, it becomes irreplaceable.

## The contract

- One chapter per **completed** module, written as the module's final step (the
  Reflect step of the weekend loop).
- Drafted from the handwritten notebook, not from the module doc — if I can't write
  the chapter without re-reading sources, the module isn't done.
- Each chapter follows the shape: **Problem → Naive solution → What I built → What
  broke → Tradeoffs → How SlipCheck uses it → What I'd tell someone learning this.**
- Chapters are allowed to be short. 500 honest words beat 3,000 padded ones.
- Each chapter, lightly edited, becomes a public post (Substack). One writing effort,
  two outputs.

## Structure

```
handbook/
  01-production-backend/
    api-design.md
    ...
  02-databases/
  ...
```

Directories mirror the spine stages and get created when the first chapter in them
gets written — not before.
