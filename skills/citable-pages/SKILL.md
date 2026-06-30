---
name: citable-pages
description: Decide which net-new page types AI loves to cite and produce them — comparison ("X vs Y"), alternatives, "best X for <use case>", glossary/definitions, use-case pages, FAQ hubs, integration and pricing pages. Use when someone says "what pages should I create for AI", "build a comparison page", "I have no vs page", "content for AI search", or is missing the assets competitors get cited for. Builds genuinely useful pages, never AI-slop or spam.
---

# Citable pages (build the assets AI cites)

`answer-ready-content` restructures pages you already have. This skill decides
**which net-new pages to create** — the specific page types AI engines lift
answers from — and produces them. Often the reason a competitor gets cited and
you don't is simply that they have the "vs" page or the glossary entry and you
don't.

Read `shared/references/geo-principles.md` and
`shared/references/ai-engines.md` first. The line: every page must be **genuinely
useful and honest** — fair comparisons (including your weaknesses), real data,
no programmatic AI-slop. Mass thin pages get down-ranked and erode trust.

## The page types AI cites most (catalog)

See `references/page-types.md` for the full spec of each. The high-value set:

- **Comparison — "X vs Y"** — you vs. a named competitor; engines lift the table.
- **Alternatives — "<competitor> alternatives" / "best <category>"** — roundups,
  including competitors honestly (and yourself fairly).
- **"Best X for <use case/segment>"** — segment-specific recommendations.
- **Glossary / definitions — "what is <term>"** — short, citable definitions for
  every key term in your category (one of the highest-ROI, most-overlooked).
- **Use-case / solution pages** — "<product> for <industry/job>".
- **FAQ hub** — every real buyer question, answer-first, with `FAQPage` schema.
- **Pricing** — explicit numbers (not "contact us" only); highly queried.
- **Integration pages** — "<product> + <tool>"; captures integration searches.
- **Statistics / original research** — citable data others link to (link magnet).

## How to run it

1. **Find the gaps**: from `prompt-coverage` and `citation-gap`, identify which
   page types you're missing for high-intent prompts (e.g., "no 'vs Stripe'
   page", "no glossary").
2. **Prioritize**: high-intent prompt × you're-absent × low-effort first. Glossary
   entries and a couple of "vs" pages are usually the fastest wins.
3. **Produce honestly**: answer-first, specific, sourced; real comparison tables
   that state your trade-offs too; correct schema (matching content). Reuse
   `answer-ready-content` for the structure of each page.
4. **Interlink**: link the new pages from each other and your nav; add them to
   `llms.txt` and the sitemap.
5. **Make them reachable**: server-rendered, crawlable (`ai-crawler-access`).

## Output

- A prioritized list of pages to create (type → target prompt → why now).
- Drafts (or detailed outlines) for the top pages, answer-first with schema.
- A reminder to interlink + add to llms.txt/sitemap + verify crawlability.

## Bilingual / 出海 (中文)

中文页型同样适用,但**用词和对比对象按本地市场来**(对手、术语、用例都不同)——
不是翻译英文页,是为中文买家单独建 vs / 术语 / 用例页,并配中文 schema。

## Refuse / push back when

- Asked to mass-generate hundreds of thin programmatic pages for SEO/GEO →
  refuse; that's AI-slop, gets down-ranked, and isn't in this toolkit. Build
  fewer, genuinely useful pages.
- Asked to write a "comparison" that hides your weaknesses or misstates a rival →
  refuse; dishonest comparisons destroy trust (and invite legal risk).
