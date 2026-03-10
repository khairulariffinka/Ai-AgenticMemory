---
name: memory
description: Manage project memory - read, update AGENTS.md, planner.md, and session history
---

## Language Detection

- **CRITICAL**: Detect user's language and respond in the same language
- If user uses **Bahasa Melayu (Malay)**, respond entirely in **Bahasa Melayu Malaysia**
- Auto-save messages should match user's language:
  - Malay: "Sesi disimpan. Jumpa lagi!"
  - English: "Session saved. Bye!"
- Examples:
  - User (Malay): "Keluar" → "Sesi disimpan. Jumpa lagi!"
  - User (English): "exit" → "Session saved. Bye!"

# Memory Skill

Manage persistent project context - acts as a file manager.

## Primary Functions

| Function | Description |
|----------|-------------|
| **READ** | Summarize AGENTS.md, planner.md for context |
| **UPDATE** | Add/edit AGENTS.md with new decisions |
| **TRACK** | Update task progress in planner.md |
| **SAVE** | Auto-save session to history/sessions.md |

## Memory Files

| File | Purpose |
|------|---------|
| `AGENTS.md` | Tech stack, PRD, context (PROJECT-SPECIFIC) |
| `planner.md` | Project milestones (PROJECT-SPECIFIC) |
| `history/sessions.md` | Session logs (PROJECT-SPECIFIC) |

---

## READ - Summarize Context

### Start of Session
Always read these files and summarize:

1. **AGENTS.md** - Tech stack, features, requirements
2. **planner.md** - Current tasks, progress
3. **history/sessions.md** - Previous sessions

### Example Summary
```
[MEMORY LOADED]
- Tech Stack: Laravel + React + MySQL
- Current Phase: Phase 2 - Core Features
- Progress: 2/5 tasks completed
- Last Session: Created user authentication
```

---

## UPDATE - Edit AGENTS.md

### When to Update
- New tech stack decision
- New features added
- Project structure changes
- Important discoveries

### How to Update
```markdown
## Updated Section

### New Feature
- Feature: [Description]

### Decision
- [Date]: Decided to use X because Y
```

---

## TRACK - Update planner.md

### Mark Task Complete
```markdown
- [x] Task 1 - Completed
- [ ] Task 2 - Pending
```

### Update Progress
- Add notes to completed tasks
- Update phase progress

---

## SAVE - Session Auto-Save

### When to Save
- User says: "exit", "quit", "done", "bye"
- Before ending ANY session

### Auto-Save Format
```markdown
## Current Session
**Date:** [YYYY-MM-DD HH:MM]

### Tasks Done
- [Task completed 1]
- [Task completed 2]

### Pending Tasks
- [Pending task 1]
- [Pending task 2]

### Notes
- [Any notes from this session]

---

## Previous Sessions

### [Date]
- Did X, Y, Z
```

### Save Location
- `history/sessions.md` in PROJECT folder (NOT global)

---

## Workflow

1. **START** - Read AGENTS.md, planner.md, history/sessions.md
2. **DURING** - Update files when needed
3. **END** - Always auto-save to history/sessions.md

---

## Guidelines

- Always read memory first at session start
- Update immediately after significant changes
- ALWAYS auto-save before ending session
- Keep updates relevant
- Ask user if they want to add notes
- Memory is PER PROJECT - not global
