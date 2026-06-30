---
name: geo-starter
description: The no-code, non-technical on-ramp to GEO for small business owners — the 80/20 starter path and how to do it on Shopify, Wix, Squarespace, WordPress, Webflow without writing code. Use when someone says "I'm not technical", "I don't have a developer", "where do I even start with AI search", "GEO for my small business", "我不懂代码/没有技术团队怎么做", or is overwhelmed by the technical skills. Start here if you don't have a dev team.
---

# GEO starter (no code, no dev team)

Most GEO advice assumes you can edit code, add schema, and configure a CDN. A
small-business owner usually can't — and doesn't need to, to get the big wins.
This skill is the **plain-language on-ramp**: the few things that matter most, and
how to do them on the website builder you actually use, without a developer.

Read `shared/references/geo-principles.md` first (honest GEO — same rules apply at
any size). See `references/platform-howto.md` for per-platform steps.

## The 80/20 for a small business (do these first, in order)

1. **Make sure AI isn't blocked.** If you use Cloudflare (or your host has a
   "block bots" setting), AI crawlers may be getting a 403 and you'd never know.
   Check it — this is the #1 silent killer. (Details: `ai-crawler-access`; the
   no-code check is in the platform guide.)
2. **Put the answer in plain text on the page.** Say clearly, in words (not only
   in an image or a fancy widget): what you do, who for, where, price/range, and
   answers to the top questions customers ask. AI can only quote text it can read.
3. **Fill in your free profiles.** Google Business Profile (if local), your
   marketplace/LinkedIn/social profiles — complete and accurate. For many SMEs
   these get cited more than the website. (→ `local-ai-search`,
   `marketplace-and-social-geo`.)
4. **Get honest reviews.** Real reviews on Google/industry sites are a top trust
   signal AI uses. Ask happy customers; never fake them.
5. **Add an FAQ in words.** Answer the real questions buyers ask, each as a short
   heading + plain answer. This alone makes you far more quotable.

That's the bulk of the value. Everything below is optional polish.

## Do it on your platform (no code)

Most builders let you do the essentials through settings or a plugin/app — no
coding. See `references/platform-howto.md` for Shopify, Wix, Squarespace,
WordPress, and Webflow: where to edit page text and meta, add schema via an
app/plugin, publish an `llms.txt`, and check if bots are blocked.

## What to DIY vs hand off

- **DIY (you can do today)**: write clear page text + FAQ, fill profiles, ask for
  reviews, check the "block AI bots" toggle, install a no-code SEO/schema app.
- **Hand off (brief someone)**: custom schema at scale, fixing JS-rendering, CDN
  rules, hreflang, content clusters. If you outsource, use `hire-and-brief-geo`
  so you don't overpay or get scammed.

## Output

- A short, prioritized **starter checklist** tailored to their platform and
  whether they're local / online / export.
- The single most important thing to fix first (usually: a blocked crawler or an
  answer that only exists in an image/PDF/JS).
- A clear DIY-vs-handoff split so they're not stuck.

## Bilingual / 出海 (中文)

中文小老板同理:先确认没被 CDN 拦、把"做什么/给谁/在哪/多少钱/常见问题"用**文字**
写清楚、填好各平台资料、攒真实口碑。代码相关的(schema/渲染/CDN)能外包就外包,
用 `hire-and-brief-geo` 防被坑。出海的看 `export-supplier-geo`。

## Refuse / push back when

- Asked for "one magic setting" → there isn't one; give the honest 80/20.
- Pushed to buy a complex technical setup they don't need yet → start with the
  free, high-impact basics first.
