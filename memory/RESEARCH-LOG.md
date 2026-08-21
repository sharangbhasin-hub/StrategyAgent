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

## 2026-08-17 — Pre-market Research (re-run, access restored)

Note: PERPLEXITY_API_KEY unset (intentional per deployment); used WebSearch
fallback for all queries below.

### Account
- Equity: $100,000
- Cash: $100,000
- Buying power: $400,000 (margin — sizing still governed by equity, not BP)
- Positions: none | Open orders: none
- Daytrade count: 0

### Market Context
- WTI: ~$82.77/bbl | Brent: ~$88-91/bbl (elevated, rising on Middle East
  escalation concerns — 30yr Treasury yields at highest since 2007 on
  inflation-from-oil worry)
- S&P 500 futures: +0.11% premarket, mixed (Dow soft, Nasdaq/S&P green).
  Polymarket ~62% odds of an up day.
- VIX: ~14.6, near 2026 low — cheap vol, but read as complacency risk into
  a seasonally rougher stretch
- Catalysts: Mideast conflict flare-up (oil/rates risk); AI trade momentum
  continuing (chipmakers rallying); retail earnings week (Walmart, Home
  Depot, Target reporting)
- Earnings before open: heavy retail earnings this week (Walmart/HD/Target);
  no single mega-cap confirmed before today's open in search results
- Econ calendar: PPI came in hot (headline +0.7% vs +0.4% est; YoY +1.6%,
  hottest since April) — inflation risk flag. No CPI today (next Sept 11).
  FOMC meeting upcoming (date not pinned down by search).
- Sector momentum YTD: S&P 500 +13% YTD. Energy leads (+22% YTD, XLE
  $61.91, +1.4% on the day, near 52-wk high). Healthcare also strong
  (flight-to-safety). Semis red-hot (SMH +56.7% YTD, +101% 1yr) but
  extended off Big Tech capex earnings — chase risk.

### Trade Ideas (watchlist only — not executed this session)
1. XLE (Energy) — catalyst: Brent/WTI bid on Mideast escalation, sector
   YTD leader, near 52-wk high $63.46. Entry ~$61.90-62.10 (current),
   stop ~$57.50 (-7%), target ~$68 (+10%, ~1.5:1 — needs a stronger case
   before sizing; momentum trade, not a value one).
2. SMH (Semis/AI) — catalyst: Big Tech capex/cloud beats (MSFT, AMZN)
   feeding chip demand, AI trade intact. Already +56.7% YTD and extended —
   flag as chase risk, not a fresh-breakout entry. Would want a pullback
   to ~$560-570 before considering, stop ~7% below entry, target 2:1.
3. XLV (Healthcare) — catalyst: flight-to-safety bid amid low-VIX
   complacency + Mideast/rate risk. Needs a specific name/entry level
   before actionable — flagging sector only pending follow-up research.

### Risk Factors
- VIX near 2026 lows = cheap protection but complacency; a shock (oil
  spike, hot inflation surprise) could snap volatility higher fast
- Hot PPI print raises inflation/rate risk — could pressure long-duration
  / growth names
- Geopolitical: Middle East escalation is the single biggest wildcard —
  headline risk cuts both ways (oil up further vs. de-escalation reversal)
- SMH/semis already extended (+56.7% YTD) — poor risk/reward for a
  fresh long here
- Day 1 of a live account: zero trade history to validate execution,
  fills, and stop-order mechanics before committing capital

### Decision
HOLD — Day 1, no positions yet. Three ideas flagged above are watchlist
only; none meet full entry-checklist rigor (confirmed catalyst + sized
stop + 2:1 min R:R) for immediate execution. Defer to market-open workflow
to confirm live quotes/levels before any entry. Patience > activity.

## 2026-08-18 — Pre-market Research
Note: PERPLEXITY_API_KEY unset (exit 3) — used native WebSearch fallback for all queries below.

### Account
- Equity: $100,000
- Cash: $100,000
- Buying power: $400,000 (margin — sizing still governed by equity, not BP)
- Positions: none | Open orders: none
- Daytrade count: 0

### Market Context
- WTI: ~$83-85/bbl | Brent: ~$91/bbl — both elevated, rising on Hormuz
  crisis: Trump rejected extending the 60-day Iran ceasefire that expired
  Monday, no broader peace deal reached.
- S&P 500 futures: -0.41%, Nasdaq -0.76%, Dow -0.16%, Russell -0.24% —
  broad-based red premarket. Polymarket only ~27% odds of an up day
  (bearish lean).
- VIX: 15.19, up 6.6% off Friday's 2026 low of 14.2 — vol waking up from
  complacency, consistent with the Iran escalation headline.
- Catalysts: Iran/Hormuz ceasefire collapse driving oil + rates risk;
  heavy retail earnings week (Walmart, Home Depot, Target, Lowe's); Fed
  July meeting minutes due later this week (calendar highlight); housing
  data also due this week.
- Earnings before open: retail earnings cluster this week (WMT/HD/TGT/LOW)
  — specific before-open names for today not clearly isolated in search
  results; no confirmed mega-cap print before today's open.
- Econ calendar: no CPI/PPI/jobs release pinned to today specifically;
  Fed minutes (Wed-ish) and housing data are this week's main events.
- Sector momentum YTD: Energy +32.1% (top), Technology +30.7%,
  Transportation +26.3%, Capital Goods +25.2%, Healthcare +12.55%
  (flight-to-safety bid). Laggards: Services -1.3%, Consumer Discretionary
  -4.3%.
- Held tickers: none — no positions to check news on.

### Trade Ideas (watchlist only)
1. XLE (Energy) — catalyst: Iran/Hormuz-driven oil spike, sector YTD
   leader (+32%). Entry ~current, stop ~7% below, target ~10-12% above
   (~1.5:1). Risk: chasing a geopolitical spike that could reverse fast
   on any de-escalation headline — timing risk is high right now, not a
   clean breakout.
2. XLV (Healthcare) — catalyst: flight-to-safety bid amid rising VIX +
   Iran risk-off tape, YTD +12.55% and building. Needs a specific
   name/entry level before actionable; sector-only flag pending
   follow-up at market open.
3. No tech/semis idea today — sector is cooling off its AI-capex run and
   futures are red across the board; poor risk/reward for a fresh long
   into a risk-off premarket.

### Risk Factors
- Iran/Hormuz ceasefire collapse is the dominant, two-sided headline risk
  today — oil spikes further on any new escalation, snaps back hard on
  any de-escalation signal. Bad day to open new energy longs into the
  spike.
- VIX jumping off 2026 lows (+6.6%) signals the complacency regime may be
  cracking — expect wider intraday swings.
- Broad futures red (S&P -0.41%, Nasdaq -0.76%) ahead of the open — no
  confirmed bullish catalyst to trade against the tape.
- Heavy retail earnings week (WMT/HD/TGT/LOW) — any miss/guide-down could
  hit Consumer Discretionary/Retail further; already YTD laggard.
- Fed minutes later this week — positioning risk into the release.

### Decision
HOLD — Day 2, still zero positions. Iran/Hormuz headline risk is live and
two-sided; VIX is waking up off 2026 lows; broad futures are red. Not a
day to chase XLE into an oil spike or open a fresh position without more
confirmation at the open. No entry today clears full checklist rigor
(confirmed catalyst + sized stop + 2:1 min R:R) given the volatility
backdrop. Defer to market-open workflow. Patience > activity.

## 2026-08-19 — Pre-market Research
Note: PERPLEXITY_API_KEY unset (exit 3) — used native WebSearch fallback for all queries below.

### Account
- Equity: $100,000
- Cash: $100,000
- Buying power: $400,000 (margin — sizing still governed by equity, not BP)
- Positions: none | Open orders: none
- Daytrade count: 0

### Market Context
- WTI: ~$84.9-85/bbl | Brent: ~$91.5/bbl — both elevated, still driven by
  Iran/Hormuz standoff; Trump firmly ruled out talks with Iran.
- S&P 500 futures: mixed/conflicting reads, net leaning down (~-0.18%),
  Nasdaq 100 futures -0.37%, Dow -0.11%, Russell -0.19%. Overnight driver:
  brutal Asia selloff (MSCI APAC -2%, South Korea -5.5%, Samsung/SK Hynix
  both -7%+) as the semiconductor trade unwinds hard.
- VIX: ~15.8-15.9, up ~4.3% on the day, off Monday's 2026 low (~14.2) —
  vol continuing to wake up, second straight up day for VIX.
- Catalysts: (1) Semiconductor selloff spreading from Asia — largest
  single-day chip-stock damage of the year, direct read-through risk to
  US semis (SMH) at the open; (2) 10Y Treasury yield ~4.73%, 30Y ~5.32%
  (highest since 2007) — rate pressure weighing on risk assets broadly;
  (3) Iran/Hormuz tension still live and two-sided; (4) heavy retail
  earnings dump today.
- Earnings before open: Analog Devices (ADI), TJX, Lowe's (LOW), Target
  (TGT), Estee Lauder (EL) — 38 names reporting total today, retail-heavy.
- Econ calendar: FOMC July minutes released today (afternoon) — main
  scheduled event; no CPI/PPI/NFP pinned to today specifically.
- Sector momentum YTD: Energy still top (~+22-32% depending on source),
  Healthcare a surprising #2 as flight-to-safety bid persists into rising
  VIX. Tech/semis momentum is now actively breaking down overnight, not
  just "cooling" — SMH-linked names at real risk of a gap-down open.
- Held tickers: none — no positions to check news on.

### Trade Ideas (watchlist only)
1. XLV (Healthcare) — catalyst: continued flight-to-safety bid, YTD #2
   sector, benefiting from both risk-off tape and rising-yield rotation
   out of long-duration growth. Needs a specific name/level check at open
   before actionable; sector-only flag still pending follow-up.
2. XLE (Energy) — catalyst: Iran/Hormuz-driven oil strength persists.
   Still the top YTD sector, but timing risk remains high — two-sided
   headline (any de-escalation snaps oil back). No fresh entry into a
   possible spike top.
3. No semis/tech idea — actively avoid. Overnight Asia chip selloff
   (Samsung/SK Hynix -7%+) is a real negative catalyst, not just froth;
   SMH and mega-cap AI names are the highest-risk long today, not a dip
   to buy without confirmation the damage doesn't spread to the US open.

### Risk Factors
- Semiconductor unwind spreading from Asia is the dominant new risk today
  — could cascade into US mega-cap tech/AI names at the open; day to
  watch, not trade, in that space.
- 10Y yield at 4.73%, 30Y at 5.32% (highest since 2007) — a real
  macro headwind for equity valuations broadly, not just a headline blip.
- Iran/Hormuz standoff still live and two-sided (oil spikes on
  escalation, snaps back on any de-escalation signal).
- Heavy retail earnings today (TJX/LOW/TGT/EL) — any miss/guide-down
  compounds pressure on an already-lagging Consumer Discretionary sector.
- FOMC minutes this afternoon — positioning risk into the release.

### Decision
HOLD — Day 3, still zero positions. New negative catalyst overnight
(Asia semis selloff, multi-decade-high long yields) argues for more
caution, not less. No idea today clears full entry-checklist rigor
(confirmed catalyst + sized stop + 2:1 min R:R). Defer to market-open
workflow to see how US semis/tech open and whether yields keep climbing.

## 2026-08-20 — Pre-market Research
Note: PERPLEXITY_API_KEY unset (exit 3) — used native WebSearch fallback for all queries below.

### Account
- Equity: $100,000
- Cash: $100,000
- Buying power: $400,000 (margin — sizing still governed by equity, not BP)
- Positions: none | Open orders: none
- Daytrade count: 0

### Market Context
- WTI: ~$84.25-85.34/bbl | Brent: ~$93.01/bbl (+1.52%) — still Iran/Hormuz
  driven; US reportedly intensifying economic pressure on Iran.
- S&P 500 futures: +0.16%, Nasdaq 100 +0.42%, Dow +0.06%, Russell 2000
  +0.24% — modest green tape, driven by a Treasury buyback announcement
  (doubling debt repurchases to $4B+) pulling yields lower.
- VIX: ~15.8, up off Friday's 2026 low of 14.2 but not elevated — vol
  still calm despite the geopolitical/inflation crosscurrents.
- Catalysts: (1) Treasury buyback doubling — yields down, broad tailwind;
  (2) Moderna phase 3 win on personalized melanoma cancer vaccine — best
  single-day stock move in company history, biotech/healthcare bid;
  (3) hot PPI print (headline +0.7% vs +0.4% consensus, YoY +1.6%) —
  inflation running hotter than expected days before next week's FOMC;
  (4) retail sales +0.6% vs +0.4% expected — resilient consumer;
  (5) Bitcoin up on White House crypto-bill push.
- Earnings before open: WMT, BABA, DE, AAP, NTES, FUTU, ATHM, DQ, SCSC,
  LYTS. After close: ROST, FLO, OSIS.
- Econ calendar: PPI + Retail Sales released this morning (both hotter
  than expected). No CPI/jobs data today. FOMC meeting next week.
- Sector momentum: Energy leading WTD (+6%), Healthcare/Financials also
  up >1% WTD. YTD leaders: Materials (+22%), Consumer Staples,
  Industrials, Energy. Tech/Communications/Discretionary/Financials in
  lagging quadrant; Real Estate/Utilities improving.
- Held tickers: none — no positions to check news on.

### Trade Ideas (watchlist only)
1. XLE (Energy) — catalyst: oil at multi-week highs on Iran/Hormuz
   escalation, sector both YTD (#4) and WTD (#1) momentum leader. Ref
   price ~$63.60. Illustrative entry ~$63.50-64.00, stop ~7% below
   (~$59.20, respects 3%+ distance rule), target ~$68.50-69.00 (~2:1
   R:R). Risk: same two-sided geopolitical headline flagged prior two
   days — any de-escalation snaps oil back fast. Still no confirmed
   breakout level at today's open.
2. XLV (Healthcare) — catalyst: Moderna trial win. Ref price already
   gapped from $169.73 to $175.25 (+3.25%) yesterday on the news — sector
   is extended, not a fresh entry. Watching for a pullback/consolidation
   before treating as actionable; chasing an already-extended gap fails
   the entry-checklist R:R test.
3. XLB (Materials) — catalyst: YTD momentum leader (+22%), classic
   inflation-hedge sector and today's hot PPI print supports the rotation
   thesis. Ref price ~$52.50-52.90. Illustrative entry ~$52.50-53.00,
   stop ~7% below (~$49.00), target ~$58.00 (~2:1 R:R). Needs open
   confirmation — no breakout trigger yet, still watchlist only.

### Risk Factors
- Iran/Hormuz standoff still live and two-sided — oil (and XLE) can
  reverse hard on any de-escalation headline, same risk flagged 2 days
  running.
- Inflation surprising hot (PPI, retail sales) days before FOMC — could
  pressure the "yields down on Treasury buyback" tailwind if the market
  reprices rate-cut odds down.
- XLV move is already largely priced in on a single-stock (Moderna)
  catalyst — sector-wide follow-through at the open is unconfirmed.
- Heavy earnings day (WMT, BABA, DE, ROST after close) — index-level
  volatility risk around large-cap prints.
- VIX still low (~15.8) despite live geopolitical/inflation risk —
  complacency could unwind quickly on a surprise.

### Decision
HOLD — Day 4, still zero positions, zero trades used of weekly cap. Three
watchlist ideas (XLE, XLV, XLB) all lack a confirmed open-level trigger:
XLE carries repeat two-sided geopolitical risk, XLV is already extended
on a single-stock catalyst, XLB has no breakout confirmation yet. None
clears full entry-checklist rigor pre-open. Defer to market-open workflow
to check actual opening prices/volume before any entry. Patience >
activity.
Patience > activity.

## 2026-08-21 — Pre-market Research
Note: PERPLEXITY_API_KEY unset (exit 3) — used native WebSearch fallback for all queries below.

### Account
- Equity: $100,000
- Cash: $100,000
- Buying power: $400,000 (margin — sizing still governed by equity, not BP)
- Positions: none | Open orders: none
- Daytrade count: 0

### Market Context
- WTI: ~$86.16-86.18/bbl | Brent: ~$93.01-93.24/bbl — modest pullback off
  Thursday's Iran/Hormuz-driven spike, essentially flat overnight.
- S&P 500 futures: +0.08%, Nasdaq 100 +0.20%, Dow +0.05%, Russell 2000
  +0.33% — light green tape, 65% odds of a higher open per prediction
  markets. Bessent touting "toughest sanctions" for Iran + a fiscal/debt
  buyback plan; 30Y yield up to 5.25% on the fiscal chatter.
- VIX: ~15.82-15.87 — near 2026 lows, calm despite live geopolitical risk.
- Notable cross-current: gold +0.5% to ~$4,540 (+3.6% WTD) — safe-haven
  bid running alongside the equity futures bounce, worth watching as a
  risk-off tell if it keeps building.
- Earnings before open: none of significance today (light Friday).
  Next earnings wave starts Mon 8/25 (BMO, DKS, INTU, ZM) and Tue 8/26
  (NVDA, CRM, WSM, CRWD, SNPS, A, HPQ, OKTA).
- Econ calendar: no CPI/PPI/jobs data today — light calendar. FOMC next
  week; yesterday's hot PPI/retail-sales prints still the overhang into it.
- Sector momentum: Energy (+22% YTD), Consumer Staples (+16%), Materials
  (+15.7%), Industrials (+11.9%) in the leading quadrant. Tech (-3.8%),
  Consumer Discretionary (-4.6%), Financials (-5.7%), Communications
  lagging. Deere raised FY net-income guidance — fresh positive catalyst
  for Industrials specifically.
- Held tickers: none — no positions to check news on.

### Trade Ideas (watchlist only)
1. XLI (Industrials) — catalyst: Deere guidance raise + sector already
   in the leading momentum quadrant (+11.9% YTD). Needs today's open
   confirmation of follow-through (volume, breakout level) before sizing
   an entry; illustrative stop ~7-8% below entry, target sized for 2:1+.
   New idea vs. prior days — not yet confirmed.
2. XLB (Materials) — same repeat catalyst as prior 2 sessions (YTD
   momentum leader, inflation-hedge rotation on hot PPI). Still no
   observed breakout trigger at the open in three straight sessions —
   third day flagging this one without a fill; treat as fading
   conviction, not a stronger signal.
3. XLE (Energy) — oil cooling off slightly overnight after the
   Iran/Hormuz spike; sector momentum still #1 YTD but the two-sided
   geopolitical risk (flagged 3 days running) is unchanged. Lower
   conviction today given the pullback in oil itself.

### Risk Factors
- Gold's safe-haven rally (+3.6% WTD) running alongside a "risk-on"
  futures bounce is a mixed signal — could presage a risk-off turn if
  equities fail to hold the modest premarket gain.
- 30Y yield at 5.25%/multi-decade highs on fiscal/buyback chatter — same
  valuation headwind flagged the last two days, still unresolved.
- Iran/Hormuz geopolitical risk remains two-sided and live for the third
  straight session — XLE thesis unchanged and unconfirmed.
- Light Friday calendar (no data, no major earnings) — lower conviction
  for fresh catalysts; typical lighter Friday volume can produce false
  breakout signals.
- XLB has now been flagged 3 sessions running with no entry trigger —
  worth deprioritizing vs. chasing it a 4th day.

### Decision
HOLD — Day 5, still zero positions, zero trades used of weekly cap.
Light Friday calendar (no CPI/PPI/jobs, no major earnings) and no
confirmed breakout on any watchlist name (XLI new but unconfirmed, XLB
stale after 3 flags, XLE lower-conviction on cooling oil). Defer to
market-open workflow to check actual opening prices/volume. Patience >
activity.
