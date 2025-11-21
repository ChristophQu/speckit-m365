# SpecKit M365 Companion - Instructions

## Overview

SpecKit M365 Companion is a framework that brings **Spec-Driven Development** to
Microsoft 365 Copilot users. It provides templates, prompts, and a folder structure
that enables Product Owners to follow the Spec Kit methodology without needing CLI
tools or code agents.

## How It Works

### The Spec-First Workflow

All work follows this progression:

1. **Constitution** → Establishes project principles and governance
2. **Specification** → Defines what to build (user stories, requirements)
3. **Plan** → Outlines how to build it (milestones, approach)
4. **Tasks** → Breaks down the plan into actionable work items

### Two Environments

| Environment | What's Available | What You Do |
|-------------|------------------|-------------|
| **Dev Machine** | Spec Kit CLI, Claude Code, Git | Maintain framework, sync templates |
| **Corporate Machine** | M365 Copilot, OneDrive | Use framework via Copilot Notebooks |

## Folder Structure

```
SpecKit-M365/
├── _framework/              ← You are here (templates & prompts)
│   ├── speckit_m365_instructions.md
│   ├── notebook_startprompt.md
│   ├── onenote_startprompt.md
│   ├── constitution_template.md
│   ├── spec_template.md
│   ├── plan_template.md
│   ├── tasks_template.md
│   └── commands_cheatsheet.md
└── projects/
    ├── _template/           ← Copy this to start a new project
    └── [YourProject]/       ← Your project folders
```

## Getting Started

### 1. Set Up Your Project

1. Copy the `projects/_template/` folder
2. Rename it to your project name (e.g., `projects/CustomerPortal/`)
3. Open the README in your new project folder for next steps

### 2. Initialize a Copilot Notebook

1. Go to Microsoft 365 Copilot and create a new Notebook
2. Name it: **"SpecKit – [YourProjectName]"**
3. Copy the contents of `notebook_startprompt.md` as your first message
4. The assistant will acknowledge its role and list available commands

### 3. Start Working

Use the command vocabulary to create your project artifacts:

| Command | What It Does |
|---------|--------------|
| `/constitution` | Create or review project constitution |
| `/spec` | Create or update feature specifications |
| `/plan` | Create implementation plan from specs |
| `/tasks` | Generate task list from plan |
| `/review` | Check consistency across artifacts |
| `/summary` | Generate stakeholder overview |

## Key Concepts

### Project Folder Structure

Each project has three subfolders:

| Folder | Purpose | Examples |
|--------|---------|----------|
| `sources/` | Raw input materials | Confluence exports, Jira screenshots, emails |
| `docs/` | Curated documentation | Constitution, specs, plans, task lists |
| `notes/` | Informal content | Meeting notes, scratchpad, research |

### Document Naming Convention

Use numbered prefixes for clear ordering:

```
docs/
├── 01_constitution.md
├── 02_system_overview.md
├── 03_feature_catalogue.md
├── 04_architecture.md
└── 05_tasks_mvp.md
```

### The _framework Folder

This folder contains **read-only reference materials**:

- **Do NOT modify** these files in your day-to-day work
- **Do reference** them when the assistant needs template structure
- Templates are copied/adapted into your project's `docs/` folder

## Tips for Success

1. **Follow the workflow order**: Constitution → Spec → Plan → Tasks
2. **Reference files explicitly**: Tell the assistant which files to read
3. **Save outputs manually**: Copy assistant responses to your project files
4. **Use clear project names**: Stick to letters, numbers, hyphens, underscores
5. **Keep sources organized**: Date or label your raw inputs for traceability

## Troubleshooting

### "The assistant doesn't know about my project"

Make sure you:
- Used the start prompt from `notebook_startprompt.md`
- Mentioned your project folder path when asking for help
- Referenced specific files when needed (e.g., "read my constitution at...")

### "Commands aren't working as expected"

The assistant follows the start prompt instructions. If behavior seems off:
- Re-paste the start prompt to reset context
- Be explicit about which command you're running
- Provide file paths when the command needs input

### "I need to update the framework"

Framework updates come from the dev machine maintainer:
1. They update the Git repository
2. They create a new ZIP of the `framework/` folder
3. You replace your OneDrive copy with the new version

## Related Files

- [notebook_startprompt.md](notebook_startprompt.md) - Copilot Notebook initialization
- [onenote_startprompt.md](onenote_startprompt.md) - OneNote initialization
- [commands_cheatsheet.md](commands_cheatsheet.md) - Quick command reference
- [constitution_template.md](constitution_template.md) - Constitution structure
- [spec_template.md](spec_template.md) - Specification structure
- [plan_template.md](plan_template.md) - Plan structure
- [tasks_template.md](tasks_template.md) - Tasks structure
