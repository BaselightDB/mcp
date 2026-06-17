# Baselight MCP

Public metadata for the [Baselight](https://baselight.ai) MCP server.

## What is Baselight?

Baselight is a hosted catalog of 70,000+ public datasets — finance, demographics, climate, sports, crypto, and more — sourced from providers like Our World in Data, the World Bank, Kaggle, Eurostat, and the CIA World Factbook. Datasets are exposed through a single SQL interface so you can search, query, and join them without managing storage or pipelines.

The Baselight MCP server lets AI assistants and other MCP clients reach that catalog directly: discover datasets, inspect schemas, and run queries from inside the tools you already use.

## What's in this repo

This repository hosts public metadata for the Baselight MCP server alongside a one-click installable bundle.

## Contents

- [`registry/server.json`](./registry/server.json) — the [Model Context Protocol registry](https://modelcontextprotocol.io) entry that describes the remote server, its endpoint, and required headers.
- [`mcpb/`](./mcpb/) — the Baselight [MCP Bundle (.mcpb)](https://github.com/modelcontextprotocol/mcpb), a packaged proxy to the remote server for MCPB-compatible hosts such as Claude Desktop. Released via GitHub Releases.

The Baselight MCP server itself is hosted at `https://api.baselight.app/mcp` — there is no server code to install from this repo.

## Connecting to the MCP server

The server is reachable at:

```
https://api.baselight.app/mcp
```

Authentication uses either OAuth (sign in with your Baselight account from inside the client) or an API key sent as the `x-api-key` header. Generate an API key from **Account Settings → Integrations** at [baselight.app](https://baselight.app).

### Example: VS Code

Add to `settings.json`:

```json
"mcp": {
  "servers": {
    "baselight": {
      "type": "http",
      "url": "https://api.baselight.app/mcp",
      "headers": { "x-api-key": "YOUR_API_KEY" }
    }
  }
}
```

### Example: Claude Desktop (custom connector)

Settings → Connectors → Add custom connector:

- **Name:** Baselight
- **URL:** `https://api.baselight.app/mcp`
- **Authentication:** OAuth

For other clients (Gemini CLI, LibreChat, Smithery, etc.), see the full guide: <https://baselight.ai/docs/connecting-to-the-baselight-mcp-server/>.

## Links

- Baselight: <https://baselight.ai>
- Connection guide: <https://baselight.ai/docs/connecting-to-the-baselight-mcp-server/>
- Model Context Protocol: <https://modelcontextprotocol.io>
