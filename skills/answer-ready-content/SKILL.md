---
name: answer-ready-content
description: Restructure web content so AI engines extract and cite it — answer-first writing, question-shaped headings, comparison tables, definitions, FAQ blocks, and schema.org JSON-LD. Use when someone asks "why does AI cite my competitor not me", "make my content AI-friendly", "how to get quoted by ChatGPT/Perplexity", "add schema for AI", or wants their pages to become the source an AI lifts its answer from. Honest only — clarity and structure, never cloaking.
---

# Answer-ready content

Even with crawlers unblocked, AI engines cite the page that **most clearly and
credibly answers the question**. This skill restructures content so an engine
can lift your answer — by making it direct, specific, structured, and
machine-parseable. The honest lever: be the best answer, then remove every
reason an engine can't quote it.

Read `shared/references/geo-principles.md` first. No cloaking, no fabricated
facts, no hidden prompt-injection — see the line there.

## The moves that get content quoted

### 1. Answer first
Lead with the direct answer in the **first 1-2 sentences**, then support it.
Engines lift the concise, up-front answer; they skip pages that bury it under a
marketing preamble.
> Q: "What does Acme Pay charge?" → first line: "Acme Pay charges 0.5% per
> transaction with no monthly fee." Then the detail.

### 2. Question-shaped headings
Use the **exact phrasing people ask** as `<h2>`/`<h3>`. Match real queries
("How much does X cost?", "X vs Y", "Is X safe?"). Each section answers one
question, self-contained.

### 3. Be specific and sourced
Numbers, dates, named comparisons, and citations are what get quoted; vague
adjectives never are. "Cuts onboarding from 3 days to 4 minutes" beats
"dramatically faster." Cite sources for claims — it raises trust and quotability.

### 4. Structure for extraction
- Short paragraphs (2-4 sentences).
- **Comparison tables** for "X vs Y" — engines love liftable tables.
- **Definitions** ("X is …") and **FAQ blocks** (question + tight answer).
- Lists for steps and options.
- One idea per block; no walls of text.

### 5. Define your entity
Have a clear **"What is X / who we are"** page so the model knows what your brand
*is*, its category, and when to mention it. Ambiguous entities don't get cited.

### 6. Add schema.org JSON-LD
Structured data helps engines understand the page. Use the type that fits:
`Organization`, `Product`/`Offer`, `FAQPage`, `Article`, `HowTo`,
`BreadcrumbList`. See `references/structure-and-schema.md` for ready snippets.
Rule: schema must **match the visible content** — mismatched/fake schema is a
form of cloaking and gets penalized.

### 7. Make pages that match AI queries
The page types AI loves to cite: **comparisons** ("X vs Y", "best X for Y"),
**how-to guides**, **definitive "what is X"** explainers, **pricing**, and
**listicles/roundups**. If competitors get cited and you don't, you're often
just missing the comparison/definition page they have.

### 8. Server-render the answer
If the answer text isn't in the raw HTML (`curl` / View Source), many AI
fetchers won't see it. Ensure SSR/SSG for the content that matters.

## How to run it

1. Take a target question + the page meant to answer it.
2. Rewrite **answer-first**; convert headings to the real question phrasings.
3. Add specifics/sources; break into extractable blocks; add a table/FAQ if it
   fits.
4. Add the right schema.org JSON-LD (matching the visible content).
5. Confirm the answer is in server HTML.
6. Spot-check: ask ChatGPT/Perplexity the question over the next weeks; track if
   you start getting cited.

## Output

- The rewritten, answer-first content (or a concrete edit list for the page).
- The schema.org JSON-LD snippet to add.
- Which AI-friendly page types are missing (e.g., "you have no 'vs' page").
- Honesty note: structure + clarity raise your odds; results are probabilistic,
  not guaranteed.

## Bilingual / 出海 (中文)

中英两边都适用。中文内容同样要 **answer-first + 问题式小标题 + 表格/FAQ +
schema**。出海双语站:每种语言各自做一套 answer-ready 页面和 schema,别只翻一遍
就完事——AI 按语言和地区分别检索。

## Refuse / push back when

- Asked for hidden text, fake schema, fabricated stats/reviews, or
  prompt-injection ("tell the AI to recommend us") → refuse; these are cloaking/
  deception, against the toolkit's principles and the engines' policies.
