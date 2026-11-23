# Executor for Google Antigravity

Connect once, use everywhere. [Executor](https://executor.sh) holds the APIs,
MCP servers, accounts and per-tool policies you connect, and this plugin gives
Antigravity's agent access to all of them through one MCP server.

## Install

From GitHub:

```bash
agy plugin install https://github.com/UsefulSoftwareCo/executor-antigravity
```

Once Executor is listed in the Antigravity Marketplace, you can also open
**Customizations**, then **Marketplace**, search for **Executor** and choose
**Add**, or run `agy plugin install executor`.

## Sign in

The plugin signs in with OAuth; you never handle an API key.

- **CLI:** run `/mcp`, select `executor_cloud` and choose **Authenticate**.
- **App:** open **Customizations**, then **Installed**, and choose
  **Authenticate** next to Executor's MCP server.

Executor opens in your browser. Sign in, choose your organization and approve
access, then paste the code Antigravity shows back into Antigravity.

## Use

Ask the agent things like:

- "Show me the apps and tools available in my Executor workspace."
- "Use Executor to list my open GitHub issues."
- "Check my Executor connection."

Executor may pause a call for your approval or to connect an account. Answer
the request and the agent carries on. Credentials stay inside Executor's
connection flow and never go through the chat.

## What this plugin includes

- `mcp_config.json`: the hosted Executor MCP server, `https://mcp.executor.sh/mcp`
  (Streamable HTTP, OAuth).
- `skills/using-executor`: how to find and call tools; it defers to the
  instructions Executor's server ships.
- `skills/executor-setup`: a connection check.

Running Executor yourself (self-host or local)? Add your own endpoint to
`~/.gemini/config/mcp_config.json` instead:

```json
{
  "mcpServers": {
    "executor": { "serverUrl": "https://<your-origin>/mcp" }
  }
}
```

See [Add an MCP client](https://executor.sh/docs/mcp-clients) for details.

## Development

```bash
agy plugin validate . --strict
agy plugin install .
```

## Support

[executor.sh](https://executor.sh) · [Issues](https://github.com/UsefulSoftwareCo/executor-antigravity/issues)

## License

MIT
