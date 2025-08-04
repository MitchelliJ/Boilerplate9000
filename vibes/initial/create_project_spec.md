## Goal
To guide an AI assistant in creating a high-level Project Spec (spec) based on the initial user prompt. The spec will contain the to-be-used tech stack. It is required to be formatted in markdown and saved to the /reference directory in the root of the project with the filename '[project-name]-spec.md' (e.g., 'banking-app-spec.md').

## Process

1.  **Receive Initial Prompt:** The user provides a brief description for the overall project.
2.  **Ask Clarifying Questions to gather details:** Before writing the spec, the AI *must* ask clarifying questions to gather sufficient detail. The goal is to gather enough input to create a comprehensive project description. Number each question and have answers be multiple choice (a b c etc). Format this nicely with each answer on a new line.
3.  **Pause to ingest answers to clarifying questions** Let the user answer the clarifying questions first, then proceed to clarifying the tech stack.
3.  **Ask Clarifying Questions on Tech Stack:** Then the AI *must* ask clarifying questions to settle on the tech stack. Suggest libraries and frameworks that are a natural fit for the project and explain why they should be considered, but respect the users preferences.
4.  **Generate spec:** Based on the initial prompt and the user's answers to the clarifying questions, generate a spec using the structure outlined below.
5.  **Save PRD:** Save the generated document as 'spec-[project-name].md' (e.g., 'spec-banking-app.md') inside the `/vibes` directory.

## Spec Structure
1.  **Project description:** A comprehensive description of the project
2.  **Intended users:** A brief description of the intended users (primary, secondary)
3.  **Feature list:** A list containing a high level overview of features (each described by one concise sentence). The first 'feature' should always be project initialization.
4.  **Main screens:** A high level overview of the most important screens, navigation and use of layouts.
5.  **Tech stack:** A list of the chosen tech stack for this frontend