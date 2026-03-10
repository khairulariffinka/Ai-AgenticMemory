# AgenticMemory

**A customizable AI coding agent framework for OpenCode**

AgenticMemory is an OpenCode-compliant AI agent framework featuring persistent memory, parallel subagent execution, and intelligent task routing. It features multi-mode operation, 14 specialized subagents, and an easy rename protocol for personalization.

**Topics:** `ai-agent` `opencode` `coding-assistant` `memory-system` `subagent` `parallel-execution` `customizable` `agentic-ai`

## Features

| Feature | Description |
|---------|-------------|
| **Persistent Memory** | Tracks decisions, patterns, project context across sessions |
| **Multi-mode** | dev, quick, review, refactor, debug, test modes |
| **Parallel Execution** | Subagents run simultaneously for faster delivery |
| **Intelligent Routing** | Automatically selects optimal subagents for tasks |
| **Customizable** | Rename the agent to your preferred name |
| **Easy Updates** | Smart update preserves your customizations |

## Quick Start

### 1. Install

```bash
"Load install.md"
```

### 2. Activate AgenticMemory

After installation, activate AgenticMemory using one of these methods:

#### Method A: Tab Key (Recommended)
```
[TAB] → Build → Plan → agentic-memory
```
Press Tab to cycle through agents until you reach agentic-memory.

#### Method B: @ Mention
```
@agentic-memory, build a login page for me
```

### 3. Give a Task

```bash
build a login page for me
```

Or with specific mode:

```bash
quick, build a test API for user
review, audit the auth module code
```

---

## How to Use

### Tab Key (Primary Agent)

AgenticMemory is configured as a **primary agent** (`mode: all`), meaning it appears in the Tab cycle:

```
[TAB] cycles: Build → Plan → agentic-memory → Build...
```

Once selected, give your task directly:

```
build user authentication system
```

### @ Mention (Subagent)

You can also invoke AgenticMemory from any other agent:

```
@agentic-memory, review this code
```

### Specify Mode

Include the mode in your task:

| Mode | Example | Best For |
|------|---------|----------|
| **dev** | `build user auth` | Full workflow + audits |
| **quick** | `quick, build test API` | Fast, skip audits |
| **review** | `review, audit this module` | Code review only |
| **debug** | `debug, fix this error` | Verbose troubleshooting |
| **refactor** | `refactor, improve this code` | Code improvement |
| **test** | `test, write tests for this feature` | TDD workflow |

## Operating Modes

| Mode | Description | Best For |
|------|-------------|----------|
| **dev** | Full workflow with all audits | Production code |
| **quick** | Skip audits, fast iteration | Prototyping |
| **review** | Audit-only mode | Code reviews |
| **refactor** | Focus on refactoring | Improving existing code |
| **debug** | Verbose logging, step-by-step | Troubleshooting |
| **test** | Test-first development | TDD workflow |

## Subagents

### Coder Subagents
| Agent | Specialty |
|-------|-----------|
| `backend-coder` | APIs, databases, server-side logic |
| `frontend-coder` | UI components, React/Vue, styling |
| `test-coder` | Unit, integration, E2E tests |
| `devops-coder` | Docker, CI/CD, deployment |

### Auditor Subagents
| Agent | Specialty |
|-------|-----------|
| `security-auditor` | OWASP Top 10, secrets detection |
| `performance-auditor` | Optimization, N+1 queries |
| `style-auditor` | Code style, naming conventions |

### Utility Subagents
| Agent | Specialty |
|-------|-----------|
| `planner` | Hierarchical planning, risk assessment |
| `memory` | Semantic search, decision tracking |
| `git-manager` | Git operations, commits |
| `docs-manager` | Documentation generation |

## Project Structure

```
Ai-AgenticMemory/
├── VERSION.yaml           # Version tracking
├── README.md              # This file
├── install.md             # Installation wizard
├── rename.md              # Rename protocol
├── update.md              # Update protocol
│
├── core/                  # Core components (always updated)
│   ├── agents/            # Subagents
│   │   ├── memory.md
│   │   ├── planner.md
│   │   ├── coder.md
│   │   └── ...
│   └── skills/            # Core skills
│       ├── planner/
│       ├── coder/
│       ├── auditor/
│       └── ...
│
├── agent/                 # Primary agent (user renames this)
│   ├── agentic-memory.md
│   └── skills/
│       └── agentic-memory/
│           └── SKILL.md
│
└── features/              # Optional extensions
    └── relationship-memory/
```

## Installation

### Requirements
- OpenCode installed

### Steps

1. **Clone or download this repository**

2. **Run the install protocol**
   ```
   "Load install.md"
   ```

3. **Restart OpenCode or reload configuration**

4. **Test the installation**
   ```bash
   "agentic-memory, hello!"
   ```

   Or use Tab to select agentic-memory:
   ```
   [TAB] → agentic-memory → "hello!"
   ```

## Customization

### Rename the Agent

```bash
User: "Load rename.md"
AI: "What would you like to rename 'agentic-memory' to?"
User: "nova"
AI: ✅ Renamed to "nova"
```

### Valid Names
- Lowercase letters and numbers
- Hyphens between words
- 1-64 characters
- No spaces or special characters

**Examples:** `nova`, `my-agent`, `code-helper-123`

## Updating

### Check for Updates

```bash
"Load update.md"
```

The update protocol will:
- Update core agents and skills
- Preserve your customizations
- Add new components

### What Gets Updated

| Component | Update Behavior |
|-----------|-----------------|
| Core agents | Always updated |
| Core skills | Always updated |
| Primary agent | Preserved if renamed |
| User customizations | Never overwritten |

## Usage Examples

### Build Feature

```bash
User: "agentic-memory, build user authentication"

AgenticMemory:
  [MODE: dev]
  [PLANNER] Creating plan...
    - 4 tasks identified
    - 2 parallel groups

  [GROUP 1]
    ├─ backend-coder: User model + API
    └─ frontend-coder: Login form

  [GROUP 2]
    └─ test-coder: E2E tests

  [AUDIT]
    ├─ security-auditor: ✅ Passed
    └─ performance-auditor: ✅ Passed

  ✓ Complete!
```

### Code Review

```bash
User: "agentic-memory, review the auth module"

AgenticMemory:
  [MODE: review]

  [AUDIT - Parallel]
    ├─ security-auditor: 2 issues found
    ├─ performance-auditor: ✅ Passed
    └─ style-auditor: 3 minor issues

  [REPORT]
    Risk Score: 6.5/10 (MEDIUM)
```

### Quick Prototype

```bash
User: "agentic-memory, quick mode, build a test API"

AgenticMemory:
  [MODE: quick] Skipping audits
  [EXECUTE] Running tasks...
  ✓ Complete! (Time: 45s)
```

## Multi-Language Support

AgenticMemory detects and responds in your language:

```bash
User: "agentic-memory, build a login page"
AgenticMemory: Sure! I'll build the login page for you...
```

**Supported Languages:**
- English
- Bahasa Melayu Malaysia

## Requirements
- OpenCode CLI

## License
MIT License

## Credits
Created by khairulariffinka
Inspired by AI memory architecture patterns

---

**Version**: 1.1.0
**Last Updated**: March 2026
