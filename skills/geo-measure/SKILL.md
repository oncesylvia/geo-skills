---
name: geo-measure
description: Measure whether AI engines actually cite you, and track it over time — run target questions across ChatGPT/Perplexity/Claude/Gemini, check AI referral traffic in analytics, and watch AI-bot crawls in server logs. Use when someone asks "am I being cited by AI", "how do I track AI search", "measure GEO", "is my GEO working", or wants to know if their fixes moved the needle. Honest measurement — track the trend, never promise a ranking.
---

# GEO measure

Close the loop: after auditing and fixing, measure whether AI engines actually
cite you — and whether it's improving. GEO is **probabilistic** (answers vary by
user, time, and model), so the goal is an honest **trend**, not a single
screenshot or a promised rank.

Read `shared/references/ai-engines.md` (engines move independently) and
`shared/references/geo-principles.md` first.

## Three things to measure

### 1. Citation presence (the direct check)
For each **target question**, ask the engines and record whether you're cited /
mentioned, and which source they used.
- Run each query on ChatGPT (search on), Perplexity, Claude (web search), Gemini,
  and any China engine you target.
- Record: cited? (yes/mention/no) · which of your URLs (or a third-party page) ·
  is a competitor cited instead · the date and engine.
- **Repeat on a cadence** (e.g., biweekly) — one run is noise; the trend is signal.
- Vary phrasings of the same intent; engines are sensitive to wording.

### 2. AI referral traffic (are AI answers sending visits?)
In your analytics, segment referrers from AI surfaces:
- `chatgpt.com` / `chat.openai.com`, `perplexity.ai`, `gemini.google.com`,
  `claude.ai`, `copilot.microsoft.com`, and China engines.
- Rising AI-referral sessions = you're being surfaced and clicked. Track it as
  its own channel over time.

### 3. AI-bot crawl activity (are they even fetching you?)
In server/CDN logs, count hits from `OAI-SearchBot`, `PerplexityBot`,
`ChatGPT-User`, `Claude-User`, `Googlebot`, etc.
- No crawl hits = a reach problem → back to `ai-crawler-access`.
- Crawls but no citations = a parse/trust/off-site problem → `answer-ready-content`
  / `earn-mentions`.

## How to run it

1. Lock a **fixed set of target questions** (so runs are comparable).
2. Build a tracking sheet (see `references/tracking-template.md`).
3. Baseline now (before/after a fix shows impact).
4. Re-run on a cadence; log results; watch the trend per engine.
5. Diagnose by combining the three signals (crawl? referral? citation?) to know
   which gate to work next.

## Output

- A populated tracking sheet (questions × engines × dates).
- A read on the trend: improving / flat / which engine is lagging.
- A diagnosis pointing to the next skill (reach / parse / trust / off-site).
- Honesty note: report what's measured; never invent citation numbers or promise
  a ranking. If results are flat, say so and investigate.

## Bilingual / 出海 (中文)

国内引擎(豆包/文心/元宝/Kimi/通义)各自单独测,别和海外混为一谈。referral 来源
对应各自域名;日志里看 `Bytespider`/`Baiduspider`/`Sogou` 的抓取。趋势分引擎看。

## Refuse / push back when

- Asked to report a citation "ranking" or a guaranteed number → GEO is
  probabilistic; report observed presence and trend, not a fabricated rank.
- Asked to fabricate before/after numbers to look good → never. Measure honestly.
