---
name: ai-brand-monitor
description: Monitor and correct what AI says about your brand — find where ChatGPT/Perplexity/Claude/Gemini state wrong pricing, outdated features, confuse you with a competitor, or surface stale negatives, then fix the upstream sources so AI corrects itself. Use when someone says "AI says the wrong thing about my company", "ChatGPT has outdated info on us", "AI confuses us with a competitor", "fix my AI reputation", or wants to know what AI tells people about their brand. The defensive half of GEO.
---

# AI brand monitor (the defensive half)

Getting cited is offense. This is **defense**: businesses are damaged less by AI
ignoring them than by AI **describing them wrongly** — quoting an old price,
missing a flagship feature, confusing them with a competitor, or resurfacing a
years-old incident. This skill finds what AI says about your brand and fixes the
**upstream sources** so the answer corrects itself.

Read `shared/references/geo-principles.md`, `shared/references/ai-engines.md`,
and `shared/references/geo-governance.md` first. The honest line: you correct
**inaccuracies**; you do not manipulate engines to bury **true** criticism — fix
the underlying reality and the real sources instead.

## Step 1 — Capture what AI currently says

Run the brand-defining prompts across each engine you care about and record the
verbatim answer + the sources it used:

- `what is <brand>` / `who is <brand>`
- `<brand> pricing` / `how much does <brand> cost`
- `<brand> features` / `does <brand> do <key thing>`
- `is <brand> legit / safe / trustworthy`
- `<brand> reviews` / `<brand> complaints`
- `<brand> vs <competitor>` / `<brand> alternatives`
- `who owns <brand>` / `where is <brand> based`

Re-run periodically (answers drift). Note the **source** behind each claim — that
is what you'll fix.

## Step 2 — Classify the problems

| Type | Example | Usually caused by |
|---|---|---|
| **Outdated** | old price, deprecated feature | stale page, old blog/review, cached crawl |
| **Wrong/hallucinated** | a feature you don't have | thin info → model guesses |
| **Confusion** | mixed up with a same-name company | weak entity signals |
| **Stale negative** | a resolved 2021 incident | an old article ranking high |
| **Missing** | "I don't have info on <brand>" | no reachable, clear source |

## Step 3 — Fix the upstream source (this is the leverage)

AI repeats its sources. Correct the source and the answer follows:

- **Outdated/wrong** → update your own canonical page (pricing, features),
  make it answer-first and crawlable, refresh the `dateModified`. Update stale
  third-party listings (G2, Crunchbase, directories) you control.
- **Confusion** → strengthen entity signals: a clear "what is <brand>" page,
  `Organization` schema with `sameAs`, a **Wikidata** item disambiguating you
  from the same-name entity. (→ `answer-ready-content`, `earn-mentions`.)
- **Stale negative** → publish current, factual information that out-ranks and
  contextualizes it; correct the record honestly. Don't try to scrub the truth —
  address it.
- **Missing** → you have a reach/parse problem → `ai-crawler-access` +
  `answer-ready-content`.
- **Engine feedback** → most engines have a "report/feedback" path on answers;
  use it for clear factual errors. For defamatory/harmful output, see the
  escalation note in `geo-governance.md`.

## Step 4 — Verify the correction

Re-run the prompts over the following weeks (engines cache; corrections lag).
Track in the `geo-measure` sheet with a "claim accuracy" column. Confirm the
corrected source is crawlable and answer-first, or the fix won't propagate.

## Output

- A table: prompt → what AI said → problem type → source behind it → the fix.
- The highest-risk inaccuracy to fix first (wrong price / competitor confusion /
  harmful claim).
- An honesty note: we correct false/outdated claims and strengthen real signals;
  we do not suppress true negative information by manipulation.

## Bilingual / 出海 (中文)

国内引擎(豆包/文心/元宝)对品牌的表述同样会错/会过时,且常引**百度百科/知乎**。
修法一样:改上游真实来源(自家页 + 百度百科词条 + 知乎高赞),别用水军压评。
出海双语:每种语言各跑一遍品牌提示词,海内外结论不同。

## Refuse / push back when

- Asked to bury **true** negative info, fake corrections, or astroturf positive
  narratives → refuse; fix the reality and the real sources. Manipulation is
  detectable and against the toolkit's principles.
