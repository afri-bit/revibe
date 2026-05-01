# Revibe 🎧

<div align="center">

<img src=".docs/img/revibe.svg" alt="Revibe logo" width="50%"/>


### *Stop vibe-coding. Start understanding.*

**An AI mentor that refuses to write your code — and that's the whole point.**

[![GitHub stars](https://img.shields.io/github/stars/afri-bit/revibe?style=social)](https://github.com/afri-bit/revibe)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Made for Copilot](https://img.shields.io/badge/Made%20for-GitHub%20Copilot-181717?logo=github)](https://github.com/features/copilot)

</div>

## What is Revibe?

**Revibe** turns your AI coding agent into a **patient programming teacher** — one that hands you questions instead of answers, builds you a personalized learning plan, and remembers your progress in plain markdown.

It's a clone-and-go repository. No accounts, no servers, no subscriptions beyond what you already have. The whole "product" is a handful of carefully written markdown files that teach your agent how to teach you.

## Who is This for?

**Revibe** is built for developers who can already write *some* code but feel like AI autocomplete has hollowed out their fundamentals. The "I shipped it but I don't really understand it" crowd. If that's you, welcome.

It also works for committed beginners who already have a code editor set up — just expect more friction than a tutorial site.

It is **not** built for people who want code generated faster. Use Copilot the normal way for that.

## How it works

```
You: /revibe-start

Revibe: Hey — before we dive in, what do you want to be able to
        build by the end of this? And what's pulled you toward
        learning it?

You: I want to actually understand recursion. I keep using it
     but every time I write one it feels like guessing.

Revibe: Got it. Let me ask you a few things to figure out where
        to start. No right answers, no scoring — just calibrating.

        First one: in your own words, what does it mean for a
        function to "call itself"?
```

…and from there, a real learning plan generated for *you*, lessons one concept at a time, exercises you actually attempt before any feedback, and progress saved between sessions.

## Quick start

```bash
git clone git@github.com:afri-bit/revibe.git my-learning-journey
cd my-learning-journey
code .
```

Then in GitHub Copilot Chat:

1. Click the agent dropdown next to the chat input.
2. Select **`revibe`**.
3. Type `/revibe-start` and press enter.

That's it. The agent runs intake, gauges where you are, generates a learning plan, and starts teaching.

When you're done for the day:

```
/revibe-pause
```

Come back tomorrow, run `/revibe-start`, and pick up exactly where you left off.

## Slash commands

| Command | What it does |
|---|---|
| `/revibe-start` | Begin or resume a session |
| `/revibe-pause` | End the session and save progress |
| `/revibe-status` | Show where you are in your plan |
| `/revibe-review <topic>` | Revisit a past concept |
| `/revibe-skip <reason>` | Skip the current lesson |
| `/revibe-reveal <reason>` | Force-show a solution (rare; you'll redo a similar one) |
| `/revibe-replan` | Adjust the plan if it isn't fitting |
| `/revibe-exit` | End the course entirely |

## Prerequisites

You need:

- **[Visual Studio Code](https://code.visualstudio.com/)** (free)
- **[GitHub Copilot](https://github.com/features/copilot)** subscription — Free, Pro, Pro+, or Student all work
- **Git** installed locally
- A terminal you can clone a repo from

That's the whole setup tax. If you've never cloned a repo before, you'll spend ~15 minutes getting set up before your first lesson. That's real friction — but it's also the last time you'll need to do it.

> **Heads up:** Revibe assumes you're comfortable enough with basic dev tooling to clone and open a repository. If that part is itself new, [Replit](https://replit.com) or a beginner YouTube course will get you coding faster. Come back to Revibe once you've outgrown those.

## Recommended model

Revibe relies on the agent following a strict set of rules — most importantly, *never giving direct answers*. Models that follow nuanced instructions reliably do the best job. We recommend, in order:

| Model | Why | Plan availability |
|---|---|---|
| **Claude Sonnet 4.6** ⭐ | Best at following the "don't give answers" rule and staying in the Mentor persona | Copilot Pro / Pro+ |
| **Claude Opus 4.7** | Even stronger reasoning; slower and more expensive | Copilot Pro+ |
| **GPT-5.2** | Solid all-rounder; occasionally slips and shows code | Copilot Pro / Pro+ |
| **Auto mode** | Falls back when nothing else is selected | All plans (incl. Free / Student) |

> [!WARNING]  
> If you're on the Free or Student plan, Claude models aren't directly selectable — Auto mode will mix them in, but expect more variance in how strictly the Mentor sticks to its rules.

To switch models in Copilot Chat, click the model name at the bottom of the chat panel and pick from the list.

## Works with

- ✅ **GitHub Copilot Chat** (VS Code) — primary target
- ✅ **Claude Code** — reads `AGENTS.md` automatically
- ✅ **Cursor** — reads `AGENTS.md` automatically
- ⚠️ **Inline autocomplete (ghost text)** — can't be controlled by `AGENTS.md` rules. While doing exercises, prefer Copilot Chat over inline suggestions, or temporarily disable inline suggestions (`Ctrl+Shift+P` → "Toggle Copilot Suggestions").

## Project structure

```
revibe/
├── README.md                                ← you are here
├── AGENTS.md                                ← always-on cross-agent instructions
├── CONTRIBUTING.md                          ← how to propose changes
├── CODE_OF_CONDUCT.md                       ← Contributor Covenant
├── SECURITY.md                              ← how to report concerns
├── CHANGELOG.md                             ← user-facing change log
├── memory/
│   └── MEMORY.md                            ← your profile + progress (built up as you learn)
├── learning_plan/                           ← your plan lives here (generated, not pre-shipped)
│   ├── README.md                            ← how personal plans vs examples differ
│   └── examples/                            ← reference plans contributors can crib from
└── .github/
    ├── workflows/
    │   └── ci.yml                           ← markdown lint + link checks on PRs
    ├── agents/
    │   └── revibe.agent.md                  ← the Mentor's full ruleset
    └── prompts/
        ├── revibe-start.prompt.md           ← /revibe-start
        ├── revibe-pause.prompt.md           ← /revibe-pause
        ├── revibe-status.prompt.md          ← /revibe-status
        ├── revibe-review.prompt.md          ← /revibe-review
        ├── revibe-skip.prompt.md            ← /revibe-skip
        ├── revibe-reveal.prompt.md          ← /revibe-reveal
        ├── revibe-replan.prompt.md          ← /revibe-replan
        └── revibe-exit.prompt.md            ← /revibe-exit
```

## Philosophy

Three rules, in order of importance:

1. **Never write the answer.** Hints, questions, partial pseudocode — yes. Working solutions — no.
2. **One concept per response.** No information dumps.
3. **Progress is real, not invented.** A concept counts as "learned" only when you can explain *why* your solution works, not just that it does.

The Mentor follows these even when you push back. *Especially* when you push back.

## What Revibe is **not**

- ❌ Not a code generator
- ❌ Not a curriculum site with pre-built content
- ❌ Not a replacement for actually writing code yourself
- ❌ Not magic — if you don't put in the work, it can't help you

## Contributing

Revibe is intentionally tiny. Before opening a PR:

- Bug fixes and clarifications: open an issue first.
- New slash commands or workflow changes: discuss in an issue first — we're protective of the small surface area.
- Reference learning plans (well-crafted plans for specific topics): very welcome — drop them in `learning_plan/examples/`.

## License

[MIT](LICENSE) — fork it, remix it, build your own version.

---

<div align="center">

*Built for developers who'd rather understand than ship.*

</div>
