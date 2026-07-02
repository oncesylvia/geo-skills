# GEO score rubric (4 dimensions, honest data)

Equal-weight 0-100 score. Structure is simple on purpose (four 25% dimensions);
the discipline is in the **data**: anchor every dimension to a real check or
search, and label anything sampled/estimated. Never score off an AI-simulated
"mention rate".

## Anchoring bands (real finding → score)

### 1. AI visibility (25%)
*How present are you in AI answers for the prompts your buyers use?*
- Cited/named across most target prompts → **80–95**
- Appears sometimes / mentioned but not linked → **50–79**
- Rarely appears → **30–49**
- Absent from the answer set (verified) → **15–29**
> Source: run the prompts on the engines, or search the sources they cite. Small
> sample → label "sampled". Engine you can't query → "needs manual check".

### 2. Infrastructure (25%) — fully objective
*Can AI reach and parse you?*
- Bots 200 + server-rendered + llms.txt + sitemap + schema → **85–95**
- Reachable but missing 1–2 (JS-render / no schema / no llms.txt) → **60–84**
- Reachable but answer not in HTML / thin → **40–59**
- Blocked (403) or unreachable → **15–39**
> Source: `ai-crawler-access` + `technical-foundations` checks (curl status codes,
> View-Source, presence of llms.txt/sitemap/schema). This dimension is measured,
> not estimated.

### 3. Competitive (25%)
*Versus who AI cites today.*
- Cited more/as much as rivals for target prompts → **75–95**
- Real differentiation but low awareness → **50–74**
- Behind on both citation and differentiation → **25–49**
> Source: `citation-gap` — who's cited now, is your differentiation real, is your
> awareness present.

### 4. Reputation (25%)
*Do trusted third parties vouch for you?*
- Real, positive third-party presence (reviews/threads/roundups) → **80–100**
- Some presence, mixed/neutral → **55–79**
- Thin / no presence (a risk, esp. for trust-sensitive products) → **40–54**
- Real negative overhang → **20–39**
> Source: search Reddit/知乎/V2EX/review/roundup sites for real mentions. No
> presence = thin, not "70 by default".

## Overall
Average of the four. **≥90 excellent / ≥75 good / ≥60 fair / <60 poor.** ±5 tuning.

## The honesty rules (the differentiator)
- Infrastructure is always measured → real.
- AI-visibility & reputation are *observed/searched* → report as sampled if the
  sample is small; mark un-measurable engines "needs manual check".
- Never fabricate a mention-rate percentage or per-engine number.
- The score is a **prioritization heuristic**, not a ranking guarantee — say so.

## Reading the shape (common patterns)
- **High infra, low visibility/reputation** → "technically excellent, commercially
  invisible": the fix is off-site presence + content, not the website.
- **Low infra** → fix reach/render first; nothing else scores until AI can see you.
- **Low competitive, ok elsewhere** → you're present but a rival owns the prompts →
  `citation-gap` + `citable-pages`.
