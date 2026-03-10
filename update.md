# Update Protocol

Smart update protocol that updates core components while preserving user customizations.

## Usage

```
User: "Load update.md"
AI: [Checks for updates and applies them]
```

## Update Process

### Step 1: Check Current Version

Read the installed VERSION.yaml or check for version marker:

```
Look for: ~/.config/opencode/.agentic-memory-version
If not found, assume version: 0.0.0 (needs full install)
```

Compare with project VERSION.yaml to determine if update is needed.

### Step 2: Detect User Customizations

Before updating, detect if user has customized the primary agent:

```
Check: ~/.config/opencode/agents/

If agent is named anything other than "agentic-memory":
  - User has renamed it
  - DO NOT overwrite
  - Note: "Custom agent detected: {name}"

If agent file has been modified:
  - Compare modification date with install date
  - If modified, DO NOT overwrite
  - Note: "Custom agent detected, preserving changes"
```

### Step 3: Update Core Agents

Core agents are ALWAYS updated (users should not modify these):

```bash
# Files to update (overwrite existing):
cp core/agents/memory.md ~/.config/opencode/agents/
cp core/agents/planner.md ~/.config/opencode/agents/
cp core/agents/coder.md ~/.config/opencode/agents/
cp core/agents/auditor.md ~/.config/opencode/agents/
cp core/agents/security.md ~/.config/opencode/agents/
cp core/agents/backend-coder.md ~/.config/opencode/agents/
cp core/agents/frontend-coder.md ~/.config/opencode/agents/
cp core/agents/test-coder.md ~/.config/opencode/agents/
cp core/agents/devops-coder.md ~/.config/opencode/agents/
cp core/agents/security-auditor.md ~/.config/opencode/agents/
cp core/agents/performance-auditor.md ~/.config/opencode/agents/
cp core/agents/style-auditor.md ~/.config/opencode/agents/
cp core/agents/git-manager.md ~/.config/opencode/agents/
cp core/agents/docs-manager.md ~/.config/opencode/agents/
```

### Step 4: Update Core Skills

Core skills are ALWAYS updated:

```bash
# Folders to update (overwrite existing):
cp -r core/skills/planner ~/.config/opencode/skills/
cp -r core/skills/coder ~/.config/opencode/skills/
cp -r core/skills/auditor ~/.config/opencode/skills/
cp -r core/skills/memory ~/.config/opencode/skills/
cp -r core/skills/security ~/.config/opencode/skills/
```

### Step 5: Add New Components (if any)

Check if any NEW agents or skills exist in the update that weren't in the previous version:

```
For each NEW file in core/agents/:
  If not exists in ~/.config/opencode/agents/:
    Copy the new file
    Log: "Added new agent: {name}"

For each NEW folder in core/skills/:
  If not exists in ~/.config/opencode/skills/:
    Copy the new folder
    Log: "Added new skill: {name}"
```

### Step 6: Update Primary Agent (if not customized)

```bash
# Only if user hasn't renamed or customized:
cp agent/agentic-memory.md ~/.config/opencode/agents/
cp -r agent/skills/agentic-memory ~/.config/opencode/skills/
```

### Step 7: Update Version Marker

Write the new version to mark successful update:

```bash
echo "1.0.0" > ~/.config/opencode/.agentic-memory-version
```

### Step 8: Report Results

```
✅ Update Complete!

Updated:
- X Core agents
- X Core skills

Preserved:
- {custom-agent-name} (your customized agent)

Added:
- {new-agent} (new subagent)
- {new-skill} (new skill)

Version: 0.x.x → 1.0.0
```

## Update Scenarios

### Scenario 1: Standard Update
```
User has default "agentic-memory"
→ All files updated including primary agent
```

### Scenario 2: User Renamed Agent
```
User renamed to "nova"
→ Core agents/skills updated
→ "nova" preserved (not overwritten)
```

### Scenario 3: User Modified Agent
```
User modified agentic-memory.md
→ Core agents/skills updated
→ Modified agent preserved with warning
```

### Scenario 4: Fresh Install
```
No previous installation detected
→ Redirect to install.md
```

## Example Session

```
User: Load update.md

AI: Checking for updates...

Current version: 0.9.0
Latest version: 1.0.0
Update available! ✓

Analyzing your setup...
- Custom agent detected: "nova" (will preserve)
- Core agents: 14 (will update)
- Core skills: 5 (will update)
- New components: 2 agents, 1 skill

Proceed with update? [Y/n]: y

Updating...
  ├─ core/agents/* → ✓
  ├─ core/skills/* → ✓
  ├─ New: api-coder.md → ✓
  ├─ New: api-auditor.md → ✓
  └─ New: api skill → ✓

✅ Update Complete!

Updated: 14 agents, 5 skills
Added: 2 agents (api-coder, api-auditor), 1 skill (api)
Preserved: nova (your customized agent)

Version: 0.9.0 → 1.0.0
```

## Rollback

If something goes wrong:

```
User: "Rollback the update"

AI: Restoring previous version...
    - Restoring from backup (if exists)
    - Or re-run install.md for fresh start
```

## Notes

- Always backup before major updates
- Core components are always updated (users shouldn't modify)
- User customizations are always preserved
- Version tracking enables smart updates
