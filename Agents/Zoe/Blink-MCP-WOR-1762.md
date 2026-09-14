# Blink MCP Connection — WOR-1762

**Status:** in_review — awaiting board approval of secret binding
**Issue:** [WOR-1762](/WF365/issues/WOR-1762)
**Date:** 2026-09-14

## What was done

1. Installed blink skills via `npx skills add blink-new/blink-plugin` (15 skills)
2. Added `@blinkdotnew/mcp` as MCP server in `/root/.hermes/profiles/zoe/config.yaml`
3. John provided the BLINK_API_KEY — proposed as Paperclip secret (`blink/api-key`)
4. Created binding proposal (`env.BLINK_API_KEY`) to inject key into Zoe's env
5. Updated `config.yaml` with MCP server config including env reference
6. Verified MCP server starts cleanly with the key (no auth errors)
7. Issue moved to `in_review` — "Confirm secret binding" card created

## Still needed

- Board approval of the secret binding card
- After approval: restart gateway → verify blink_project_list → mark done

## Notes

- Blink MCP exposes 62 tools for serverless infrastructure
- Auth is via `BLINK_API_KEY` env var (stdio transport)
- Secret proposal: `675a9110-5c67-4499-81b0-e203b41dd0e8`
- Binding proposal: `231c1ff2-cfd4-4b04-b62a-ab5c51d48527`
