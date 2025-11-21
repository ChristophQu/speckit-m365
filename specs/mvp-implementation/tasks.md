# Tasks: SpecKit M365 Companion MVP

**Input**: [plan.md](plan.md)
**Specs**: [001-framework-layout](../001-framework-layout/spec.md), [002-notebook-workflow](../002-notebook-workflow/spec.md)

## Format: `[ID] [P?] [Milestone] Description`

- **[P]**: Can run in parallel (no dependencies)
- **[Milestone]**: Which milestone this task belongs to (M1-M5)
- Category tags: `docs` | `repo-structure` | `prompts` | `examples`

---

## Phase 1: Setup - Repository Structure (M1)

**Purpose**: Establish the complete folder hierarchy for the framework

- [ ] T001 [M1] `repo-structure` Create `framework/_framework/` directory
- [ ] T002 [P] [M1] `repo-structure` Create `framework/projects/_template/` directory with subdirs
- [ ] T003 [P] [M1] `repo-structure` Create `framework/projects/_template/sources/` with `.gitkeep`
- [ ] T004 [P] [M1] `repo-structure` Create `framework/projects/_template/docs/` with `.gitkeep`
- [ ] T005 [P] [M1] `repo-structure` Create `framework/projects/_template/notes/` with `.gitkeep`
- [ ] T006 [P] [M1] `repo-structure` Create `upstream/spec-kit-base/` with `.gitkeep`
- [ ] T007 [M1] `docs` Create `upstream/README.md` explaining sync intent
- [ ] T008 [P] [M1] `docs` Create `upstream/VERSION.md` placeholder

**Checkpoint**: Directory structure complete

---

## Phase 2: Framework Templates (M2)

**Purpose**: Populate `_framework/` with all templates and prompts

**Depends on**: T001 (framework/_framework/ exists)

- [ ] T009 [M2] `docs` Create `framework/_framework/speckit_m365_instructions.md` - master instructions (L)
- [ ] T010 [P] [M2] `prompts` Create `framework/_framework/notebook_startprompt.md` - Copilot Notebook init (M)
- [ ] T011 [P] [M2] `prompts` Create `framework/_framework/onenote_startprompt.md` - OneNote Copilot init (M)
- [ ] T012 [P] [M2] `docs` Create `framework/_framework/constitution_template.md` (S)
- [ ] T013 [P] [M2] `docs` Create `framework/_framework/spec_template.md` (S)
- [ ] T014 [P] [M2] `docs` Create `framework/_framework/plan_template.md` (S)
- [ ] T015 [P] [M2] `docs` Create `framework/_framework/tasks_template.md` (S)
- [ ] T016 [M2] `docs` Create `framework/_framework/commands_cheatsheet.md` - quick reference (M)

**Checkpoint**: All framework templates complete

---

## Phase 3: Project Template (M3)

**Purpose**: Create a complete, copyable project template

**Depends on**: T002-T005 (template directory structure exists)

- [ ] T017 [M3] `docs` Create `framework/projects/_template/README.md` - template usage guide (M)

**Checkpoint**: Project template ready for copying

---

## Phase 4: Example Project (M4)

**Purpose**: Demonstrate framework usage with a concrete example

**Depends on**: M3 complete (T017)

- [ ] T018 [M4] `repo-structure` Copy `_template/` to `framework/projects/example/`
- [ ] T019 [M4] `examples` Create `framework/projects/example/README.md` - example overview (S)
- [ ] T020 [P] [M4] `examples` Create sample constitution in `example/docs/01_constitution.md` (S)
- [ ] T021 [P] [M4] `examples` Create sample meeting notes in `example/notes/` (S)

**Checkpoint**: Example project demonstrates framework usage

---

## Phase 5: Public Documentation (M5)

**Purpose**: Polish repository for GitHub publication

**Depends on**: M4 complete

- [ ] T022 [M5] `docs` Update root `README.md` with comprehensive project documentation (L)
- [ ] T023 [P] [M5] `docs` Review all content for clarity and consistency (M)

**Checkpoint**: Repository ready for publication

---

## Dependencies & Execution Order

### Milestone Dependencies

```text
M1 (Structure) ─┬─► M2 (Templates) ────────┐
                │                          │
                ├─► M3 (Project Template) ─┼─► M4 (Example) ─► M5 (Docs)
                │                          │
                └─► (upstream placeholder) ─┘
```

### Task Dependencies Within Milestones

- **M1**: T001 must complete before T009-T016; T002-T008 can run in parallel
- **M2**: All tasks can run in parallel once T001 is complete
- **M3**: T017 depends on M1 structure being in place
- **M4**: T018 first, then T019-T021 can run in parallel
- **M5**: T022 first (main README), then T023

### Parallel Opportunities

```text
# After T001 completes, launch all M2 templates in parallel:
T009, T010, T011, T012, T013, T014, T015, T016

# M1 parallel tasks:
T002, T003, T004, T005, T006, T007, T008

# M4 parallel tasks (after T018):
T019, T020, T021
```

---

## Effort Estimates

| Size | Description | Examples |
|------|-------------|----------|
| S | Small - straightforward, under 15 min | Template copies, placeholder files |
| M | Medium - requires thought, 15-45 min | Start prompts, cheatsheet |
| L | Large - significant content, 45+ min | Main instructions, root README |

### Summary by Milestone

| Milestone | Task Count | Effort Distribution |
|-----------|------------|---------------------|
| M1 | 8 | 7S, 1M |
| M2 | 8 | 4S, 3M, 1L |
| M3 | 1 | 1M |
| M4 | 4 | 3S, 1M |
| M5 | 2 | 1M, 1L |
| **Total** | **23** | **14S, 6M, 3L** |

---

## Notes

- All tasks are documentation/structure only (no code)
- Tasks marked `[P]` can be executed in parallel with other `[P]` tasks in same phase
- Commit after each milestone or logical group of tasks
- Review against Constitution principles after completing each milestone
