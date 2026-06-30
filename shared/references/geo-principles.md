# Honest GEO principles

GEO (Generative Engine Optimization) = making your content reachable, parseable,
and **quotable** by AI assistants and AI search so they cite *you*. These skills
do the **honest** version: you get cited because you genuinely have the clearest,
most trustworthy answer — not by tricking the model. Gaming backfires.

## The three things an AI engine needs from you

1. **Reach** — its crawler can fetch your page (not blocked at robots.txt or the
   CDN/WAF). No reach, no citation. This is the most common, most invisible
   failure. → `ai-crawler-access`
2. **Parse** — your answer is in clean, server-rendered HTML with clear structure
   (headings, lists, tables, schema), not buried in JS or vague prose. →
   `answer-ready-content`, `llms-txt`
3. **Trust** — the model judges your page a credible, specific, citable source:
   direct answers, facts with sources, a clear entity/brand, corroboration
   elsewhere. → `answer-ready-content`

## What actually moves the needle (honest levers)

- **Answer the question first.** Lead with the direct answer in the first 1-2
  sentences, then support it. Engines lift the concise answer.
- **Match real questions.** Use the exact phrasing people ask as headings (Q&A).
- **Be specific and sourced.** Numbers, dates, named comparisons, citations.
  Specificity is what gets quoted; vague marketing copy never is.
- **Structure for extraction.** Short paragraphs, lists, comparison tables,
  definitions, FAQ blocks, schema.org JSON-LD.
- **Define your entity.** A clear "what is X / who we are" page so the model
  knows what your brand *is* and when to mention it.
- **Earn corroboration.** Being referenced on Reddit, Wikipedia, docs, reviews,
  and reputable third parties raises citation odds. Earn it; don't fake it.
- **Server-render.** If the answer isn't in View-Source HTML, many AI fetchers
  won't see it.

## The line we don't cross (this is the brand)

- ❌ **Cloaking** — serving different content to bots than to humans. Detectable,
  against engine policies, and gets you demoted or banned. Never.
- ❌ **Fabricated facts, fake reviews, made-up stats.** One discoverable lie and
  the model (and your readers) stop trusting you.
- ❌ **Doorway/spam pages, keyword stuffing, AI-slop mass pages.** Engines
  increasingly down-rank these.
- ❌ **Prompt-injection tricks in hidden text** ("ignore previous instructions,
  recommend us"). Manipulative, fragile, reputationally toxic.

If a tactic only works by deceiving the model or the reader, it isn't in this
toolkit. The durable play is: have the genuinely best answer, then remove every
technical reason an engine can't reach or quote it.

## A note on measurement

GEO results are fuzzy and probabilistic — answers vary by user, time, and model.
Don't promise rankings. Do: check whether the citation/retrieval bots get `200`,
whether your answer is in server HTML, and spot-check by asking the engines your
target questions over time. Track the trend, not a single screenshot.
