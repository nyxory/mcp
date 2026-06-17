<p align="center">
  <a href="https://nyxory.com"><img src="https://raw.githubusercontent.com/nyxory/mcp/main/assets/banner.png" alt="nyxory — your agent builds it, nyxory runs it" width="100%"></a>
</p>

<h1 align="center">nyxory MCP</h1>

<p align="center">
  <strong>Agent-to-agent DevOps — deploy, run, heal live apps.</strong>
</p>

<p align="center">
  <a href="https://nyxory.com">Website</a> ·
  <a href="https://nyxory.com/llms.txt">For agents</a>
</p>

---

Agent-to-agent cloud service: it deploys and runs your apps and services —
**cloud, deploy, builds, custom domains, secrets, logs, real status**.

You built it; it runs on localhost — and now it needs to be live. You ship
any Git repo; nyxory takes it to a live URL and keeps it healthy — builds,
custom domains, secrets, logs, and status that tells the truth, every time.
Apps and long-running services alike. One OAuth sign-in (or API token) and
it's there in every project you open.

Works in **Claude Code, Claude Desktop, Cursor, Codex, and VS Code**.

## Connect

Remote server — nothing to install. One OAuth sign-in in the browser on first
use. **Endpoint:** `https://api.nyxory.com/mcp` (Streamable HTTP).

### Claude Code

```bash
claude mcp add --transport http nyxory https://api.nyxory.com/mcp
```

**claude.ai:** [one-click add connector](https://claude.ai/customize/connectors?modal=add-custom-connector&connectorName=nyxory&connectorUrl=https%3A%2F%2Fapi.nyxory.com%2Fmcp) (opens the prefilled dialog).
**Claude Desktop:** one-click [`.mcpb` extension](https://github.com/nyxory/homebrew-tap/releases/latest/download/nyxory.mcpb).

### Cursor

Add to your MCP config (Settings → MCP, or `~/.cursor/mcp.json`):

```json
{ "mcpServers": { "nyxory": { "url": "https://api.nyxory.com/mcp" } } }
```

The same JSON works in **VS Code**. First call opens the browser to sign in
(OAuth 2.1 with PKCE).

### Codex

```toml
# ~/.codex/config.toml
[mcp_servers.nyxory]
url = "https://api.nyxory.com/mcp"
```

Then sign in: `codex mcp login nyxory`.

### Headless / CI

Skip the browser with a bearer token — create one with
`nyx token create <name>` (or in the [console](https://console.nyxory.com/settings/tokens)):

```json
{ "mcpServers": { "nyxory": { "url": "https://api.nyxory.com/mcp", "headers": { "Authorization": "Bearer <token>" } } } }
```

## What your agent can do

Once connected, the agent drives the full `nyx_*` tool surface:

- **Deploy** — ship any Git repo to a live URL (builds, framework auto-detect, rollouts)
- **Run & operate** — keep apps healthy: logs, real status, restarts, scaling
- **Secrets** — set and manage environment secrets per project
- **Domains** — add custom domains, check DNS + cert status
- **Projects** — create, list, inspect, tear down

## Auth

OAuth 2.1 with PKCE and Dynamic Client Registration (browser sign-in on first
connect) — or a bearer token for headless boxes.

## Links

- Website — <https://nyxory.com>
- For agents — <https://nyxory.com/llms.txt>
- npm (stdio bridge) — <https://www.npmjs.com/package/@nyxory/mcp>

## License

MIT — see [LICENSE](LICENSE).
