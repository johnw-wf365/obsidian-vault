# Blink MCP Connection — WOR-1762

**Status:** done ✅
**Issue:** [WOR-1762](/WF365/issues/WOR-1762)
**Date:** 2026-09-14

## What was built

1. **MCP server configured** in `/root/.hermes/profiles/zoe/config.yaml`:
   ```yaml
   mcp_servers:
     blink:
       command: npx
       args: ["-y", "@blinkdotnew/mcp@latest"]
       env:
         BLINK_API_KEY: (via .env)
       timeout: 180
       connect_timeout: 120
   ```

2. **API key** stored in `/root/.hermes/profiles/zoe/.env` as `BLINK_API_KEY`

3. **Gateway restarted** — blink MCP server loaded with **91 tools** available

## Verification

- `hermes mcp list -p zoe` → blink ✓ enabled
- `blink_project_list` → returned valid response (0 projects, as expected)
- All 91 tools accessible: projects, backends, databases, auth, storage, queues, domains, AI gateway, phone numbers, etc.

## How to test

Ask Zoe (via Telegram or chat):
- "List my blink projects"
- "Create a new blink project called test-project"
- "Deploy a backend to blink"

The blink tools are now native agent tools, prefixed `mcp_blink_*`.
