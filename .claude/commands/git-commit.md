---
description: Create a git message by analyzing the git diffs
allowed-tools: Bash(git status:*), Bash(git diff --staged), Bash(git commit:*)
---

## Context:
- Current git status: !`git status`
- Current git diff: !`git diff --staged`

Analyze the current staged changes and write a git message, it should be in present tense, explain `why` something has changed, not just `what` has changed.

## Commit types with emojis:
Only use these emojis while commiting

- ✨ `feat:` - New feature
- 🐛 `fix:` - Bug fix
- 🔨 `refactor:` - Refactoring code
- 📝 `docs:` - Documentation
- 🎨 `style:` - Styling/formatting
- ✅ `test:` - Tests
- ⚡ `perf:` - Performance

## Format
Use this format for making a commit message

```
<emoji> <type>: <concise_description>
<optional_body_explaining_why>
```

## Output
1. Provide brief Summary of staged changes
2. Propose commit message with appropriate emoji
3. Ask for confirmation before commiting

DONOT auto-commit until user approves/confirm it.
