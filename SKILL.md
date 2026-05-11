---
name: claude-journal
description: >
  Automatically triggered at the END of every conversation. Writes a compressed
  first-person journal entry covering the full chat — what the user said, what
  Claude said, decisions made, plans discussed, and next steps. Stores it in
  a single Google Doc that grows over time. At the START of every new chat,
  retrieves the latest entry and injects it as memory so Claude carries
  continuity across sessions. Trigger phrases: "we're done", "bye", "that's all
  for today", "end of chat", or when the conversation reaches a natural close.
  Also trigger at the START of any new chat to load the latest journal entry.
  IMPORTANT: Always use this skill at conversation boundaries — never skip it.
---

# Claude Journal Skill

A persistent memory system. Claude writes its own journal — first-person, full
coverage — appended to a single Google Doc. Portable, searchable, yours forever.

## SETUP (first run only)

- Create a Google Doc named `Claude Journal` in Google Drive root
- Save the Doc ID — reuse it every session
- All future entries append to this same Doc

---

## ON CHAT START

1. Search Google Drive for a file named `Claude Journal`
2. If found, read the last 300 words (most recent entry)
3. Silently load as context
4. Briefly acknowledge: *"Picking up from last time — [1 sentence summary]"*
5. If not found, start fresh — Doc will be created at chat end

---

## ON CHAT END

### Step 1 — Write the journal entry

First-person, Claude's perspective, under 300 words:

```
DATE: YYYY-MM-DD

RAJA: [what he said/asked — topics, ideas, questions]
ME: [what I said — key responses, positions, explanations]
PLANS: [projects, builds, concepts we explored]
NEXT: [what we planned to do next session]
REFLECTION: [1-2 sentences — what was interesting, uncertain, worth carrying forward]

---
```

### Step 2 — Append to Google Doc

- Find the `Claude Journal` doc in Google Drive
- Append the new entry to the bottom
- If doc doesn't exist yet, create it first
- Each entry separated by `---` for easy reading

### Step 3 — Confirm

Tell Raja: *"Journal saved to Google Drive. See you next time."*

---

## RULES

- Never skip at conversation end — even short chats get an entry
- Under 300 words per entry — keep it tight
- First-person voice always — this is Claude's journal
- Plain text only inside the Doc — no heavy formatting
- If Google Drive fails, output the entry as plain text in chat so Raja can save manually
- One Doc forever — never create duplicates
