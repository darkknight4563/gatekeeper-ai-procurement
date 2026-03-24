# Gatekeeper AI — Energy Sector Procurement Intelligence

A Claude Cowork plugin that turns Claude into an expert energy sector procurement analyst. Analyze vendor proposals, compare bids with weighted scoring, check compliance, assess risks, and generate professional evaluation reports with interactive visual dashboards.

## What It Does

Drop vendor proposal PDFs into your Cowork folder and tell Claude to evaluate them. Gatekeeper AI handles the rest:

- **Proposal Analysis** — Extracts pricing, delivery schedules, technical specs, compliance status, key personnel, risks, strengths, and weaknesses from each vendor proposal
- **Bid Comparison** — Weighted scoring across 6 criteria (technical compliance, pricing, delivery, HSE, experience, commercial terms) with ranked recommendations
- **Pricing Extraction** — Line-item detail with hidden cost detection, escalation clauses, and payment term analysis
- **Compliance Checking** — Pass/fail evaluation against specific RFP requirements with evidence citations
- **Risk Assessment** — Comprehensive risk register covering commercial, technical, HSE, supply chain, regulatory, and geopolitical risks
- **Visual Dashboards** — Radar charts, pricing comparison bars, delivery timelines, compliance heatmaps, risk matrices, and executive scorecards rendered inline
- **Report Generation** — Executive-ready procurement evaluation reports suitable for board-level review

## Who It's For

- Procurement teams in oil & gas, subsea, marine, and industrial sectors
- Supply chain managers evaluating vendor bids
- Project managers overseeing equipment procurement
- Engineering teams reviewing technical proposals
- Anyone who needs to compare vendor proposals objectively

## Slash Commands

| Command | Description |
|---------|-------------|
| `/procurement:evaluate` | Full end-to-end evaluation of all proposals in the working folder |
| `/procurement:analyze` | Deep analysis of a single vendor proposal |
| `/procurement:dashboard` | Generate interactive visual dashboard from existing analysis data |

## Domain Coverage

- Drilling Equipment & Services
- Subsea Systems (manifolds, trees, umbilicals, ROVs)
- Production Equipment (separators, compressors, turbines)
- Maintenance & Inspection Services
- Engineering & Consulting Services
- Marine Logistics (vessels, helicopters, port services)
- Construction Materials & IT/Automation

## Standards Knowledge

DNV-ST-F119, API 17E, NORSOK Z-001, ISO 45001, ISO 9001, ISO 14001, IOGP, MARPOL, EU ETS, ATEX/IECEx, Petroleumstilsynet requirements.

## Installation

### From Cowork

1. Click **Customize** → **Add Plugins** → search for "Gatekeeper AI"
2. Install and the tools are immediately available

### Manual

```bash
claude plugin install gatekeeper-ai-procurement
```

Or clone this repo and point Cowork at it as a custom plugin folder.

## Architecture

The plugin connects to the Gatekeeper AI MCP server, which uses Claude (Sonnet) as an analysis engine under the hood. Each tool call sends domain-specific prompts to the Anthropic API and returns structured, typed results that Claude can render as tables, charts, or reports.

```
User → Claude Cowork → Plugin Skills/Commands → MCP Connector → Gatekeeper AI Server → Anthropic API
                                                                        ↓
                                                              Structured procurement analysis
                                                                        ↓
                                                              Visual dashboards & reports
```

## Data Security

Vendor proposals are commercially sensitive. Gatekeeper AI is designed for enterprise procurement environments with strict data handling requirements.

**Key security properties:**
- **Stateless processing** — No vendor data is stored on the server. All processing is request/response with zero persistence.
- **API key authentication** — All endpoints require Bearer token authentication (v1.1.0+).
- **HTTPS only** — All data in transit is encrypted via TLS.
- **Zero retention available** — Anthropic's Enterprise API tier ensures analysis data is not stored or used for training.

**Enterprise deployment options:**

| Tier | How It Works | Data Residency |
|------|-------------|----------------|
| On-Premise | Server runs inside your infrastructure | Data never leaves your network |
| Private Cloud (EEA) | Dedicated instance in EU/EEA with DPA | GDPR-compliant, data stays in region |
| Managed Cloud | Hosted with API key auth and zero retention | Data transits but is not persisted |
| Local Desktop | Runs on your machine via stdio | Data stays on your machine |

For Norwegian Continental Shelf operators (Equinor, Aker BP, etc.): on-premise deployment ensures proposal data stays within your existing security perimeter, compliant with NORSOK Z-001 data classification and Petroleumstilsynet requirements.

See the [full security documentation](https://github.com/darkknight4563/gatekeeper-ai-mcp-server#data-security--enterprise-deployment) in the MCP server repo.

## About

Built by [Gatekeeper AI](https://github.com/darkknight4563/gatekeeper-ai-mcp-server) — an agentic AI platform for energy sector procurement that has delivered documented client savings and significant procurement cycle-time reduction.

## License

Proprietary — Gatekeeper AI © 2026
