
---
## 2026-08-17 17:10 UTC (fallback — ClickUp not configured)
ALERT: pre-market research aborted - all required env vars missing (ALPACA_API_KEY, ALPACA_SECRET_KEY, PERPLEXITY_API_KEY, CLICKUP_API_KEY, CLICKUP_WORKSPACE_ID, CLICKUP_CHANNEL_ID)

---
## 2026-08-17 17:19 UTC (fallback — ClickUp unreachable)
ALERT: pre-market research BLOCKED - egress policy denies paper-api.alpaca.markets, data.alpaca.markets, AND api.clickup.com (403 on CONNECT tunnel, policy denial per agent proxy). Cannot pull account/positions/orders, cannot post ClickUp alert. Credentials (Alpaca, ClickUp) are all set correctly - this is a network egress allowlist issue, not a config issue. No trade decision possible today. Needs admin to add these hosts to the session's egress policy.
