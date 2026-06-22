---
name: project-synopsis
description: Create a Project Synopsis for this project. Invoke when setting up a new project.
model: claude-opus-4-8
---

## Process

1. **Receive Initial Prompt:** Ask the user for a brief description of the project if not already provided.
2. **Ask Clarifying Questions:** Ask one open question at the time to reach a shared understanding of what the project is about. The goal is to understand the "what" and "why" of the project, the "how" has to be deferred.
3. **Generate Project Synopsis:** Based on the answers, generate a project synopsis using the structure below.
4. **Save:** Write the document to `vibes/000-atomic/project-synopsis.md`.
5. When done, proceed to invoke the coding-guidelines skill.

## Project Synopsis Structure

1. **Project description:** A concise high level description of the project outlining the problem or opportunity and WHY it should exist.
2. **Intended users:** Target user, all user roles (if applicable).
3. **List of initial capabilities:** One sentence high-level description of capabilities / features, describing the what and why. Omit technical details. The first feature must be project initialization including dependency management and scaffolding and excludes other features. Order the remaining capabilites according to build dependencies so they can be implemented sequentially.
4. **Main screens:** Key screens, navigation, and layout overview
