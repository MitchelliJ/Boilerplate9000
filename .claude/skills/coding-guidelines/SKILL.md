---
name: coding-guidelines
description: Generate coding and architecture guidelines for this project.
model: claude-opus-4-8
---

Act as an experienced project manager and software architect.

## Process

1. **Read existing project synopsis at `vibes/000-atomic/project-synopsis.md`.** If no project synopsis is found, ask the user for one.
2. **Ask Clarifying Questions:** Interview the user relentlessly about the plan until a shared understanding is reached. Resolve each decision required for the structure below. Ask questions one at the time, suggest suitable options with pros and cons and let the user decide. Label questions 1., 2., 3., et cetera. Label suitable options A., B., C., et cetera. If a question can be answered by exploring the codebase, explore the codebase instead.
3. **Document frequently used commands:** Suggest commands for starting the dev server, running the lint/typecheck/test suite, and any other frequently-used commands worth documenting and save these to `COMMANDS.md` in the project root. The first section should always include the commands to start server and a check command running required linters, typechecks and unit tests (if any). Also document a standalone lint + typecheck command (static checks only, no tests) that the `go` skill runs as a phase gate after each parent task. Setup pre-commit hooks based on user preferences if relevant.
4. **Generate Coding Guidelines:** Using the answers provided by the user, generate the coding guidelines document following the structure below. Save coding guidelines to `vibes/000-atomic/coding-guidelines.md`. Use clear Markdown, distinct sections, write concise and understandable for a junior developer.

## coding-guidelines.md Structure

- **IMPORTANT:** This is a living, project-wide reference that defines rules and conventions governing architecture, structure, style, naming, testing, dependencies and development practices. This serves to ensure consistency, maintainability and predictable decision-making across the project. It must remain continuously updated to reflect the current state of the codebase, tooling and engineering standards. It serves as authoritative source of truth for implementation practices.
- **Tech stack** — Chosen tech stack with brief justification for each choice. Organised in frontend, backend and database sections. Include relevant frameworks, (component) libraries, managed services (if any) and other dependencies chosen by the user.
- **Setup and architectural conventions** — Code organization, module structure, where tests live, authentication & authorization architecture.
- **Coding Standards and Style** — Naming conventions, documentation and commenting standards, environment secrets, error handling.
- **Deployment** - Brief description on deployment strategy.
- **Changelog** — One line per change with timestamp (DD-MM-YYYY)

## COMMANDS.md structure

# Development

[what it does]
`[command]`

# Check (lint + typecheck + unit tests)

[what it does]
`[command]`

# Lint & Typecheck (phase gate)

[what it does]
`[command]`

# Other

[what it does]
`[command]`
