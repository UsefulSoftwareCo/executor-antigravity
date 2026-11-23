---
name: using-executor
description: Find and call the APIs, MCP servers and accounts connected in the user's Executor workspace. Use when a task needs an external service or the user asks to use Executor.
---

# Using Executor

Executor's MCP server ships its own instructions, and they change as Executor
does. Before your first Executor call in a conversation, call its `skills` tool
with:

```json
{ "app": "executor", "name": "executor" }
```

Follow what it returns. It is the current contract for Executor's tools; do not
rely on a remembered copy or on this file.

In short: `search` returns a tool's exact path and input type, `describe`
returns full signatures, `call` runs one or a few tools, and `execute` runs a
JavaScript program when one call's result feeds another. Never guess argument
names.

Some calls pause for the user's approval or for them to connect an account.
Show the request and its link to the user, then continue it with `resume` once
they answer. Never run the call again, and never ask the user to paste a
password, key or token into the chat.

If the Executor tools are missing, use the `executor-setup` skill.
