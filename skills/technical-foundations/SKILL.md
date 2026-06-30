---
name: technical-foundations
description: Fix the technical layer below content — discovery (sitemaps, IndexNow, Bing/Google submission), rendering (server-render so AI fetchers that don't run JS still see your answer), speed (avoid fetcher timeouts), and freshness (dateModified, update cadence). Use when someone says "AI can reach my site but still doesn't cite me", "my content is JS-rendered", "submit my site to AI", "IndexNow", "make my pages render for bots", or has access fixed but visibility still flat. The plumbing beneath answer-ready-content.
---

# Technical foundations

`ai-crawler-access` gets bots in the door. But discovery, rendering, speed, and
freshness decide whether they actually **find and ingest** your answer. This is
the plumbing: invisible when right, fatal when wrong (a JS-only page an AI fetcher
can't render is as invisible as a blocked one).

Read `shared/references/ai-engines.md` and `shared/references/geo-principles.md`
first. See `references/discovery-and-rendering.md` for commands and specifics.

## The four technical jobs

### 1. Discovery — help engines find your pages fast
- **XML sitemap**, complete and current, with accurate `<lastmod>`; submit it.
- **Bing Webmaster Tools** (feeds Copilot — don't skip Bing) + **Google Search
  Console**.
- **IndexNow** — ping Bing/Yandex instantly when content changes, so updates are
  picked up in minutes not weeks.
- Clean internal linking + canonical tags so crawl budget isn't wasted.

### 2. Rendering — the answer must be in server HTML
- Many AI fetchers **don't execute JavaScript**. If your answer only appears after
  client-side JS, it's invisible to them.
- Use **SSR/SSG or prerendering** for content pages. Verify with
  `curl https://site/page` / View Source: is the answer text actually there?
- SPA marketing sites are the classic silent failure here.

### 3. Speed — don't get dropped on a timeout
- AI fetchers have short patience. Slow TTFB / heavy pages can time out before
  your content loads. Keep content pages fast and lightweight.

### 4. Freshness — engines favor current content
- Accurate `dateModified` / `<lastmod>`; a real update cadence on key pages.
- Audit **content decay**: outdated pages get dropped or cited wrongly. Refresh
  prices, stats, and "best of <year>" pages on schedule.

## How to run it

1. **Discovery check**: sitemap present/valid/submitted? IndexNow set up? In Bing
   + Google consoles?
2. **Render check**: `curl` each key page — is the answer in the raw HTML? If not,
   that's the priority fix (SSR/prerender).
3. **Speed check**: TTFB and weight of content pages.
4. **Freshness check**: are dates accurate? which pages are stale?
5. Output the gaps, fix discovery + rendering first (highest impact).

## Output

- A technical checklist with pass/fail per item (see the reference).
- The priority fix (almost always: server-render a JS-only answer, or set up
  sitemap+IndexNow).
- Verification commands and what "good" looks like.

## Bilingual / 出海 (中文)

国内:提交**百度站长 / 必应站长**;`Baiduspider` 同样不擅长跑 JS,内容要 SSR。
区域 CDN 别因地域规则拖慢/拦截海外或国内爬虫。新鲜度对国内引擎同样重要。

## Refuse / push back when

- Asked to serve bots a server-rendered version different from what users see →
  that's cloaking; SSR must render the **same** content for everyone.
