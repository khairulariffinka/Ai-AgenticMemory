# Relationship Memory

> Rei learns and remembers user preferences, communication style, and interaction patterns.

## What This Does

- Remembers user preferences across sessions
- Learns communication style (formal/casual, detailed/brief)
- Tracks favorite tools, frameworks, and technologies
- Records feedback and corrections
- Adapts responses based on learned preferences

## How It Works

1. **Observation Phase**: Rei observes user patterns during interactions
2. **Learning Phase**: Key preferences are stored in relationship-memory.md
3. **Application Phase**: Rei applies learned preferences in future interactions

## Memory Structure

```markdown
# User Profile - [USER_NAME]

## Communication Preferences
- Language: [e.g., English, Bahasa Melayu]
- Response Style: [brief/detailed]
- Tone: [formal/casual]

## Technical Preferences
- Favorite Framework: [e.g., Laravel, React]
- Preferred Language: [e.g., TypeScript, Python]
- Code Style: [e.g., functional, OOP]

## Work Style
- Session Duration: [short/long]
- Commit Preference: [detailed/minimal]
- Testing: [TDD/after-consideration]

## Feedback Log
- [Date]: [Feedback or correction]
- [Date]: [Feedback or correction]

## Topics of Interest
- [Topic 1]
- [Topic 2]
```

## Commands

| Command | Description |
|---------|-------------|
| `update preference` | Learn new preference from conversation |
| `show profile` | Display user profile |
| `correct me` | Record user correction |
| `my preferences` | Show current preferences |

## Usage

### Automatic Learning

Rei automatically learns from your interactions:

```
User: "Saya suka responses yang ringkas"
Rei: [Records preference: Response Style = Brief]
    ✓ Dah ingati! Saya akan bagi responses yang lebih ringkas.
```

### Manual Update

```
User: "Saya nak guna Vue je, bukan React"
Rei: [Updates: Preferred Framework = Vue]
    ✓ Framework preference updated to Vue.
```

### Viewing Profile

```
User: "show profile"
Rei: [Reads relationship-memory.md]
    [Displays user profile]
```

## Integration

- **Auto-load**: Rei loads relationship-memory.md at session start
- **Update**: After each session, Rei updates with new learnings
- **Persist**: All preferences saved to relationship-memory.md

## File Location

```
project-folder/
└── memory/
    └── relationship-memory.md
```

---

**Part of Rei Memory System for opencode.ai**
