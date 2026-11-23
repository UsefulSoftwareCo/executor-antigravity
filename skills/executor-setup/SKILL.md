---
name: executor-setup
description: Check the Executor connection and explain the next setup step. Use when the user asks to set up or check Executor, or when Executor's tools are missing.
---

# Set up Executor

Check whether the Executor MCP server's `skills`, `search`, `call` and
`execute` tools are available.

If they are:

1. Call `skills` with `{ "app": "executor", "name": "executor" }` and follow it.
2. Call `search` with `{ "query": "Executor" }`. It should return tool paths for
   the Executor app itself. Then search for the service the user cares about.
3. Summarize which apps and accounts are connected and confirm Executor is
   ready. Do not show credentials or private data.

If the server asks for sign-in, ask the user to finish the Executor sign-in in
their browser (choose an organization and approve access), then try again.

If the tools are missing, ask the user to open Customizations, then Installed,
find Executor and choose Authenticate, or restart its MCP server. In the CLI,
`/mcp` shows the server's status and logs. Do not ask the user for an access
token.

If Executor is connected but the service they need is not, send them to
[executor.sh](https://executor.sh) to add it, then check again.
