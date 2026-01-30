# Tickets Plugin

File-based issue tracker for AI coding agents.

## Why

GitHub Issues and Jira live outside the repo. Tickets keeps work items in-repo as markdown files, searchable by any agent, version controlled, and movable between state folders.

## Installation

First, add the boomship marketplace (one-time):

```shell
/plugin marketplace add boomship/ccmarketplace
```

Then install the plugin:

```shell
/plugin install tickets@boomship
```

## Usage

```shell
/tickets
```

Lists open tickets and lets you create, update, or move them.

## Structure

```
tickets/issues/
├── open/          # Ready to work
├── in-progress/   # Being worked on
├── blocked/       # Waiting
└── closed/        # Done
```

## Ticket Format

Files named `YYYY-MM-DD-short-title.md`:

```markdown
# Title
Owner: <name>
Priority: P1|P2|P3
Context: links to code, files, commits
Description: what is needed
Acceptance:
- Done criteria
Notes:
- YYYY-MM-DD: Update entry
```
