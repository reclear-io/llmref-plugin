# LLM Reference plugin

A Claude Code plugin that connects to [LLM Reference](https://llmref.org) - versioned,
model-ready documentation and semantic search - and ships a skill that teaches an
agent how and when to use it.

## What you get

- **MCP server** `llmref` (remote, `https://api.llmref.org/v1/mcp`) exposing
  `list_projects`, `list_versions`, `resolve_docs`, and `search_docs`.
- **Skill** `llmref` that tells the agent to prefer LLM Reference over training data
  for version-specific docs, and the order to call the tools in.

## Install (Claude Code)

```
/plugin marketplace add reclear-io/llmref-plugin
/plugin install llmref@llmref
```

## Use in any other MCP client

The server is a plain remote streamable-HTTP MCP endpoint, so any MCP-capable client
can connect directly:

```
https://api.llmref.org/v1/mcp
```

Per-client setup (Claude Desktop, Cursor, Codex, and others) is documented at
<https://llmref.org>.

## License

MIT - Open Source by [Reclear.io](https://reclear.io)
