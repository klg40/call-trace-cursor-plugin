# Call Trace for Cursor

Connect Cursor to your Call Trace workspace through a hosted, read-only MCP server.

## What Cursor can do

- Search calls by text, status, agent, queue, or date.
- Read call metadata and processing status.
- Inspect transcripts and speaker-separated chunks.
- Explain QA scores, summaries, script adherence, emotions, and prohibited-phrase findings.
- Compare call volume, completion, errors, and agent performance.

## Install

Install **Call Trace** from the Cursor Marketplace. Cursor will configure the remote MCP server and open your browser to complete Call Trace OAuth authorization.

For local plugin testing, copy this repository to:

```text
~/.cursor/plugins/local/call-trace
```

Then restart Cursor or run **Developer: Reload Window**.

## Authentication and permissions

- Endpoint: `https://www.call-trace.com/mcp`
- Transport: Streamable HTTP
- Authentication: OAuth 2.1 authorization code flow with PKCE
- Scope: `analysis:read`
- Access: read-only and restricted to the authenticated user's company

The plugin does not expose create, update, or delete tools. OAuth access can be revoked from Call Trace or disconnected in Cursor.

## Available tools

| Tool | Purpose |
| --- | --- |
| `search_calls` | Find calls using text, status, agent, queue, and date filters. |
| `get_call` | Read call metadata and processing status. |
| `get_transcript` | Read transcript text and speaker chunks. |
| `get_call_analysis` | Read QA scores, summaries, script steps, emotion, and prohibited-phrase findings. |
| `get_team_metrics` | Summarize volume, completion, errors, and agent scores. |

## Example prompts

- “Find my latest completed calls and summarize their QA scores.”
- “Show the transcript and QA analysis for this call.”
- “Compare agent performance during the last 30 days.”

## Security

Every MCP request is tenant-scoped on the server. Call Trace never uses an identifier supplied by the model to bypass the company associated with the OAuth token.

- [Privacy policy](https://www.call-trace.com/privacy)
- [Terms of service](https://www.call-trace.com/terms)
- [Support](mailto:support@call-trace.com)

## License

MIT
