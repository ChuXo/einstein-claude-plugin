---
name: einstein-crypto
description: Crypto and market intelligence via the Agent Einstein MCP server — AI price forecasts with a published accuracy record, whale and smart-money flows, market sentiment, prediction-market signals, Bitcoin cycle position, congressional trades, token safety. Use when the question is about crypto prices, forecasts, on-chain flows, market sentiment, a token's safety, or a prediction market.
---

# Agent Einstein

This plugin connects to Einstein's public MCP server at
`https://emc2ai.io/api/mcp`. Tools appear as `mcp__einstein__*`.

## Free — no account, no key, no cost to the caller

Eighteen tools read snapshots Einstein's own scheduled automations already
computed. They answer anonymously and are safe to call whenever they help.

- `get_price_forecast` — dual-model (Google TimesFM 2.5 + Kronos) forecast for
  BTC, ETH, SOL or BNB, including whether the two models agree.
- `get_forecast_accuracy` — the **measured** record of those forecasts (MAPE,
  direction hit rate). Cite this rather than any accuracy claim in prose; it is
  the only accuracy number that is computed rather than asserted.
- `get_market_sentiment` — crypto and TradFi Fear & Greed, altcoin season.
- `get_top_movers`, `get_smart_money_flow`, `get_smart_money_inflow`,
  `get_hyperliquid_whales`, `get_polymarket_whales`,
  `get_prediction_market_catalysts`, `get_prediction_market_yields`,
  `get_bitcoin_cycle_position`, `check_token_safety`, `get_congress_trades`,
  `get_government_contracts`, `get_analyst_accuracy`, `get_social_hype`,
  `get_launchpad_radar`.
- `list_einstein_capabilities` — the full catalog. **Start here** when you are
  not sure which tool fits.

A free tool that reports "not warm yet" means the snapshot has not been computed
recently. That is not an error and it is not worth retrying in a loop — say so
and move on.

Most of these accept `limit` (1-25, default 10) and it is applied to the row
lists inside the answer, not just echoed back. Ask for what you will actually
read: the default already trims, and a payload that comes back with a
`truncated` block is telling you how many rows exist behind the ones you got.

## Paid — account plus prepaid credit

Paid tools run live work: security scans on an arbitrary contract, wallet
analysis, forecasts on any token, backtests, deep research.
They need an Einstein account (OAuth 2.1, which the host will prompt for) and a
credit balance, and they say what they cost before running.

A paid call without an account returns a **sign-in prompt**, not a silent
failure. A paid call with no balance returns a normal result carrying a top-up
link — surface that link to the user rather than treating it as an error.

## Choosing a tool

- "What will BTC do?" → `get_price_forecast`, then `get_forecast_accuracy` so
  the user can weigh it.
- "Is this token safe?" → `check_token_safety` first (free, and honestly reports
  UNKNOWN for anything unscreened). Only reach for the paid
  `analyze_token_security` when the user wants a live scan of a specific
  contract.
- "What's the market doing?" → `get_market_sentiment` + `get_top_movers`.
- Anything else → `list_einstein_capabilities`.

## Honesty rules

- **This is information, not advice.** Einstein's market, on-chain and strategy
  output is AI-generated research — not financial, investment, legal or tax
  advice, and not a personalised recommendation. No human adviser reviews it
  before the user sees it. Say so the first time you present anything the user
  could act on with money (a forecast, a signal, an allocation, a yield), and
  present it as analysis to weigh rather than as an instruction to follow.
- Never state a forecast as a certainty. The tools return bands and model
  agreement; pass both through.
- Never invent an accuracy, precision or hit-rate figure. If you need one, call
  `get_forecast_accuracy`.
- Free-tool data is a cached snapshot with an age attached. Quote the age.
- When a result carries a `truncated` block, say how many rows exist — never
  report the rows you received as if they were the whole set.
