# MCP Billing Spec v1

**An open standard for billing, metering, receipts, verification, and dispute resolution in MCP tool ecosystems.**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

---

## Why This Exists

There are 10,000+ MCP servers but most are hobby-quality because developers can't earn from them. Multiple companies are building billing solutions independently with incompatible schemas. This fragmentation hurts everyone:

- **Agents** must learn different billing APIs per provider
- **Providers** can't switch billing platforms without rewriting integrations
- **Platforms** compete on implementation details instead of value

This spec creates a common language for MCP billing.

## What It Covers

| Section | Description |
|---------|-------------|
| **Meter Events** | Standard schema for recording tool invocations |
| **Signed Receipts** | HMAC-SHA256 tamper-proof proof of every call |
| **Pricing Declarations** | How providers declare per-call and per-token pricing |
| **Verification Levels** | 4-tier provider verification (unverified → email → domain → code) |
| **Dispute Resolution** | Filing, status flow, resolution types |
| **Trust Scores** | Composite scoring from verification + SLA + disputes |

## Read the Spec

📄 **[mcp-billing-v1.md](./mcp-billing-v1.md)** — The full specification

🌐 **[noui.bot/specs/mcp-billing-v1](https://noui.bot/specs/mcp-billing-v1)** — Web version

## Reference Implementation

The [Agent Bazaar](https://noui.bot) at noui.bot is the reference implementation:

- **API:** `https://noui.bot/api/v1` (v0.4.0)
- **SDK:** `npm install @noui/bazaar-sdk`
- **OpenAPI:** `https://noui.bot/api/openapi.json`
- **Source:** [github.com/TombStoneDash/noui-bot](https://github.com/TombStoneDash/noui-bot)

## For Other Billing Providers

This spec is designed to be implementable by anyone — including our competitors. If you're building MCP billing (xpay, TollBit, MCP Hive, or something new), you can:

1. **Implement the receipt schema** — agents get consistent billing experiences regardless of provider
2. **Use the verification levels** — a shared trust vocabulary for the ecosystem
3. **Adopt the dispute schema** — standard resolution flow across platforms
4. **Reference this spec** — and contribute to making it better

We'd rather be the reference implementation of a universal standard than a walled garden.

## Contributing

- Open an issue for spec feedback, clarifications, or proposed changes
- PRs welcome for typos, examples, and additional appendices
- Major schema changes should go through an issue discussion first

## License

MIT — Copy it. Fork it. Implement it. That's the point.

---

Built by [TombStone Dash LLC](https://tombstonedash.com) · San Diego, CA
One human, one AI. The void is open.
