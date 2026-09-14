# Blink.new MCP Integration

**Issue:** [WOR-1762](/WF365/issues/WOR-1762)
**Status:** In review — waiting for Blink API key
**Assigned:** [[Agents/Zoe|Zoe]]

## Plan

1. Add `@blinkdotnew/mcp` as an MCP server via `mcp.json` using stdio transport
2. Authenticate with `BLINK_API_KEY` env var (format: `blnk_ak_*`)
3. Register through Paperclip tool gateway
4. Verify with `blink_project_list` tool call

## Research

- **Docs:** https://blink.new/docs/cloud/tools/mcp
- **npm:** `@blinkdotnew/mcp`
- **Tools:** 62 MCP tools across 18 categories (projects, databases, auth, backends, domains, queues, storage, AI gateway, phone, connectors, etc.)
- **Get key:** blink.new → Settings → API Keys

## Config shape

```json
{
  "mcpServers": {
    "blink": {
      "command": "npx",
      "args": ["-y", "@blinkdotnew/mcp@latest"],
      "env": {
        "BLINK_API_KEY": "blnk_ak_..."
      }
    }
  }
}
```
