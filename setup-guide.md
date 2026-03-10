# Setup Guide

Complete guide to setting up AgenticMemory with OpenCode.

## Table of Contents

1. [Prerequisites](#prerequisites)
2. [Installation](#installation)
3. [Post-Install](#post-install)
4. [Customization](#customization)
5. [Testing](#testing)
6. [Troubleshooting](#troubleshooting)

## Prerequisites

### Required

| Requirement | How to Check | Install |
|-------------|--------------|---------|
| OpenCode CLI | `opencode --version` | [opencode.ai](https://opencode.ai) |

### Optional

| Requirement | Purpose |
|-------------|---------|
| Git | For version control |
| GitHub CLI | For PR creation |

## Installation

### Step 1: Download AgenticMemory

```bash
# Option A: Clone with Git
git clone https://github.com/khairulariffinka/Ai-AgenticMemory.git
cd Ai-AgenticMemory

# Option B: Download ZIP
# Download from GitHub, extract, then:
cd Ai-AgenticMemory
```

### Step 2: Run Installation

In OpenCode, run the installation protocol:

```
Load install.md
```

The AI will:
1. Check OpenCode installation
2. Copy core agents to `~/.config/opencode/agents/`
3. Copy core skills to `~/.config/opencode/skills/`
4. Copy primary agent and skill
5. Verify installation

### Step 3: Restart OpenCode

```bash
# Restart OpenCode to load new agents
opencode
```

Or reload configuration if your OpenCode version supports it.

## Post-Install

### Verify Installation

Check that files are in place:

```
~/.config/opencode/
├── agents/
│   ├── agentic-memory.md    ← Primary agent
│   ├── memory.md            ← Memory subagent
│   ├── planner.md           ← Planning subagent
│   ├── coder.md             ← Coding subagent
│   └── ... (other subagents)
└── skills/
    ├── agentic-memory/      ← Primary skill
    ├── planner/
    ├── coder/
    ├── auditor/
    ├── memory/
    └── security/
```

### Test Basic Functionality

```
User: "agentic-memory, hello!"

AgenticMemory: [LOADING] Hello! I am AgenticMemory...
              [MEMORY] Loading context...
              Ready to help you build!
```

## Customization

### Rename the Agent

To personalize your agent:

```
User: "Load rename.md"
AI: "What would you like to rename 'agentic-memory' to?"
User: "nova"
AI: ✅ Renamed to "nova"
```

**Valid names:**
- `nova`
- `my-agent`
- `code-helper-123`

**Invalid names:**
- `My Agent` (no spaces)
- `nova_v2` (no underscores)
- `agent!` (no special characters)

### Supported Languages

AgenticMemory responds in your language:

| Your Language | Agent Response |
|---------------|----------------|
| English | English |
| Bahasa Melayu | Bahasa Melayu Malaysia |

```
User: "agentic-memory, tolong explain kod ni"
AgenticMemory: Baik! Saya akan terangkan kod ini...
```

## Testing

### Test 1: Basic Response
```
"agentic-memory, hello!"
```
Expected: Agent responds with greeting

### Test 2: Planning
```
"agentic-memory, plan a login feature"
```
Expected: Agent creates a hierarchical plan

### Test 3: Coding
```
"agentic-memory, create a simple hello world function"
```
Expected: Agent writes code

### Test 4: Memory
```
"agentic-memory, remember that I prefer TypeScript"
```
Expected: Agent acknowledges and stores preference

### Test 5: Language Detection
```
"agentic-memory, apa khabar?"
```
Expected: Agent responds in Bahasa Melayu

## Troubleshooting

### "Agent not found"

**Cause:** OpenCode hasn't loaded the new agents.

**Solution:**
1. Restart OpenCode
2. Or reload configuration
3. Verify files exist in `~/.config/opencode/agents/`

### "Permission denied"

**Cause:** Write permissions issue.

**Solution:**
```bash
# Linux/macOS
chmod -R u+w ~/.config/opencode/

# Windows
# Run as Administrator or check folder permissions
```

### "Files already exist"

**Cause:** Previous installation.

**Solution:**
- Use `update.md` to update existing installation
- Or backup and remove old files:
  ```bash
  mv ~/.config/opencode ~/.config/opencode.backup
  ```

### "Skill not loading"

**Cause:** SKILL.md file issues.

**Solution:**
1. Check file is named exactly `SKILL.md` (uppercase)
2. Check YAML frontmatter is valid
3. Restart OpenCode

### "Rename failed"

**Cause:** Invalid name or file locked.

**Solution:**
1. Use only lowercase letters, numbers, hyphens
2. Close any programs using the files
3. Try again with a different name

## Uninstallation

To remove AgenticMemory:

```bash
# Remove agents
rm ~/.config/opencode/agents/agentic-memory.md
rm ~/.config/opencode/agents/memory.md
rm ~/.config/opencode/agents/planner.md
# ... (remove other agent files)

# Remove skills
rm -rf ~/.config/opencode/skills/agentic-memory
rm -rf ~/.config/opencode/skills/planner
rm -rf ~/.config/opencode/skills/coder
# ... (remove other skill folders)

# Remove version marker
rm ~/.config/opencode/.agentic-memory-version
```

## Next Steps

After installation:

1. **Read the README.md** for full feature documentation
2. **Try the examples** to learn the workflow
3. **Customize the agent name** to personalize it
4. **Start building!**

## Getting Help

- **Documentation:** README.md
- **Issues:** GitHub Issues
- **OpenCode Docs:** [opencode.ai/docs](https://opencode.ai/docs)

---

**Version**: 1.0.0
