# GEO tracking templates

Keep runs comparable: fix your target questions and engines, then re-run on a
cadence. One run is noise; the trend is the signal.

## Citation tracker (CSV)

Save as `geo-tracking.csv`. One row per (question × engine × date).

```csv
date,question,engine,cited,your_url,competitor_cited,source_used,notes
2026-06-22,best stablecoin payment API for startups,Perplexity,no,—,Acme Pay,reddit.com/r/...,cited a reddit thread
2026-06-22,best stablecoin payment API for startups,ChatGPT,mention,/what-is,—,our docs,mentioned not linked
2026-06-22,how to accept USDC on a website,ChatGPT,yes,/docs/quickstart,—,our quickstart,answer-first page worked
```

- `cited`: `yes` (linked/cited) / `mention` (named, not linked) / `no`.
- Re-run the same rows every 2 weeks; watch `cited` move per engine.

## Channel tracker (referral traffic)

Monthly, from analytics — sessions from AI surfaces:

```markdown
| Month | chatgpt.com | perplexity.ai | gemini | claude.ai | copilot | 国内引擎 |
|-------|-------------|---------------|--------|-----------|---------|---------|
| 2026-05 | 12 | 4 | 1 | 2 | 0 | — |
| 2026-06 | 41 | 17 | 3 | 6 | 1 | — |
```

Rising = you're being surfaced and clicked.

## Crawl tracker (server/CDN logs)

```markdown
| Week | OAI-SearchBot | PerplexityBot | ChatGPT-User | Claude-User | Googlebot |
|------|---------------|---------------|--------------|-------------|-----------|
| W24  | 0 | 0 | 0 | 0 | 120 |   ← AI bots not crawling → reach problem
| W26  | 38 | 22 | 9 | 7 | 130 |  ← fixed CDN block; now crawling
```

## Reading the three together (diagnosis)

| Crawl? | Referral/Citation? | Means | Next |
|---|---|---|---|
| No | No | Reach problem — bots blocked | `ai-crawler-access` |
| Yes | No | Parse/trust/off-site problem | `answer-ready-content` / `earn-mentions` |
| Yes | Rising | Working — keep compounding | maintain + expand questions |

## Cadence

- Citation tracker: **every 2 weeks** (same questions).
- Channel tracker: **monthly**.
- Crawl tracker: **weekly** glance after any reach fix.

Report the **trend**. Never fabricate a citation count or promise a ranking.
