# GEO Skills

![GEO Skills — get your site cited by AI](assets/social-card.png)

Open-source [Claude Code](https://claude.com/claude-code) skills to get your
business **found, cited, and correctly represented by AI** — ChatGPT, Perplexity,
Claude, Gemini, and AI search — then turn that visibility into revenue.

Most "AI never mentions my site" problems are boring and fixable: the crawler is
blocked at your CDN, your answer is trapped in JavaScript, or the citation lives
on a Reddit thread you're not part of. The bigger enterprise risks: AI describes
you **wrongly**, or it cites you but you don't **convert**. These skills cover the
whole surface, the **honest** way — be genuinely the clearest answer, have real
presence where AI looks, fix what AI gets wrong, decide your policy on purpose,
and close the loop to pipeline. **No cloaking, no fake reviews, no
prompt-injection tricks** — those get you penalized.

## The three gates + the jobs of a business

An AI engine needs three things: **reach** (it can fetch your page), **parse**
(your answer is in clean HTML), **trust** (you're a credible source — on your own
site *and* in the third-party places AI trusts). Around that, a business has these
jobs:

```
  OFFENSE         DEFENSE         STRATEGY         OUTCOME        REACH           FRONTIER
  get found  →    fix what AI →   know where  →   turn it    →   more markets →  be usable by
  & cited         says wrong      you stand       into revenue   & local         AI agents
```

Engines differ in how they pick sources — see
[ai-engines.md](shared/references/ai-engines.md). The enterprise decisions
(bot/IP policy, misinformation & defamation response, ownership) are in
[geo-governance.md](shared/references/geo-governance.md).

## Is this for you? / 这套适合你吗?

**Use it if 👇 / 符合就用得上:**
- AI assistants don't mention you — but competitors get cited / AI 不引用你,却引用对手
- AI says something **wrong** about your brand / AI 把你说错了
- AI sends traffic but it doesn't convert / AI 来了流量却不转化
- You're going global or local (出海 / 本地) / 出海或本地生意
- You want it done honestly — real content, no gaming / 想靠真内容,不作弊

**Maybe skip it if 👇:**
- You only care about classic Google ranking, not AI answers / 只在乎传统 SEO
- You want to trick AI into recommending you — this toolkit refuses that / 想骗 AI(会拒绝)

## Skills (16, grouped by job)

**Start here**
| Skill | Use it when… |
|---|---|
| **[geo-audit](skills/geo-audit/SKILL.md)** | "Why doesn't AI cite my site?" → 3-gate audit + prioritized fixes |

**🟢 Offense — get found & cited (your own site)**
| Skill | Use it when… |
|---|---|
| **[ai-crawler-access](skills/ai-crawler-access/SKILL.md)** | AI bots get 403 → two-layer fix: robots.txt **and** the CDN/WAF that silently blocks them |
| **[technical-foundations](skills/technical-foundations/SKILL.md)** | Access is fixed but still invisible → discovery (sitemap/IndexNow), JS rendering, speed, freshness |
| **[answer-ready-content](skills/answer-ready-content/SKILL.md)** | A page exists but AI cites a rival → answer-first rewrite + schema |
| **[citable-pages](skills/citable-pages/SKILL.md)** | Missing the page types AI lifts (vs / alternatives / glossary / use-case) |
| **[topical-authority](skills/topical-authority/SKILL.md)** | AI cites big sites, not you → content clusters + E-E-A-T to become the source |
| **[llms-txt](skills/llms-txt/SKILL.md)** | Add a correct `/llms.txt` (+ `llms-full.txt`) |

**🟢 Offense — off your site**
| Skill | Use it when… |
|---|---|
| **[earn-mentions](skills/earn-mentions/SKILL.md)** | AI cites Reddit/reviews/roundups, not you → honest off-site presence (no fake reviews/astroturf) |

**🔵 Defense — fix what AI says**
| Skill | Use it when… |
|---|---|
| **[ai-brand-monitor](skills/ai-brand-monitor/SKILL.md)** | AI states wrong price/features, confuses you with a rival, surfaces stale negatives → fix the upstream source |

**🟣 Strategy & measurement**
| Skill | Use it when… |
|---|---|
| **[prompt-coverage](skills/prompt-coverage/SKILL.md)** | Map the full buyer prompt space + share-of-voice vs competitors |
| **[geo-measure](skills/geo-measure/SKILL.md)** | Track citations, AI referral traffic, bot crawls — trend, not a promised rank |
| **[citation-gap](skills/citation-gap/SKILL.md)** | Reverse-engineer why a rival gets cited + a catch-up plan |

**🟡 Outcome — turn visibility into revenue**
| Skill | Use it when… |
|---|---|
| **[convert-ai-traffic](skills/convert-ai-traffic/SKILL.md)** | AI sends visits/agents but no conversions → match the answer, capture, attribute to revenue |

**🌏 Reach more markets**
| Skill | Use it when… |
|---|---|
| **[local-ai-search](skills/local-ai-search/SKILL.md)** | "near me" / local queries → Google Business Profile, NAP consistency, local schema |
| **[international-geo](skills/international-geo/SKILL.md)** | Multiple languages/countries (出海) → hreflang, real localization, regional engines |

**🟠 Frontier**
| Skill | Use it when… |
|---|---|
| **[agent-ready](skills/agent-ready/SKILL.md)** | Be not just cited but **transactable** by AI agents (data, API, MCP, agentic commerce) |

The most common single fix is **ai-crawler-access** — people fix robots.txt but
leave Cloudflare's "Block AI bots" toggle on, so AI gets a 403 and never sees the
site.

## Install

```
/plugin marketplace add oncesylvia/geo-skills
/plugin install geo-skills@geo-skills
```

Then ask naturally — "audit my site for AI citation", "Cloudflare is blocking
GPTBot", "what does ChatGPT say about my company", "why does Perplexity cite my
competitor", "AI sends traffic but no conversions", "GEO for our China market",
"make us agent-ready".

## Honest GEO only

GEO has a dark side (cloaking, AI-slop pages, fake schema, fake reviews, hidden
prompt injection). This toolkit refuses all of it — see
[geo-principles.md](shared/references/geo-principles.md). Results are
probabilistic: we fix the inputs (reach, structure, clarity, real presence,
accuracy) and never promise a ranking. Same ethos as my other tools: help you do
it right, not get burned.

## Bilingual / 出海 (中文)

中英双语,贯穿每个 skill。覆盖全球 AI(ChatGPT/Perplexity/Claude/Gemini)和国内
引擎(豆包/文心/元宝),出海最大的坑(**CDN/WAF 静默 403 拦掉 AI 爬虫**)、国内
站外信任源(知乎/小红书/百度百科)、国内本地(高德/百度地图/大众点评),以及"AI
把你说错了"的防御、多市场 hreflang、把 AI 流量变成钱的转化与归因。

## Why I built this

I run [cocodot](https://cocodot.co) and went through this myself: AI search
couldn't see the site, and the cause wasn't content — it was the CDN quietly
blocking AI bots behind a toggle nobody mentions. So I wrote down the honest
playbook, and kept going until it covered what a real business actually needs —
found, cited, correct, converting, across markets. If AI should be working for
you and isn't, I hope this helps.

## Related projects

- [**fundraising-skills**](https://github.com/oncesylvia/fundraising-skills) — Claude Code skills for founder-led fundraising.
- [**LLMprobe**](https://github.com/oncesylvia/LLMprobe) — CLI to catch LLM API model-downgrading (降智) and benchmark providers.

## License

MIT. Use it, fork it, improve it.
