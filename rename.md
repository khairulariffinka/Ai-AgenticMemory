# Rename Protocol

AI-assisted protocol to rename the primary agent from "agentic-memory" to a custom name.

## Usage

```
User: "Load rename.md"
AI: "What would you like to rename 'agentic-memory' to?"
User: "nova" (or any name)
AI: [Executes rename steps]
```

## Rename Steps

Execute these steps when user provides their chosen name:

### Step 1: Validate Name

```
Rules for valid name:
- Lowercase letters and numbers only
- Hyphens allowed between words
- No spaces, underscores, or special characters
- Must be 1-64 characters
- Cannot start or end with hyphen

Valid examples: nova, my-agent, code-helper-123
Invalid examples: My Agent, nova_v2, agent!
```

If invalid, ask user for a different name.

### Step 2: Check Current Agent

```
Check if ~/.config/opencode/agents/agentic-memory.md exists
If not, check for any existing renamed agent
If multiple agents found, ask user which to rename
```

### Step 3: Rename Agent File

```bash
# Linux/macOS
mv ~/.config/opencode/agents/agentic-memory.md ~/.config/opencode/agents/{new-name}.md

# Windows (PowerShell)
Move-Item ~/.config/opencode/agents/agentic-memory.md ~/.config/opencode/agents/{new-name}.md
```

### Step 4: Update Agent File Content

Edit the renamed agent file:

```yaml
# Change this line:
name: agentic-memory

# To:
name: {new-name}
```

Also update any references to "agentic-memory" in the file content to "{new-name}".

### Step 5: Rename Skill Folder

```bash
# Linux/macOS
mv ~/.config/opencode/skills/agentic-memory ~/.config/opencode/skills/{new-name}

# Windows (PowerShell)
Move-Item -Recurse ~/.config/opencode/skills/agentic-memory ~/.config/opencode/skills/{new-name}
```

### Step 6: Update Skill File Content

Edit `~/.config/opencode/skills/{new-name}/SKILL.md`:

```yaml
# Change this line:
name: agentic-memory

# To:
name: {new-name}
```

Also update any references to "agentic-memory" in the file content.

### Step 7: Verify Rename

```
Check that all files are correctly renamed:

~/.config/opencode/
├── agents/
│   └── {new-name}.md         ← Renamed ✓
└── skills/
    └── {new-name}/           ← Renamed ✓
        └── SKILL.md          ← Updated ✓
```

### Step 8: Complete

```
✅ Rename Complete!

Old name: agentic-memory
New name: {new-name}

Files updated:
- agents/{new-name}.md
- skills/{new-name}/SKILL.md

Test your renamed agent:
Say: "{new-name}, hello!"
```

## Example Session

```
User: Load rename.md

AI: I'll help you rename your agent.
    Current name: agentic-memory
    What would you like to rename it to?

User: nova

AI: Validating name... ✓
    Renaming agentic-memory → nova...

    1. Renaming agent file... ✓
    2. Updating agent content... ✓
    3. Renaming skill folder... ✓
    4. Updating skill content... ✓

    ✅ Rename Complete!
    Your agent is now "nova"

    Test it: "nova, hello!"
```

## Reverting

To revert to the default name:

```
User: Load rename.md
AI: What name?
User: agentic-memory
AI: [Reverts to default]
```

## Notes

- This only renames the primary agent
- Core subagents (memory, planner, coder, etc.) are NOT renamed
- The rename only affects files in ~/.config/opencode/
- Original files in the project folder are NOT modified
