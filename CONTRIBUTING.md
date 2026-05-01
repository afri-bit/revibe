# Contributing to Revibe

Revibe is intentionally tiny. The "product" is a handful of carefully written markdown files; almost every decision favors clarity and fidelity to the Mentor's Prime Directive over feature breadth.

That means contributions are welcome, but the bar for changes is unusual.

## Before you open a PR

- **Bug fixes & clarifications** — open an issue first describing what's broken or unclear, then send the PR.
- **New slash commands or workflow changes** — open an issue first to discuss the design. The slash-command surface is small on purpose.
- **Reference learning plans** — drop them in `learning_plan/examples/` following [the conventions in that folder's README](learning_plan/examples/README.md).
- **Wording tweaks to `revibe.agent.md`** — these change agent behavior, so be specific about *why* the new wording leads to a better learning outcome. Speculative rewrites will be closed.

## What stays out

- ❌ Application code, build systems, dependencies, package managers — Revibe is markdown.
- ❌ Pre-shipped curricula in the top-level `learning_plan/`. The agent generates plans for the learner; reference content goes under `examples/`.
- ❌ Anything that tempts the Mentor to give a direct answer. Read the [Prime Directive](.github/agents/revibe.agent.md#prime-directive-never-give-direct-answers) before proposing changes that touch the agent ruleset.

## Editing the Mentor ruleset

`.github/agents/revibe.agent.md` is the brain of the repo. When changing it:

1. Walk through every Hard Rule and Slash Command and confirm your change doesn't weaken any of them.
2. If your change adds a slash command, also add a `.github/prompts/revibe-<name>.prompt.md` file *and* update the README slash-command table.
3. If your change touches memory schema, also update `memory/MEMORY.md` to match (without losing the existing structure).

## Editing prompt files

Each `.github/prompts/revibe-*.prompt.md` is a thin layer that delegates to the agent ruleset. Keep them:

- **Short.** Five to fifteen lines of body.
- **Action-oriented.** They describe the *one* thing the slash command does.
- **Aligned.** Every prompt must end consistent with `revibe.agent.md`. If a prompt would contradict the ruleset, change the ruleset first or pick a different prompt.

## Style

- Markdown is rendered on GitHub; assume that as the baseline.
- Use sentence case in headings.
- Prefer short paragraphs over walls of text.
- Use code fences with explicit languages.
- Leave a blank line above and below every heading, list, and code fence.
- Run the markdown linter (`npx markdownlint-cli2 "**/*.md"`) before pushing if you're making large edits.

## Local checks

This repo has zero runtime, but CI runs two lints on every PR:

- **markdownlint** — catches structural markdown issues. Config: `.markdownlint.json`.
- **link checker** — catches broken internal and external links.

You can run the same checks locally:

```bash
npx markdownlint-cli2 "**/*.md" "#node_modules"
npx --yes markdown-link-check@3 -c .markdown-link-check.json -q -i node_modules .
```

Optional: copy `.vscode/settings.json.example` to `.vscode/settings.json` and install the recommended workspace extension (Markdownlint) for in-editor hints.

## Code of Conduct

By participating you agree to abide by the [Code of Conduct](CODE_OF_CONDUCT.md).

## Licensing

By contributing you agree your contributions will be released under the [MIT License](LICENSE).
