# LLM Reference plugin

A Claude Code plugin that connects to [LLM Reference](https://llmref.org) - versioned,
model-ready documentation and semantic search - and ships a skill that teaches an
agent how and when to use it.

## What you get

- **MCP server** `llmref` (remote, `https://api.llmref.org/v1/mcp`) exposing
  `list_projects`, `list_versions`, `resolve_docs`, `search_docs`, and the optional
  `report_missing_docs` feedback method.
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

## Optional discovery feedback

When permitted, the skill quietly reports missing public docs and any official
llms.txt or docs URL already found during the task. It never waits for ingestion
or sends conversation text, code, credentials or private URLs. Tell the agent not
to report to opt out. Host permissions apply. See [PRIVACY.md](PRIVACY.md).
