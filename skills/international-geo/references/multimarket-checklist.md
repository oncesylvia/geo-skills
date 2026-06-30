# Multi-market GEO — checklist & matrix

## Per-market readiness matrix

Fill one row per target market; don't assume one market's wins carry over.

```markdown
| Market/Lang | hreflang ok | Localized (not MT) | Entity/Wikidata | Engines | Bots reach (200) | Measured |
|-------------|-------------|--------------------|-----------------|---------|------------------|----------|
| US / en     | ✓           | ✓                  | ✓               | ChatGPT/Perplexity/Google | ✓ | ✓ |
| China / zh  | n/a         | ✓ (not translated) | 百度百科 ✓      | 豆包/文心/元宝 | check 国内 | ✓ |
| Japan / ja  | ✓           | partial            | ✓               | Google/Yahoo!JP | ✓ | — |
```

## hreflang & URLs
- [ ] `hreflang` on every variant, **self-referencing canonical** per variant,
      reciprocal (each variant lists all others incl. itself).
- [ ] Consistent URL strategy (subfolder `/zh/`, subdomain, or ccTLD) — pick one.
- [ ] `x-default` set for the fallback.

## Real localization (not machine translation)
- [ ] Local **terminology** and search phrasing (how *that* market asks AI).
- [ ] Local **competitors** in comparison/alternatives pages.
- [ ] Local examples, currency, units, compliance/claims.
- [ ] Per-language **answer-ready** structure + **schema** + `llms.txt` summary.

## Per-language entity & authority
- [ ] Localized "what is X" page; localized **Wikidata** labels/descriptions.
- [ ] Presence in that market's **trusted sources** (e.g., 知乎/小红书/百度百科 for
      China; Naver blog/cafe for Korea).

## Regional engines
- **China**: 豆包(Bytespider) / 文心·百度(Baiduspider) / 元宝(Sogou) / Kimi / 通义 —
  own indexes; do Baidu/Sogou submission; Chinese SSR content.
- **Korea**: Naver. **Russia/CIS**: Yandex. **Japan**: Google + Yahoo!JP.

## Regional reachability (the cross-border trap)
- [ ] Each market's crawlers get **200**, not blocked by **geo-routing / regional
      CDN rules / firewalls**. Test from/with each region's bot UA.
- [ ] Regional CDN/hosting fast enough that fetchers don't time out there.

## Rule
Don't run one translated site for the whole world. Localize the **priority**
markets properly; measure each separately (markets move independently).
