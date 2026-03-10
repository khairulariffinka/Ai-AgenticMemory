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

---

## Detailed Usage Tutorial

### Tutorial 1: Build a Complete Feature

Step-by-step guide to building a full feature with authentication:

#### Step 1: Activate AgenticMemory

```
[TAB] → agentic-memory
```

#### Step 2: Describe Your Requirement

```
build a user authentication system with:
- User registration (email/password)
- User login with JWT tokens
- Password reset functionality
- Protected routes example
```

#### Step 3: Agent Workflow

AgenticMemory will:

1. **Planner** - Creates hierarchical plan
2. **Parallel Execution** - Coders work simultaneously:
   - `backend-coder`: User model, API endpoints, JWT logic
   - `frontend-coder`: Registration form, login form
   - `test-coder`: Unit tests, integration tests
3. **Parallel Audit** - Auditors check code:
   - `security-auditor`: Vulnerability check
   - `performance-auditor`: Query optimization
   - `style-auditor`: Code conventions

#### Step 4: Review & Commit

AgenticMemory presents results and offers to commit:

```
✓ Files created: 8
✓ Tests added: 12
✓ Security: ✅ Passed
✓ Performance: ✅ Passed

Commit message:
"feat(auth): implement JWT authentication system now? [y/N"

Commit]:
```

---

### Tutorial 2: Code Review

#### Step 1: Activate in Review Mode

```
[TAB] → agentic-memory
```

#### Step 2: Specify Code to Review

```
review the auth module in src/auth/
```

#### Step 3: Review Results

AgenticMemory runs parallel audits:

```
[AUDIT]
├─ security-auditor: 🔴 3 issues found
│   - SQL injection risk in login endpoint
│   - Missing rate limiting
│   - Hardcoded secret detected
├─ performance-auditor: ✅ Passed
└─ style-auditor: ⚠️  2 minor issues
    - Inconsistent naming
    - Missing JSDoc comments

[REPORT]
Risk Score: 7.5/10 (HIGH)
Recommended: Fix security issues before merge
```

---

### Tutorial 3: Quick Prototype

For fast prototyping without audits:

#### Step 1: Activate with Quick Mode

```
[TAB] → agentic-memory
```

#### Step 2: Describe Simple Task

```
quick, create a REST API endpoint for /api/users
```

#### Step 3: Fast Delivery

```
[MODE: quick] Skipping audits
[EXECUTE]
├─ backend-coder: Creating endpoint... ✓
└─ test-coder: Basic tests... ✓

✓ Complete! (Time: 23s)
```

---

### Tutorial 4: Debug an Issue

For troubleshooting with verbose logging:

#### Step 1: Activate in Debug Mode

```
[TAB] → agentic-memory
```

#### Step 2: Describe the Problem

```
debug: User login returns 500 error after password reset
Error occurs in src/auth/login.ts line 42
```

#### Step 3: Step-by-Step Investigation

```
[DEBUG MODE] Verbose logging enabled

[STEP 1] Analyzing error context...
- File: src/auth/login.ts:42
- Error: Cannot read property 'compare' of undefined

[STEP 2] Checking dependencies...
- Found: bcrypt imported but password field empty

[STEP 3] Root cause identified:
- User model password field is optional
- Login handler doesn't validate password existence

[FIX] Proposed solution:
- Add null check for password field
- Return 400 if password not provided

Apply fix? [y/N]:
```

---

### Tutorial 5: Use Specific Subagents

You can invoke specific subagents directly using @ mention:

#### Direct Backend Task

```
@backend-coder, create a new API endpoint POST /api/products
```

#### Direct Security Audit

```
@security-auditor, scan the src/utils/ folder for vulnerabilities
```

#### Direct Git Operations

```
@git-manager, create a feature branch and commit pending changes
```

#### Direct Documentation

```
@docs-manager, generate API documentation for src/api/
```

---

### Tutorial 6: Refactor Existing Code

#### Step 1: Activate in Refactor Mode

```
[TAB] → agentic-memory
```

#### Step 2: Specify Refactoring Goal

```
refactor: Improve the data processing in src/services/parser.ts
- Reduce complexity from O(n²) to O(n)
- Add proper error handling
- Improve readability
```

#### Step 3: Review Changes

```
[REFACTOR]
├─ Analyzed: 3 functions, 150 lines
├─ Identified: 2 nested loops
├─ Optimized: Algorithm improved
└─ Test coverage: Maintained

[PREVIEW]
src/services/parser.ts:45-67 - refactored
src/services/parser.test.ts - updated

Apply changes? [y/N]:
```

---

### Subagent Reference

| Subagent | Invoke | Tools | Best For |
|----------|--------|-------|----------|
| `planner` | Auto-invoked | read, glob, grep | Planning & brainstorming |
| `backend-coder` | `@backend-coder` | write, edit, read, glob, grep, bash | APIs, databases |
| `frontend-coder` | `@frontend-coder` | write, edit, read, glob, grep, bash | UI components |
| `test-coder` | `@test-coder` | write, edit, read, glob, grep, bash | Unit & E2E tests |
| `devops-coder` | `@devops-coder` | write, edit, read, glob, grep, bash | Docker, CI/CD |
| `security-auditor` | `@security-auditor` | read, glob, grep | Security audit |
| `performance-auditor` | `@performance-auditor` | read, glob, grep | Performance check |
| `style-auditor` | `@style-auditor` | read, glob, grep | Code review |
| `git-manager` | `@git-manager` | read, glob, grep, bash | Git operations |
| `docs-manager` | `@docs-manager` | write, edit, read, glob, grep, bash | Documentation |
| `memory` | `@memory` | write, edit, read, glob, grep, bash | Memory operations |

---

### Common Patterns

#### Pattern 1: Full Development Cycle

```
1. [Plan] Describe feature → Planner creates plan
2. [Build] Switch to dev mode → Coders execute
3. [Audit] Automatic → Auditors check
4. [Commit] Auto-commit → Git-manager commits
```

#### Pattern 2: Review Only

```
1. [Review] Switch to review mode
2. [Audit] Run all auditors
3. [Report] Get risk score
4. [Fix] Optional: switch to dev mode to fix
```

#### Pattern 3: Quick Iteration

```
1. [Quick] Skip audits
2. [Build] Fast delivery
3. [Test] Manual verification
4. [Iterate] Repeat if needed
```

---

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

**Version**: 1.2.0
**Last Updated**: March 2026
