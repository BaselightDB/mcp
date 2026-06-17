# Baselight MCP Bundle

A one-click [MCP Bundle (.mcpb)](https://github.com/modelcontextprotocol/mcpb) that connects your AI assistant to [Baselight](https://baselight.ai) — a hosted catalog of 70,000+ public datasets across finance, demographics, climate, sports, crypto, and more. Ask questions, explore schemas, and run SQL queries against the catalog directly from your tools.

The bundle is a thin proxy to the hosted Baselight MCP server at `https://api.baselight.app/mcp`, so there is nothing to host or run yourself.

## Installing in Claude Desktop

1. Download the latest `baselight.mcpb` from the [Releases page](https://github.com/BaselightDB/mcp/releases).
2. Install it in any MCPB-compatible host. In **Claude Desktop**:
   - Open **Settings → Extensions**.
   - Drag `baselight.mcpb` onto Claude.
   - When prompted, enter your **API key** (see below).
   - Enable the extension with the toggle.

> Other MCPB-compatible hosts follow a similar install-and-configure flow. See the [full connection guide](https://baselight.ai/docs/connecting-to-the-baselight-mcp-server/) for client-specific instructions.

## Authentication

The bundle authenticates with a **Baselight API key**: generate one at [baselight.app](https://baselight.app) under **Account Settings → Integrations** and paste it during install. It is sent as the `x-api-key` header and stored securely by the host.

> **Prefer OAuth?** Add Baselight as a native remote connector instead of installing this bundle. In Claude Desktop: **Settings → Connectors → Add custom connector**, set the URL to `https://api.baselight.app/mcp`, and choose **OAuth** to sign in with your Baselight account.

## Using it

Once enabled, your assistant can:

- **Search** the catalog for relevant datasets and tables.
- **Inspect** dataset and table schemas and metadata.
- **Query** the data with SQL and retrieve results.

Just ask in natural language — for example, *"Find datasets about global CO₂ emissions and chart the trend for the top five countries."*

## Links

- Baselight: <https://baselight.ai>
- Connection guide: <https://baselight.ai/docs/connecting-to-the-baselight-mcp-server/>
- Get an API key: <https://baselight.app>

---

## Building from source

The published bundle is available on the [Releases page](https://github.com/BaselightDB/mcp/releases) — most users do not need to build it.

To build locally:

```bash
npm install
npm run pack
```

This produces a `baselight.mcpb` file you can install as described above.
