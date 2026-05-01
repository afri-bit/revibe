# Reference learning plans

This folder holds **reference plans** that contributors have crafted for specific topics. They are *not* the learner's active plan — the Mentor must ignore everything under `examples/` when looking for an active plan.

## When to use one

- A learner with a specific goal can read the example plans for inspiration before running `/revibe-start`.
- The Mentor may use them as a *starting point* during plan generation, but should still tailor the plan to the learner's intake answers (background, time available, learning style).
- Contributors who want to share their own plans should drop a new file here following the conventions below.

## Conventions

Every example plan must:

1. Use the same frontmatter schema as a generated plan, but with `status: example` and a `summary` field.
2. Be idempotent — copying it into `learning_plan/<filename>.md` and changing `status` to `active` should yield a usable plan with no further edits.
3. Have lessons sized for ~20–40 minute sessions. No multi-hour modules.
4. Stay focused on **one topic at one level** (e.g., recursion-beginner, not "all of CS").
5. End in a **capstone** — a small project that exercises every concept from the plan.

## Frontmatter

```yaml
---
plan_id: <topic>-<level>
status: example
topic: <e.g., Recursion>
level: <beginner | intermediate | advanced>
estimated_hours: <integer>
summary: <one-sentence description>
generated_on: <YYYY-MM-DD>
maintained_by: <github-handle>
---
```

## Current examples

| File | Topic | Level | Time |
|---|---|---|---|
| [`recursion-beginner.md`](recursion-beginner.md) | Recursion fundamentals | Beginner | ~6h |
