# Blink MCP Connection — WOR-1762

**Status:** done ✅
**Issue:** [WOR-1765](/WF365/issues/WOR-1762)
**Date:** 2026-09-14 → 2026-09-15

## What Was Built

1. **MCP server configured** in `/root/.hermes/profiles/zoe/config.yaml` with 91 blink tools
2. **API key** stored in `/root/.hermes/profiles/zoe/.env` as `BLINK_API_KEY`
3. **Dashboard app** at `packages/blink-dashboard/`
4. **Nginx reverse proxy** on port 9447 with basic auth

## Dashboard URL

**https://wf365.workforce365.ai:9447**

**Credentials:**
- Username: `johnw@workforce365.ai`
- Password: `C0wP!gD0gB0at`

## Architecture

- Dashboard server: port 3200
- Nginx proxy: port 9447 with SSL + basic auth
- SSL: Let's Encrypt cert (already configured for wf365.workforce365.ai)
- Auth: `/etc/nginx/.htpasswd_blink`
- Config: `/etc/nginx/sites-enabled/blink-dashboard`

## Files

| File | Purpose |
|------|---------|
| `packages/blink-dashboard/server/index.js` | Express API server wrapping Blink MCP |
| `packages/blink-dashboard/public/index.html` | Single-page dashboard UI |
| `packages/blink-dashboard/package.json` | Package config |
| `/etc/nginx/sites-enabled/blink-dashboard` | Nginx site config |
| `/etc/nginx/.htpasswd_blink` | Auth credentials |

## Auto-start Dashboard

```bash
cd packages/blink-dashboard
export BLINK_API_KEY=blnk_ak_...
node server/index.js
```

## Verification Results

- Health check: `{"status":"ok","mcpReady":true,"toolCount":91}` ✅
- Project list: returns valid empty list ✅
- Workspace list: WF365 workspace confirmed ✅
- Tool calling: all 91 tools accessible ✅
- SSL: valid certificate ✅
- Authentication: working ✅
