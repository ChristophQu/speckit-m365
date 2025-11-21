# Commands Cheatsheet

Quick reference for SpecKit M365 Companion commands.

## Command Summary

| Command | Purpose | Prerequisites |
|---------|---------|---------------|
| `/constitution` | Create/review project principles | None |
| `/spec [name]` | Create/update feature specification | None |
| `/plan` | Create implementation plan | At least one spec |
| `/tasks` | Generate task list | A plan exists |
| `/review` | Check artifact consistency | Some docs exist |
| `/summary` | Generate stakeholder overview | Some docs exist |

## Workflow Order

```
/constitution ─────────────────────────────────►
                                                 ↓
/spec ──► /spec ──► /spec ─────────────────────►
                                                 ↓
                           /plan ───────────────►
                                                 ↓
                                    /tasks ─────►
                                                 ↓
                              /review ◄─────────►
                                                 ↓
                                       /summary ─►
```

## Command Details

### `/constitution`

**What it does**: Creates or reviews your project's governing principles

**Example usage**:
```
/constitution

I want to create a constitution for our Customer Portal project.
Key principles:
- User privacy first
- Mobile-responsive design
- Accessibility compliance (WCAG 2.1)
```

**Output**: Constitution document for `docs/01_constitution.md`

---

### `/spec [Feature Name]`

**What it does**: Creates a feature specification

**Example usage**:
```
/spec User Login

Users should be able to log in with email and password.
They need password reset functionality.
Session should persist for 30 days.
```

**Output**: Specification document for `docs/XX_spec_user_login.md`

---

### `/plan`

**What it does**: Creates an implementation plan from specs

**Example usage**:
```
/plan

Please create an implementation plan based on:
- 02_spec_user_login.md
- 03_spec_dashboard.md
```

**Output**: Plan document for `docs/XX_plan.md`

**Note**: Will remind you if no specs exist yet

---

### `/tasks`

**What it does**: Generates actionable tasks from a plan

**Example usage**:
```
/tasks

Please generate tasks from 04_plan.md
```

**Output**: Task list for `docs/XX_tasks.md`

**Note**: Will remind you if no plan exists yet

---

### `/review`

**What it does**: Checks consistency across documents

**Example usage**:
```
/review

Please review:
- Constitution
- All specs
- Current plan

Check for alignment issues.
```

**Output**: Review report with findings and suggestions

---

### `/summary`

**What it does**: Creates a stakeholder-friendly overview

**Example usage**:
```
/summary

Please summarize current project status for our weekly stakeholder meeting.
```

**Output**: Brief summary focusing on status, progress, and next steps

---

## Tips

1. **Be explicit**: Mention file names when referencing documents
2. **Provide context**: The more detail you give, the better the output
3. **Follow the order**: Constitution → Spec → Plan → Tasks
4. **Save outputs**: Copy assistant responses to your project files
5. **Use /review often**: Catch inconsistencies early

## File Naming Convention

```
docs/
├── 01_constitution.md
├── 02_spec_[feature1].md
├── 03_spec_[feature2].md
├── 04_plan.md
└── 05_tasks.md
```

## Need Help?

- Review `speckit_m365_instructions.md` for full documentation
- Check templates for expected document structure
- Re-paste the start prompt if the assistant loses context
