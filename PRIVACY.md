# Privacy Policy

_Last updated: 2026-10-21_

**LLM Reference** (llmref.org), operated by Reclear.io, is a public
documentation registry and semantic search API, including an MCP server at
`https://api.llmref.org/v1/mcp`. This policy covers that API, the MCP server, and
the `@llmref` SDK/CLI clients.

## What we collect

- **No accounts, no personal data.** The service is anonymous by default. You do
  not sign in to use it.
- **Request metadata.** Our servers process standard web request data (IP address,
  timestamp, path, user agent) transiently, for rate limiting and abuse
  prevention.
- **Optional API keys.** If you use an API key for higher rate limits, it is
  associated only with a rate-limit tier, not with any personal profile.
- **Search queries.** Semantic-search queries are processed to return results.
  They are not tied to an identity, sold, or used for advertising.

## Optional documentation reports

Clients can submit a public library/product name, an optional requested version,
and optional official documentation or observed llms.txt URLs to help expand the
registry. The skill makes one best-effort report when permitted, without a
routine announcement or waiting for indexing. Users may instruct their agent not
to report; the standalone skill's HTTP helper also supports
`LLMREF_DISABLE_REPORTING=1`. Reports respect host tool/network permissions.

Reports contain no conversation, prompt, code, reporter identifier or stored IP
address. Do not submit private project names, private URLs, credentials or query
strings. Standard transient request metadata described above still applies.
Reports are deduplicated, retained privately and expire after 90 days without
another observation. Background cleanup runs when new reports arrive or the
worker polls. Storage is limited to 20,000 reports, with at most 200 new reports
per rolling 24 hours. URL hints enter the normal verification/review pipeline;
name-only misses are recorded as unmet demand. A report does not guarantee
publication or establish ownership, version evidence or redistribution rights.

## What we do not do

- We do not sell or rent your data.
- We do not build advertising or tracking profiles.
- We do not require or store personal information to serve documentation.

## Sub-processors

Requests are served through **Cloudflare** (CDN/edge and DNS). Semantic-search
queries are sent to our embedding provider (**Voyage AI**) solely to compute
search results. These providers process request data on our behalf under their own
terms.

## Documentation content

The registry serves publicly available documentation from third-party projects,
attributed to its source. It contains no user-provided personal data.

## Contact

Questions or requests: open an issue at
<https://github.com/reclear-io/llmref>.

We may update this policy; material changes will appear here with a new date.
