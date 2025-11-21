# Project Template

This is a template folder for new SpecKit M365 projects. Copy this entire folder
and rename it to start a new project.

## Quick Start

1. **Copy this folder**: Duplicate `_template/` and rename it to your project name
   - Example: `_template/` → `CustomerPortal/`
   - Use letters, numbers, hyphens, and underscores only

2. **Update this README**: Replace this content with your project overview

3. **Set up Copilot Notebook**:
   - Create a new Microsoft 365 Copilot Notebook
   - Name it: "SpecKit – [YourProjectName]"
   - Paste the start prompt from `_framework/notebook_startprompt.md`

4. **Start working**: Use the `/constitution` command to begin

## Folder Structure

```
[YourProject]/
├── README.md      ← You're reading this (replace with project overview)
├── sources/       ← Raw input materials
├── docs/          ← Curated documentation
└── notes/         ← Meeting notes and scratchpad
```

### sources/

**Purpose**: Store raw, unprocessed input materials

**Examples**:
- Confluence page exports
- Jira ticket screenshots
- Email threads (saved as .eml or .pdf)
- Requirement documents from stakeholders
- Screenshots of existing systems

**Tips**:
- Date your files: `2025-01-15_stakeholder_requirements.pdf`
- Don't edit files here; they're reference materials
- Organize into subfolders if needed: `sources/confluence/`, `sources/emails/`

### docs/

**Purpose**: Store curated, structured documentation created through the SpecKit workflow

**Expected files** (created via Copilot commands):
```
docs/
├── 01_constitution.md     ← /constitution
├── 02_system_overview.md  ← Optional context doc
├── 03_spec_[feature].md   ← /spec
├── 04_plan.md             ← /plan
└── 05_tasks.md            ← /tasks
```

**Naming convention**:
- Use numbered prefixes for ordering: `01_`, `02_`, `03_`
- Use lowercase with underscores: `spec_user_login.md`
- Be descriptive: `03_spec_user_authentication.md` not `03_spec.md`

### notes/

**Purpose**: Store informal content that doesn't fit in sources or docs

**Examples**:
- Meeting notes: `2025-01-15_kickoff_meeting.md`
- Research findings: `research_competitor_analysis.md`
- Scratchpad ideas: `brainstorm_v2_features.md`
- Decision logs: `decisions_architecture.md`

**Tips**:
- This is your workspace; organization is flexible
- Consider subfolders: `notes/meetings/`, `notes/research/`
- Use dates for time-sensitive content

## Workflow Reminder

Follow the SpecKit workflow order:

1. `/constitution` → Establish project principles
2. `/spec [feature]` → Define what to build
3. `/plan` → Outline how to build it
4. `/tasks` → Break down into actionable items
5. `/review` → Check consistency
6. `/summary` → Report to stakeholders

## Need Help?

- **Framework instructions**: `_framework/speckit_m365_instructions.md`
- **Command reference**: `_framework/commands_cheatsheet.md`
- **Templates**: `_framework/[type]_template.md`

---

*Delete everything above this line after copying the template, and replace with
your project overview.*

---

# [Your Project Name]

## Overview

[Brief description of your project]

## Team

| Role | Name |
|------|------|
| Product Owner | [Name] |
| [Other roles] | [Names] |

## Status

- [ ] Constitution created
- [ ] Initial specs defined
- [ ] Plan approved
- [ ] Tasks generated

## Links

- Copilot Notebook: [Link to your notebook]
- Related resources: [Links to other relevant materials]
