# Discovery & rendering — checklist and commands

## Discovery

- [ ] **XML sitemap** at `/sitemap.xml`, valid, lists canonical URLs with accurate
      `<lastmod>`. Split if large; keep it current (stale sitemaps mislead).
- [ ] Referenced in `robots.txt` (`Sitemap: https://site/sitemap.xml`).
- [ ] **Google Search Console** — property verified, sitemap submitted.
- [ ] **Bing Webmaster Tools** — verified, sitemap submitted (Bing feeds Copilot;
      most people forget it).
- [ ] **IndexNow** — set up so content changes ping Bing/Yandex instantly:
      generate a key, host it at `https://site/<key>.txt`, and POST changed URLs
      to the IndexNow API on publish/update. Cuts pickup from weeks to minutes.
- [ ] Canonical tags correct; no crawl traps (infinite params, duplicate URLs).

## Rendering (the silent killer)

Many AI fetchers don't run JavaScript. Test that the **answer is in the raw HTML**:

```
curl -s https://yoursite.com/key-page | grep -i "the exact answer text"
```
- Found → server-rendered ✅.
- Missing (but visible in a browser) → it's JS-rendered → AI fetchers likely can't
  see it. Fix with **SSR / SSG / prerendering** for content pages.

Also compare what a bot UA gets vs a browser — they must be the **same content**
(serving bots a different version is cloaking):
```
curl -s -A "OAI-SearchBot" https://yoursite.com/key-page | wc -c
curl -s -A "Mozilla/5.0"   https://yoursite.com/key-page | wc -c
```

## Speed

- [ ] Fast **TTFB** on content pages; avoid heavy blocking scripts. AI fetchers
      time out — a slow page can be dropped before content loads.
- [ ] Content pages lightweight; don't gate the answer behind slow JS.

## Freshness

- [ ] Accurate `dateModified` (schema) and sitemap `<lastmod>`.
- [ ] A real **update cadence** on key pages (pricing, "best of <year>", stats).
- [ ] **Content-decay audit**: list pages with old dates/stale facts; refresh or
      retire. Stale pages get dropped or cited with outdated info
      (loops with `ai-brand-monitor`).

## Priority order

1. **Rendering** — if the answer isn't in server HTML, nothing else matters.
2. **Discovery** — sitemap + Bing/Google submission + IndexNow.
3. **Freshness** — fix stale high-value pages.
4. **Speed** — trim anything causing fetcher timeouts.
