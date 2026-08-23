# Agent Einstein — Claude Code plugin

Crypto and market intelligence inside Claude Code: AI price forecasts with a
**published, checkable accuracy record**, whale and smart-money flows, market
sentiment, prediction-market signals, Bitcoin cycle position, congressional
trades and token safety.

**Eighteen tools are free** — no account, no API key, no wallet.

## Install

```
/plugin marketplace add ChuXo/einstein-claude-plugin
/plugin install einstein@einstein
```

Then ask: _"What is Einstein forecasting for BTC, and how accurate have those
forecasts been?"_

## What you get

| | |
| --- | --- |
| MCP endpoint | `https://emc2ai.io/api/mcp` (streamable HTTP) |
| Free tools | 18 — anonymous, no account |
| Paid tools | live analysis — OAuth + prepaid credit balance |
| Docs | https://emc2ai.io/mcp |
| Privacy | https://emc2ai.io/privacy-policy/ |
| Terms | https://emc2ai.io/terms-of-services/ |

The free tools read snapshots Einstein's scheduled research already computed, so
they answer fast and cost nothing. Paid tools — live security scans on any
contract, wallet analysis, forecasts on any token, backtests, deep research —
prompt for sign-in through OAuth 2.1 and draw on a prepaid credit balance. They
say what they cost before running, and a call with no balance returns a top-up
link rather than an error.

Forecast accuracy is published, not asserted — every prediction is scored and
served at
[`/api/einstein/v1/forecast/accuracy`](https://emc2ai.io/api/einstein/v1/forecast/accuracy).

The bundled `einstein-crypto` skill tells Claude which tool to reach for and how
to read "not warm yet" and "unknown" answers honestly.

Market and on-chain analysis is information, not financial advice.

---

Source of this package: [`ChuXo/Eliza`
→ `packages/project-einstein/distribution/claude-code`](https://github.com/ChuXo/Eliza/tree/develop/packages/project-einstein/distribution/claude-code).
