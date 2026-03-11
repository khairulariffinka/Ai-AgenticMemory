# AgenticMemory Subagent Tutorials

Comprehensive guide to using all 16 subagents in AgenticMemory.

---

## Table of Contents

1. [🟢 Coder Subagents](#-coder-subagents)
2. [🔴 Auditor Subagents](#-auditor-subagents)
3. [🔵 Planner](#-planner)
4. [🟣 Memory Subagents](#-memory-subagents)
5. [🟡 Utility Subagents](#-utility-subagents)

---

## 🟢 Coder Subagents

Coder subagents are responsible for writing and implementing code based on the planner's task breakdown.

---

### 1. backend-coder

#### What It Does

The `backend-coder` is a specialized backend developer focused on server-side logic, APIs, databases, and authentication. It creates robust, secure, and scalable backend code following best practices.

**Specializations:**
- **APIs:** REST, GraphQL, gRPC, WebSocket
- **Databases:** MySQL, PostgreSQL, MongoDB, Redis
- **Auth:** JWT, OAuth, Session, API Keys
- **Frameworks:** Laravel, Django, Express, FastAPI, Spring
- **Languages:** PHP, Python, Node.js, Java, Go, Rust

#### When to Use

- Creating new API endpoints
- Building database models and migrations
- Implementing authentication systems
- Writing server-side business logic
- Setting up database schemas

#### How to Use

```
@backend-coder, create a user registration API with email validation
```

```
@backend-coder, implement JWT authentication for protected routes
```

#### Example

```
@backend-coder, create a REST API for blog posts with CRUD operations

What happens:
1. Creates Post model with migration
2. Creates PostController with all CRUD methods
3. Creates API routes
4. Adds validation rules
5. Writes unit tests
```

---

### 2. frontend-coder

#### What It Does

The `frontend-coder` specializes in building user interfaces with React, Vue, Angular, or other frontend frameworks. It focuses on UI components, user experience, state management, and client-side logic.

**Specializations:**
- **Frameworks:** React, Vue, Angular, Svelte, Next.js, Nuxt
- **Styling:** Tailwind, Bootstrap, Styled Components, CSS Modules
- **State:** Redux, Zustand, Pinia, React Query, Context API
- **UI Libraries:** Material-UI, Ant Design, Chakra UI, shadcn/ui

#### When to Use

- Building UI components (buttons, forms, cards)
- Creating frontend pages and views
- Implementing state management
- Adding interactive features
- Making responsive designs

#### How to Use

```
@frontend-coder, create a login form with email and password fields
```

```
@frontend-coder, build a user profile card component with avatar
```

#### Example

```
@frontend-coder, create a dashboard page with sidebar navigation

What happens:
1. Creates Dashboard layout component
2. Creates Sidebar navigation component
3. Creates content sections
4. Adds responsive styling
5. Implements mobile menu toggle
```

---

### 3. test-coder

#### What It Does

The `test-coder` specializes in creating comprehensive test coverage including unit tests, integration tests, and E2E tests. It follows testing best practices and ensures code reliability.

**Specializations:**
- **Unit:** Jest, Vitest, PHPUnit, pytest
- **Integration:** PHPUnit, Jest, Supertest
- **E2E:** Playwright, Cypress, Selenium
- **Coverage:** Istanbul, PHPUnit Coverage
- **Mocking:** Mockery, Jest Mocks, MSW

#### When to Use

- Writing unit tests for new features
- Creating integration tests for API endpoints
- Building E2E test scenarios
- Setting up test factories
- Achieving adequate test coverage

#### How to Use

```
@test-coder, write unit tests for the UserService class
```

```
@test-coder, create E2E tests for user login flow
```

#### Example

```
@test-coder, add tests for authentication module

What happens:
1. Analyzes UserService code
2. Writes unit tests for login, logout, registration
3. Writes integration tests for auth endpoints
4. Creates test factories for User model
5. Achieves 80%+ code coverage
```

---

### 4. devops-coder

#### What It Does

The `devops-coder` specializes in Docker containers, CI/CD pipelines, deployment configurations, and infrastructure automation. It handles everything needed to deploy and run applications.

**Specializations:**
- **Containers:** Docker, Docker Compose, Kubernetes
- **CI/CD:** GitHub Actions, GitLab CI, Jenkins, CircleCI
- **IaC:** Terraform, Ansible, CloudFormation
- **Cloud:** AWS, GCP, Azure, DigitalOcean
- **Scripting:** Bash, Python, Go

#### When to Use

- Setting up Docker containers
- Creating CI/CD pipelines
- Configuring deployment scripts
- Setting up infrastructure as code
- Configuring reverse proxies

#### How to Use

```
@devops-coder, set up Docker for the Node.js application
```

```
@devops-coder, create GitHub Actions workflow for CI/CD
```

#### Example

```
@devops-coder, create deployment configuration for production

What happens:
1. Creates Dockerfile with multi-stage build
2. Creates docker-compose.yml for local dev
3. Creates GitHub Actions CI/CD pipeline
4. Configures Nginx reverse proxy
5. Creates deployment scripts
```

---

## 🔴 Auditor Subagents

Auditor subagents review code quality, security, performance, and style. They ensure code meets best practices before deployment.

---

### 5. security-auditor

#### What It Does

The `security-auditor` is a specialized security expert focused on OWASP Top 10 vulnerabilities, secrets detection, and comprehensive vulnerability scanning. It performs read-only security audits.

**OWASP Top 10 Coverage:**
| ID | Category |
|----|----------|
| A01 | Injection (SQL, NoSQL, Command) |
| A02 | Broken Authentication |
| A03 | Sensitive Data Exposure |
| A04 | XXE |
| A05 | Broken Access Control |
| A06 | Security Misconfiguration |
| A07 | XSS (Reflected, Stored, DOM) |
| A08 | Insecure Deserialization |
| A09 | Using Vulnerable Components |
| A10 | Insufficient Logging |

#### When to Use

- Before deploying to production
- After major code changes
- Security compliance checks
- Finding hardcoded secrets
- Vulnerability assessment

#### How to Use

```
@security-auditor, scan the auth module for vulnerabilities
```

```
@security-auditor, check for hardcoded API keys in the codebase
```

#### Example Output

```
[STATUS]: VULNERABILITIES DETECTED

Risk Score: 8.5/10 (HIGH)

Findings:
1. CRITICAL: SQL Injection
   File: app/Http/Controllers/UserController.php:45
   Fix: Use parameterized queries

2. HIGH: Hardcoded API Key
   File: config/services.php:12
   Fix: Use environment variables

Recommendation: Fix before deployment
```

---

### 6. security

#### What It Does

The `security` agent is the full security scanner with bash access. It performs comprehensive security audits including all OWASP Top 10 checks plus additional security patterns.

**Additional Checks:**
- CSRF protection verification
- CORS policy validation
- Rate limiting detection
- File upload security
- Open redirect detection
- ReDoS vulnerability scanning

#### When to Use

- Comprehensive security audits
- When bash access is needed for deeper analysis
- Full vulnerability assessment
- Security hardening

#### How to Use

```
@security, perform full security audit on the API code
```

```
@security, check for common vulnerabilities in the login module
```

---

### 7. performance-auditor

#### What It Does

The `performance-auditor` specializes in identifying performance issues including N+1 queries, memory leaks, and optimization opportunities.

**Performance Checks:**
| Area | Checks |
|------|--------|
| **Database** | N+1 queries, missing indexes, large result sets |
| **Memory** | Memory leaks, large arrays, inefficient loops |
| **CPU** | Expensive computations, nested loops, regex |
| **I/O** | File operations, API calls, caching |
| **Frontend** | Bundle size, render optimization |

#### When to Use

- Optimizing slow endpoints
- Finding memory leaks
- Reducing database queries
- Improving frontend performance
- Pre-deployment checks

#### How to Use

```
@performance-auditor, analyze the database queries for N+1 issues
```

```
@performance-auditor, check for memory leaks in the cache service
```

#### Example Output

```
[STATUS]: PERFORMANCE ISSUES DETECTED

Overall Score: 65/100 (NEEDS IMPROVEMENT)

Findings:
1. HIGH: N+1 Query Detected
   File: app/Http/Controllers/PostController.php:32
   Impact: 100+ queries for 100 posts
   Fix: Use with('comments')

2. MEDIUM: Missing Database Index
   File: database/migrations/2024_01_01_create_users_table.php
   Fix: Add index on email column
```

---

### 8. style-auditor

#### What It Does

The `style-auditor` focuses on code style, naming conventions, consistency, and documentation quality. It ensures code follows project standards.

**Style Checks:**
| Category | Checks |
|----------|--------|
| **Naming** | Variables, functions, classes follow conventions |
| **Formatting** | Indentation, spacing, line length |
| **Documentation** | PHPDoc/JSDoc, inline comments |
| **Consistency** | Mixed patterns, style violations |
| **Best Practices** | Language-specific idioms |

#### When to Use

- Code review processes
- Enforcing coding standards
- Before commits
- After major refactoring
- Onboarding new team members

#### How to Use

```
@style-auditor, check code style in the UserService
```

```
@style-auditor, verify naming conventions are followed
```

#### Example Output

```
[STATUS]: STYLE ISSUES DETECTED

Overall Score: 78/100 (ACCEPTABLE)

Findings:
1. MEDIUM: Inconsistent Variable Naming
   File: app/Services/UserService.php
   Issue: Mixed snake_case and camelCase
   Fix: Use camelCase consistently

2. MEDIUM: Missing PHPDoc
   File: app/Http/Controllers/UserController.php
   Fix: Add PHPDoc blocks
```

---

### 9. auditor

#### What It Does

The `auditor` is a general-purpose code reviewer that checks security, quality, performance, and best practices. It works with ANY framework or language.

**Audit Criteria:**
- **Security:** No hardcoded tokens, SQL injection, XSS
- **Quality:** Syntax correct, framework conventions, error handling
- **Performance:** No N+1 queries, proper loading
- **Best Practices:** DRY, SOLID, naming conventions

#### When to Use

- General code reviews
- Pre-commit checks
- After feature completion
- When you need multiple audit types at once

#### How to Use

```
@auditor, review the new authentication feature
```

```
@auditor, check the entire src directory for issues
```

#### Example Output

```
[STATUS]: ✅ PASSED

Summary: Code is clean, no issues found

Audit Details:
| Check | Status |
|-------|--------|
| Security | ✅ |
| Quality | ✅ |
| Best Practices | ✅ |

Commit now? [y/N]
```

---

## 🔵 Planner

### 10. planner

#### What It Does

The `planner` is an advanced planning agent that creates hierarchical task breakdowns with risk assessment, dependency tracking, and effort estimation. It organizes complex projects into manageable tasks.

**Features:**
| Feature | Description |
|---------|-------------|
| **Hierarchical Planning** | Milestones → Epics → Stories → Tasks |
| **Risk Assessment** | Risk level, impact, mitigation |
| **Dependency Tracking** | Task dependencies and blockers |
| **Effort Estimation** | Time estimates based on complexity |
| **Dynamic Replanning** | Adjust plan when requirements change |
| **Parallel Grouping** | Identify tasks that can run simultaneously |

#### When to Use

- Starting a new feature or project
- Breaking down complex tasks
- Planning sprints or milestones
- Understanding project scope
- Identifying task dependencies

#### How to Use

```
@planner, create a plan for building an e-commerce checkout
```

```
@planner, break down the user authentication feature into tasks
```

#### Example Output

```
# Project Plan: User Authentication

## Overview
- Goal: Implement complete user auth system
- Total Tasks: 8
- Parallel Groups: 2

## Milestones
### Milestone 1: Foundation
- [ ] Task AUTH-001: Create User model
- [ ] Task AUTH-002: Create database migration

### Milestone 2: Authentication
- [ ] Task AUTH-003: Create registration API
- [ ] Task AUTH-004: Create login API

## Parallel Groups
### Group 1 (Can start immediately)
- AUTH-001, AUTH-002

### Group 2 (Depends on Group 1)
- AUTH-003, AUTH-004
```

---

## 🟣 Memory Subagents

Memory subagents handle information retention, decision tracking, and knowledge management across sessions.

---

### 11. memory

#### What It Does

The `memory` agent is an advanced memory system that maintains context across sessions. It provides semantic search, decision tracking, knowledge graphs, and cross-project learning.

**Features:**
| Feature | Description |
|---------|-------------|
| **Semantic Search** | Search by meaning, not just keywords |
| **Decision Tracking** | Log why decisions were made |
| **Knowledge Graph** | Map relationships between files |
| **Cross-Project Learning** | Reuse patterns from other projects |
| **Context Compression** | Summarize old sessions |
| **Pattern Recognition** | Identify recurring patterns |

#### When to Use

- Starting a new session
- Remembering past decisions
- Finding similar implementations
- Understanding project history
- Searching for past solutions

#### How to Use

```
@memory, what decisions were made about authentication?
```

```
@memory, show me similar implementations of payment integration
```

#### Example Output

```
[MEMORY LOADED]

Project: MyApp
Tech Stack: Laravel 11 + React + MySQL

Active Decisions:
- DEC-001: Using JWT authentication (2024-01-15)
- DEC-003: Repository pattern (2024-01-10)

Relevant Patterns:
- API Resource Pattern (used 8 times)
- Repository Pattern (active)

Similar Past Work:
- Session 2024-01-15: User authentication
```

---

### 12. decision-log

#### What It Does

The `decision-log` agent tracks and manages design decisions with full context and rationale. It creates a searchable knowledge base for future reference.

**Purpose:**
- Capture design decisions during development
- Document context and constraints
- Record options considered
- Track rationale and trade-offs
- Link related decisions

#### When to Use

- Making architectural choices
- Choosing between technologies
- Selecting database approaches
- Any significant design decision
- When team needs to understand past choices

#### How to Use

```
@decision-log, log the decision to use PostgreSQL over MongoDB
```

```
@decision-log, record the JWT vs Session authentication decision
```

#### Example Format

```
## Decision: DEC-2026-001

**Date:** 2026-03-11
**Context:** Need authentication for API-first app

### Options Considered
| Option | Pros | Cons |
|--------|------|------|
| JWT | Scalable, stateless | Harder to revoke |
| Sessions | Easy to revoke | Not scalable |

### Decision
**Chosen:** JWT with refresh tokens

### Rationale
- API-first architecture
- Mobile app integration planned
- Stateless servers preferred
```

---

## 🟡 Utility Subagents

Utility subagents provide specialized services for research, documentation, and version control.

---

### 13. research

#### What It Does

The `research` agent analyzes the codebase to understand existing patterns, tech stack, and context before planning or implementation. It gathers information needed for accurate coding.

**Research Areas:**
| Area | Details |
|------|---------|
| **Tech Stack** | Framework, language, database, API style |
| **Project Structure** | Directory layout, key files |
| **Existing Patterns** | Code organization, conventions |
| **Similar Implementations** | Find reusable components |

#### When to Use

- Before starting new features
- When unfamiliar with codebase
- Finding existing solutions
- Understanding tech stack
- Investigating bugs

#### How to Use

```
@research, analyze the current project structure
```

```
@research, find how authentication is implemented
```

#### Example Output

```
# Research: New Feature Implementation

## Tech Stack Detected
- Framework: Express.js
- Language: TypeScript
- Database: PostgreSQL
- API: REST

## Relevant Files
| File | Purpose |
|------|---------|
| src/models/User.ts | User model |
| src/routes/auth.ts | Auth routes |

## Existing Patterns
- Validation: express-validator
- Error handling: custom error class
- Auth: JWT with refresh tokens

## Recommendations
- Use existing JWT pattern from auth module
- Follow validation style from controllers
```

---

### 14. git-manager

#### What It Does

The `git-manager` specializes in Git operations including commits, branches, pull requests, and conflict resolution. It handles version control professionally with smart grouping and safety checks.

**Capabilities:**
| Operation | Description |
|-----------|-------------|
| **Commit** | Smart commit message generation with grouping |
| **Branch** | Feature branch creation with naming conventions |
| **PR** | Pull request creation with auto-description |
| **Merge** | Conflict detection and resolution suggestions |
| **History** | Log analysis, change tracking |
| **Sync** | Fetch, pull, push with permission |

**⚠️ Important: NEVER auto-push** - Always gets user permission first!

---

#### When to Use

- Creating commits with smart message generation
- Managing branches (create, switch, delete)
- Creating pull requests
- Resolving merge conflicts
- Analyzing git history
- Syncing with remote

---

#### How to Use

**Basic Commands:**
```
@git-manager, commit the new authentication feature
@git-manager, create a feature branch for the payment module
@git-manager, create a pull request
@git-manager, show me the recent commits
```

**Advanced Commands:**
```
@git-manager, commit all changes as one
@git-manager, split into separate commits by feature
@git-manager, resolve merge conflict in UserController.php
@git-manager, push to remote
@git-manager, create bugfix branch for login issue
```

---

#### Commit Workflow

**Step 1: Detect Changes**
```
git-manager scans the repository and lists all changes:

Changes detected:
1. app/Models/User.php (modified)
2. app/Http/Controllers/AuthController.php (modified)
3. resources/views/auth/login.blade.php (new)
4. tests/Feature/AuthTest.php (new)
```

**Step 2: Smart Grouping**
```
Analyzing changes...

✓ Grouped by feature: Authentication

Files:
- Model: User.php
- Controller: AuthController.php
- View: login.blade.php
- Test: AuthTest.php
```

**Step 3: Generate Message**
```
Suggested commit message:
feat(auth): implement JWT authentication

- Add JWT token generation
- Create auth middleware
- Add refresh token rotation

Format: Conventional Commits
Type: feat (new feature)
Scope: auth (authentication module)
```

**Step 4: User Confirmation**
```
Commit now? [y/N]: y

✓ Committed!
Hash: 2f83dc8
Message: feat(auth): implement JWT authentication
Files: 4 changed
```

---

#### Branch Management

**Create Feature Branch:**
```
@git-manager, create feature branch for user dashboard

Creating branch...
Name: feature/user-dashboard
Base: main
✓ Branch created and checked out
```

**Create Bugfix Branch:**
```
@git-manager, create bugfix for login error

Creating branch...
Name: bugfix/login-error
Base: main
✓ Branch created and checked out
```

**Branch Naming Conventions:**
| Type | Format | Example |
|------|--------|---------|
| Feature | `feature/<id>-<description>` | `feature/123-user-auth` |
| Bugfix | `bugfix/<id>-<description>` | `bugfix/456-login-error` |
| Hotfix | `hotfix/<id>-<description>` | `hotfix/999-security-patch` |
| Refactor | `refactor/<id>-<description>` | `refactor/789-api-cleanup` |

---

#### Pull Request Workflow

**Create PR:**
```
@git-manager, create pull request for feature branch

Analyzing branch: feature/user-dashboard
Comparing with: main

Changes:
- 5 new files
- 12 modified files
- 3 deleted files

Suggested PR title: feat: implement user dashboard

Description template:
## Summary
- User dashboard with analytics
- Profile management
- Activity log

## Changes
- Add DashboardController
- Add DashboardService
- Add Vue components

## Testing
- Unit tests added
- Integration tests passing

✓ PR created: #45
URL: https://github.com/user/repo/pull/45
```

---

#### Merge Conflict Resolution

**When Conflict Detected:**
```
@git-manager, merge main into feature/user-dashboard

Conflict detected!

Files with conflicts:
1. app/Http/Controllers/UserController.php
2. app/Services/UserService.php

Showing conflicts:
---
<<<<<<< HEAD
    public function index() {
        return view('dashboard');
=======
    public function index() {
        return response()->json(['data' => $this->service->get()]);
>>>>>>> main
---

Options:
1. Keep our changes (HEAD)
2. Keep their changes (main)
3. Manual merge

Which option? [1/2/3]:
```

**Resolution Suggestion:**
```
Conflict: UserController.php:45

Both branches modified the same method differently.
- HEAD: Returns view for web
- main: Returns JSON API response

Suggested resolution: 
Since this is an API-first app, keep main's changes.
The web route should be added separately.

Apply suggestion? [y/N]:
```

---

#### History & Analysis

**View Recent Commits:**
```
@git-manager, show recent commits

Recent commits (last 10):
│ Hash │ Author │ Message │ Date │
│-----|--------|---------|------│
│ 2f83dc8 │ khairul │ feat: add auth │ 2026-03-11 │
│ 29d32b6 │ khairul │ feat: add diff │ 2026-03-10 │
│ ceb1fe2 │ khairul │ feat: research │ 2026-03-09 │
```

**View File History:**
```
@git-manager, show history for UserController.php

History: app/Http/Controllers/UserController.php
│ Commit │ Author │ Change │
|--------|--------|--------│
│ 2f83dc8 │ khairul │ Add update method │
│ 29d32b6 │ khairul │ Refactor validation │
│ a1b2c3d │ khairul │ Initial commit │
```

---

#### Safety Features

| Feature | Description |
|---------|-------------|
| **No Auto-Push** | Always asks permission |
| **Preview Changes** | Shows what will be pushed |
| **Branch Verification** | Confirms target branch |
| **No Force Push** | Unless explicitly requested |
| **Conflict Warning** | Alerts before merge |
| **Backup Reminder** | Suggests backup before risky ops |

---

#### Example Complete Workflow

```
User: @git-manager, commit my auth changes

git-manager:
1. Scanning changes...
   Found: 6 files changed

2. Smart grouping:
   ├─ Authentication (4 files)
   └─ Tests (2 files)

3. Options:
   [1] Commit all as one
   [2] Split: auth + tests
   [3] Review first

User: 1

4. Generating message...
   feat(auth): implement JWT authentication

   - Add JWT token generation
   - Create auth middleware
   - Add refresh token rotation

5. Commit now? [y/N]: y

✓ Committed!
   Hash: 2f83dc8
   Files: 6 changed

6. Push to remote? [y/N]: y

✓ Pushed to origin/main
```

---

#### Error Handling

| Error | Solution |
|-------|----------|
| Nothing to commit | Tell user "No changes to commit" |
| Merge conflict | Offer resolution options |
| Push rejected | Show reason, offer force option |
| Branch exists | Ask: overwrite or use existing? |
| No remote | Tell user to add remote first |

---

#### Integration with Other Agents

git-manager works with:

| Agent | Workflow |
|-------|----------|
| **auditor** | After audit passes → commit |
| **planner** | Mark tasks complete → commit |
| **memory** | Log session → commit |
| **coder** | Code complete → notify for commit |

---

### 15. docs-manager

#### What It Does

The `docs-manager` specializes in creating and maintaining project documentation including READMEs, API docs, inline comments, and architecture diagrams.

**Documentation Types:**
| Type | Purpose |
|------|---------|
| **README** | Project overview, setup |
| **API Docs** | Endpoint documentation |
| **Code Comments** | PHPDoc/JSDoc |
| **Architecture** | System design |
| **Changelog** | Version history |

#### When to Use

- Creating project documentation
- Writing API documentation
- Adding code comments
- Updating README
- Creating architecture diagrams

#### How to Use

```
@docs-manager, create README for the project
```

```
@docs-manager, generate API documentation for the auth endpoints
```

#### Example

```
@docs-manager, update README with installation instructions

What happens:
1. Creates comprehensive README.md
2. Adds installation section
3. Adds configuration examples
4. Creates API documentation section
5. Adds troubleshooting guide
```

---

### 16. coder

#### What It Does

The `coder` is a universal code writer that works with ANY framework or language. It reads the planner's task breakdown and implements code following project conventions.

**Key Features:**
- Works with any framework/language
- Reads AGENTS.md for conventions
- Follows planner tasks
- Implements clean code
- Marks tasks complete

#### When to Use

- General coding tasks
- When specific coder isn't needed
- Working with multiple technologies
- Following planner tasks

#### How to Use

```
@coder, implement task AUTH-001 from planner.md
```

```
@coder, create a new utility helper for date formatting
```

#### Important Workflow

1. Reads AGENTS.md first (tech stack, conventions)
2. Reads planner.md for current task
3. Writes code following conventions
4. Marks task as complete in planner.md

---

## Summary Table

| # | Subagent | Category | When to Use |
|---|----------|----------|-------------|
| 1 | backend-coder | Coder | Server-side code, APIs, databases |
| 2 | frontend-coder | Coder | UI components, React, Vue |
| 3 | test-coder | Coder | Unit tests, integration tests, E2E |
| 4 | devops-coder | Coder | Docker, CI/CD, deployment |
| 5 | security-auditor | Auditor | Security audits (read-only) |
| 6 | security | Auditor | Full security scanning |
| 7 | performance-auditor | Auditor | Performance optimization |
| 8 | style-auditor | Auditor | Code style review |
| 9 | auditor | Auditor | General code review |
| 10 | planner | Planner | Planning, task breakdown |
| 11 | memory | Memory | Context, search, patterns |
| 12 | decision-log | Memory | Recording design decisions |
| 13 | research | Utility | Codebase analysis |
| 14 | git-manager | Utility | Git operations |
| 15 | docs-manager | Utility | Documentation |
| 16 | coder | Utility | General coding |

---

## Quick Reference

### Common Workflows

**Build a feature:**
```
1. @research - Analyze codebase
2. @planner - Create plan
3. @backend-coder - Write backend
4. @frontend-coder - Write frontend
5. @test-coder - Write tests
6. @security-auditor - Security check
7. @style-auditor - Style check
8. @git-manager - Commit
```

**Code review:**
```
@auditor - General review
@security-auditor - Security check
@performance-auditor - Performance check
@style-auditor - Style check
```

---

*For more details, see individual agent documentation in `core/agents/`*
