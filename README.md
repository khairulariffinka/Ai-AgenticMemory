# AgenticMemory

**AI Coding Assistant for OpenCode**

Give it a task, it handles the rest.

```bash
"build a login page"
"create a REST API"
"review my code"
```

---

## Get Started in 3 Steps

### 1. Install

```
"Load install.md"
```

### 2. Activate

Press `TAB` until you see `agentic-memory`

### 3. Use

Just tell it what you want:

```
build a user authentication system
```

---

## What Can It Do?

| Task | Example |
|------|---------|
| Build features | `build a login page` |
| Create APIs | `create a REST API for products` |
| Write tests | `write tests for auth module` |
| Review code | `review the payment module` |
| Fix bugs | `debug: login returns 500 error` |
| Docker setup | `set up Docker for my app` |

**That's it!** No need to manage 21 subagents - AgenticMemory handles everything automatically.

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

---

## Detailed Tutorial

### Tutorial 1: Build a Complete Feature

Follow this step-by-step guide to build a full feature using the structured workflow.

#### Step 1: Activate AgenticMemory

```
[TAB] → agentic-memory
```

Or use @ mention:
```
@agentic-memory, I need to build a feature
```

#### Step 2: Start with Research

AgenticMemory will automatically invoke the research agent to analyze your codebase:

```
[RESEARCH] Analyzing codebase...

✓ Tech stack detected: Node.js + Express + PostgreSQL
✓ Project structure found
✓ Existing patterns identified:
  - JWT authentication in src/auth/
  - RESTful API conventions
  - Prisma ORM

Context gathered for planning.
```

#### Step 3: Plan the Implementation

The planner creates a structured plan:

```
[PLANNER] Creating implementation plan...

## Plan: User Authentication Feature

### Tasks:
- [ ] 1.1 Create User model with Prisma
- [ ] 1.2 Create auth routes (register/login)
- [ ] 1.3 Implement JWT middleware
- [ ] 1.4 Create login form (frontend)
- [ ] 1.5 Add unit tests

### Parallel Groups:
Group 1: User model + Auth routes
Group 2: Frontend form + Tests
```

#### Step 4: Execute the Plan

Coders implement each task:

```
[GROUP 1 - Parallel]
├─ backend-coder: Creating User model... ✓
└─ backend-coder: Creating auth routes... ✓

[GROUP 2 - Parallel]
├─ frontend-coder: Creating login form... ✓
└─ test-coder: Writing unit tests... ✓
```

#### Step 5: Review and Commit

Auditors verify the code:

```
[AUDIT - Parallel]
├─ security-auditor: ✅ Passed
├─ performance-auditor: ✅ Passed
└─ style-auditor: ✅ Passed

[GIT-MANAGER] Ready to commit

Files changed: 5
- src/models/User.ts
- src/routes/auth.ts
- src/middleware/auth.ts
- src/views/login.vue
- tests/auth.test.ts

Commit message:
feat(auth): implement JWT authentication

Commit now? [y/N]: y
✓ Committed!
```

---

### Tutorial 2: Quick Feature Request

For fast prototyping without full workflow:

#### Step 1: Activate with Quick Mode

```
[TAB] → agentic-memory
```

#### Step 2: Specify Quick Mode

```
quick, create a simple API endpoint for /api/users
```

#### Step 3: Fast Implementation

```
[MODE: quick] Skipping audits

[EXECUTE]
└─ backend-coder: Creating endpoint... ✓

✓ Complete! (Time: 15s)
```

---

### Tutorial 3: Code Review

Review existing code with audit agents:

#### Step 1: Activate in Review Mode

```
[TAB] → agentic-memory
```

#### Step 2: Specify Review Task

```
review the src/auth/ module
```

#### Step 3: Detailed Audit

```
[MODE: review]

[AUDIT - Parallel]
├─ security-auditor: 🔴 2 issues found
│   - SQL injection risk in login.ts:42
│   - Missing rate limiting
├─ performance-auditor: ✅ Passed
└─ style-auditor: ⚠️ 1 minor issue
    - Inconsistent naming

[REPORT]
Risk Score: 7.5/10 (HIGH)

Recommended fixes:
1. Use parameterized queries
2. Add rate limiting middleware
3. Standardize function naming
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
debug: Login returns 500 error after password reset
Error in src/auth/login.ts:42
```

#### Step 3: Step-by-Step Analysis

```
[DEBUG MODE] Verbose logging enabled

[STEP 1] Analyzing error context...
File: src/auth/login.ts:42
Error: Cannot read property 'compare' of undefined

[STEP 2] Checking dependencies...
- bcrypt imported ✓
- password field: undefined ❌

[STEP 3] Root cause identified:
- User model password field is optional
- Login handler doesn't validate password exists

[FIX] Proposed solution:
- Add null check: if (!user.password)
- Return 400: "Password not set"

Apply fix? [y/N]:
```

---

### Tutorial 5: Use Specific Subagents

Invoke specific subagents directly:

#### Research Phase
```
@research, analyze the codebase for payment processing patterns
```

#### Backend Task
```
@backend-coder, create a new API endpoint POST /api/products
```

#### Security Audit
```
@security-auditor, scan src/utils/ for vulnerabilities
```

#### Git Operations
```
@git-manager, create a feature branch and commit pending changes
```

---

## Operating Modes

| Mode | Description | Best For |
|------|-------------|----------|
| **dev** | Full workflow with all audits | Production code |
| **quick** | Skip audits, fast iteration | Prototyping |
| **review** | Audit-only mode | Code reviews |
| **refactor** | Focus on refactoring | Improving existing code |
| **debug** | Verbose logging, step-by-step | Troubleshooting |
| **test** | Test-first development | TDD workflow | 

## Dynamic Agent Name

AgenticMemory supports **dynamic naming** - you can rename the primary agent to your preferred name, and it will adapt its behavior accordingly.

### How to Rename

```
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

### How It Works

The agent detects its name from:
1. Agent definition file (`name` field)
2. User's custom configuration

When renamed, the agent:
- Uses the new name in greetings
- Preserves all customizations during updates
- Maintains personality and instructions

---

## Parallel Execution

AgenticMemory executes independent tasks **in parallel** for faster delivery.

### How It Works

```
Group 1 (No dependencies - runs in parallel):
├── backend-coder: Create User model
└── frontend-coder: Create login form

Group 2 (Depends on Group 1):
├── backend-coder: Create auth API
└── frontend-coder: Integrate API

Group 3 (Final):
├── test-coder: Write tests
└── security-auditor: Security audit
```

### Execution Flow

1. Planner identifies all tasks
2. Tasks are grouped by dependencies
3. Independent tasks run in parallel
4. Wait for completion
5. Execute next group
6. Continue until complete

---

## Adaptive Workflow

The workflow adapts based on context:

| Factor | Adaptation |
|--------|------------|
| File size | Large files → thorough audit, small → quick |
| File type | Config → skip audit, logic → full audit |
| Project phase | Prototype → skip checks, production → full |
| User history | User prefers X → adapt accordingly |
| Error rate | Many failures → slow down, add debugging |

---

## Context-Aware Intelligence

Before executing, AgenticMemory checks:

1. **Project Knowledge**
   - "Have I worked on this project before?"
   - Load relevant decisions and patterns

2. **Similar Tasks**
   - "Did similar task in Project X"
   - Suggest proven approaches

3. **User Preferences**
   - "User prefers detailed commits"
   - "User skips certain audits"
   - Adapt accordingly

4. **Risk Assessment**
   - High-risk task? Add extra audits
   - Low-risk? Streamline process

---

## Error Recovery

AgenticMemory handles failures gracefully:

| Scenario | Recovery |
|----------|----------|
| Coder fails | Retry with more context, try alternative, escalate to user |
| Auditor fails | Return to coder for fixes, add debug mode |
| Parallel task fails | Continue independent tasks, re-queue failed, report partial success |

---

## Session Auto-Save

Every session is automatically saved:

- Tasks completed with subagent attribution
- Decisions made during session
- Patterns identified
- Performance metrics
- Cross-project learnings

---

## Skills System

AgenticMemory uses a **skills** system for specialized capabilities:

```
core/skills/
├── planner/      # Planning skill
├── coder/        # Coding skill
├── auditor/      # Audit skill
├── memory/       # Memory skill
├── security/    # Security skill
└── research/     # Research skill
```

Skills are loaded dynamically based on task requirements. See [TUTORIALS.md](./TUTORIALS.md) for details.

---

## 📋 BRS & SDS: Project Specification Management

AgenticMemory now includes comprehensive **Business Requirement Specification (BRS)** and **System Design Specification (SDS)** management for professional project documentation.

### 🎯 What Are BRS & SDS?

**BRS (Business Requirement Specification)**
- **Purpose:** Document what the system should do from a business perspective
- **Audience:** Clients, stakeholders, project managers
- **Content:** Requirements, scope, budget, timeline, exclusions
- **Language:** Bilingual (English + Bahasa Melayu) support
- **Protection:** Clear scope exclusions prevent scope creep

**SDS (System Design Specification)**
- **Purpose:** Document how the system will be built technically
- **Audience:** Developers, architects, technical leads
- **Content:** Architecture, database design, API specs, decisions
- **Language:** English (technical standard)
- **Value:** Clear blueprint for implementation

### 🚀 Quick Start

#### Create Your First BRS
```bash
# After meeting with client
User: "@brs-manager create BRS"

Paste meeting notes or voice transcript here...
Client: ABC Sdn Bhd
Project: Inventory Management System
Budget: RM 40,000
Timeline: 3 months
Key features: Stock tracking, reports, alerts

@brs-manager:
✓ Detected project type: Web Application
✓ Selected: brs-web-template.md
✓ Generated: docs/BRS-v1.0.md (16 sections)
✓ Requirements: 24 total (10 MUST, 8 SHOULD, 6 NICE)

Next: Review BRS with client and get approval
```

#### Create SDS from BRS
```bash
# After BRS approved by client
User: "@sds-manager create SDS from BRS"

@sds-manager:
✓ Reading BRS-v1.0.md (24 requirements)
✓ Designing architecture: Laravel + React + MySQL
✓ Creating database ERD (6 entities)
✓ Specifying APIs (12 endpoints)
✓ Logging architectural decisions (3 decisions)

Generated: docs/SDS-v1.0.md (12 sections)
```

#### Handle Change Requests
```bash
# When client wants new feature
User: "@brs-manager create change request"

Feature: Add mobile app support

@brs-manager:
⚠️ IMPACT ANALYSIS
├─ Technical: Major architecture change
├─ Timeline: +6 weeks
├─ Cost: +RM 25,000
└─ Risk: HIGH (new tech stack)

📋 COMPARISON
Current BRS: Web responsive only
Proposed: Add native mobile apps

Generated: CR-001-mobile-app.md
Recommendation: "Defer to Phase 2"
```

### 📊 BRS Structure (16 Sections)

| Section | Content | Bilingual |
|---------|---------|-----------|
| 1. Executive Summary | Project overview, goals | ✅ EN + BM |
| 2. Stakeholders | Who's involved | ✅ EN + BM |
| 3. Business Objectives | SMART goals | ✅ EN + BM |
| 4. User Personas | Target users | ✅ EN + BM |
| 5. Functional Requirements | What system does (MoSCoW) | ✅ EN + BM |
| 6. Non-Functional Requirements | Performance, security | EN only |
| 7. Constraints & Dependencies | Limitations | ✅ EN + BM |
| 8. **Scope Exclusions** ⭐ | What's NOT included | ✅ EN + BM |
| 9. Future Phases | Roadmap | ✅ EN + BM |
| 10. Timeline & Milestones | Schedule | EN only |
| 11. Budget Estimate | Cost breakdown | ✅ EN + BM |
| 12. Risk Assessment | Potential issues | EN only |
| 13. Assumptions | What we assume | ✅ EN + BM |
| 14. Approval Matrix | Sign-off table | ✅ EN + BM |
| 15. Change Log | Version history | ✅ EN + BM |

**Section 8 (Scope Exclusions) is CRITICAL** - This protects you from scope creep by explicitly stating what's not included.

### 🏗️ SDS Structure (12 Sections)

| Section | Content | Key Value |
|---------|---------|-----------|
| 1. System Overview | High-level description | Context |
| 2. Architecture | Diagrams, components | Blueprint |
| 3. Data Model | ERD, schemas | Database design |
| 4. API Specifications | Endpoints, request/response | Integration contract |
| 5. Component Design | Service layer, classes | Implementation guide |
| 6. Security Architecture | Auth, authorization | Security requirements |
| 7. Scalability & Performance | Traffic, caching | Growth planning |
| 8. **Decision Log** ⭐ | Why we chose X over Y | Knowledge preservation |
| 9. Implementation Phases | Development roadmap | Project planning |
| 10. Testing Strategy | Coverage, types | Quality assurance |
| 11. Deployment Architecture | Infrastructure | DevOps guide |
| 12. Future Considerations | Phase 2+ prep | Extensibility |

**Section 8 (Decision Log) is CRITICAL** - Documents architectural decisions with rationale for future reference.

### 💡 Common Workflows

#### Workflow 1: New Project Kickoff
```
1. Client meeting → Take notes
2. @brs-manager create BRS
3. Review BRS with client
4. Client approves (digital signature)
5. @sds-manager create SDS from BRS
6. @planner create implementation plan
7. Start development
```

#### Workflow 2: Scope Change Management
```
1. Client requests new feature
2. @brs-manager create change request
3. Review impact (time/cost/risk)
4. Present to client
5. Client decides: Accept/Defer/Reject
6. If accepted:
   - Update BRS to v1.1
   - Update SDS accordingly
   - Adjust planner timeline
7. Document decision
```

#### Workflow 3: Development Reference
```
1. Developer starts task
2. Check SDS Section 4: API specs
3. Check SDS Section 3: Database schema
4. Check BRS: Acceptance criteria
5. Implement dengan confident
6. Verify against specs
```

### 🛡️ Scope Protection (Why This Matters)

**Problem:** Client tiba-tiba nak tambah feature
```
Client: "Eh tambah TikTok integration boleh?"

Without BRS:
You: "Er... boleh kot..."
→ Scope creep
→ Delayed project
→ Reduced profit

With BRS:
You: "Check BRS Section 8 - Scope Exclusions. 
       TikTok not included dalam Phase 1.
       Saya boleh create Change Request."

@brs-manager generates CR:
├─ Effort: +80 hours
├─ Cost: +RM 16,000
├─ Timeline: +3 weeks
└─ Risk: HIGH

Client: "Mahalnya! Takpe dulu lah."
→ Scope protected
→ Timeline maintained
→ Profit preserved
```

### 🌐 Language Support

**Option 1: English Only**
```bash
@brs-manager create BRS english
```
All content dalam English.

**Option 2: Bilingual (Default)**
```bash
@brs-manager create BRS bilingual
```
English primary dengan Bahasa Melayu summaries.

**Best For:**
- English only: International clients, technical teams
- Bilingual: Malaysian clients, mixed stakeholders

### 📁 File Organization

```
project/
├── docs/
│   ├── BRS-v1.0.md              # Initial requirements
│   ├── BRS-v1.1.md              # After CR-001
│   ├── SDS-v1.0.md              # Technical specs
│   ├── CHANGELOG.md             # Version history
│   ├── SIGNATURES.md            # Approvals
│   └── CR-001-feature-x.md      # Change requests
└── planner.md                   # Implementation plan
```

### 🎓 Learning Resources

- **Tutorial #19:** BRS-Manager Deep Dive → [TUTORIALS.md](./TUTORIALS.md#19-brs-manager)
- **Tutorial #20:** SDS-Manager Deep Dive → [TUTORIALS.md](./TUTORIALS.md#20-sds-manager)
- **BRS Skill:** Standards & templates → `core/skills/brs/SKILL.md`
- **SDS Skill:** Standards & patterns → `core/skills/sds/SKILL.md`

---

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
| `security` | Full security scanner with bash access |
| `security-auditor` | OWASP Top 10, secrets detection |
| `performance-auditor` | Optimization, N+1 queries |
| `style-auditor` | Code style, naming conventions |
| `auditor` | General code review |

### Planner & Research
| Agent | Specialty |
|-------|-----------|
| `planner` | Hierarchical planning, risk assessment |
| `research` | Codebase analysis and context gathering |

### Memory & Decision
| Agent | Specialty |
|-------|-----------|
| `memory` | Semantic search, decision tracking |
| `decision-log` | Design decisions with rationale |

### Utility Subagents
| Agent | Specialty |
|-------|-----------|
| `git-manager` | Git operations, commits |
| `docs-manager` | Documentation generation |
| `coder` | Universal code writer |
| `database-expert` | SQL optimization, schema design |
| `api-designer` | REST/GraphQL API design |
| `doc-scout` | Fetch live docs for external libraries |

### Specification Subagents
| Agent | Specialty |
|-------|-----------|
| `brs-manager` | Business Requirement Specifications with scope protection |
| `sds-manager` | System Design Specifications with architecture tracking |

> 📚 **Want detailed tutorials?** See [TUTORIALS.md](./TUTORIALS.md) for complete guides on every subagent with examples and workflows.

## Project Structure

```
Ai-AgenticMemory/
├── VERSION.yaml           # Version tracking
├── README.md              # This file
├── TUTORIALS.md          # Detailed subagent tutorials
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

---

## Project Context: AGENTS.md

AgenticMemory uses the official OpenCode **AGENTS.md** file as the source of truth for project context.

### What is AGENTS.md?

AGENTS.md is the official OpenCode file for project context:
- **Tech Stack** - Framework, language, database
- **Coding Conventions** - Naming, structure, patterns
- **Features** - Project requirements and features
- **Decisions** - Major design decisions with rationale

### AgenticMemory Workflow

```
1. RESEARCH: Analyze codebase → Find patterns
2. PLANNER: Creates plan → Auto-creates AGENTS.md if not exists
3. CODER: Reads AGENTS.md → Uses specified tech stack
4. DECISION-LOG: Logs decisions → Updates AGENTS.md
5. MEMORY: Updates AGENTS.md → Syncs context changes
6. AUDITOR: Verify → Check conventions
7. GIT-MANAGER: Commit → Push (with permission)
```

### Structured Development Phases

| Phase | Agent | Purpose |
|-------|-------|---------|
| **Research** | `@research` | Analyze codebase, find patterns |
| **Plan** | `planner` | Create implementation plan |
| **Execute** | `coders` | Implement changes |
| **Commit** | `git-manager` | Commit (with permission) |
| **Review** | `auditors` | Verify implementation |

### AGENTS.md Structure

```markdown
# Project: MyApp

## Tech Stack
- Frontend: React + TypeScript
- Backend: Node.js + Express
- Database: PostgreSQL

## Decisions

### DEC-2026-001: Use JWT for Authentication
**Date:** 2026-03-10
Chose JWT because stateless and scales horizontally.

## Coding Conventions
- Variables: camelCase
- Classes: PascalCase
- Files: kebab-case
```

---

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

AgenticMemory uses **version tracking** to ensure smart updates. The current version is stored in `VERSION.yaml` and compared during updates.

### Check for Updates

```bash
"Load update.md"
```

The update protocol will:
- Check current version vs latest version
- Update core agents and skills
- Preserve your customizations (especially for renamed agents)
- Add new components automatically

### What Gets Updated

| Component | Update Behavior |
|-----------|-----------------|
| Core agents | Always updated |
| Core skills | Always updated |
| Primary agent (default name) | Full overwrite |
| Primary agent (renamed) | Diff/merge - preserves name & customizations |
| User customizations | Never overwritten |

### Update for Renamed Agents

When you rename your primary agent (e.g., to "nova" or "my-agent"), updates are applied using **diff-based merge**:

- **Preserved**: Your custom agent name
- **Preserved**: Your custom instructions and personalizations
- **Updated**: New features and improvements from the latest version

```
Example: You renamed to "nova"

Update applied:
+ NEW: relationship-memory feature
+ UPDATED: parallel execution enhancements
~ PRESERVED: Your custom name "nova"
~ PRESERVED: Your custom instructions
```

This ensures you always get the latest updates while keeping your personal agent identity.

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
| `decision-log` | `@decision-log` | write, edit, read, glob, grep | Decision logging |

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

**Version**: 0.0.3
**Last Updated**: March 2026
