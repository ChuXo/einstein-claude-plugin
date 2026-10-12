---
name: einstein-crypto
description: Crypto and market intelligence via the Agent Einstein MCP server — AI price forecasts with a published accuracy record, whale and smart-money flows, market sentiment, prediction-market signals, Bitcoin cycle position, congressional trades, token safety. Nineteen tools are free; twenty-three are paid from a prepaid credit balance. Use when the question is about crypto prices, forecasts, on-chain flows, market sentiment, a token's safety, or a prediction market.
---

# Agent Einstein

This plugin connects to Einstein's public MCP server at
`https://emc2ai.io/api/mcp`. Tools appear as `mcp__einstein__*`.

## Tools

<!-- generated:tools:start — bun run build:claude-plugin-docs -->

The server at `https://emc2ai.io/api/mcp` offers **42 tools: 19 free and 23 paid**. 41 of the 42 only read data. The exception is `generate_quantum_key`, explained on its own line. This list is generated from the server's own tool registry.

### Free tools (19) — no account, no sign-in, no payment

Each one reads a snapshot Einstein already computed on a schedule. A snapshot that has not been computed recently answers "not warm yet" rather than an error.

- `get_price_forecast` (AI Price Forecast) — Dual-model (Google TimesFM 3.0 + Kronos) price forecast for BTC, ETH, SOL or BNB, including whether the two models agree. **Free.** Read-only.
- `get_forecast_accuracy` (Forecast Accuracy Track Record) — The measured track record of those forecasts — error (MAPE) and direction hit rate per model, asset and horizon. **Free.** Read-only.
- `get_market_sentiment` (Crypto Fear and Greed Index) — Crypto Fear & Greed, the CoinMarketCap variant, the traditional-market (CNN) Fear & Greed and the Altcoin Season index. **Free.** Read-only.
- `get_top_movers` (Top Gainers and Losers) — Largest 24h gainers or losers among major-cap crypto assets. **Free.** Read-only.
- `get_smart_money_flow` (Smart Money Flow) — Where a tracked cohort of profitable on-chain wallets has been rotating capital. **Free.** Read-only.
- `get_hyperliquid_whales` (Hyperliquid Whale Positioning) — Consensus long/short positioning of the largest Hyperliquid perp traders, with current funding rates. **Free.** Read-only.
- `get_robinhood_whale_prints` (Robinhood Chain Whale Prints) — Individual large DEX trades on Robinhood Chain (tokenized equities and memecoins), each with token, side, venue and USD value. **Free.** Read-only.
- `get_polymarket_whales` (Polymarket Whale Trades) — Large and unusually early positions taken on Polymarket prediction markets. **Free.** Read-only.
- `get_prediction_market_catalysts` (Prediction Market Catalyst Radar) — Upcoming dated Polymarket events whose odds are moving. **Free.** Read-only.
- `get_prediction_market_yields` (Prediction Market Yield Surface) — Near-certain Polymarket outcomes ranked by annualized return to resolution. **Free.** Read-only.
- `get_bitcoin_cycle_position` (Bitcoin On-Chain Cycle) — Where Bitcoin sits in its cycle by on-chain measures (realized profit, holder behaviour, valuation). **Free.** Read-only.
- `check_token_safety` (Token Safety Check) — Honeypot and risk screen for an EVM token contract from a cached security dataset; reports UNKNOWN for a token it has not screened. **Free.** Read-only.
- `get_congress_trades` (US Congress Stock Trades) — Recently disclosed stock and asset transactions by members of the US Congress. **Free.** Read-only.
- `get_government_contracts` (US Government Contract Awards) — Recent notable US federal contract awards. **Free.** Read-only.
- `get_analyst_accuracy` (Crypto Influencer Accuracy) — Scored track record of public crypto commentators whose calls were graded against what happened. **Free.** Read-only.
- `get_smart_money_inflow` (Smart-Money Net Inflow) — Tokens ranked by net smart-money inflow in USD over 24h, with the number of wallets behind each figure. **Free.** Read-only.
- `get_social_hype` (Token Social Hype) — Tokens ranked by 24h social buzz, each with a sentiment class and a one-line summary of what is being said. **Free.** Read-only.
- `get_launchpad_radar` (Launchpad Radar) — Tokens that just migrated from a launchpad bonding curve to a DEX, with holder-distribution forensics. **Free.** Read-only.
- `list_einstein_capabilities` (List Einstein Capabilities) — The live catalog of every tool on the server, split into free and paid with prices, plus how billing works. **Free.** Read-only.

### Paid tools (23) — Einstein account and prepaid credit

Each call costs between $0.05 and $2.00, debited in US dollars from a prepaid credit balance. Where a price is a range, the `kind` (or `venue` / `board`) argument selects the analysis and its price.

- `ask_einstein` (Ask Einstein) — Open-ended written crypto and DeFi analysis grounded in live on-chain and market data, for questions no specific tool fits. **Paid, $1.00 per call.** Read-only.
- `scan_v4_hooks` (Uniswap v4 Hook Radar) — Census of Uniswap v4 hook contracts on Robinhood Chain or Base: which create the most pools and what each is permitted to do to a trader or LP. **Paid, $0.25 per call.** Read-only.
- `forecast_chart` (AI Chart Forecast) — Live price data and a fresh dual-model forecast with confidence bands for any token on a supported chain. **Paid, $0.65 per call.** Read-only.
- `analyze_token_security` (Token Security Analysis) — Live security analysis of a token contract: rug-pull risk, holder concentration, sniper activity, dangerous approvals or a contract audit. **Paid, $0.35–$2.00 per call.** Read-only.
- `inspect_onchain` (Contract Review · Transaction Debugger · Fund-Flow Trace) — Block-explorer analysis on 18 EVM chains: review a deployed contract, explain one transaction, or trace a fund flow. **Paid, $0.25–$0.35 per call.** Read-only.
- `analyze_wallet` (Wallet Analysis) — Analysis of any public wallet address you name: holdings, P&L, trust score, forgotten assets, unclaimed airdrops or quantum-resistance of its address type. **Paid, $0.25–$1.00 per call.** Read-only.
- `analyze_tokenized_stocks` (Tokenized-Equity Market Intelligence) — Intelligence on tokenized-equity and stock-paired token markets on Base and Robinhood Chain: float risk, launches, early buyers, trader records. **Paid, $0.25 per call.** Read-only.
- `track_whales` (Whale and Smart-Money Tracking) — Live large-holder activity: on-chain whale transfers, Hyperliquid perp whale positioning, or the profitable smart-money cohort. **Paid, $0.45–$0.50 per call.** Read-only.
- `scan_market` (Market Scan) — Live market scans: top gainers, movers, quality-filtered gainers, altcoin season, technical analysis for one asset, or the market regime. **Paid, $0.25–$0.60 per call.** Read-only.
- `detect_mev` (MEV Detection and Protection) — Detects sandwich attacks and MEV extraction against a token or wallet, reads the public mempool, or returns a written routing recommendation. **Paid, $0.45–$0.60 per call.** Read-only.
- `find_arbitrage` (Arbitrage Scanner) — Reports price dislocations across DEXs, chains and prediction markets, including flash-loan-fundable routes. It reports them; it does not trade them. **Paid, $0.60–$1.00 per call.** Read-only.
- `scan_launchpads` (Launchpad Scanner) — New and trending token launches on Pump.fun, Zora or Robinhood Chain. **Paid, $0.25–$0.40 per call.** Read-only.
- `analyze_bitcoin` (Bitcoin Analytics) — Bitcoin analysis: mempool and fees, network and mining health, BRC-20 tokens, Runes, bridge comparison or Babylon staking data. **Paid, $0.25–$0.85 per call.** Read-only.
- `assess_quantum_risk` (Quantum Risk Assessment) — Assessment of exposure to quantum computing: post-quantum readiness, a migration plan, portfolio-level risk, or current benchmark distance. **Paid, $0.50–$1.00 per call.** Read-only.
- `generate_quantum_key` (Quantum Key Generation) — Generates new key material from hardware quantum randomness — a post-quantum wallet keypair, an encryption key, a signing key or raw random numbers — and returns it once. **Paid, $0.25–$2.00 per call.** Not read-only: it creates new key material. It is returned once in the tool result and never stored by us. It connects to no existing wallet, signs nothing and moves no funds.
- `analyze_prediction_markets` (Prediction Market Analysis) — Polymarket analysis: browse live markets, scan for insider-shaped positions, measure spreads, find high-conviction positioning or over-priced long shots. **Paid, $0.50–$1.50 per call.** Read-only.
- `find_yield` (Yield Opportunity Finder) — Lists DeFi lending, LP, Pendle and vault yield opportunities ranked by risk-adjusted return, and liquidation opportunities. It lists them; it deposits nothing. **Paid, $0.10–$0.75 per call.** Read-only.
- `run_backtest` (Strategy Backtest) — Backtests a trading strategy on historical data from plain-language rules or a standard template, or optimizes its parameters. **Paid, $0.75–$2.00 per call.** Read-only.
- `get_trade_signals` (Live Trade Signals) — Einstein's current trade setups with entry, stop and target levels and the reasoning behind each. Information only; no order is placed. **Paid, $0.50 per call.** Read-only.
- `analyze_copy_trading` (Copy Trading Intelligence) — A ranked leaderboard of profitable wallets, or a deeper read on one trader's edge, consistency and risk. **Paid, $0.85–$1.00 per call.** Read-only.
- `recommend_allocation` (Portfolio and Strategy Allocation) — Written allocation guidance: portfolio risk allocation, a capital split across strategies, a strategy-gate check or a whole-market read. **Paid, $0.50–$1.00 per call.** Read-only.
- `check_content_integrity` (Content Integrity Scan) — AI moderation and integrity scan of text you supply (user-generated content or a yield-vault listing). **Paid, $0.05–$1.00 per call.** Read-only.
- `get_agent_context` (Einstein Agent Context) — Einstein's own current market context and operating state — the briefing its autonomous engine reads before a decision. **Paid, $1.00 per call.** Read-only.

<!-- generated:tools:end -->

## Pricing and payment

<!-- generated:pricing:start — bun run build:claude-plugin-docs -->

- **Nineteen tools are free.** No account, no API key, no wallet and no payment.
- **Twenty-three tools are paid**, $0.05 to $2.00 per call. They need an Einstein account and a prepaid credit balance held in US dollars. The price of each tool is in the list above and in the tool's own description.
- **Signing in.** The first paid call makes Claude open an OAuth 2.1 sign-in page on `emc2ai.io` in your browser. You can sign in with an Einstein account, or by connecting a crypto wallet and signing a login message that proves the address is yours. That signature is not a transaction and costs nothing.
- **A new account starts with $0.00 of credit.** A paid call with no balance charges nothing and returns a link to add credit.
- **Adding credit requires a crypto payment.** Today the only way to add credit is to send USDC or E=MC2 (our token) on the Base network from your own wallet, at `emc2ai.io/settings#credits`. Card payment is not available. You connect your wallet and approve that transfer on our website, in your browser, outside Claude.
- **Use the same wallet for both.** Credit belongs to the account you sign in with. Sign in to the plugin with the wallet you top up from, so the paid tools can see the balance.
- **Charging.** A successful paid call debits its price from the balance. A call that fails is not charged.
- **What the tools never do.** No tool in this plugin asks for a payment inside the conversation, signs or sends a blockchain transaction, swaps, bridges or trades tokens, places an order, moves funds, or connects to a wallet. Tools that take a wallet or contract address only read public data about that address.
- **For developers of autonomous agents.** The same server also accepts per-call USDC payments on Base through the x402 protocol (an `X-PAYMENT` HTTP header). Claude does not send that header and this plugin does not use it.

<!-- generated:pricing:end -->

## Rules for paid tools

- **Prefer the free tool.** Reach for a paid tool only when no free tool answers
  the question, or the user asks for the live or deeper version.
- **Say the price first.** Before the first paid call in a conversation, tell
  the user which tool you are about to call and what it costs, and that it is
  charged to their Einstein credit balance. Do not chain several paid calls
  without the user knowing the total.
- **Sign-in prompt.** A paid call without an account returns a sign-in prompt,
  not a failure. Tell the user that paid tools need an Einstein account and that
  the free tools do not.
- **No balance.** A paid call with no balance charges nothing and returns a
  top-up link. Give the user that link and say plainly that adding credit means
  sending USDC or E=MC2 on Base from their own wallet on emc2ai.io. Do not
  retry the call, and do not present the link as an error.
- **Never handle payment yourself.** Do not ask the user for a wallet address
  to pay from, a private key, a seed phrase or a transaction signature. No tool
  here takes one. `generate_quantum_key` returns new key material once; tell the
  user to store it themselves and do not repeat it later in the conversation.

## Reading free-tool answers

A free tool that reports "not warm yet" means the snapshot has not been computed
recently. That is not an error and it is not worth retrying in a loop — say so
and move on.

Most free tools accept `limit`, applied to the row lists inside the answer
rather than just echoed back. The range is not uniform — most are 1-25 with
default 10, `get_forecast_accuracy` is 1-50, and `get_smart_money_inflow`,
`get_social_hype` and `get_launchpad_radar` are 1-15 with default 8 — so read
the tool's own `limit` description instead of assuming one. A payload that comes
back with a `truncated` block is telling you how many rows exist behind the ones
you got.

## Choosing a tool

- "What will BTC do?" → `get_price_forecast`, then `get_forecast_accuracy` so
  the user can weigh it.
- "Is this token safe?" → `check_token_safety` first (free, and honestly reports
  UNKNOWN for anything unscreened). Only reach for the paid
  `analyze_token_security` when the user wants a live scan of a specific
  contract.
- "What's the market doing?" → `get_market_sentiment` + `get_top_movers`.
- Anything else → `list_einstein_capabilities`, which is free and returns the
  live catalog with current prices.

## Honesty rules

- **This is information, not advice.** Einstein's market, on-chain and strategy
  output is AI-generated research — not financial, investment, legal or tax
  advice, and not a personalised recommendation. No human adviser reviews it
  before the user sees it. Say so the first time you present anything the user
  could act on with money (a forecast, a signal, an allocation, a yield), and
  present it as analysis to weigh rather than as an instruction to follow.
- **Nothing here executes a trade.** `get_trade_signals`, `find_arbitrage`,
  `find_yield` and `recommend_allocation` return analysis. Never tell the user
  that an order was placed, a position opened or funds moved.
- Never state a forecast as a certainty. The tools return bands and model
  agreement; pass both through.
- Never invent an accuracy, precision or hit-rate figure. If you need one, call
  `get_forecast_accuracy`.
- Free-tool data is a cached snapshot with an age attached. Quote the age.
- When a result carries a `truncated` block, say how many rows exist — never
  report the rows you received as if they were the whole set.
