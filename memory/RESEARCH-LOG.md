# Research Log

Daily pre-market research entries will be appended here.

Format each entry:

## YYYY-MM-DD — Pre-market Research

### Account
- Equity: $X
- Cash: $X
- Buying power: $X
- Daytrade count: N

### Market Context
- WTI / Brent:
- S&P 500 futures:
- VIX:
- Today's catalysts:
- Earnings before open:
- Economic calendar:
- Sector momentum:

### Trade Ideas
1. TICKER — catalyst, entry $X, stop $X, target $X, R:R X:1
2. ...

### Risk Factors
- ...

### Decision
TRADE or HOLD (default HOLD if no edge)

## 2026-08-17 — Pre-market Research

### Account
- BLOCKED — egress policy denies paper-api.alpaca.markets (403 on CONNECT tunnel).
  Could not pull equity/cash/buying power/daytrade count.

### Market Context
- Not researched — run aborted before Perplexity/WebSearch step once account
  access failed. PERPLEXITY_API_KEY also unset (intentional; would have used
  WebSearch fallback).

### Trade Ideas
- None — no account/position data available, so no trade can be sized or
  validated against risk rules.

### Risk Factors
- Infra: session egress policy is blocking paper-api.alpaca.markets,
  data.alpaca.markets, AND api.clickup.com (all 403 on CONNECT — confirmed via
  agent proxy status, not a credential issue; all required keys verified set).
  ClickUp alert could not be posted; logged to DAILY-SUMMARY.md fallback
  instead.

### Decision
HOLD — no trade possible, workflow blocked at Step 2 (account state pull).
Needs admin to allowlist Alpaca/ClickUp hosts in the session network policy.
