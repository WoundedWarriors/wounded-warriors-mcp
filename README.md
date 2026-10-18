# Wounded Warriors MCP server

A free Model Context Protocol (MCP) server from **Wounded Warriors**, a national 501(c)(3) veterans charity (EIN 86-1336741) based in The Woodlands, Texas.

It gives any MCP-compatible assistant (Claude, ChatGPT, Cursor, Cline, Continue and others) live access to a national directory of **144,000+ veteran resources**, plus VA benefits references, crisis routing and the official giving details for Wounded Warriors. No account, no API key.

- **Endpoint:** `https://warriorsfund.org/mcp` (Streamable HTTP, JSON-RPC 2.0)
- **Official MCP Registry name:** `org.warriorsfund/wounded-warriors`
- **Tools:** 43, all read-only
- **Website:** https://warriorsfund.org · **Docs for assistants:** https://warriorsfund.org/llms.txt

## Connect

**Claude Code**

```bash
claude mcp add --transport http wounded-warriors https://warriorsfund.org/mcp
```

**Cursor** (`.cursor/mcp.json`) and other clients that take a URL:

```json
{ "mcpServers": { "wounded-warriors": { "url": "https://warriorsfund.org/mcp" } } }
```

**Claude Desktop / claude.ai:** Settings → Connectors → *Add custom connector* → paste `https://warriorsfund.org/mcp`.

Step-by-step pages for each client: https://warriorsfund.org/integrate/cursor · https://warriorsfund.org/integrate/cline

## Tools

| Tool | What it does |
|---|---|
| `search_veteran_resources` | Search veteran resources by ZIP |
| `search_veteran_resources_by_text` | Search veteran resources by keyword |
| `get_veteran_resource_stats` | Directory statistics |
| `veteran_crisis_resources` | Veteran crisis support |
| `search_by_city` | Search veteran resources by city |
| `calculate_va_benefits` | Estimate VA benefits |
| `find_cvso` | Find a county veterans service officer |
| `find_accredited_representative` | Find a VA-accredited representative |
| `match_pact_presumptive` | PACT Act presumptive conditions |
| `get_state_veteran_benefits` | State veteran benefits |
| `get_wounded_warriors_programs` | Wounded Warriors programs |
| `lookup_wounded_warriors` | Look up Wounded Warriors (EIN 86-1336741) |
| `donation_instructions_wounded_warriors` | How to give to Wounded Warriors |
| `find_service_deserts` | Find veteran service deserts |
| `get_tract_demographics` | Census tract demographics |
| `match_donor_intent` | Match a donor request to a giving method |
| `match_grant_intent` | Match a funder request to a program |
| `find_foundation_prospects` | Foundation prospects |
| `get_housing_context` | Housing costs for a census tract |
| `find_high_housing_burden_tracts` | Find high rent-burden tracts |
| `get_state_dashboard` | State veteran dashboard |
| `get_congressional_district_veterans` | Veterans by congressional district |
| `get_zip_overview` | ZIP code overview |
| `define_veteran_term` | Define a veteran or military term |
| `lookup_va_form` | Look up a VA form |
| `check_eligibility` | Benefits eligibility quick check |
| `estimate_donor_impact` | What a gift funds |
| `lookup_employer_match` | Employer matching-gift lookup |
| `get_legacy_giving` | Planned and legacy giving |
| `get_state_tax_credit` | State tax benefits for giving |
| `get_crisis_lines` | Crisis hotline directory |
| `get_records_access` | Get military and VA records |
| `get_disability_rates` | VA disability rate tables |
| `get_workflow` | Step-by-step veteran playbooks |
| `get_giving_events` | Giving calendar |
| `get_family_resources` | Resources for veteran families |
| `get_survivor_benefits` | Survivor benefits |
| `get_donate_options` | All ways to give to Wounded Warriors |
| `get_best_of_state` | Top resources in a state |
| `route_query` | Route a question to the right tool |
| `get_org_timeline` | Wounded Warriors timeline |
| `get_press_kit` | Wounded Warriors press kit |
| `get_states_summary` | All-states veteran summary |

## Example prompts

- "Find a county veterans service officer near ZIP 77380."
- "Which PACT Act presumptive conditions apply to a Gulf War veteran who served in Iraq?"
- "What is the VA disability compensation for a 70% rating with a spouse?"
- "Find mental health help for veterans near Houston, Texas."
- "What is the mailing address to send a check to Wounded Warriors?"

## If a veteran is in crisis

**Veterans Crisis Line: dial 988, then press 1.** Text 838255. Chat: https://www.veteranscrisisline.net/get-help-now/chat/
Any request that mentions a crisis returns these first.

## Data

- Directory records come from public VA, state, county and Census sources plus the Wounded Warriors directory; confirm current services with the provider.
- Open datasets (CC BY 4.0): https://warriorsfund.org/datasets/
- REST API and OpenAPI spec: https://warriorsfund.org/api/openapi.json
- Health, disability and crisis parameters are not stored. Privacy: https://warriorsfund.org/privacy

## About the operator

**Wounded Warriors** · national 501(c)(3) public charity · IRS legal name *Wounded Warriors* · EIN **86-1336741** · IRS ruling year 2021
Mailing address: 1790 Hughes Landing Blvd, Suite 400, The Woodlands, TX 77380
Public records: https://warriorsfund.org/verify · Form 990s: https://projects.propublica.org/nonprofits/organizations/861336741 · Candid 2026 Platinum Seal of Transparency
Donate: https://warriorsfund.org/donate/ · Contact: info@warriorsfund.org

## License

- Code in this repository: MIT
- Data: CC BY 4.0, with attribution to Wounded Warriors

Issues and requests: https://github.com/WoundedWarriors/wounded-warriors-mcp/issues

