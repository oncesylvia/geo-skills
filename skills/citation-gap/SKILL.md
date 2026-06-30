---
name: citation-gap
description: Reverse-engineer why an AI engine cites a competitor (or a Reddit thread) instead of you, then produce a prioritized catch-up plan. Use when someone says "why does ChatGPT/Perplexity recommend my competitor", "AI cites X not me", "citation gap analysis", or wants to close the specific gap on a query they care about. Honest — match or beat the cited source on real merit, never copy or spam.
---

# Citation gap analysis

For a query you care about, an engine is citing *someone else*. This skill finds
out **why** — by examining the actually-cited source against the three gates —
and gives you a concrete, honest catch-up plan. The goal is to deserve the
citation more than they do, not to copy or game them.

Read `shared/references/ai-engines.md`, `shared/references/geo-principles.md`
first.

## Inputs

- The **target question** where you're losing.
- The engine(s) doing the citing.
- Who/what gets cited today (run the query — often a competitor page, a Reddit
  thread, a G2 listing, or a "best X" roundup). Pairs with `geo-measure`.

## Analyze the cited source against the three gates

Fetch and inspect what the engine actually cites, and compare to your page:

### Reach
- Is the cited source easily crawlable while **your** page is blocked (CDN 403,
  JS-only)? If your page can't be fetched, that alone explains it. →
  `ai-crawler-access`.

### Parse / structure
- Does the cited page **answer the question directly and up front**, with clear
  headings, a table, or an FAQ — while yours buries it? Note the specific
  structural differences. → `answer-ready-content`.
- Does it have schema, a clear entity page, server-rendered text that you lack?

### Trust / off-site
- Is it cited because it's a **third-party the engine trusts** (Reddit, a
  roundup, G2) rather than a vendor site at all? Then the gap is **off-site
  presence**, not your page. → `earn-mentions`.
- Is the source more specific, more sourced, more recent than you?

## Produce the catch-up plan

A prioritized, honest list — what *they* pass that *you* fail, cheapest-first:

| Gap | They have | You're missing | Fix (skill) | Effort |
|---|---|---|---|---|
| Reach | crawlable | CDN blocks GPTBot | unblock CDN | low |
| Structure | answer-first + table | buried answer | rewrite | low |
| Off-site | cited Reddit thread | no presence there | earn it honestly | high |

Then: **the one move most likely to flip this query**, and a realistic note on
which gaps are quick (reach, structure) vs. slow (off-site, entity).

## The honest line

- Match or beat them on **real merit** — clearer answer, better data, genuine
  community presence. 
- ❌ Don't scrape/duplicate their content, don't spam the same Reddit thread,
  don't fabricate to look more authoritative. Those backfire and violate the
  toolkit's principles.

## Output

- Why the current source wins, gate by gate (with the specifics you observed).
- The prioritized catch-up table.
- The single highest-leverage move, and honest effort/uncertainty notes.

## Bilingual / 出海 (中文)

国内同理:对手可能赢在**知乎高赞/百度百科/榜单**而非自家站——那差距在站外
(→ `earn-mentions` 中文部分),不是改你网页能解决的。分引擎、分语言各看一遍。

## Refuse / push back when

- Asked to copy a competitor's content or spam the cited source → refuse; win on
  real merit. Plagiarism and spam get penalized and aren't in this toolkit.
