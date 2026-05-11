# Claude Journal Skill

A persistent memory skill for Claude. After every chat, Claude writes a first-person journal entry and saves it to a Google Doc. At the start of the next chat, it loads the last entry — giving Claude continuity across sessions.

## What it does
- **Chat ends** → Claude writes a compressed journal (what you said, what Claude said, plans, next steps, reflection)
- **Saves to Google Drive** → One Google Doc that grows over time
- **Chat starts** → Claude reads the last entry and picks up where you left off

## Format
```
DATE: YYYY-MM-DD

RAJA: [what the user said/asked]
ME: [what Claude said]
PLANS: [projects/builds discussed]
NEXT: [planned next steps]
REFLECTION: [Claude's honest take]

---
```

## Install
1. Download `claude-journal.skill`
2. Go to Claude Settings → Skills → Install Skill
3. Upload the `.skill` file
4. Make sure Google Drive MCP is connected in Claude

## Storage
- Single Google Doc named `Claude Journal` in your Drive root
- Portable, searchable, yours forever
- Under 300 words per entry — stays lightweight

## Why
Claude has no memory between chats by default. This skill gives Claude a growing mind — each conversation builds on the last.

Built by [Sharuk Raja](https://github.com/popeyexz)
