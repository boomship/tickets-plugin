---
description: File-based issue tracker. Create, list, and move tickets between states (open, in-progress, blocked, closed).
---

# Tickets

Manage a file-based issue tracker at `tickets/issues/` in the repo. Check open tickets at session start to pick up pending work.

## Structure

```
tickets/issues/
├── open/          # New and ready to work
├── in-progress/   # Currently being worked on
├── blocked/       # Waiting on something
└── closed/        # Done
```

## Ticket Format

Filename: `P<n>-YYYY-MM-DD-short-title.md` (priority prefix so `ls` sorts by importance)

```markdown
# Title
Owner: <name>
Context: links to code, files, commits
Description: what is needed
Acceptance:
- Bullet list of done criteria
Notes:
- YYYY-MM-DD: Update entry
```

Priority lives in the filename prefix only — no duplication inside the file.

## Operations

### List open tickets
```bash
ls tickets/issues/open/
```

### Create a ticket
Write a new file to `tickets/issues/open/P<n>-YYYY-MM-DD-short-title.md` using the format above.

### Move ticket state
```bash
git mv tickets/issues/open/FILE.md tickets/issues/in-progress/
git mv tickets/issues/in-progress/FILE.md tickets/issues/blocked/
git mv tickets/issues/in-progress/FILE.md tickets/issues/closed/
```

### Add a note
Append a dated bullet under `Notes:` in the ticket file.

## Tips
- Keep filenames stable when moving between folders
- Use P1 for blockers, P2 for important, P3 for nice-to-have
- Link to specific files/lines in Context field
- Date all note entries
