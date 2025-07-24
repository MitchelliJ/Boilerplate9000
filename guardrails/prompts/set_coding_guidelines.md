Act as an experienced project manager and software architect. Help me flesh out the coding guidelines for this project.

## Purpose
The generated document will serve as a foundational reference for our development team, ensuring quality, consistency, maintainability, and good documentation of the codebase.

## Process

1.  **Receive Initial Prompt:** The user provides a description outlining the project.
2.  **Ask Clarifying Questions:** Before writing the Coding Guidelines, you *must* ask clarifying questions. The goal is to make the right choices for the project. When appropriate, suggest suitable options.
3.  **Generate Coding Guidelines:** Based on the initial prompt and the user's answers to the clarifying questions, generate the Coding Guidelines using the structure outlined below.
4.  **Save Coding Guidelines:** Save the generated document as `coding_guidelines.md` inside the `/reference` directory.

## Sections to cover in the Coding Guidelines

- Project Context
   We are building [short high level project description]

- Tech stack to be used
   - Selection of frontend and backend frameworks
   - Necessary libraries and dependencies
   - Optional use of frontend component libraries

- Setup and architectural conventions:
   - Preferred code organization structure
   - Module organization and dependency management
   - Scalability and maintainability
   - Security, performance, or accessibility concerns
   - Regulatory or compliance requirements

- Coding Standards and Style
   - Naming conventions (variables, methods, classes, etc)
   - Code commenting conventions
   - Management of environment variable secrets
   - Error handling and logging
   - Monitoring

- Tooling guidelines
   - Best practices for our use case for all to be used frameworks, libraries and tools

- Testing standards //to be expanded

- Deployment standards //to be expanded

- Change log
   When changing or updating this document, append one line outlining the change in one sentence with a timestamp (DD-MM-YYYY)

## Deliverable
Provide the document formatted in clear Markdown with distinct sections, making it easy to update. The document should be clear, concise, and easy to understand - even for a junior developer.
Include a section at the end with a changelog of one line per change, and keep this up to date.