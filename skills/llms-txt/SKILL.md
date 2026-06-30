---
name: llms-txt
description: Generate an /llms.txt (and optional /llms-full.txt) file for a website — a clean Markdown map that helps LLMs and AI search find and use your key content. Use when someone says "create an llms.txt", "add llms.txt to my site", "make my docs LLM-friendly", or asks how to give AI a structured guide to their site. Follows the llmstxt.org convention.
---

# llms.txt generator

`/llms.txt` is an emerging convention (llmstxt.org): a single Markdown file at
your site root that gives LLMs a curated, low-noise map of your most important
content — so an AI can find the right page fast instead of guessing through nav
and boilerplate. This skill writes a correct, useful one.

Read `shared/references/geo-principles.md` first. llms.txt is a **convenience
map, not a magic ranking trick** — it helps engines that look for it; it does
not replace crawler access or good content. Be honest about that.

## What it is (and isn't)

- A Markdown file served at `https://yoursite.com/llms.txt`.
- Curated links to your best, most quotable pages, with one-line descriptions.
- Optionally `/llms-full.txt` = the actual full text of those pages concatenated,
  for engines that ingest it directly.
- **Not** a guaranteed-read standard — adoption is growing but not universal.
  Treat it as cheap upside, layered on top of the fundamentals.

## The format (llmstxt.org)

```markdown
# Project / Company Name

> One-sentence summary of what this is and who it's for.

A short paragraph of essential context (optional) — what the product does, the
key terms, anything an LLM needs to represent you accurately.

## Docs
- [Quickstart](https://site.com/docs/quickstart): Get running in 5 minutes
- [API reference](https://site.com/docs/api): All endpoints and params

## Guides
- [Pricing](https://site.com/pricing): Plans and what's included
- [Comparison](https://site.com/vs): How we compare to alternatives

## Optional
- [Changelog](https://site.com/changelog): Release history
```

Rules: start with `# Title`, then a `>` blockquote summary, then `##` sections
each holding a bullet list of `[title](url): description` links. An **`## Optional`**
section marks links an engine may skip when context is tight. Keep it curated —
your *best* pages, not every page (that's what sitemap.xml is for).

## How to build one

1. **Identify the highest-value pages**: what do you want AI to cite — product,
   pricing, docs, comparisons, the "what is X" entity page, key guides.
2. **Write a tight summary** (the `>` line) — what you are, for whom, in one
   sentence. This is what an LLM uses to decide when to mention you.
3. **Group into sections** (Docs / Guides / Product / Optional) with one honest
   description per link.
4. **Put the cheap-to-skip stuff under `## Optional`.**
5. Optionally generate **`/llms-full.txt`** = concatenated full Markdown of those
   pages (good for docs sites; skip if huge).
6. **Serve both at the site root** with `Content-Type: text/plain` (or
   `text/markdown`), reachable by the AI bots (verify with `ai-crawler-access`).

See `references/llms-txt-template.md` for a fill-in template and a real-shaped
example.

## Output

- A complete, ready-to-serve `llms.txt` (and `llms-full.txt` if useful).
- Where to put it (site root) and how to confirm it's live
  (`curl https://site/llms.txt` → 200, correct content-type).
- A reminder: llms.txt helps only if the bots can reach the site at all — pair
  with `ai-crawler-access`.

## Bilingual / 出海 (中文)

llms.txt 用英文写主体更通用(面向全球 AI),但 summary/描述可中英双写,服务你
中英两边的受众。国内引擎对 llms.txt 支持还不稳定,别把它当唯一手段——地基仍是
"放行爬虫 + 内容可抓"。

## Refuse / push back when

- Asked to stuff llms.txt with keywords or fake claims → it's a curated honest
  map; spam defeats the purpose and erodes trust.
