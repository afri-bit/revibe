---
plan_id: recursion-beginner
status: example
topic: Recursion
level: beginner
estimated_hours: 6
summary: A first principles tour of recursion — base cases, the call stack, and when recursion is the right tool.
generated_on: 2026-05-02
maintained_by: afri-bit
---

# Plan: Recursion from First Principles

## Goal

By the end, the learner will be able to:

- Explain in plain language what it means for a function to call itself, and why a base case is non-negotiable.
- Trace a small recursive call by hand, step by step, including how the call stack grows and unwinds.
- Decide when recursion is genuinely the right tool versus when iteration is clearer.
- Write and debug a small recursive function from scratch, in any language they already know.

## Modules

### Module 1: The shape of self-reference

- Lesson 1.1 — What "calling itself" actually means [status: not_started]
- Lesson 1.2 — Why a base case is the whole game [status: not_started]
- Lesson 1.3 — Tracing a call by hand: the stack diagram [status: not_started]
- ✅ Checkpoint 1: Trace `factorial(4)` on paper and explain each stack frame in your own words.

### Module 2: Reading recursion

- Lesson 2.1 — Spotting the recursive idea in a problem statement [status: not_started]
- Lesson 2.2 — Simple list problems: sum, length, contains [status: not_started]
- Lesson 2.3 — Off-by-one and infinite-recursion failure modes [status: not_started]
- ✅ Checkpoint 2: Given a buggy recursive function, identify whether the base case, the recursive step, or both are wrong — without running it.

### Module 3: Writing recursion

- Lesson 3.1 — The "trust the recursive call" mental move [status: not_started]
- Lesson 3.2 — Reverse a list, count nodes, flatten one level [status: not_started]
- Lesson 3.3 — When recursion is clearer than a loop (and when it isn't) [status: not_started]
- ✅ Checkpoint 3: Write `reverse(list)` recursively without looking up an example. Explain why your base case is correct.

### Module 4: Common patterns

- Lesson 4.1 — Tree traversal: the natural home of recursion [status: not_started]
- Lesson 4.2 — Divide and conquer in miniature: binary search [status: not_started]
- Lesson 4.3 — A taste of memoization: why repeated work matters [status: not_started]
- ✅ Checkpoint 4: Implement an in-order tree traversal recursively. Predict its output before running it.

## Capstone

Build a tiny **directory size calculator**. Given a path, return the total size of all files inside, recursing into subdirectories. Constraints:

- No loops over directory entries that aren't strictly necessary — the structure is recursive, so the code should be too.
- Handle empty directories and unreadable files without crashing.
- Be ready to explain how your function would behave on a directory with a 200-deep nesting (without trying it).

The Mentor must not write this code. The learner produces it; the Mentor reviews via questions only.
