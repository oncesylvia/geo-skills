# How each AI engine picks its sources

Engines differ in what they index and how they choose what to cite. Optimizing
blindly wastes effort — match the engine your audience actually uses. Verify
specifics against each vendor's docs; this is a working map, not gospel.

## Global engines

### ChatGPT (search)
- **Crawls** with `OAI-SearchBot`; live-browses with `ChatGPT-User`. Has used
  Bing's index historically while building its own.
- **Cites** sources inline. Favors pages that directly answer, are fresh, and are
  reachable + parseable (server HTML).
- **Optimize for**: crawler access for OAI-SearchBot/ChatGPT-User, answer-first
  content, clear entity, corroboration on trusted sites.

### Perplexity
- **Crawls** with `PerplexityBot`; live-fetches with `Perplexity-User`. A
  citation-first answer engine — every answer lists sources.
- **Favors** fresh, well-structured, authoritative pages that answer directly;
  pulls heavily from Reddit, news, docs, and roundups.
- **Optimize for**: structured answer-ready content, recency, and being present
  in the third-party sources it likes (Reddit threads, listicles, docs).

### Google AI Overviews / AI Mode
- Uses **Google's main index** (`Googlebot`). **`Google-Extended` does NOT gate
  AI Overviews** — it only controls Gemini API/Vertex grounding & training. You
  cannot opt out of AI Overviews separately from Search.
- **Favors** what classic Google favors: helpful, relevant, well-structured
  content from sites that rank — plus strong entity signals.
- **Optimize for**: classic SEO still matters here + clear structure + schema.

### Gemini (app)
- Grounds answers in **Google Search** (Google index). Similar levers to AI
  Overviews; `Google-Extended` affects training/grounding via API.

### Claude (web search)
- Fetches with `Claude-User` / `Claude-SearchBot`; cites sources.
- **Optimize for**: reachable, server-rendered, directly-answering pages.

### Microsoft Copilot / Bing
- Uses **Bing's index** (`Bingbot`). Don't forget Bing — submit via Bing
  Webmaster Tools; it feeds Copilot.

## The cross-engine pattern: third-party sources matter as much as your site

Across ChatGPT, Perplexity, and Google, a large share of citations come from
**places that aren't your website**:
- **Reddit** — heavily weighted across engines (data deals + real discussion).
- **Wikipedia / Wikidata** — entity grounding; who/what your brand *is*.
- **Review & directory sites** — G2, Capterra, Product Hunt, Trustpilot.
- **YouTube** — increasingly surfaced.
- **Listicles / roundups** — "best X for Y" posts you're (honestly) included in.
- **Reputable press & docs**.

So GEO is two halves: your **own site** (reach + structure) and your **off-site
presence** (the sources engines trust). Both matter. → `earn-mentions`.

## China engines (出海 / 国内)

Mostly their own search indexes — classic local SEO still applies:
- **豆包 (Doubao, ByteDance)** — `Bytespider`, ByteDance index.
- **文心一言 / 百度 AI 搜索** — `Baiduspider`, Baidu index (Baidu SEO matters a lot).
- **腾讯元宝** — Sogou/Tencent lineage (`Sogou web spider`).
- **Kimi (Moonshot) / 通义 (Alibaba)** — own retrieval.
- **Optimize for**: don't let your CDN/WAF block these spiders; do basic
  Baidu/Sogou submission; provide Chinese answer-ready content (not just
  translated). 国内对 llms.txt 支持仍不稳定——地基(放行+可抓+真内容)更重要。

## Practical takeaway

1. Pick the 1-2 engines your audience uses.
2. Make sure their bots reach you (`ai-crawler-access`).
3. Answer-first, structured content (`answer-ready-content`).
4. Earn presence in the third-party sources that engine weights (`earn-mentions`).
5. Measure per engine (`geo-measure`) — they won't move together.
