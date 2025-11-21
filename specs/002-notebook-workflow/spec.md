# Feature Specification: M365 Copilot Notebook Workflow

**Feature Branch**: `002-notebook-workflow`
**Created**: 2025-11-21
**Status**: Draft
**Input**: M365 Copilot Notebook workflow and OneNote variant for SpecKit M365 Companion

## User Scenarios & Testing *(mandatory)*

### User Story 1 - Initialize Copilot Notebook for Project (Priority: P1)

A Product Owner wants to start using M365 Copilot for their project. They create a new
Copilot Notebook named "SpecKit – ProjectName", paste the start prompt from the framework,
and the assistant is immediately ready to help with spec-driven work using the defined
command vocabulary.

**Why this priority**: This is the entry point for all M365 Copilot interaction. Without
a properly initialized notebook, users cannot use the framework's workflow at all.

**Independent Test**: Can be tested by creating a new Copilot Notebook, pasting the start
prompt, and verifying the assistant responds with awareness of the available commands.

**Acceptance Scenarios**:

1. **Given** a user has access to M365 Copilot Notebooks, **When** they create a new
   notebook and paste the start prompt, **Then** the assistant acknowledges its role as
   "SpecKit M365 Companion" and lists available commands.

2. **Given** an initialized notebook, **When** the user types `/help` or asks about
   commands, **Then** the assistant explains all available commands and their purposes.

---

### User Story 2 - Execute Spec-Driven Commands (Priority: P1)

A Product Owner working in their Copilot Notebook wants to create a project constitution.
They type `/constitution` and the assistant guides them through creating a constitution
document, referencing the template from `_framework/` and outputting to the project's
`docs/` folder.

**Why this priority**: Command execution is the core functionality that enables the
spec-driven workflow. Equally critical as notebook initialization.

**Independent Test**: Can be tested by typing `/constitution` in an initialized notebook
and verifying the assistant produces appropriate guidance and output format.

**Acceptance Scenarios**:

1. **Given** an initialized notebook with project context, **When** the user types
   `/constitution`, **Then** the assistant helps create a constitution document following
   the framework template.

2. **Given** an initialized notebook, **When** the user types `/spec "Feature name"`,
   **Then** the assistant helps create a specification document for that feature.

3. **Given** an initialized notebook, **When** the user types `/plan`, **Then** the
   assistant helps create an implementation plan based on existing specs.

4. **Given** an initialized notebook, **When** the user types `/tasks`, **Then** the
   assistant helps break down the plan into actionable tasks.

---

### User Story 3 - Review and Summarize Work (Priority: P2)

A Product Owner wants to check consistency of their project artifacts or get a summary
for stakeholders. They use `/review` to validate document alignment or `/summary` to
generate a brief overview.

**Why this priority**: Review and summary are valuable but secondary to the core
creation workflow (constitution → spec → plan → tasks).

**Independent Test**: Can be tested by using `/review` on a project with existing docs
and verifying the assistant identifies any inconsistencies or gaps.

**Acceptance Scenarios**:

1. **Given** a project with constitution and specs, **When** the user types `/review`,
   **Then** the assistant checks for alignment between artifacts and reports findings.

2. **Given** a project with multiple documents, **When** the user types `/summary`,
   **Then** the assistant produces a concise overview suitable for stakeholder updates.

---

### User Story 4 - Use OneNote as Alternative (Priority: P3)

A Product Owner prefers using OneNote instead of Copilot Notebooks. They set up a OneNote
section for their project, use Copilot in OneNote with the provided start prompt, and
can follow the same command-based workflow.

**Why this priority**: OneNote is an optional alternative for users who prefer it, but
the primary workflow is Copilot Notebooks.

**Independent Test**: Can be tested by setting up a OneNote section with the start prompt
and verifying basic command functionality works.

**Acceptance Scenarios**:

1. **Given** a user with M365 Copilot in OneNote, **When** they create a project section
   and use the OneNote start prompt, **Then** they can execute the same commands as in
   Copilot Notebooks.

2. **Given** a OneNote project section, **When** documents are created via commands,
   **Then** they are organized as pages within the section structure.

---

### Edge Cases

- What happens when a user runs `/plan` before creating specs? The assistant should
  guide them to create specs first, explaining the dependency.

- What happens when referenced framework files are not accessible? The assistant should
  clearly explain which files are needed and where to find them.

- How does the assistant handle ambiguous project context? It should ask clarifying
  questions about which project folder to use.

## Requirements *(mandatory)*

### Functional Requirements

- **FR-001**: Framework MUST provide a `notebook_startprompt.md` file containing the
  initialization prompt for Copilot Notebooks.

- **FR-002**: Framework MUST provide a `onenote_startprompt.md` file containing the
  initialization prompt for OneNote with Copilot.

- **FR-003**: Start prompts MUST define the assistant's role as "SpecKit M365 Companion
  for [ProjectName]" and establish its purpose.

- **FR-004**: Start prompts MUST declare all available commands:
  - `/constitution` - Create or review project constitution
  - `/spec` - Create or update feature specifications
  - `/plan` - Create implementation plans from specs
  - `/tasks` - Generate task lists from plans
  - `/review` - Check consistency across project artifacts
  - `/summary` - Generate stakeholder-friendly overview

- **FR-005**: Each command MUST have documented behavior specifying:
  - Required inputs (which files/context needed)
  - Expected outputs (what document is produced)
  - Target location (where output should be saved/referenced)

- **FR-006**: Start prompts MUST instruct the assistant to reference files from:
  - `_framework/` for templates and instructions
  - `projects/[ProjectName]/` for project-specific context

- **FR-007**: Framework MUST provide a `commands_cheatsheet.md` summarizing all
  commands with one-line descriptions for quick reference.

- **FR-008**: Commands MUST enforce the spec-first workflow order:
  - `/constitution` can run independently
  - `/spec` can run independently
  - `/plan` requires at least one spec to exist
  - `/tasks` requires a plan to exist

- **FR-009**: The `/review` command MUST check for:
  - Alignment between constitution principles and spec requirements
  - Consistency between spec requirements and plan milestones
  - Coverage of plan items in task lists

- **FR-010**: The `/summary` command MUST produce output suitable for non-technical
  stakeholders, avoiding jargon and focusing on status and next steps.

### Key Entities

- **Copilot Notebook**: A Microsoft 365 Copilot conversation container. One notebook
  per project, named "SpecKit – [ProjectName]".

- **Start Prompt**: The initial instruction text pasted into a notebook to configure
  the assistant's behavior and command vocabulary.

- **Command**: A slash-prefixed keyword (e.g., `/spec`) that triggers specific
  assistant behavior defined in the start prompt.

- **Project Context**: The combination of framework files and project-specific files
  that the assistant references when executing commands.

- **OneNote Section**: An alternative container for users preferring OneNote, where
  pages serve as documents and Copilot assists via the embedded assistant.

## Success Criteria *(mandatory)*

### Measurable Outcomes

- **SC-001**: A user can initialize a Copilot Notebook for a project in under 2 minutes
  by copying the start prompt.

- **SC-002**: 100% of defined commands (`/constitution`, `/spec`, `/plan`, `/tasks`,
  `/review`, `/summary`) are documented in the start prompt.

- **SC-003**: Users can complete the full workflow (constitution → spec → plan → tasks)
  in a single notebook session without external tools.

- **SC-004**: The assistant correctly refuses to run `/plan` or `/tasks` when
  prerequisite documents are missing, and explains what is needed.

- **SC-005**: The `/summary` command output is understandable by someone with no
  knowledge of the Spec Kit methodology.

- **SC-006**: OneNote users can execute all core commands using the OneNote-specific
  start prompt.

## Assumptions

- Users have access to Microsoft 365 Copilot (standard enterprise license).
- Copilot Notebooks support pasting multi-paragraph start prompts.
- Copilot can reference files by path when users mention OneDrive locations.
- Users will manually save/copy assistant outputs to appropriate project files.
- OneNote with Copilot has similar instruction-following capabilities as Copilot Notebooks.
