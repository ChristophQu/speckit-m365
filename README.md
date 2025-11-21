# SpecKit M365 Companion

A framework for bringing **Spec-Driven Development** to Microsoft 365 Copilot users.

## What is This?

SpecKit M365 Companion helps Product Owners practice the [Spec Kit](https://github.com/anthropics/specify) methodology using Microsoft 365 Copilot (Notebooks and OneNote) as their main interface—no CLI tools or code agents required.

### The Problem

- **Spec Kit** provides excellent tools for spec-driven development
- But it requires CLI access and developer tooling
- Many corporate environments **only allow M365** (no CLI, no Copilot Studio)
- Product Owners need a way to use the methodology with what they have

### The Solution

This framework provides:

- **Templates and prompts** optimized for M365 Copilot
- **A folder structure** that syncs well with OneDrive/SharePoint
- **A command vocabulary** (`/constitution`, `/spec`, `/plan`, `/tasks`) for Copilot
- **Examples** showing expected document formats

## Quick Start

### 1. Get the Framework

Download or clone this repository, then copy the `framework/` folder to your OneDrive:

```
/OneDrive/SpecKit-M365/
├── _framework/          ← Templates and prompts
└── projects/
    ├── _template/       ← Copy this for each new project
    └── example/         ← Reference example
```

### 2. Create a Project

1. Copy `projects/_template/` to `projects/YourProjectName/`
2. Open the README in your new project folder

### 3. Set Up Copilot

1. Create a new **Microsoft 365 Copilot Notebook**
2. Name it: **"SpecKit – YourProjectName"**
3. Copy the contents of `_framework/notebook_startprompt.md` as your first message
4. The assistant will acknowledge its role and list available commands

### 4. Start Working

Use commands to create your project artifacts:

| Command | Purpose |
|---------|---------|
| `/constitution` | Create project principles and governance |
| `/spec [name]` | Create a feature specification |
| `/plan` | Create an implementation plan |
| `/tasks` | Generate a task list |
| `/review` | Check consistency across documents |
| `/summary` | Generate a stakeholder overview |

## Repository Structure

```
speckit-m365/
├── framework/                 # DISTRIBUTE THIS FOLDER
│   ├── _framework/            # Templates, prompts, instructions
│   │   ├── speckit_m365_instructions.md
│   │   ├── notebook_startprompt.md
│   │   ├── onenote_startprompt.md
│   │   ├── constitution_template.md
│   │   ├── spec_template.md
│   │   ├── plan_template.md
│   │   ├── tasks_template.md
│   │   └── commands_cheatsheet.md
│   └── projects/
│       ├── _template/         # Copyable project template
│       └── example/           # Reference example
├── upstream/                  # Placeholder for Spec Kit sync
├── specs/                     # Development specs (not distributed)
└── README.md                  # This file
```

## How It Works

### Two Environments

| Environment | Tools Available | Role |
|-------------|-----------------|------|
| **Dev Machine** | Spec Kit CLI, Claude Code, Git | Maintain framework |
| **Corporate Machine** | M365 Copilot, OneDrive | Use framework |

### Distribution Flow

1. Framework is maintained in this Git repository
2. The `framework/` folder is copied/zipped to corporate OneDrive
3. Users work with Copilot Notebooks referencing the framework files

### Workflow

Follow the Spec Kit methodology:

```
Constitution → Specifications → Plan → Tasks
     ↓              ↓            ↓       ↓
  Principles    What to build  How    Action items
```

## Documentation

- **[Instructions](framework/_framework/speckit_m365_instructions.md)** - Full usage guide
- **[Commands Cheatsheet](framework/_framework/commands_cheatsheet.md)** - Quick reference
- **[Example Project](framework/projects/example/)** - See it in action

## Relationship to Spec Kit

This is a **companion framework**, not a replacement for [Spec Kit](https://github.com/anthropics/specify).

| Spec Kit | SpecKit M365 Companion |
|----------|------------------------|
| CLI-based tooling | M365 Copilot interface |
| Full development workflow | Documentation workflow only |
| Requires dev environment | Works on locked-down laptops |
| Creates code artifacts | Creates planning artifacts |

Use Spec Kit on your dev machine; use this companion on corporate machines.

## Contributing

Contributions are welcome! Please:

1. Follow the existing code style and documentation patterns
2. Update relevant documentation for any changes
3. Test prompts with M365 Copilot before submitting

## License

[Add license information here]

---

Built with the [Spec Kit](https://github.com/anthropics/specify) methodology.
