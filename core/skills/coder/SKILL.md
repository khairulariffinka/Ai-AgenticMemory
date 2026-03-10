---
name: coder
description: Write clean code based on planner.md task breakdown - works with any framework/language
---

## Language Detection

- **CRITICAL**: Detect user's language and respond in the same language
- If user uses **Bahasa Melayu (Malay)**, respond entirely in **Bahasa Melayu Malaysia**
- Code comments can be in English for technical clarity, but conversation must be in Malay when user uses Malay
- Examples:
  - User (Malay): "Tulis kod untuk login" → Respond in Malay, code in English
  - User (English): "Write code for login" → Respond in English

# Coder Skill

Write code based on planner.md task breakdown.

## When to Use

- Implement tasks from planner
- Write new features
- Fix bugs
- Create new files or modify existing

## Workflow

1. **Read planner.md** - Get current task to work on
2. **Identify next unchecked task** - Look for `[ ]` task
3. **Read project context** - Check AGENTS.md for tech stack
4. **Write code** - Implement the task
5. **Update planner.md** - Mark task as `[x]`

## Tech Stack Detection

Automatically detect and adapt to:

| Type | Examples |
|------|----------|
| **Framework** | Laravel, Django, Express, React, Vue, Next.js |
| **Language** | PHP, Python, JavaScript, TypeScript, Go, Rust |
| **Database** | MySQL, PostgreSQL, MongoDB, SQLite |
| **API** | REST, GraphQL, gRPC |
| **Style** | Tailwind, Bootstrap, CSS Modules |

## Project Structure Detection

Auto-detect common structures:

```
# Web Backend
/src
  /controllers
  /models
  /routes
  /middleware

# Frontend
/src
  /components
  /pages
  /hooks
  /services

# API
/api
  /v1
  /controllers
```

## Rules

- Write code only - don't plan or change logic
- Follow project conventions (check AGENTS.md)
- Minimal comments unless necessary
- Output: code block + filename
- Always mark task as complete in planner.md

## Example Output

```
src/app/Http/Controllers/HomeController.php
```php
public function index() {
    return view('home');
}
```

[x] Step 1.1 - Create HomeController
```

## Error Handling

- If unclear: ask for clarification before writing
- If blocked: report what you need
- If done: always update planner.md
- If framework unknown: ask user

## Code Standards

Follow these automatically:

| Convention | Rule |
|------------|------|
| Variables | camelCase |
| Constants | UPPER_SNAKE_CASE |
| Classes | PascalCase |
| Files | kebab-case or snake_case |
| Functions | camelCase |

## Validation

Always include:
- Input validation
- Error handling
- Type hints/type annotations
- Documentation for public APIs
