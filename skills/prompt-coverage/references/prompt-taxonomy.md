# Prompt taxonomy — mapping the buyer's AI questions

Buyers ask AI different things at different stages. Map all of it, then target
the high-intent prompts you're absent from. Build this per language/market.

## By journey stage

### Awareness (problem-aware, not solution-aware)
- "why is <pain/symptom> happening"
- "how do I <achieve outcome>"
- "is it normal that <problem>"
- Intent: low-to-mid. You win these with genuinely helpful guides; brand rarely
  named yet, but you can become the cited source.

### Solution / category (looking for an approach)
- "what is <category>"
- "best way to <do job>"
- "tools / software for <use case>"
- "how to <do job> without <constraint>"
- Intent: mid. This is where category-defining and "what is X" pages get cited.

### Comparison / consideration (evaluating options)
- "best <category> for <segment/use case>"
- "<competitor> alternatives"
- "<A> vs <B>"
- "is <product/approach> worth it"
- "cheapest / most secure / easiest <category>"
- Intent: high. Comparison + "best for" + alternatives pages win here.

### Decision / brand (you're on the shortlist)
- "<brand> pricing / cost"
- "is <brand> legit / safe / good"
- "<brand> reviews / complaints"
- "<brand> vs <competitor>"
- "does <brand> do <feature>"
- Intent: highest. Also the zone `ai-brand-monitor` defends (accuracy matters most here).

### Post-purchase / retention
- "how to <task> with <product>"
- "<product> <error> fix"
- "<product> integration with <X>"
- Intent: existing customers; good docs reduce churn and get cited as support.

## Phrasing variants

For each prompt, list 3-5 real phrasings (engines are wording-sensitive):
> "best stablecoin payment API" / "top stablecoin payment providers for startups"
> / "what's the easiest way to accept USDC on my site"

## Intent scoring (prioritize)

| Signal | Weight |
|---|---|
| Buying intent (decision/comparison > awareness) | high |
| You're currently absent | high |
| Winnable (you can genuinely be the best answer) | high |
| Volume / how often asked | medium |

Target the top cells. Ignore low-intent + already-won. A focused 20-prompt
roadmap beats tracking 500.

## Share-of-voice sheet (extend the geo-measure tracker)

```csv
prompt,stage,intent,engine,you_cited,competitorA,competitorB,third_party_owner,date
best stablecoin payment API for startups,comparison,high,Perplexity,no,yes,no,reddit,2026-06-22
<brand> pricing,decision,high,ChatGPT,yes,—,—,own-site,2026-06-22
```

SoV = (# priority prompts you appear in) / (total priority prompts), tracked over
time, per engine. It's sampled and probabilistic — report the trend.
