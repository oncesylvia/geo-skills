---
name: geo-scorecard
description: Turn a GEO audit into a scored, visual scorecard — a 0-100 GEO score across four equal-weight dimensions (AI visibility, infrastructure, competitive, reputation) plus a shareable scorecard image. Use when someone asks "give me a GEO score", "score my AI visibility", "AIVO score", "a scorecard for my brand's GEO", or wants a headline number + visual report instead of a long audit. Every dimension is anchored to real measured/searched signals — never an AI-simulated "mention rate".
---

# GEO scorecard (scored, visual, honest)

Turns the findings from `geo-audit` (and the other geo-skills) into a single
**0-100 GEO score + a scorecard image** — the headline deliverable clients and
readers want. The difference from flashy "diagnosis" tools: **every dimension is
anchored to something actually measured or searched, and estimates are labeled.**
No fabricated "mention rate %".

Read `shared/references/geo-principles.md` first. See
`references/aivo-scoring.md` for the full rubric and `references/scorecard-template.svg`
for the visual.

## The four dimensions (25% each)

| Dimension | Scored from — REAL signal |
|---|---|
| **AI visibility** | Observed presence in AI answers for the target prompts (query the engines / check the sources they cite + AI-referral traffic). Sampled → labeled sampled. |
| **Infrastructure** | Directly measured: bot access (curl → 200 vs 403), server-rendered HTML, llms.txt, sitemap, schema. Fully objective. |
| **Competitive** | Who AI cites today vs you; real differentiation + current awareness. Evidence-based. |
| **Reputation** | Real third-party mentions/reviews (Reddit/知乎/V2EX/review sites). No presence = thin (a risk), not a default 70. |

## How to run it

1. **Gather real findings** — run `geo-audit` (reach/parse/trust) + a
   `citation-gap` / `prompt-coverage` sample + a reputation search. Everything you
   score must come from a real check or search.
2. **Score each dimension** against the anchoring bands in
   `references/aivo-scoring.md` (measured finding → score range).
3. **Compute overall** = average of the four. ≥90 excellent / ≥75 good /
   ≥60 fair / <60 poor. ±5 tuning.
4. **Label estimates.** Infrastructure is fully measured; AI-visibility and
   reputation are *observed/sampled* — mark small samples and anything you could
   not measure directly (e.g. a China engine you can't query) as "needs manual
   check". Never invent a number.
5. **Render the scorecard** — fill `references/scorecard-template.svg` with the
   overall score + a bar per dimension (green high / amber mid / red low), export
   to PNG. Keep the "real data · estimates labeled" line — that's the trust mark.

## Output

- The overall GEO score + grade, and the four dimension scores with the real
  evidence behind each.
- The scorecard image (1200×630).
- The one-line verdict (e.g. "technically excellent, commercially invisible") and
  the single highest-leverage fix.
- An honesty note: the score is a prioritization heuristic, not a guarantee;
  which parts are measured vs sampled.

## Bilingual / 出海 (中文)

四维等权打分对中文/国内同样适用。**基建**直接实测(curl/查证);**AI 可见性、舆情**
真去搜、样本小就标"抽样";查不到的国内引擎标"需人工核",**绝不用 AI 模拟的"提及率%"**。
"别人给你猜的分,你给的是实测的分"——这就是可信度。

## Refuse / push back when
- Asked to simulate a "mention rate" or invent per-engine numbers to fill the
  score → refuse; score only what's measured/observed, label the rest.
- Asked to inflate the score for a client/self → the honesty is the value; report
  the real number, good or bad.
