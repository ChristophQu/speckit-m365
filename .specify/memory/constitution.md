<!--
  Sync Impact Report
  ==================
  Version change: 0.0.0 → 1.0.0 (initial ratification)

  Added principles:
  - I. Spec-First Workflow
  - II. File-Based Architecture
  - III. Environment Separation
  - IV. Simplicity & Enterprise-Friendliness
  - V. Clear Terminology

  Added sections:
  - Scope & Boundaries
  - Delivery & Distribution
  - Governance

  Templates requiring updates:
  - .specify/templates/plan-template.md: ✅ No updates required (generic template)
  - .specify/templates/spec-template.md: ✅ No updates required (generic template)
  - .specify/templates/tasks-template.md: ✅ No updates required (generic template)

  Follow-up TODOs: None
-->

# SpecKit M365 Companion Constitution

## Purpose

SpecKit M365 Companion is a reusable framework that enables Product Owners to practice
**Spec-Driven Development** using the Spec Kit methodology, while relying on **Microsoft 365
Copilot** (Notebooks and optionally OneNote) as their primary working interface.

This framework bridges the gap between:

- **Upstream GitHub Spec Kit**: The original open-source toolkit maintained at
  `anthropics/specify` that provides CLI tooling, templates, and agent prompts for
  spec-driven workflows.
- **Corporate M365 environments**: Locked-down enterprise laptops where users have access
  to M365 Copilot but cannot install CLI tools, code agents, or Copilot Studio.

## Core Principles

### I. Spec-First Workflow

All work MUST follow the Spec Kit progression:

1. **Constitution** → Establishes project principles and governance
2. **Specification** → Defines what to build (user stories, requirements, success criteria)
3. **Plan** → Outlines how to build it (milestones, technical approach)
4. **Tasks** → Breaks down the plan into actionable work items

No implementation or detailed planning proceeds without a ratified specification.
This principle ensures clarity, traceability, and alignment before effort is invested.

### II. File-Based Architecture

All artifacts MUST be stored as plain-text files (Markdown preferred) in a predictable
folder structure:

- Framework templates and prompts live in `_framework/`
- Per-project work lives in `projects/<ProjectName>/`
- Each project folder contains `sources/`, `docs/`, and `notes/` subdirectories

**Rationale**: File-based storage ensures compatibility with OneDrive/SharePoint sync,
version control (Git), and M365 Copilot's file-reference capabilities. No database,
API, or proprietary format dependencies.

### III. Environment Separation

The framework distinguishes two execution environments:

| Environment | Capabilities | Role |
|-------------|--------------|------|
| **Dev Machine** | Spec Kit CLI, Claude Code, Git, full tooling | Maintain framework, update templates, sync upstream |
| **Corporate Machine** | M365 Copilot, OneDrive, SharePoint only | Use framework via Copilot Notebooks / OneNote |

Artifacts flow **one-way** from Dev → Corporate (via ZIP or OneDrive sync).
The framework MUST NOT require any tooling beyond M365 on corporate machines.

### IV. Simplicity & Enterprise-Friendliness

- Templates and prompts MUST be understandable without training
- Folder and file naming MUST use clear, numbered prefixes (e.g., `01_constitution.md`)
- All prose MUST be in English and suitable for open-source publication
- The framework MUST work on locked-down enterprise laptops with standard M365 licenses

**Rationale**: Enterprise Product Owners may not be developers. The framework succeeds
only if it is immediately usable by its target audience.

### V. Clear Terminology

To avoid confusion, these terms have precise meanings:

| Term | Definition |
|------|------------|
| **Spec Kit** (upstream) | The original GitHub toolkit (`anthropics/specify`) |
| **SpecKit M365 Companion** | This framework (the current repository) |
| **Framework** | The `_framework/` folder with templates and prompts |
| **Project** | A specific initiative using the framework (lives in `projects/<Name>/`) |
| **Notebook** | A Microsoft 365 Copilot Notebook (one per project) |

Documentation MUST use these terms consistently to prevent ambiguity.

## Scope & Boundaries

### In Scope (MVP)

- Framework folder structure with M365-compatible templates and prompts
- Per-project template (`sources/`, `docs/`, `notes/`)
- Notebook start prompts and command conventions (`/constitution`, `/spec`, `/plan`,
  `/tasks`, `/review`, `/summary`)
- Multi-project setup using OneDrive folders
- Optional OneNote variant with equivalent structure

### Out of Scope (MVP)

- Automatic GitHub API integrations
- Code-generation features (this framework focuses on docs/spec/plan/tasks only)
- Real-time integration with corporate M365 tenants (everything is file-based)
- Copilot Studio automation (not available in target environments)

## Delivery & Distribution

The framework is maintained on a private dev machine with full Spec Kit + Claude Code
tooling. Distribution to corporate environments follows this pattern:

1. Framework updates are made in the Git repository
2. The `framework/` folder is exported as a ZIP archive
3. The ZIP is transferred to OneDrive or SharePoint
4. Corporate users extract and use the framework with M365 Copilot

No runtime dependencies on the dev machine are permitted for corporate usage.

## Governance

- This Constitution supersedes all other practices within the repository
- Amendments require:
  1. A documented rationale
  2. Review of impact on existing templates and prompts
  3. Version increment following semantic versioning
- All contributions MUST verify compliance with these principles
- Complexity beyond what is specified here MUST be justified in writing

**Version**: 1.0.0 | **Ratified**: 2025-11-21 | **Last Amended**: 2025-11-21
