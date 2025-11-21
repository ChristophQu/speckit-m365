# Implementation Plan: SpecKit M365 Companion MVP

**Date**: 2025-11-21
**Specs**:
- [001-framework-layout/spec.md](../001-framework-layout/spec.md)
- [002-notebook-workflow/spec.md](../002-notebook-workflow/spec.md)

## Summary

This plan covers the MVP implementation of SpecKit M365 Companion, a documentation
framework that enables Product Owners to use Spec-Driven Development with Microsoft
365 Copilot. The MVP delivers:

1. A complete folder structure (`framework/`, `upstream/`)
2. All framework templates and prompts (`_framework/`)
3. A copyable project template (`projects/_template/`)
4. Start prompts for Copilot Notebooks and OneNote
5. An example project demonstrating usage

## Project Context

**Project Type**: Documentation framework (no code)
**Primary Format**: Markdown files
**Storage**: Git repository → ZIP distribution → OneDrive/SharePoint
**Target Platform**: Windows/macOS with Microsoft 365 Copilot
**Testing**: Manual validation of folder structure and document templates

## Constitution Check

*Based on [.specify/memory/constitution.md](../../.specify/memory/constitution.md)*

| Principle | Status | Notes |
|-----------|--------|-------|
| I. Spec-First Workflow | PASS | Constitution → Specs → Plan → Tasks flow followed |
| II. File-Based Architecture | PASS | All artifacts are Markdown in predictable folders |
| III. Environment Separation | PASS | Framework designed for Dev → Corporate distribution |
| IV. Simplicity & Enterprise-Friendliness | PASS | Numbered files, clear naming, English prose |
| V. Clear Terminology | PASS | Terms defined in constitution used consistently |

## Project Structure

### Repository Root

```text
speckit-m365/
├── .specify/                    # Spec Kit tooling (dev machine only)
├── .claude/                     # Claude Code commands (dev machine only)
├── specs/                       # Feature specifications (dev machine only)
│   ├── 001-framework-layout/
│   ├── 002-notebook-workflow/
│   └── mvp-implementation/      # This plan
├── framework/                   # USER-FACING CONTENT (distributed to corporate)
│   ├── _framework/              # Global templates and prompts
│   │   ├── speckit_m365_instructions.md
│   │   ├── notebook_startprompt.md
│   │   ├── onenote_startprompt.md
│   │   ├── constitution_template.md
│   │   ├── spec_template.md
│   │   ├── plan_template.md
│   │   ├── tasks_template.md
│   │   └── commands_cheatsheet.md
│   └── projects/
│       ├── _template/           # Copyable project template
│       │   ├── README.md
│       │   ├── sources/         # Raw inputs (exports, screenshots)
│       │   ├── docs/            # Curated documentation
│       │   └── notes/           # Meeting notes, scratchpad
│       └── example/             # Example project demonstrating usage
│           ├── README.md
│           ├── sources/
│           ├── docs/
│           └── notes/
├── upstream/                    # Placeholder for Spec Kit template sync
│   ├── spec-kit-base/
│   ├── README.md
│   └── VERSION.md
└── README.md                    # Project documentation
```

### OneDrive Target Structure (after distribution)

```text
/OneDrive/SpecKit-M365/
├── _framework/                  # Copied from framework/_framework/
└── projects/
    ├── _template/               # Copied from framework/projects/_template/
    ├── ProjectAlpha/            # User's first project (copied from _template)
    └── ProjectBeta/             # User's second project
```

## Milestones

### M1: Repository Structure

**Goal**: Establish the complete folder hierarchy for the framework.

**Scope**:
- Create `framework/` with `_framework/` and `projects/` subdirectories
- Create `upstream/` placeholder structure
- Add `.gitkeep` files to preserve empty directories
- Create placeholder README files

**Work Items**:
- Create directory structure
- Add `.gitkeep` files
- Create `upstream/README.md` explaining sync intent
- Create `upstream/VERSION.md` placeholder

---

### M2: Framework Templates and Prompts

**Goal**: Populate `_framework/` with all templates and prompts for M365 usage.

**Scope**:
- `speckit_m365_instructions.md` - Master instructions for framework usage
- `notebook_startprompt.md` - Copilot Notebook initialization prompt
- `onenote_startprompt.md` - OneNote Copilot initialization prompt
- `constitution_template.md` - Template for project constitutions
- `spec_template.md` - Template for feature specifications
- `plan_template.md` - Template for implementation plans
- `tasks_template.md` - Template for task lists
- `commands_cheatsheet.md` - Quick reference for all commands

**Work Items**:
- Draft each template file with clear instructions
- Ensure consistent terminology (per Constitution V)
- Include examples where helpful
- Number files for clear ordering

---

### M3: Project Template

**Goal**: Create a complete, copyable project template.

**Scope**:
- `projects/_template/README.md` explaining the template
- `sources/` subdirectory with `.gitkeep`
- `docs/` subdirectory with `.gitkeep`
- `notes/` subdirectory with `.gitkeep`

**Work Items**:
- Create template folder structure
- Write comprehensive README for the template
- Add suggested document naming conventions

---

### M4: Example Project

**Goal**: Provide a concrete example showing framework usage.

**Scope**:
- `projects/example/` with sample content
- Example constitution, spec skeleton, or notes
- README explaining what the example demonstrates

**Work Items**:
- Copy template to `example/`
- Add sample documents showing expected format
- Document the example's purpose

---

### M5: Public Documentation

**Goal**: Polish repository documentation for GitHub publication.

**Scope**:
- Root `README.md` with:
  - Project overview
  - Quick start guide
  - Distribution instructions
  - License information
- Ensure all content is open-source friendly

**Work Items**:
- Write comprehensive root README
- Add license file (if needed)
- Review all content for clarity

## Dependencies

```text
M1 (Structure) ─┬─► M2 (Templates)
                │
                ├─► M3 (Project Template)
                │
                └─► M4 (Example) ─────► M5 (Documentation)
```

- M2, M3 can proceed in parallel after M1
- M4 depends on M3 (uses template)
- M5 depends on M4 (references example)

## Notes

- This is a documentation-only project; no code, tests, or builds required
- All artifacts are Markdown files suitable for Git and OneDrive
- The `specs/` directory is for dev machine only; not distributed to corporate
- The `framework/` directory is what gets distributed
