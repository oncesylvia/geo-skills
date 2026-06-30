---
name: international-geo
description: Make a business citable by AI across languages and markets — hreflang, per-market content (not just translation), per-language entity and schema, regional engines (China's 豆包/文心, Naver, Yandex), and regional crawler/CDN reachability. Use when someone says "GEO for multiple countries", "出海 AI search", "hreflang for AI", "get cited in other languages", "我们要做海外/多语言 AI 搜索", or runs a cross-border business. The multi-market layer.
---

# International GEO (多市场 / 出海)

Being cited in one language/market doesn't carry to others — engines retrieve per
language and region, and each market has different competitors, phrasings,
trusted sources, and even different AI engines. This skill makes a business
citable across markets the right way, which a single-language GEO effort misses.

Read `shared/references/ai-engines.md` (incl. the China-engines section) and
`shared/references/geo-principles.md` first. See `references/multimarket-checklist.md`.

## The multi-market jobs

### 1. Targeting (tell engines which version is for whom)
- **hreflang** tags mapping language/region variants, with a self-referencing
  canonical per variant. Wrong/missing hreflang = engines serve the wrong version
  or dilute both.
- A clear URL strategy (subfolders/subdomains/ccTLDs) consistently applied.

### 2. Real localization (not translation)
- Per-market **content**, not a machine translation: local terminology, the
  competitors *that* market compares against, local examples, currency, units,
  compliance. AI lifts the version that genuinely answers a local query.
- Per-language **answer-ready** pages, **schema**, and `llms.txt` summary.

### 3. Per-language entity & authority
- Your brand is an entity in each language — localized "what is X" page,
  localized Wikidata labels, presence in each market's trusted sources.

### 4. Regional engines
- **China**: 豆包/文心/元宝/Kimi/通义 — own indexes; do Baidu/Sogou submission;
  Chinese answer-ready content; watch CDN geo-rules. (See ai-engines.md.)
- **Korea**: Naver. **Russia/CIS**: Yandex. **Japan**: strong Google + Yahoo!JP.
  Each has its own crawler and norms.

### 5. Regional reachability
- Make sure each market's crawlers actually reach you — **geo-routing, regional
  CDN rules, or firewalls** can block a region's bots (a cross-border classic).
  Verify per region (pairs with `ai-crawler-access` + `technical-foundations`).

## How to run it

1. List target **markets/languages** and the engines that matter in each.
2. **hreflang + URL** audit: correct, self-canonical, consistent?
3. **Localization** audit: real per-market content + schema + entity, or just
   translated?
4. **Reachability**: do regional/China bots get 200 from each market's URLs?
5. Prioritize by market value; build per-market answer-ready content + presence.

## Output

- A per-market readiness matrix (hreflang / localization / entity / engines /
  reachability).
- The priority market and its first moves.
- A note that markets don't move together — measure each separately
  (`geo-measure`).

## Bilingual / 出海 (中文)

这正是出海的核心:**别用一套翻译打全球**。中国市场单独一套(豆包/文心 + 知乎/
小红书/百度百科 + 高德本地 + 中文 schema),海外另一套。CDN 别因地域规则把某个
市场的 AI 爬虫挡在外面。

## Refuse / push back when

- Asked to auto-translate the whole site as the "localization" → flag that thin MT
  underperforms and can read as low-quality; recommend real localization for
  priority markets.
