# Blink MCP Connection — WOR-1762

**Status:** done ✅
**Issue:** [WOR-1762](/WF365/issues/WOR-1762)
**Date:** 2026-09-15

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

## Issue Fixed

The dashboard was showing a blank page because the `/api/tools` endpoint wasn't returning a `success: true` field. Fixed the response format in `server/index.js`:

```javascript
// Before
res.json({ tools: mcpTools, count: mcpTools.length });

// After  
res.json({ success: true, tools: mcpTools, count: mcpTools.length });
```

## Verification

- Health check: `{"status":"ok","mcpReady":true,"toolCount":91}` ✅
- Tools list: `success: true, count: 91` ✅
- Project list: returns valid empty list ✅
- Page loads correctly ✅
- SSL: valid certificate ✅
- Authentication: working ✅

## Files

| File | Purpose |
|------|---------|
| `packages/blink-dashboard/server/index.js` | Express API server wrapping Blink MCP |
| `packages/blink-dashboard/public/index.html` | Single-page dashboard UI |
| `packages/blink-dashboard/package.json` | Package config |
| `/etc/nginx/sites-enabled/blink-dashboard` | Nginx site config |
| `/etc/nginx/.htpasswd_blink` | Auth credentials |

## Auto-start

```bash
cd packages/blink-dashboard
export BLINK_API_KEY=blnk_ak_...
node server/index.js
```
