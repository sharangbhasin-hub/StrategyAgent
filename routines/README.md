# Cloud Routines

These five prompts are the production path. Paste each one verbatim into its own
Claude Code cloud routine (do not paraphrase — the env-var check block and the
commit-and-push step are load-bearing). See `GUIDE.md` Part 7 for the full
walkthrough of creating a routine, and Part 9 for troubleshooting.

Paper vs. live trading is controlled entirely by the `ALPACA_ENDPOINT` /
`ALPACA_DATA_ENDPOINT` environment variables you set on each routine — not by
the prompt text below. Start every routine's env vars pointed at
`https://paper-api.alpaca.markets/v2` until you've watched a full week of runs.

| File | Cron (America/Chicago) | Purpose |
|---|---|---|
| pre-market.md | `0 6 * * 1-5` | Research catalysts, write today's trade ideas |
| market-open.md | `30 8 * * 1-5` | Execute planned trades, set trailing stops |
| midday.md | `0 12 * * 1-5` | Cut losers, tighten stops on winners |
| daily-summary.md | `0 15 * * 1-5` | Snapshot portfolio, send recap |
| weekly-review.md | `0 16 * * 5` | Weekly stats, grade, strategy updates |

Required environment variables on every routine: `ALPACA_API_KEY`,
`ALPACA_SECRET_KEY`, `ALPACA_ENDPOINT`, `ALPACA_DATA_ENDPOINT`,
`PERPLEXITY_API_KEY`, `PERPLEXITY_MODEL`, `CLICKUP_API_KEY`,
`CLICKUP_WORKSPACE_ID`, `CLICKUP_CHANNEL_ID`. Also enable "Allow unrestricted
branch pushes" in the routine's environment settings, or `git push` will
silently fail.
