# GEO Skills

![GEO Skills — get your site cited by AI](assets/social-card.png)

Open-source [Claude Code](https://claude.com/claude-code) skills to get your
business **cited — and correctly represented — by AI**: ChatGPT, Perplexity,
Claude, Gemini, and AI search.

Most "AI never mentions my site" problems are boring and fixable: the crawler is
blocked at your CDN, your answer isn't in the HTML, or the citation lives on a
Reddit thread you're not part of. And the bigger enterprise risk isn't being
ignored — it's being described **wrongly**. These skills cover the whole picture,
the **honest** way: be genuinely the clearest answer, have real presence where AI
looks, fix what AI gets wrong about you, and decide your policy on purpose. **No
cloaking, no fake reviews, no prompt-injection tricks** — those get you penalized.

## The three gates + the four jobs

An AI engine needs three things from you: **reach** (it can fetch your page),
**parse** (your answer is in clean HTML), **trust** (you're a credible source —
on your own site *and* in the third-party places AI trusts). Around that, a
business has four jobs:

```
  OFFENSE          DEFENSE           STRATEGY            FRONTIER
  get cited   →    fix what AI   →   know where you  →   be usable by
  (on + off-site)  says wrong        stand & measure     AI agents
```

Engines differ in how they pick sources — see
[ai-engines.md](shared/references/ai-engines.md). The enterprise decisions
(bot/IP policy, misinformation & defamation response, ownership) are in
[geo-governance.md](shared/references/geo-governance.md).

## Is this for you? / 这套适合你吗?

**Use it if 👇 / 符合就用得上:**
- AI assistants don't mention you — but competitors get cited / AI 不引用你,却引用对手
- AI says something **wrong** about your brand (price, features, mixed up with a rival) / AI 把你说错了
- You're going global (出海) and want AI search to find you / 出海,想被 AI 搜索找到
- You want to do it honestly — real content, no gaming / 想靠真内容,不想灌水作弊

**Maybe skip it if 👇:**
- You only care about classic Google ranking, not AI answers / 只在乎传统 SEO
- You want to trick AI into recommending you — this toolkit refuses that / 想骗 AI(这套会拒绝)

## Skills (11, grouped by job)

**Start here**
| Skill | Use it when… |
|---|---|
| **[geo-audit](skills/geo-audit/SKILL.md)** | "Why doesn't AI cite my site?" → 3-gate audit + prioritized fixes |

**🟢 Offense — get cited (your own site)**
| Skill | Use it when… |
|---|---|
| **[ai-crawler-access](skills/ai-crawler-access/SKILL.md)** | AI bots get 403 → the two-layer fix: robots.txt **and** the CDN/WAF that silently blocks them |
| **[answer-ready-content](skills/answer-ready-content/SKILL.md)** | A page exists but AI cites a rival → answer-first rewrite + schema |
| **[citable-pages](skills/citable-pages/SKILL.md)** | You're missing the page types AI lifts (vs / alternatives / glossary / use-case) |
| **[llms-txt](skills/llms-txt/SKILL.md)** | Add a correct `/llms.txt` (+ `llms-full.txt`) |

**🟢 Offense — get cited (off your site)**
| Skill | Use it when… |
|---|---|
| **[earn-mentions](skills/earn-mentions/SKILL.md)** | AI cites Reddit/reviews/roundups, not you → honest off-site presence (no fake reviews/astroturf) |

**🔵 Defense — fix what AI says**
| Skill | Use it when… |
|---|---|
| **[ai-brand-monitor](skills/ai-brand-monitor/SKILL.md)** | AI states wrong price/features, confuses you with a rival, or surfaces stale negatives → fix the upstream source |

**🟣 Strategy & measurement**
| Skill | Use it when… |
|---|---|
| **[prompt-coverage](skills/prompt-coverage/SKILL.md)** | Map the full buyer prompt space + share-of-voice vs competitors |
| **[geo-measure](skills/geo-measure/SKILL.md)** | Track citations, AI referral traffic, bot crawls — trend, not a promised rank |
| **[citation-gap](skills/citation-gap/SKILL.md)** | Reverse-engineer why a rival gets cited + a catch-up plan |

**🟠 Frontier**
| Skill | Use it when… |
|---|---|
| **[agent-ready](skills/agent-ready/SKILL.md)** | Prepare to be not just cited but **transactable** by AI agents (data, API, MCP, agentic commerce) |

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
competitor", "what pages should I build for AI", "make us agent-ready".

## Honest GEO only

GEO has a dark side (cloaking, AI-slop pages, fake schema, fake reviews, hidden
prompt injection). This toolkit refuses all of it — see
[geo-principles.md](shared/references/geo-principles.md). Results are
probabilistic: we fix the inputs (reach, structure, clarity, real presence,
accuracy) and never promise a ranking. Same ethos as my other tools: help you do
it right, not get burned.

## Bilingual / 出海 (中文)

中英双语。除了全球 AI(ChatGPT/Perplexity/Claude/Gemini),也覆盖国内引擎
(豆包/文心/元宝)、出海最大的坑(**CDN/WAF 静默 403 拦掉 AI 爬虫**)、国内站外
信任来源(**知乎/小红书/B站/百度百科**),以及"AI 把你说错了"的防御侧。

## Why I built this

I run [cocodot](https://cocodot.co) and went through this myself: AI search
couldn't see the site, and the cause wasn't content — it was the CDN quietly
blocking AI bots behind a toggle nobody mentions. So I wrote down the honest
playbook, and kept going until it covered what a real business needs. If AI
should be citing you and isn't — or is getting you wrong — I hope this helps.

## Related projects

- [**fundraising-skills**](https://github.com/oncesylvia/fundraising-skills) — Claude Code skills for founder-led fundraising.
- [**LLMprobe**](https://github.com/oncesylvia/LLMprobe) — CLI to catch LLM API model-downgrading (降智) and benchmark providers.

## License

MIT. Use it, fork it, improve it.
