---
name: coding-guidelines
description: Generate coding and architecture guidelines for this project.
model: claude-opus-4-6
---

Act as an experienced project manager and software architect.

## Process

1. **Read existing spec:** If `vibes/spec-*.md` exists, read it as the starting point. Otherwise ask the user for a project description.
2. **Ask Clarifying Questions:** Ask numbered clarifying questions for each section of the structure below. Suggest suitable options with pros and cons but let the user decide. Wait for answers before generating.
3. **Document frequently used commands:** Suggest commands for starting the dev server, running the lint/typecheck/test suite, and any other frequently-used commands worth documenting. Also setup pre-commit hooks at this stage.
4. **Generate Coding Guidelines:** Using the structure below and the answers provided by the user, generate the full coding guidelines document.
5. **Generate COMMANDS.md:** Using the answers from step 3, generate a `COMMANDS.md` file. The first section should always include the commands to start server and a check command running required linters, typechecks and unit tests (if any).
6. **Save both files:**
   - Write coding guidelines to `vibes/coding_guidelines.md` — clear Markdown, distinct sections, concise and understandable for a junior developer.
   - Write commands reference to `COMMANDS.md` in the project root.

## Structure

- **Project Context** — Concise high-level description of what is being built.
- **Tech stack** — Organised in frontend, backend and database sections. Include frameworks, libraries, optionally a component library and managed services (if any) the project depends on. 
- **Setup and architectural conventions** — Code organization, module structure, where tests live, authentication & authorization architecture.
- **Coding Standards and Style** — Naming conventions, documentation and commenting standards, environment secrets, error handling.
- **Deployment standards** - Brief description on deployment strategy.
- **Changelog** — One line per change with timestamp (DD-MM-YYYY)

## COMMANDS.md structure

# Development
[what it does]
`[command]`

# Check (lint + typecheck + unit tests)
[what it does]
`[command]`

# Other
[what it does]
`[command]`
