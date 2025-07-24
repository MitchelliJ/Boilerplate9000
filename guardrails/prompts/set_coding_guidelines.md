**Prompt Template for Generating Backend Code Guidelines**

---

Can you help me create a comprehensive and detailed document outlining backend code guidelines and best practices?

**Purpose**:
This document will serve as a foundational reference for our development team, ensuring consistency, maintainability, and quality in our codebase.

**Project Context**:
We are building a [complex/simple/moderate] backend system using the following technology stack:

- [List technology stack items here as an array, e.g., NestJS, TypeORM, Swagger UI, AWS S3, AWS Secrets Manager, RabbitMQ, etc.]

Our repository structure is [monorepo/multi-repo], consisting of:

- One primary API service
- [Number] small microservices performing tasks such as background jobs, workers, or scheduled cron jobs

**Sections to Cover in the Guidelines:**

1. **Setup and Architectural Conventions**

   - Folder and file structure
   - Module organization and dependency management
   - Best practices for scalability and maintainability

2. **Coding Standards and Style**

   - ESLint configuration and rules (based on Airbnb TypeScript standards)
   - Prettier configuration for code formatting
   - Naming conventions (variables, methods, classes, etc.)
   - Recommended patterns (controllers, services, repositories, DTOs)

3. **Tooling Guidelines**

   - General best practices for tooling integration
   - For each entry in the tech stack, add detailed guidelines and best practices

4. **Testing Standards**

   - Jest setup and best practices
   - Guidelines for unit testing, integration testing, and end-to-end testing
   - Recommended test file structure and naming conventions

5. **Static Code Analysis and CI/CD**
   - SonarQube integration for static code analysis
   - Basic CI/CD pipeline setup (Coolify, GitHub Actions)
   - Recommended stages and quality gates for code integration

**Deliverable**:
Provide the document formatted in clear Markdown with distinct sections, making it easily reusable and adaptable for future technology scopes or additional tooling.
