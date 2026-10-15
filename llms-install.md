# Installing the Scalelist MCP server

Scalelist is a remote MCP server. There is nothing to clone, build or run locally.

1. Add this server to the client's MCP settings:

```json
{
  "mcpServers": {
    "scalelist": {
      "type": "streamableHttp",
      "url": "https://mcp.scalelist.com/mcp"
    }
  }
}
```

2. The first time a tool is called, the client opens a browser window to sign in to Scalelist (OAuth). New accounts get 20 free credits, no credit card.

3. Test the connection with a free call: ask for the account info (`scalelist_get_account_info`) or count an audience (`scalelist_people_count`). Neither spends credits.

If the client only supports stdio servers, use the bridge instead:

```json
{
  "mcpServers": {
    "scalelist": {
      "command": "npx",
      "args": ["-y", "mcp-remote", "https://mcp.scalelist.com/mcp"]
    }
  }
}
```

No API key or environment variable is needed. Docs: https://scalelist.com/mcp-server/
