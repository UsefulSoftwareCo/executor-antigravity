# Executor for Google Antigravity

Connect once, use everywhere. [Executor](https://executor.sh) holds the APIs,
MCP servers, accounts and per-tool policies you connect, and this plugin gives
Antigravity's agent access to all of them through one MCP server.

## Install

### Marketplace

Open **Customizations**, then **Marketplace**, search for **Executor** and
choose **Add**. In the CLI:

```bash
agy plugin install executor
```

### From GitHub

Until the Marketplace listing is live, install it straight from this repository:

```bash
agy plugin install https://github.com/UsefulSoftwareCo/executor-antigravity
```

## Sign in

The plugin uses OAuth, so there is nothing to paste. The first time the
Executor MCP server connects, Antigravity opens Executor in your browser. Sign
in, choose your organization and approve access. To sign in again later, open
**Customizations**, then **Installed**, and choose **Authenticate** next to
Executor.

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
