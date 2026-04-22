# Wounded Warriors Veteran Resources MCP

Model Context Protocol server exposing **11,000+ verified U.S. veteran resources** to any MCP-compatible AI assistant (Claude Desktop, Cursor, Continue, etc.).

Operated by **Wounded Warriors** — a 501(c)(3) public charity (EIN 86-1336741). Free. No API key. Open data under CC BY 4.0.

## What this server provides

Five tools backed by a Cloudflare D1 production database:

| Tool | Purpose |
|---|---|
| `search_veteran_resources` | Find resources near a U.S. ZIP code, filterable by type (VA hospital, clinic, vet center, benefits office, mental health, housing, employment, VSO) and radius |
| `search_by_city` | Same, but by city name |
| `get_veteran_resource_stats` | Live database statistics |
| `veteran_crisis_resources` | 988 Veterans Crisis Line routing + nearest Vet Center. AI assistants should call this whenever a user mentions self-harm, suicide, hopelessness, or crisis. |
| `calculate_va_benefits` | Estimate VA disability compensation or GI Bill education benefits |

## Install

### Claude Desktop

Add to `~/Library/Application Support/Claude/claude_desktop_config.json`:

```json
{
  "mcpServers": {
    "wounded-warriors-veterans": {
      "url": "https://warriors-fund-api.emperormew.workers.dev/mcp"
    }
  }
}
```

Restart Claude Desktop. Five tools appear automatically.

### Cursor / other MCP clients

Point your MCP client at `https://warriors-fund-api.emperormew.workers.dev/mcp`. No authentication. HTTP JSON-RPC 2.0. Protocol version `2025-03-26`.

### Smithery

```
npx @smithery/cli install wounded-warriors-veterans --client claude
```

## Example prompts

- *"Find VA hospitals near ZIP 77380"*
- *"What mental health resources are available in California?"*
- *"A veteran friend mentioned feeling hopeless — what should I tell them?"* (auto-routes to 988)
- *"Estimate VA disability compensation for a 70% rating"*
- *"Find veteran resources in Houston, Texas"*

## Veterans Crisis Line

If you are a veteran in crisis, or you know a veteran who may be in crisis:

**Call 988, Press 1** (available 24/7, free, confidential)
Text: **838255**
Chat: https://www.veteranscrisisline.net/get-help-now/chat/

## Data integrity

- Every resource record has a `verified_date` and SHA-256-hashed integrity attestation
- Full dataset export (SHA-256-verified): `https://warriors-fund-api.emperormew.workers.dev/api/export/snapshot`
- OpenAPI spec: `https://warriors-fund-api.emperormew.workers.dev/api/openapi.json`
- Dataset schema (JSON-LD): `https://warriors-fund-api.emperormew.workers.dev/api/grantmaker/snapshot`

## Nonprofit operator

This server is operated by **Wounded Warriors**, a Texas 501(c)(3) public charity:

- EIN: **86-1336741**
- Candid Seal of Transparency: **Platinum**
- Charity Navigator: **3-star (75%)**
- 88% program expense ratio (3-year average, FY2022–FY2024)
- Contact: info@warriorsfund.org

## License

- **Code**: MIT (this repo)
- **Data**: CC BY 4.0 — free to use, share, and adapt with attribution to Wounded Warriors

## Issues / contributions

Report issues or request features at: https://github.com/WoundedWarriors/wounded-warriors-mcp/issues
