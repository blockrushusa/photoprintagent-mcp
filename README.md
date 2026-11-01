# PhotoPrintAgent MCP

Official connector configuration for [PhotoPrintAgent](https://photoprintagent.com), operated by Rainmaker LLC. This repository contains only public connection metadata and documentation. The hosted commerce service is proprietary and is not distributed here.

## Connect

Use HTTPS Streamable HTTP:

- Narrow: `https://photoprintagent.com/mcp-narrow` — catalog, estimates, owned photos/previews, order status and website checkout handoff; no charge or order execution tools.
- Full: `https://photoprintagent.com/mcp` — full commerce integration.

The default package connects to the narrow endpoint. Public catalog and estimates need no account. Protected tools require a PhotoPrintAgent account and scoped OAuth with PKCE; grant only the scopes needed. OAuth supports dynamic registration and client metadata documents. Do not paste passwords, API keys or order access links into public issues.

[Documentation and setup](https://photoprintagent.com/docs/mcp) · [Machine-readable contract](https://photoprintagent.com/docs/mcp.json)

### Claude

Add a custom connector in Settings → Connectors using the narrow URL. Sign in when requesting account data. For Claude Code, install this plugin repository or configure `.mcp.json`.

### Cursor and portable Agent Plugins

Install this repository using a client that supports the Agent Plugins standard. The root `plugin.json` and `mcp.json` declare the connection.

### Gemini CLI

`gemini extensions install https://github.com/blockrushusa/photoprintagent-mcp`

The root Gemini manifest uses the same narrow endpoint. Review the requested connection before installing.

## Example workflows

1. Ask for available 4x6 and 5x7 prints. Use live catalog IDs and artwork dimensions, not invented product identifiers.
2. Estimate ten prints for ZIP 06511, CT. Preserve unknown shipping/tax values; an estimate is not a payable quote.
3. Sign in to read your recent orders and events. Accepted/processing does not mean shipped. Report unavailable tracking explicitly.

Only currently available catalog products are orderable. Delivery is US-only. Browsing is free; printing and shipping are paid, with the final total reviewed before approval. Never place or duplicate an order without explicit customer approval. Complete payment on the website. Do not disclose confidential fulfillment routing or suppliers.

## Validation status

The deployed v2.4.0 endpoints were verified with the MCP SDK and native Claude catalog, estimate and authenticated not-found checks on November 1, 2026. Individual marketplace approval and native installation in other clients are separate; this repository does not claim those approvals.

## Support and privacy

[Support](https://photoprintagent.com/support) · [Privacy](https://photoprintagent.com/privacy) · [Terms](https://photoprintagent.com/terms). Report security issues privately to support@photoprintagent.com. Do not include customer photos, addresses or credentials in GitHub issues.
