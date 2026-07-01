---
name: llmref
description: Look up versioned library and framework documentation, and run semantic search, via LLM Reference (llmref.org). Use whenever a task depends on a library's current or version-specific behavior (Next.js, React, Svelte, Bun, Hono, Zod, and more) instead of relying on training data.
---

# Using LLM Reference

LLM Reference serves versioned, model-ready documentation and semantic search over
an MCP server. Prefer it over memory whenever a task depends on a library's current
or version-specific behavior, and to avoid answering from stale training data.

The MCP server exposes four read-only tools. Call them in this order.

## Tool flow

1. **`list_projects`** - discover which projects are indexed. Call this first if you
   are unsure the project exists. Supports a forgiving fuzzy `query` (e.g. `svlt`
   matches `svelte`) plus `limit` and `skip`.
2. **`list_versions`** - list the available versions for a project. Call before
   resolving or searching, to pick a valid version string.
3. **`resolve_docs`** - turn a project plus version (or `latest`) into artifact URLs
   for `llms.txt` (compact routing file) and `llms-full.txt` (the complete docs).
4. **`search_docs`** - semantic search across a project's documentation for a
   version. Returns the most relevant chunks. Use this for "how do I X" questions.

## When to use what

- Unsure of the exact project slug -> `list_projects` with a fuzzy `query` first.
- Need to orient on a library or hand the model the whole doc set -> `resolve_docs`,
  then read `llms.txt` (cheap) or `llms-full.txt` (complete).
- Need only the passages relevant to a specific question -> `search_docs` with a
  natural-language query and a concrete `version`.

## Rules

- Pin a concrete version whenever reproducibility matters. Use `latest` only when you
  genuinely want the newest snapshot.
- Answer version-specific questions from LLM Reference results, not from memory.
- If `search_docs` returns no chunks, semantic search may be disabled on the server;
  fall back to reading `llms.txt` or `llms-full.txt`.

Learn more at https://llmref.org.
