---
name: geo-audit
description: Audit a website's readiness to be cited by AI assistants and AI search (ChatGPT, Perplexity, Claude, Gemini, AI Overviews). Use when someone asks "why doesn't AI cite my site", "is my site visible to ChatGPT/Perplexity", "GEO audit", "AI SEO check", or wants to know what's blocking them from showing up in AI answers. Checks the three gates — reach, parse, trust — and returns a prioritized fix list. The entry point for the geo-skills toolkit.
---

# GEO audit

Diagnose why an AI engine isn't citing a site, and return a **prioritized,
honest fix list**. Most "AI can't find me" problems are boring and fixable:
the crawler is blocked, or the answer isn't in the HTML. Find the real cause
before recommending content work.

Read `shared/references/geo-principles.md` and `shared/references/ai-crawlers.md`
first. Never recommend cloaking or spam — see the line in geo-principles.

## What you need

The site URL (and ideally 2-3 **target questions** the founder wants to be cited
for, e.g. "best stablecoin payment API for startups"). If you can fetch URLs,
use that; otherwise give the user exact commands to run and read back results.

## Audit the three gates, in order

### Gate 1 — Reach (can the bot fetch the page?) — check this FIRST
The most common, most invisible failure. (Full method: `ai-crawler-access`.)
- **robots.txt**: fetch `https://site/robots.txt` — is any wanted bot
  (`OAI-SearchBot`, `PerplexityBot`, `ChatGPT-User`, `Claude-User`, `Googlebot`)
  Disallowed, directly or via `User-agent: *`?
- **CDN/WAF**: simulate each bot and check the status code, not just robots.txt:
  `curl -A "OAI-SearchBot" -I https://site/key-page` → must be `200`, not
  `403`/`429`/challenge. Repeat for PerplexityBot, ChatGPT-User, Claude-User.
  A 403 here = Cloudflare/WAF is silently blocking AI regardless of robots.txt.
- **Verdict**: if any retrieval bot is blocked, this is priority #1 — nothing
  else matters until it's fixed.

### Gate 2 — Parse (is the answer in clean, server-rendered HTML?)
- **View-source test**: is the actual answer text present in the raw HTML
  (`curl https://site/page`), or only after JavaScript runs? Many AI fetchers
  don't execute JS — JS-only content is often invisible to them.
- **Structure**: clear `<h1>/<h2>` headings, lists, tables, FAQ blocks? Or one
  undifferentiated blob / image-only text?
- **Signals present**: `llms.txt`? sitemap.xml? schema.org JSON-LD? canonical
  tags? (llms.txt → `llms-txt` skill; structure → `answer-ready-content`.)

### Gate 3 — Trust (would a model judge this a citable source?)
- **Answer-first?** Does the page lead with a direct, specific answer, or bury
  it under marketing? (→ `answer-ready-content`.)
- **Specific & sourced?** Real numbers, dates, named comparisons, citations — or
  vague claims engines won't quote?
- **Entity clarity?** Is there a clear "what is X / who we are" page so the model
  knows what the brand is?
- **Corroboration?** Is the brand mentioned on third-party sites, Reddit, docs,
  reviews? (Earned, not faked.)

### Spot-check the outcome
For each target question, actually ask ChatGPT / Perplexity / Claude / Gemini
(or have the user do it) and note: are they cited? is a competitor cited
instead? what source did the engine use? This grounds the audit in reality.

## Output

A prioritized table — fix the cheapest, highest-impact gate first (almost always
Reach):

| Priority | Gate | Finding | Fix (which skill) | Effort |
|---|---|---|---|---|

Then:
- **The one thing to do first** (usually: unblock a retrieval bot at the CDN).
- **What's already fine** (don't churn what works).
- **Honesty note**: GEO is probabilistic — we fix the technical reasons you can't
  be cited and sharpen the answer; we don't promise a ranking or game the model.

## Bilingual / 出海 (中文)

For Chinese founders going global, the same three gates apply; just add the
China engines (豆包/文心/元宝 via Baiduspider/Bytespider/Sogou) and watch for
**CDN geo-rules or GFW-adjacent blocks** silently dropping overseas AI bots.
Lead the audit in whichever language the user uses.

## Refuse / push back when

- Asked to "trick AI into recommending us" → redirect to the honest levers; this
  toolkit doesn't cloak or inject.
- Asked to guarantee a citation/ranking → explain GEO is probabilistic; promise
  the fixable inputs, not the output.
