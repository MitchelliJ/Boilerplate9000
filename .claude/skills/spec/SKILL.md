---
name: spec
description: Create a Project Specification for this project.
model: claude-opus-4-6
---

Your skill instructions here...

## Process

1. **Receive Initial Prompt:** Ask the user for a brief description of the project if not already provided.
2. **Ask Clarifying Questions — Project Details:** Ask numbered multiple-choice questions (a, b, c…) to gather enough detail for a comprehensive project description. Format each answer on its own line. Wait for the user to answer before continuing.
3. **Ask Clarifying Questions — Tech Stack:** Ask a second set of numbered questions about the tech stack. Suggest libraries and frameworks that are a natural fit for the project and explain briefly why. Respect the user's preferences.
4. **Generate Spec:** Based on the answers, generate a spec using the structure below.
5. **Save:** Write the document to `vibes/spec-[project-name].md` (e.g. `vibes/spec-banking-app.md`).

## Spec Structure

1. **Project description:** A comprehensive and concise description of the project
2. **Intended users:** Primary and secondary users
3. **Feature list:** High-level features, one sentence each. The first feature is always project initialization including dependency management and scaffolding.
4. **Main screens:** Key screens, navigation, and layout overview
5. **Tech stack:** The chosen tech stack with brief justification for each choice
