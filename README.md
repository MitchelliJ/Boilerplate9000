# Boilerplate9000

A structured vibe-coding workflow for Claude Code with TDD enforcement built in. Not using Claude Code? The raw prompts are in `.claude\skills`. Remove the Claude Code frontmatter and tag the files into any AI chat to follow the same workflow manually.

## How to use

Run these commands in order inside Claude Code:

### Initial Setup (Once)
1. `/spec` — Define your project and settle on a tech stack
2. `/coding-guidelines` — Set coding standards and generate a `COMMANDS.md` with your dev commands

### Feature Development (Repeat for each feature)
3. `/prd [feature]` — Write a Product Requirements Document, including test requirements for every functional requirement
4. `/tasks` — Break the PRD into a task list structured as RED → GREEN → REFACTOR blocks — tests come before implementation
5. `/go` — Implement the feature, working through the task list with TDD verification gates (must see tests fail before implementing, must see them pass before marking done)

### TDD Utilities
- `/tdd [unit]` — Drive a single function or class through strict RED-GREEN-REFACTOR interactively
- `/verify` — Run tests, lint, and typecheck and confirm everything passes before declaring anything done

> Each command saves its output to the `vibes/` directory, organized per feature. This serves as context and documentation and has the added benefit of being a time capsule!

![Kermit sipping coffee while vibe coding](r9soy.jpg)

✨I encourage you to fork this repo and customize the prompts to your own project needs and prompting style.

## TDD Principles

This workflow enforces test-driven development at every stage:

- **Tests are requirements** — every functional requirement in a PRD includes a test specification
- **RED before GREEN** — tasks are structured so a failing test must be confirmed before any implementation starts
- **Evidence, not claims** — `/go` requires pasting actual test output before marking a task done; "should work" is not acceptable
- **No regressions** — a newly broken test stops all forward progress until fixed
- **Iron Law** — no production code before a failing test, no exceptions

## Tips

- Take your sweet time to review the generated Project Spec and feature PRDs before running `/go`.
- `/go` auto-detects the latest PRD — pass a path as argument to target a specific one.
- Run `/go` in a fresh conversation for each new feature to avoid context pollution.
- Use `/tdd` when you want tighter, interactive control over a specific unit.
- Use `/verify` at the end of any session before committing.

## Connect With Me

- 💼 [LinkedIn](https://www.linkedin.com/in/michielberk/)
- 🐦 [Bluesky](https://bsky.app/profile/michielberk.com)
- 🌐 [Personal Website](https://michielberk.com/)

## Credits

This workflow is largely a personal evolution on the works of Harper Reed, Ryan Carson, David Dodda and Jesse Vincent. You can find their work here:
- https://harper.blog/2025/02/16/my-llm-codegen-workflow-atm/
- https://github.com/snarktank/ai-dev-tasks (the YouTube video is worth watching)
- https://blog.daviddodda.com/most-ai-code-is-garbage-heres-how-mine-isnt
- https://blog.fsck.com/