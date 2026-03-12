# Install Protocol

Installation wizard for AgenticMemory. This protocol installs all core components and the primary agent.

## Prerequisites

- OpenCode installed
- `~/.config/opencode/` directory exists (created automatically by OpenCode)

## Installation Steps

Execute these steps in order:

### Step 1: Verify OpenCode Installation

```
Check if ~/.config/opencode/ exists
If not, inform user: "Please install OpenCode first"
```

### Step 2: Install Core Agents

Copy all files from `core/agents/` to `~/.config/opencode/agents/`:

```bash
# Linux/macOS
cp -r core/agents/* ~/.config/opencode/agents/

# Windows (PowerShell)
Copy-Item -Recurse core/agents/* ~/.config/opencode/agents/
```

Files to install:
- memory.md
- planner.md
- research.md
- coder.md
- auditor.md
- security.md
- backend-coder.md
- frontend-coder.md
- test-coder.md
- devops-coder.md
- security-auditor.md
- performance-auditor.md
- style-auditor.md
- git-manager.md
- docs-manager.md
- decision-log.md
- database-expert.md
- api-designer.md
- doc-scout.md
- brs-manager.md
- sds-manager.md

### Step 3: Install Core Skills

Copy all folders from `core/skills/` to `~/.config/opencode/skills/`:

```bash
# Linux/macOS
cp -r core/skills/* ~/.config/opencode/skills/

# Windows (PowerShell)
Copy-Item -Recurse core/skills/* ~/.config/opencode/skills/
```

Folders to install:
- planner/
- coder/
- auditor/
- memory/
- security/
- research/
- decision-log/
- brs/
- sds/

### Step 4: Install Primary Agent

Copy the primary agent file:

```bash
# Linux/macOS
cp agent/agentic-memory.md ~/.config/opencode/agents/

# Windows (PowerShell)
Copy-Item agent/agentic-memory.md ~/.config/opencode/agents/
```

### Step 5: Install Primary Skill

Copy the primary skill folder:

```bash
# Linux/macOS
cp -r agent/skills/agentic-memory ~/.config/opencode/skills/

# Windows (PowerShell)
Copy-Item -Recurse agent/skills/agentic-memory ~/.config/opencode/skills/
```

### Step 6: Verify Installation

Check that all files are in place:

```
~/.config/opencode/
├── agents/
│   ├── agentic-memory.md    ← Primary agent
│   ├── memory.md
│   ├── planner.md
│   ├── coder.md
│   ├── auditor.md
│   └── ... (other subagents)
└── skills/
    ├── agentic-memory/       ← Primary skill
    │   └── SKILL.md
    ├── planner/
    ├── coder/
    └── ... (other skills)
```

### Step 7: Complete

```
✅ Installation Complete!

Installed:
- 1 Primary agent: agentic-memory
- 21 Subagents
- 9 Skills

Next Steps:
1. Restart OpenCode or reload configuration
2. Test by saying: "agentic-memory, hello!"
3. (Optional) Rename with: "Load rename.md"

To customize the agent name, use the rename protocol.
```

## Troubleshooting

### "Directory not found"
- OpenCode creates `~/.config/opencode/` on first run
- Run OpenCode once before installing

### "Permission denied"
- Check write permissions for `~/.config/opencode/`
- On Linux/macOS: `chmod -R u+w ~/.config/opencode/`

### "Files already exist"
- Previous installation detected
- Use `update.md` to update existing installation
- Or manually backup and remove old files

## Platform-Specific Notes

### Linux/macOS
- Use bash commands above
- Path: `~/.config/opencode/`

### Windows
- Use PowerShell commands
- Path: `%USERPROFILE%\.config\opencode\` or `~\.config\opencode\`

### WSL
- Use Linux commands
- Path: `~/.config/opencode/`
