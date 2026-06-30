# Interpreting blocks & fixing each platform

## Reading the curl results

```
curl -A "OAI-SearchBot" -I https://yoursite.com/page
```

| Response | Means | Where to fix |
|---|---|---|
| `HTTP/2 200` | Reachable ✅ | nothing |
| `403 Forbidden` | WAF/bot rule is blocking the user-agent | CDN/WAF (layer 2) |
| `429 Too Many Requests` | Rate-limited / bot-throttled | CDN rate rules |
| `503` + JS challenge HTML | Bot-fight / managed challenge | CDN challenge settings |
| `200` but answer missing from body | JS-only rendering | server-render content |

Always test a **real content page**, not just the homepage — rules sometimes
differ by path. Compare against a normal browser UA to confirm the bot is the
discriminator:
```
curl -A "Mozilla/5.0" -I https://yoursite.com/page      # baseline
curl -A "PerplexityBot" -I https://yoursite.com/page    # the bot
```
If baseline is 200 and the bot is 403 → it's a bot-management block.

## Cloudflare (most common culprit)

1. **Security → Bots**: the **"Block AI bots" / "AI Scrapers and Crawlers"**
   toggle blocks GPTBot, ClaudeBot, etc. with a 403. Turn it off, or use the
   "allow specific" option if you want training blocked but retrieval allowed.
2. **Bot Fight Mode** (Security → Bots): challenges many non-browser UAs. It can
   catch AI retrieval bots. Disable, or move to Super Bot Fight Mode with an
   allowlist.
3. **WAF → Custom rules / Managed rules**: look for any rule blocking by
   user-agent or "definitely automated". Add a custom rule **above** them:
   *Skip / Allow when* `User-Agent contains "OAI-SearchBot"` (repeat for
   PerplexityBot, ChatGPT-User, Claude-User, etc.).
4. **Verified-bots-only** rules drop bots Cloudflare hasn't verified — make sure
   your chosen AI bots are exempted.
5. Re-test with the curls. Changes propagate in seconds to a minute.

## AWS WAF / CloudFront

- Check the **AWS WAF Bot Control** managed rule group and `AWSManagedRulesBot...`
  — it can label and block these UAs. Add a rule action **Allow** for requests
  whose `User-Agent` matches your chosen bots, ordered before the block rules.
- Check CloudFront/ALB rate-based rules.

## Akamai / Fastly / Imperva

- **Akamai Bot Manager**: AI crawlers may be categorized and denied; set the
  category/UA to **Allow** (Monitor, not Deny).
- **Fastly**: review any VCL or Next-Gen WAF (Signal Sciences) rules blocking by
  UA or automation signal.
- **Imperva**: check the bot-access policy; allow the AI retrieval bots.

## Vercel / Netlify

- **Vercel**: Firewall / Attack Challenge Mode can challenge bots; add a bypass
  for the chosen user-agents. Also check any `middleware.ts` that blocks by UA.
- **Netlify**: check any edge function / `_headers` / firewall traffic rules.

## After any change

Re-run the full curl set from the SKILL. Every retrieval bot you chose to allow
should now return `200`. Keep a note of what you changed and where — the next
person (or future you) will forget there were two layers.

## 中文要点(出海/国内)

- **最常见的坑**:只改了 `robots.txt`,但 **Cloudflare 的「Block AI bots」开关
  和 Bot Fight Mode 还开着**,AI 爬虫被 403 拦在门外,你还以为是内容问题。
- **两道都要放行**:robots.txt(第一道,只是"君子协议")+ CDN/WAF(第二道,
  真正的拦截)。
- **验证**:用 `curl -A "OAI-SearchBot" -I 你的页面` 看是不是 `200`;是 `403`
  就去 CDN 放行。
- **国内引擎**(豆包/文心/元宝):别在 WAF 里误杀 `Baiduspider`/`Bytespider`/
  `Sogou web spider`;海外 CDN 的地域规则也可能把它们挡了。
- **JS 站注意**:很多 AI 抓取器不跑 JS,确认答案在「查看源代码」里就有,而不是
  渲染后才出现。
