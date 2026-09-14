# Blink MCP Connection — WOR-1762

**Status:** in_review — waiting for BLINK_API_KEY
**Issue:** [WOR-1762](/WF365/issues/WOR-1762)
**Date:** 2026-09-14

## What was done

1. Installed blink skills via `npx skills add blink-new/blink-plugin` (15 skills installed)
2. Added `@blinkdotnew/mcp` as MCP server in `/root/.hermes/profiles/zoe/config.yaml`:
   ```yaml
   mcp_servers:
     blink:
       command: npx
       args: ["-y", "@blinkdotnew/mcp@latest"]
       timeout: 180
       connect_timeout: 120
   ```
3. Created interaction card asking for `BLINK_API_KEY` (format: `blnk_ak_*`)
4. Issue moved to `in_review` — will wake when key is provided

## Still needed

- **BLINK_API_KEY** from blink.new → Settings → API Keys
- Once received: propose as Paperclip secret, add to config's `env` block, restart gateway, verify with `blink_project_list`

## Notes

- Blink MCP exposes 62 tools for serverless infrastructure
- Auth is via `BLINK_API_KEY` env var (stdio transport)
- The `mcp` Python package is already installed in the Hermes venv
- Blink skills are at `/opt/paperclip/app/.agents/skills/blink-*/SKILL.md`
