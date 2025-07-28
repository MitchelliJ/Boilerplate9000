## Goal
To guide an AI assistant in creating a detailed Product-Requirements-Document (PRD) based on the initial user prompt. The PRD list will be handed off to a junior Project Manager for implementation. It is required to be formatted in markdown and saved to the /reference directory in the root of the project with the filename '[project-name]-PRD.md' (e.g., 'banking-app-prd.md').

## Process

1.  **Receive Initial Prompt:** The user provides a brief description or request for a new feature or functionality.
2.  **Ask Clarifying Questions:** Before writing the PRD, the AI *must* ask clarifying questions to gather sufficient detail. The goal is to gather enough input to create the feature description. Make sure to provide options in letter/number lists so the user can respond easily with multiple choice.
3.  **Generate PRD:** Based on the initial prompt and the user's answers to the clarifying questions, generate a PRD using the structure outlined below.
4.  **Save PRD:** Save the generated document as '[project-name]-PRD.md' (e.g., 'banking-app-prd.md') inside the /reference directory.

## PRD Structure
1.  **Feature description:** In the format 'As a <type of user>, I want <some capability or action>, so that <value or outcome it enables>.'
2.  **Sub-actions:** Break the feature description down into the sub-actions reflecting the steps the user takes.
3.  **User stories:** Break each sub-action down into a user story. Use multiple user stories when required.
4.  **Functional requirements:** Enrich the user stories with a list of functional requirements.
4.  **Acceptance criteria:** What would prove this story is working correctly from he users point of view?
5.  **Non-Goals (Out of Scope):** Clearly state what this feature will *not* include to manage scope.
6.  **Further considerations:** List any remaining questions or areas that would be wise to explore or clarify.