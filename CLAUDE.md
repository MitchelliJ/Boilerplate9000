# Boilerplate9000

## Vibe workflow

This project uses a vibe-coding workflow. Run these skills in order when starting a new project:

### Initial Setup (Once)
1. `/spec` — Interactive Q&A to define the project and tech stack. Saves to `vibes/spec-[name].md`.
2. `/coding-guidelines` — Generates coding conventions and command reference. Saves to `vibes/coding_guidelines.md` and `COMMANDS.md`.

### Feature Development (Repeat for each feature)
3. `/prd [feature description]` — Generates a Product Requirements Document for a feature, including test requirements for each functional requirement. Saves to `vibes/[N]. [Feature Name]/prd-[feature-name].md`.
4. `/tasks` — Generates a task list from a PRD. Tasks follow RED → GREEN → REFACTOR order — tests are written before implementation. Saves to the same folder as the PRD as `to-do-prd-[feature-name].md`.
5. `/go` — Implements the feature by working through the task list with TDD verification gates. Auto-detects the latest PRD and task file, or pass a path as argument.

### TDD Utilities (Use as needed)
- `/tdd [unit description]` — Drive a single function, class, or module through strict RED-GREEN-REFACTOR interactively.
- `/verify` — Run evidence-based verification (tests + lint + typecheck) before claiming anything is done.

Generated docs live in `vibes/`. When they exist, always read `vibes/spec-*.md`, `vibes/coding_guidelines.md`, and `COMMANDS.md` before writing code.

---

## Project context

> This project is freshly initialized — no spec or guidelines exist yet.
> Run `/spec` to get started, then `/coding-guidelines`.
>
> **After running those two skills**, replace this section with a 2–3 sentence summary of what this project does. Dev commands will be in `COMMANDS.md`.
