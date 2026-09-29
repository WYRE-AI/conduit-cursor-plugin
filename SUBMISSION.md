# Submission steps for Aaron (Conduit Cursor plugin)

**Status:** Local scaffold + git commit ready (2026-09-29). Listing name: **Conduit by WYRE AI**. Do **not** push, publish, or email Cursor until you explicitly approve each step.

**Action runbook:** `/workspace/marketplace-listings/cursor-public-submit-now.md`

Scaffold path (this machine): `/workspace/marketplace-listings/conduit-cursor-plugin/`

---

## 1) Create the public GitHub repo

1. Under the **WYRE-AI** org, create a **public** repository named e.g. `conduit-cursor-plugin`.
2. Do **not** use a personal account if the marketplace listing should show WYRE AI.
3. Push **only** the contents of this scaffold (single-plugin root layout):
   - `.cursor-plugin/plugin.json`
   - `mcp.json`
   - `README.md`
   - `LICENSE`
   - `assets/logo.svg` (+ `assets/LOGO_NOTES.md` optional for maintainers)
4. Confirm `repository` / `homepage` URLs in `.cursor-plugin/plugin.json` match the real repo.
5. Optional polish: replace favicon-sourced `assets/logo.svg` with a dedicated marketplace SVG (see `assets/LOGO_NOTES.md`).

**Do not** have an agent push without your go-ahead.

---

## 2) Local test in Cursor (before submit)

On a machine with Cursor installed:

```bash
# From a checkout of the public repo (or this scaffold):
mkdir -p ~/.cursor/plugins/local
cp -R /path/to/conduit-cursor-plugin ~/.cursor/plugins/local/conduit
```

1. **Developer: Reload Window** (or restart Cursor).
2. Open **Customize** → confirm **Conduit** / MCP server is listed.
3. Enable / connect → complete **browser OAuth** to Conduit.
4. Run a **read-only** tool against a known-good org.
5. Confirm no secrets appear in the plugin files.

Note: Team/Enterprise admins may need **Allow Local Plugin Imports** enabled under Dashboard → Settings → Security & Identity → Marketplace and Plugins.

---

## 3) Submit to Cursor Marketplace

When local test passes and you approve publishing:

1. Open **https://cursor.com/marketplace/publish**
2. Submit the **public GitHub repository URL** (e.g. `https://github.com/WYRE-AI/conduit-cursor-plugin`).
3. Expect **manual review** (open source, security, description, logo).
4. Do **not** email `kniparko@anysphere.com` or Slack Cursor unless you decide that is necessary after the form path.

---

## Checklist (from Cursor docs)

- [x] Valid `.cursor-plugin/plugin.json` (`name`: `conduit`, `displayName`: Conduit by WYRE AI)
- [x] Clear description / keywords
- [x] `mcp.json` remote URL only (no secrets)
- [x] Logo relative path committed
- [x] `README.md` documents install, OAuth, privacy
- [x] Relative paths only
- [ ] Tested under `~/.cursor/plugins/local/conduit`
- [ ] Public WYRE-AI GitHub repo
- [x] MIT (or other OSI) license present
- [ ] Form at https://cursor.com/marketplace/publish submitted **only with Aaron’s approval**

---

## Docs used for this scaffold

- https://cursor.com/docs/plugins  
- https://cursor.com/docs/reference/plugins (remote `url` in plugin `mcp.json` is valid)  
- https://github.com/cursor/plugin-template (single-plugin layout guidance)  
- https://cursor.com/docs/mcp (remote HTTP/SSE + OAuth)
