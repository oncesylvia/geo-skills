# No-code GEO, per platform

You can do the essentials through settings or an app/plugin on every major
builder — no coding. The goal each time: (1) the answer is in real page **text**,
(2) **schema** is added (via app), (3) an **llms.txt** exists, (4) **bots aren't
blocked**, (5) **sitemap** is submitted.

## Is AI being blocked? (check first, any platform)
- If you're on **Cloudflare**: dashboard → Security → Bots → make sure
  **"Block AI bots" / Bot Fight Mode** isn't blocking the crawlers you want
  (turn off, or allow them). This is the #1 silent SME failure.
- Quick test (ask anyone technical, or use an online "fetch as" tool): does
  `https://yoursite.com` return normally to a bot, or a 403/challenge?

## Shopify
- **Page text/FAQ**: edit via Online Store → Pages; add an FAQ page in words.
- **Schema**: most themes add Product schema automatically; an app (e.g., an
  SEO/schema app) adds FAQ/Organization schema — no code.
- **llms.txt / robots**: apps or theme settings; Shopify manages robots.txt (can
  customize via `robots.txt.liquid` if needed — that's a hand-off task).
- **Sitemap**: auto at `/sitemap.xml`; submit in Google/Bing webmaster tools.

## Wix
- **Text/FAQ**: edit pages directly; use the FAQ element with real Q&A text.
- **Schema**: Wix SEO settings allow custom structured data per page (no code);
  business info schema via SEO settings.
- **Meta/sitemap**: Wix SEO tools; sitemap auto; connect Google Search Console.
- **Bots**: Wix serves rendered HTML; verify your key text is in the page.

## Squarespace
- **Text/FAQ**: add an FAQ/accordion block with real text (not just an image).
- **Schema**: built-in for some types; use code blocks only if comfortable (else
  hand off). Fill SEO settings + business info.
- **Sitemap**: auto at `/sitemap.xml`; submit to Google/Bing.

## WordPress
- **Plugins do it no-code**: an SEO plugin (Yoast/Rank Math) adds schema, sitemaps,
  meta, and breadcrumbs; an FAQ block plugin adds FAQ schema.
- **llms.txt**: a plugin can generate/serve it, or upload the file.
- **Caching/CDN**: if behind Cloudflare, check the AI-bot setting.

## Webflow
- **Text/FAQ**: add real text content; FAQ section.
- **Schema**: add JSON-LD in page settings' custom code field (copy-paste a
  snippet from `answer-ready-content` — light touch, no real coding).
- **Sitemap**: auto; enable + submit. Webflow renders server-side HTML (good).

## After any platform
- Confirm the **answer text is visible** in the page (right-click → View Source,
  search for your answer).
- Submit your sitemap in **Google Search Console** and **Bing Webmaster Tools**.
- Fill your **Google Business Profile** and key marketplace/social profiles.

## When to stop DIY and hand off
Custom schema at scale, JS-rendering fixes, CDN/WAF rules, hreflang, content
clusters → brief a freelancer with `hire-and-brief-geo`. The basics above you can
do yourself today.
