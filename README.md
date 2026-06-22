# Boilerplate9000

A structured vibe-coding workflow for Claude Code combining spec driven development with test driven development (TDD) using subagents to manage context.

![Kermit sipping coffee while vibe coding](r9soy.jpg)

## How to use

Run these commands in order inside Claude Code:

### Initial Setup (Once)
1. `/project-synopsis` — Define what your project (the "what" and "why")
2. `/coding-guidelines` — Settle on your tech stack, set coding standards, and generate a `COMMANDS.md` with your dev commands (also used in skills).

### Feature Development (Repeat for each feature)
3. `/prd [feature]` — Co-create a Product Requirements Document, including test requirements for a feature
4. `/create-tasks` — Break the PRD into a task list structured as RED → GREEN → REFACTOR blocks
5. `/go` — Implement the feature through the task list with test driven development verification gates

### How `/go` works

`/go` runs as an **orchestrator** that never writes code itself — it spawns specialist subagents and owns all verification via bash commands:

- **`write-test`** writes one focused failing test for a single behavior (RED). It can't run anything as it has no access to bash.
- **`write-code`** writes the minimal code to make a failing test pass (GREEN), or refactors without changing behavior. It can't run anything as it also has no access to bash.
- **The orchestrator** `/go` runs every test, lint, and typecheck itself with the bash tool, gates on the actual output, and only then marks a task done.

This write/verify separation means no task is ever marked complete on reasoning alone — only on test output created by the orchestrator using bash to run unit tests. It also enforces strict TDD discipline.

> Each command saves its output to the `vibes/` directory, organized per feature. This serves as context for skills and agents and serves as documentation. It has the added benefit of being a time capsule!

## Tips

- Take your time to review the generated Project Synopsis and feature PRDs before running `/go`.
- `/go` auto-detects the latest PRD — pass a path as argument to target a specific one.
- Run `/go` in a fresh conversation or after compacting for each new feature to avoid context window limits.
- ✨I encourage you to fork this repo and customize the prompts to your own project needs and prompting style.

## Connect With Me

- 💼 [LinkedIn](https://www.linkedin.com/in/michielberk/)
- 🐦 [Bluesky](https://bsky.app/profile/michielberk.com)
- 🌐 [Personal Website](https://michielberk.com/)

## Credits

This workflow is largely a personal evolution on the works of Harper Reed, Ryan Carson, David Dodda, Jesse Vincent, and Tabish Bidiwale and others. You can find their work here:
- https://harper.blog/2025/02/16/my-llm-codegen-workflow-atm/
- https://github.com/snarktank/ai-dev-tasks (the YouTube video is worth watching)
- https://blog.daviddodda.com/most-ai-code-is-garbage-heres-how-mine-isnt
- https://blog.fsck.com/
- https://github.com/Fission-AI/OpenSpec
