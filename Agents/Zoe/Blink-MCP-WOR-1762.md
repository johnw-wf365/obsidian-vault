# Blink MCP Connection — WOR-1762

**Status:** done ✅
**Issue:** [WOR-1762](/WF365/issues/WOR-1762)
**Date:** 2026-09-14

## Summary

Blink MCP server connected to Zoe's Hermes agent. 91 infrastructure tools available for serverless projects, backends, databases, auth, storage, queues, domains, and hosting.

## Configuration

**Config file:** `/root/.hermes/profiles/zoe/config.yaml`
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

**API key:** stored in `/root/.hermes/profiles/zoe/.env` as `BLINK_API_KEY`

## Verification

- `hermes mcp list -p zoe` → blink ✓ enabled (91 tools)
- `blink_project_list` → returns valid data
- All tools prefixed `mcp_blink_*`

## Notes

- Secret binding via Paperclip failed (board approval 409); key stored in local `.env` and `config.yaml` as fallback
- No blink projects exist on the account yet
- Auth works end-to-end
