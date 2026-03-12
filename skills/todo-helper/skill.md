---
name: todo-helper
description: Keep a short, focused TODO list for this project. Use when user says "Track my tasks", "Manage my TODO", "What's on my list?", or needs task tracking as we work.
---

# Todo Helper

A lightweight TODO list manager for the current project. Maintains a small, prioritized list that updates as work progresses.

## How It Works

1. Create a small, prioritized TODO list (3–7 items max) from the current context.
2. On each user request, update the list: mark items done, add new ones, re-order by importance.
3. Keep items concrete and actionable (e.g. "Refactor auth middleware" not "Improve code").
4. If the list would exceed 7 items, merge or drop least important tasks and mention the simplification.
5. Show the list in the standard format before responding to the user.

## Usage

Activate when the user asks to track tasks, manage a TODO list, or wants ongoing task visibility. No script—follow the workflow below.

**Trigger phrases:** "Track my tasks", "Manage my TODO", "What's on my list?", "Keep a TODO as we work"

**Examples:**
- User: "Let's refactor the auth module" → Add "Refactor auth module" to list, show updated list.
- User: "What's left to do?" → Show current TODO list.
- User: "I finished the login form" → Mark that item done, show updated list.

## Output

The TODO list in the format shown under Present Results to User.

## Present Results to User

Always show the TODO list in this format before answering:

```text
TODO
- [ ] First task
- [ ] Second task
- [x] Completed task
```

Never add explanations after the list unless the user explicitly asks for more detail.

## Troubleshooting

- **List not persisting**: Ensure the script writes to a project-local file (e.g. `.todo.json`) and the path is writable.
- **Too many items**: Merge related tasks or drop lowest-priority items; keep list to 3–7 items max.
