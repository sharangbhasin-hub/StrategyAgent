# Cloud Routines

These five prompts are the production path. They're live as Claude Code cloud
routines (scheduled cloud agents, created via the `/schedule` flow), each
pointed at the same cloud environment. See `GUIDE.md` Part 7 for the original
design write-up — a few details below differ from what that doc assumes,
based on what actually happened standing this up.

## Deployed routines

| File | Cron (UTC) | Local time (America/Chicago) | Trigger ID |
|---|---|---|---|
| pre-market.md | `0 11 * * 1-5` | 6:00 AM CDT | `trig_01LBP2TGDzLZVpdUhVECLpuR` |
| market-open.md | `30 13 * * 1-5` | 8:30 AM CDT | `trig_01TTAJpEhM1RTsKGJU22sUPT` |
| midday.md | `0 17 * * 1-5` | 12:00 PM CDT | `trig_01TmLu7RnZtPQkFacoLzeC5d` |
| daily-summary.md | `0 20 * * 1-5` | 3:00 PM CDT | `trig_01Cc4g8DiykeJSx2ArtVnh2m` |
| weekly-review.md | `0 21 * * 5` | 4:00 PM CDT, Fridays | `trig_012xYVhZDqhmd8vFQ2onhXK4` |

All run against the "Default" cloud environment (`env_018HEpt6CLgYRycFZeyMrqTH`)
at claude.ai/code/environments. Manage/monitor at claude.ai/code/routines.

**DST caveat:** the routine API's cron is fixed UTC with no timezone field —
the times above are calibrated for CDT (UTC-5). When US clocks fall back in
November, every cron_expression needs manually shifting by one hour to keep
firing at the same market-relative time (e.g. pre-market's `0 11` becomes
`0 12`). Revisit this repo around the DST changeover.

## What differs from GUIDE.md Part 7

- **No "Allow unrestricted branch pushes" toggle.** It doesn't exist in the
  current product. Routines can push to `main` as long as the branch isn't
  protected and doesn't carry someone else's open PR or foreign-authored
  commits — tested and confirmed working directly to `main` for this repo.
- **Secrets live on the cloud environment, not the routine.** Set at
  claude.ai/code/environments → the environment → environment variables.
  Not part of the routine's create/update body.
- **Outbound network access is allowlisted per environment**, not open by
  default. The "Default" environment's Network access is set to Custom with
  `paper-api.alpaca.markets`, `data.alpaca.markets`, and `api.clickup.com`
  added — without this, every Alpaca/ClickUp call 403s at the egress proxy.
- **No `PERPLEXITY_API_KEY` is set.** This deployment intentionally skips
  Perplexity (no signup) and relies on the graceful WebSearch fallback that
  `scripts/perplexity.sh` already triggers (exit code 3) and every prompt
  already handles.

Required environment variables on the shared environment: `ALPACA_API_KEY`,
`ALPACA_SECRET_KEY`, `ALPACA_ENDPOINT`, `ALPACA_DATA_ENDPOINT`,
`CLICKUP_API_KEY`, `CLICKUP_WORKSPACE_ID`, `CLICKUP_CHANNEL_ID`.
