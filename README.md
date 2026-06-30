# GEO Skills

![GEO Skills — get your site cited by AI](assets/social-card.png)

Open-source [Claude Code](https://claude.com/claude-code) skills to get your site
**cited by AI** — ChatGPT, Perplexity, Claude, Gemini, and AI search.

Most "AI never mentions my site" problems are boring and fixable: the crawler is
blocked at your CDN, or your answer isn't in the HTML. These skills find the real
cause and fix it — the **honest** way. You earn citations by genuinely being the
clearest answer, then removing every technical reason an engine can't reach or
quote you. **No cloaking, no spam, no prompt-injection tricks** — those get you
penalized.

## How it works → which skill

```
  ① Diagnose        ② Fix reach           ③ Map content      ④ Win the citation
 ┌────────────┐   ┌────────────────────┐ ┌──────────────┐  ┌────────────────────┐
 │ geo-audit  │ → │ ai-crawler-access  │→│ llms-txt     │→ │ answer-ready-       │
 │ 3 gates    │   │ robots + CDN/WAF   │ │ site map for │  │ content            │
 │ check      │   │ (the silent block) │ │ LLMs         │  │ answer-first+schema│
 └────────────┘   └────────────────────┘ └──────────────┘  └────────────────────┘
```

The three gates an AI engine needs from you: **reach** (it can fetch your page),
**parse** (your answer is in clean HTML), **trust** (you're a credible, specific
source).

## Is this for you? / 这套适合你吗?

**Use it if 👇 / 符合就用得上:**
- You have a product/site and AI assistants don't mention you (but competitors get cited) / AI 不引用你,却引用对手
- You're not sure if ChatGPT/Perplexity can even crawl your site / 不确定 AI 能不能抓到你
- You're going global (出海) and want AI search to find you / 出海,想被 AI 搜索找到
- You want to do it honestly — real content, no gaming / 想靠真内容,不想灌水作弊

**Maybe skip it if 👇:**
- You only care about classic Google ranking and not AI answers / 只在乎传统 SEO
- You want to trick AI into recommending you — this toolkit refuses that / 想骗 AI 推荐你(这套会拒绝)

## Skills

| Skill | Use it when… | What you get |
|---|---|---|
| **[geo-audit](skills/geo-audit/SKILL.md)** | "Why doesn't AI cite my site?" | A 3-gate (reach/parse/trust) audit + prioritized fix list |
| **[ai-crawler-access](skills/ai-crawler-access/SKILL.md)** | AI bots get 403 / can't see your site | The **two-layer** fix: robots.txt **and** the CDN/WAF (Cloudflare etc.) that silently blocks AI bots |
| **[llms-txt](skills/llms-txt/SKILL.md)** | "Add an llms.txt" | A correct `/llms.txt` (+ `llms-full.txt`) mapping your best content for LLMs |
| **[answer-ready-content](skills/answer-ready-content/SKILL.md)** | "AI cites my competitor, not me" | Answer-first rewrites, question-shaped headings, comparison/FAQ blocks, and schema.org JSON-LD |

The most common fix is **ai-crawler-access** — people fix robots.txt but leave
Cloudflare's "Block AI bots" toggle on, so AI gets a 403 and they never see why.

## Install

```
/plugin marketplace add oncesylvia/geo-skills
/plugin install geo-skills@geo-skills
```

Then ask naturally — "audit my site for AI citation", "Cloudflare is blocking
GPTBot", "write an llms.txt for my site", "make this page answer-first for AI".

## Honest GEO only

GEO has a dark side (cloaking, AI-slop pages, fake schema, hidden prompt
injection). This toolkit refuses all of it — see
[geo-principles.md](shared/references/geo-principles.md). Results are
probabilistic: we fix the inputs (reach, structure, clarity) and never promise a
ranking. Same ethos as my other tools: help you do it right, not get burned.

## Bilingual / 出海 (中文)

中英双语。除了全球 AI(ChatGPT/Perplexity/Claude/Gemini),也覆盖国内引擎
(豆包/文心/元宝 的 Baiduspider/Bytespider/Sogou)和出海最大的坑——**CDN/WAF 静默
403 拦掉 AI 爬虫**。技术地基同样适用两边。

## Why I built this

I run [cocodot](https://cocodot.co) and went through this myself: AI search
couldn't see the site, and the cause wasn't content — it was the CDN quietly
blocking AI bots behind a toggle nobody mentions. So I wrote down the honest,
two-layer fix. If AI should be citing you and isn't, I hope this saves you the
debugging.

## Related projects

- [**fundraising-skills**](https://github.com/oncesylvia/fundraising-skills) — Claude Code skills for founder-led fundraising.
- [**LLMprobe**](https://github.com/oncesylvia/LLMprobe) — CLI to catch LLM API model-downgrading (降智) and benchmark providers.

## License

MIT. Use it, fork it, improve it.
