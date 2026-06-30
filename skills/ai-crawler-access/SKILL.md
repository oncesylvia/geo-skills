---
name: ai-crawler-access
description: Make sure AI crawlers can actually reach a site — fix robots.txt AND the CDN/WAF (Cloudflare, Akamai, Fastly, AWS WAF, Vercel) that silently blocks AI bots with 403s. Use when someone says "let AI crawl my site", "ChatGPT/Perplexity can't see my site", "unblock GPTBot/ClaudeBot", "Cloudflare blocking AI bots", "robots.txt for AI", or AI engines return 403 to their pages. The single highest-impact, most-overlooked GEO fix.
---

# AI crawler access (the two-layer fix)

If an AI engine can't fetch your page, it can't cite you — and the block is
usually invisible. The fix has **two layers** that people forget are separate:
robots.txt (advisory) **and** the CDN/WAF (which can 403 AI bots regardless of
robots.txt). This skill gets both right.

Read `shared/references/ai-crawlers.md` (the bot list + the two-layer trap) and
`shared/references/geo-principles.md` first.

## Step 1 — Decide your policy

Two separate decisions (see ai-crawlers.md):
- **Retrieval/citation bots** (`OAI-SearchBot`, `ChatGPT-User`, `PerplexityBot`,
  `Perplexity-User`, `Claude-User`, `Claude-SearchBot`, plus `Googlebot`) →
  **almost always allow.** This is what gets you cited live.
- **Training bots** (`GPTBot`, `ClaudeBot`, `Google-Extended`, `CCBot`,
  `Applebot-Extended`, `Bytespider`…) → your call (presence vs. IP/values). You
  can allow retrieval while blocking training.

## Step 2 — Diagnose what's actually blocking (don't guess)

Test the live status code per bot, because robots.txt and the CDN can disagree:

```
curl -A "OAI-SearchBot" -I https://yoursite.com/important-page
curl -A "PerplexityBot"  -I https://yoursite.com/important-page
curl -A "ChatGPT-User"   -I https://yoursite.com/important-page
curl -A "Claude-User"    -I https://yoursite.com/important-page
curl -A "Googlebot"      -I https://yoursite.com/important-page
```
- `200` → reachable. `403`/`429`/`503`/HTML challenge → **blocked at the CDN/WAF**
  even if robots.txt looks fine. Also fetch `/robots.txt` and read the rules.

See `references/robots-and-cdn.md` for interpreting results and platform steps.

## Step 3 — Fix layer 1: robots.txt

Allow the bots you chose; make sure no broad rule clobbers them. Example that
allows retrieval (and training) while keeping a couple of paths private:

```
# Allow AI retrieval/citation
User-agent: OAI-SearchBot
User-agent: ChatGPT-User
User-agent: PerplexityBot
User-agent: Perplexity-User
User-agent: Claude-User
User-agent: Claude-SearchBot
Allow: /
Disallow: /admin/
Disallow: /checkout/

# Optional: allow training crawlers too
User-agent: GPTBot
User-agent: ClaudeBot
User-agent: Google-Extended
Allow: /

User-agent: *
Allow: /
Sitemap: https://yoursite.com/sitemap.xml
```
Pitfalls: a stray `Disallow: /` under `User-agent: *`; blocking by mistake;
forgetting the `Sitemap:` line. robots.txt is **public and advisory** — it
guides polite bots, it does not enforce.

## Step 4 — Fix layer 2: the CDN/WAF (the part everyone misses)

This is where the silent 403s come from. By platform (see
`references/robots-and-cdn.md` for detail):

- **Cloudflare**: turn OFF "Block AI bots" / "AI Scrapers and Crawlers"
  (Security → Bots), or set it to allow your chosen bots. Check **Bot Fight
  Mode**, **WAF managed/custom rules**, and any "verified-bots-only" rule that
  drops these user-agents. Add an allow rule for the retrieval bots.
- **AWS WAF / CloudFront**: check the Bot Control managed rule group and any
  rate/UA rules; add an allow for the chosen user-agents.
- **Akamai / Fastly / Imperva**: check bot-management categories; allow the AI
  retrieval bots explicitly.
- **Vercel / Netlify**: check firewall/attack-challenge settings and any
  middleware that blocks by user-agent.

## Step 5 — Verify the fix

Re-run the Step 2 curls — every chosen retrieval bot should now return `200`.
Then confirm the **answer is in server-rendered HTML** (`curl https://site/page`
and look for the text), since reach is useless if the content is JS-only.

## Output

- Which bots were blocked and **at which layer** (robots vs CDN).
- The corrected robots.txt (ready to paste).
- The exact CDN/WAF setting to change, for their platform.
- The verification commands and expected `200`s.
- A note if content is JS-only (hand to `answer-ready-content` / server-render).

## Bilingual / 出海 (中文)

中文要点见 `references/robots-and-cdn.md` 末尾:很多人只改了 robots.txt,**CDN
（尤其 Cloudflare 的「Block AI bots」开关 + Bot Fight Mode）还在 403**,于是 AI
永远抓不到也看不出原因。两道都要放行。国内引擎(豆包/文心)同理,别在 WAF 误杀
Baiduspider/Bytespider。

## Refuse / push back when

- Asked to allow bots only for cloaking (serve bots different content) → refuse;
  that's against engine policy and the toolkit's principles.
