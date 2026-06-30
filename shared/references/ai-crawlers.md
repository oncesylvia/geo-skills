# AI crawlers & user-agents (the list that matters)

To be cited by an AI engine, its crawler must be able to **reach** your pages.
Two different jobs use different bots, and you usually want to allow the
**retrieval/citation** bots even if you're unsure about the **training** ones.

> Verify current user-agent strings against each vendor's official docs before
> relying on them — vendors add and rename bots often. Treat this as a starting
> map, not gospel.

## The bots, by purpose

### Retrieval / live citation (allow these — this is what gets you cited)
These fetch a page in real time to answer a user and **cite the source**.
Blocking them = you can't be cited.

- **OAI-SearchBot** — OpenAI, powers ChatGPT search results & citations
- **ChatGPT-User** — OpenAI, fires when a user's ChatGPT browses to your page
- **PerplexityBot** / **Perplexity-User** — Perplexity indexing & live fetch
- **Claude-User** / **Claude-SearchBot** — Anthropic, user-triggered & search fetch
- **Googlebot** — Google's regular crawler **also feeds AI Overviews / AI Mode**
  (you cannot opt out of AI Overviews separately from normal Search)

### Training crawlers (allowing is optional — your call)
These collect data to train models. Allowing can increase your presence in a
model's "memory"; blocking is a values/IP choice and won't stop live citation
if you still allow the retrieval bots above.

- **GPTBot** — OpenAI training
- **ClaudeBot** — Anthropic training
- **Google-Extended** — gates Gemini training & grounding (NOT regular Search)
- **CCBot** — Common Crawl (feeds many models' training sets)
- **Applebot-Extended** — Apple Intelligence training (Applebot itself is Search)
- **Amazonbot**, **meta-externalagent** (Meta), **cohere-ai**, **Bytespider**
  (ByteDance — aggressive; many sites rate-limit it)

### China AI search (for 出海 / 国内双向)
If you target Chinese AI answer engines, also consider their fetchers:
**Baiduspider** (文心/百度 AI), **Bytespider** (豆包/抖音), **Sogou web spider**
(腾讯元宝 lineage), plus 360. 国内多走自有搜索索引,放行逻辑类似:别在 CDN/WAF
误杀它们。

## The trap most people miss: two layers, not one

robots.txt is **advisory** and only the first gate. The silent killer is your
**CDN/WAF returning 403/429 to AI bots** before robots.txt even matters:

1. **robots.txt** — don't `Disallow` the bots you want; an over-broad
   `Disallow: /` or a blanket `User-agent: *` block hits them too.
2. **CDN / WAF / bot management** — Cloudflare's "Block AI bots" /
   "AI Scrapers & Crawlers" toggle, Bot Fight Mode, and some managed rules
   return 403 to these user-agents **regardless of robots.txt**. Akamai,
   Fastly, AWS WAF, Vercel have equivalents. **You must allowlist there too.**

If you only fix robots.txt and the CDN is still blocking, you stay invisible to
AI and never see why. Always verify **both layers** (see `ai-crawler-access`).

## How to verify a bot can actually reach you

- `curl -A "OAI-SearchBot" -I https://yoursite.com/key-page` → expect `200`,
  not `403`/`429`/a challenge page.
- Repeat with `PerplexityBot`, `ChatGPT-User`, `Claude-User`, `Googlebot`.
- Check server/CDN logs for these user-agents: are they getting 200s?
- Beware JS-only pages: many AI fetchers don't run JavaScript well — confirm the
  answer content is in the **server-rendered HTML** (View Source, not DevTools).
