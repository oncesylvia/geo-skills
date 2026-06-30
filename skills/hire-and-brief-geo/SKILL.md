---
name: hire-and-brief-geo
description: Help a non-technical owner outsource GEO/AI-search/SEO work without getting ripped off — what to actually ask for, how to brief a freelancer or agency, fair pricing, scam red flags, and how to verify the work was done. Use when someone says "I need to hire someone for this", "is this SEO/GEO agency legit", "how much should GEO cost", "they promised #1 on AI", "找人做/外包靠谱吗会不会被坑", or must delegate the technical parts. The don't-get-burned skill.
---

# Hire & brief GEO (don't get ripped off)

Most small-business owners can't do the technical GEO work themselves and must
hire it out — which is exactly where they get overcharged or scammed (guaranteed
rankings, "submit to 1000 directories", vague deliverables, blackhat tactics that
get them penalized). This skill makes the owner a smart buyer: know what to ask
for, brief it clearly, spot the cons, and verify what you paid for.

Read `shared/references/geo-principles.md` and
`shared/references/geo-governance.md` first.

## First: do you even need to hire? (the cheap wins are DIY)
Point them to `geo-starter` — the highest-impact basics (clear page text, FAQ,
profiles, reviews, checking the "block AI bots" toggle) are free and need no dev.
Hire for the **technical** parts: schema at scale, JS-rendering/SSR, CDN/WAF
rules, hreflang, content clusters, original research pages.

## 🚩 Scam & low-value red flags (walk away)
- **"Guaranteed #1 / guaranteed AI citations."** No one can guarantee it — GEO and
  search are probabilistic. This alone disqualifies them.
- **Blackhat offers**: buying links, fake reviews, "AI content at scale" (slop),
  cloaking, hidden text, "submit to 1000 directories." These get you **penalized**,
  not ranked.
- **Vague deliverables / no reporting**: "we'll do SEO" with no specific scope,
  no before/after, no access to what they changed.
- **No access / black box**: won't use *your* accounts (Search Console, GBP, CMS)
  or explain changes — you can't verify or keep the work if you leave.
- **Lock-in**: they keep ownership of your site, GBP, or content.
- **Pressure & secrecy**: "proprietary method we can't explain."

## ✅ What to ask for (a real scope)
Brief them against the actual jobs (use these skill names as the checklist):
- Crawler access fixed (robots + **CDN/WAF**), verified with status codes.
- Server-rendered content / JS-render fixes; sitemap + Bing/Google submission.
- Answer-first content + **schema.org** on key pages; an FAQ; comparison/glossary
  pages where useful.
- `llms.txt` published.
- Profiles (GBP / marketplace / social) completed and consistent.
- A measurement setup (citation/referral tracking) and **monthly reporting**.
- **Deliverables in writing**, work done in **your** accounts, and a summary of
  exactly what changed.

## 💰 Fair pricing & engagement
- Prefer **defined-scope projects** or transparent retainers with named
  deliverables over open-ended "SEO retainers."
- Ask for **examples and references** you can check; a small paid trial task
  before a big contract.
- Pricing varies by market and scope — get **2-3 quotes** and compare scope, not
  just price. Cheapest-with-guarantees is usually the scam.

## 🔎 Verify the work (you can check, even non-technical)
- Crawler access: have them show `curl -A "OAI-SearchBot" -I` returns **200** (or
  use an online "fetch as bot" tool).
- Rendering: View Source — is your answer text actually in the HTML?
- Schema: a schema validator shows valid markup matching the page.
- Profiles: GBP/listings complete and consistent.
- Reporting: a real before/after on citations/referrals, in your accounts.

## Output

- A go/no-go read on a vendor (red flags present?).
- A ready-to-send **scope/brief** for the work the business needs.
- A short **verification checklist** so they confirm they got what they paid for.

## Bilingual / 出海 (中文)

中文小老板尤其容易被"保证上首页/保证被 AI 推荐""一键发 1000 个目录""AI 批量
生成内容"这类话术割韭菜——**这些不仅没用,还会被惩罚**。要点:用你自己的账号做、
要书面交付物和月报、先小额试做、对比 2-3 家的**范围**而非只看价格。先把
`geo-starter` 的免费基础自己做了,再外包技术活。

## Refuse / push back when

- Asked to help draft a brief that includes blackhat tactics (fake reviews, link
  buying, cloaking, slop) → refuse and explain it gets them penalized; brief the
  honest scope instead.
