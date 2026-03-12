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
  - Track the custom name for later merge
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
cp core/agents/research.md ~/.config/opencode/agents/
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
cp core/agents/decision-log.md ~/.config/opencode/agents/
cp core/agents/database-expert.md ~/.config/opencode/agents/
cp core/agents/api-designer.md ~/.config/opencode/agents/
cp core/agents/doc-scout.md ~/.config/opencode/agents/
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
cp -r core/skills/research ~/.config/opencode/skills/
cp -r core/skills/decision-log ~/.config/opencode/skills/
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

### Step 6: Update Primary Agent

Handle both default and renamed primary agents:

```
# If user has renamed their agent (e.g., "nova"):
# 1. Apply diff-based merge to update their agent with new features
# 2. Preserve user's custom name, instructions, and customizations
# 3. Merge strategy:
#    - Add new sections from updated agentic-memory.md
#    - Update existing sections that haven't been customized
#    - Preserve user-specific customizations (name, custom instructions, etc.)
# 4. Prompt user: "Update your renamed agent '{name}' with latest features? [Y/n]"

# If agent is still named "agentic-memory" (not renamed):
cp agent/agentic-memory.md ~/.config/opencode/agents/
cp -r agent/skills/agentic-memory ~/.config/opencode/skills/

# If no primary agent exists at all:
#  - Copy the default primary agent
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
- Primary agent "{name}" (diff/merge applied - your custom name preserved)

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
→ "nova" updated via diff/merge (preserves name, gets new features)
```

### Scenario 3: User Modified Agent
```
User modified agentic-memory.md
→ Core agents/skills updated
→ Modified agent updated via diff/merge (preserves customizations)
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
- Primary agent: "nova" (renamed by user)
- Core agents: 19 (will update)
- Core skills: 7 (will update)
- New components: 2 agents, 1 skill

Proceed with update? [Y/n]: y

Updating...
  ├─ core/agents/* → ✓
  ├─ core/skills/* → ✓
  ├─ New: api-coder.md → ✓
  ├─ New: api-auditor.md → ✓
  ├─ New: api skill → ✓
  └─ Primary agent "nova": diff/merge → ✓

✅ Update Complete!

Updated: 19 agents, 7 skills
Primary agent "nova": Updated with new features (your custom name preserved)
Added: 2 agents (api-coder, api-auditor), 1 skill (api)

Version: 0.9.0 → 1.0.0
```

### Diff-Based Merge for Renamed Agents

When user has renamed their primary agent, the AI will:

1. **Read both files**: user's agent + new agentic-memory.md
2. **Identify changes**: What sections are new/updated in the new version
3. **Merge intelligently**:
   - Add entirely new sections from the update
   - Update core functionality sections (if user hasn't heavily modified)
   - Preserve user's custom sections, name, and personal instructions
4. **Prompt for confirmation**: Show what will change before applying

```
Merge Preview for "nova":
+ NEW: relationship-memory feature (added)
+ UPDATED: parallel subagent execution (enhanced)
~ PRESERVED: Your custom instructions (unchanged)
~ PRESERVED: Agent name "nova" (unchanged)

Apply these changes? [Y/n]
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
- Renamed primary agents: Diff-based merge applied (preserves name + customizations, adds new features)
- Version tracking enables smart updates
