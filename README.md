# StrategyAgent — Autonomous Trading Bot

An autonomous, cloud-scheduled trading agent built on Claude Code. Five cron
jobs research, trade, manage risk, and report on a live (paper, to start)
Alpaca account. There is no separate bot process — every scheduled run is a
fresh Claude Code invocation that reads its memory from this git repo,
acts, and commits the result back to `main`. See [GUIDE.md](GUIDE.md) for
the full design writeup.

## Two ways to run this

- **Local mode** — you invoke slash commands (`/portfolio`, `/trade`,
  `/pre-market`, `/market-open`, `/midday`, `/daily-summary`,
  `/weekly-review`) manually inside Claude Code. Credentials come from a
  local `.env` file. Good for testing.
- **Cloud mode** — Claude's cloud routines fire each `routines/*.md` prompt
  on a cron schedule. Credentials come from environment variables set on
  the routine, not a `.env` file. This is the production path — see
  `routines/README.md` and `GUIDE.md` Part 7.

## Quickstart

1. Copy `env.template` to `.env` and fill in your Alpaca (paper), Perplexity,
   and ClickUp credentials.
2. Open this repo in Claude Code and run `/portfolio`. You should see
   account equity, cash, positions, and open orders print cleanly.
3. Once that works locally, follow `GUIDE.md` Part 7 to set up the five
   cloud routines from `routines/*.md`.

## Layout

- `CLAUDE.md` — agent rulebook, auto-loaded every session.
- `scripts/` — the only way the agent touches the outside world (Alpaca,
  Perplexity, ClickUp API wrappers).
- `memory/` — the agent's persistent state, committed to `main`.
- `routines/` — cloud routine prompts (production).
- `.claude/commands/` — local slash commands.

## Strategy in one paragraph

Swing trading, stocks only, no options. Max 5-6 positions, max 20% of
equity each, max 3 new trades/week, 75-85% capital deployed. Every
position gets a real 10% trailing GTC stop. Cut losers at -7% manually.
Full rules in `memory/TRADING-STRATEGY.md`.
