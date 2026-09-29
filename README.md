# Conduit by WYRE AI for Cursor

**Conduit** by [WYRE AI](https://conduit.wyre.ai) is a hosted **MCP (Model Context Protocol) gateway** for MSPs. One governed HTTPS endpoint gives your AI clients organization isolation, role-based permissions, and audit logs for access to connected PSA, RMM, documentation, and security tools.

This Cursor Marketplace plugin configures Cursor to use Conduit’s remote MCP server. Vendor API keys stay in Conduit — never in this plugin.

## MCP endpoint

```text
https://conduit.wyre.ai/v1/mcp
```

Transport: Streamable HTTP (remote `url` in `mcp.json`). Cursor discovers this file automatically from the plugin root.

## Install

### From the Cursor Marketplace (after listing is live)

1. Open **Customize** in Cursor.
2. Find **Conduit by WYRE AI** (plugin name `conduit`).
3. Install (project or user scope).
4. When prompted, complete **Conduit OAuth** in the browser (sign in to your Conduit org).

### Local development / pre-publish test

1. Copy this plugin folder to `~/.cursor/plugins/local/conduit` on a machine running Cursor.  
   (Symlinks that point *outside* `~/.cursor/plugins/local` are skipped; copy or symlink *inside* that folder.)
2. Restart Cursor or run **Developer: Reload Window**.
3. Open **Customize** and confirm the Conduit MCP server appears.
4. Connect and complete browser OAuth, then try a read-only tool.

## Authentication (OAuth)

Conduit is **OAuth-only**. On first use, Cursor opens a browser sign-in to Conduit. There is no API token in this repo and no `variables` / bearer placeholder in `mcp.json`.

Client setup guide: [Connecting a client](https://conduit.wyre.ai/docs/guides/connecting-a-client/)

## Privacy & docs

- Privacy: https://conduit.wyre.ai/privacy  
- Docs (getting started): https://conduit.wyre.ai/docs/getting-started/  
- Connecting a client: https://conduit.wyre.ai/docs/guides/connecting-a-client/  
- Product: https://conduit.wyre.ai  

## What’s in this plugin

| Path | Purpose |
|------|---------|
| `.cursor-plugin/plugin.json` | Cursor Plugin manifest (`name`: `conduit`) |
| `mcp.json` | Remote MCP → `https://conduit.wyre.ai/v1/mcp` |
| `assets/logo.svg` | Logo (see `assets/LOGO_NOTES.md`) |

Single-plugin layout at repo root (no `.cursor-plugin/marketplace.json`).

## License

MIT — see [LICENSE](./LICENSE).

## Support

WYRE AI — aaron@wyre.ai — https://conduit.wyre.ai
