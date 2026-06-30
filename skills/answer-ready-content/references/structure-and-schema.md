# Structure patterns & schema.org snippets

## Answer-first, before/after

**Before (buried):**
> At Acme, we've spent years reimagining how modern businesses think about
> payments in an increasingly digital world. Our mission is… [3 paragraphs] …
> and pricing starts at just 0.5%.

**After (answer-first):**
> **Acme Pay charges 0.5% per transaction, with no monthly fee.** Volume
> discounts begin at $1M/mo. Here's how that compares and what's included: …

## Question-shaped headings

Turn marketing headers into the queries people type:
- "Our Pricing" → "How much does Acme Pay cost?"
- "Why Acme" → "Acme Pay vs Stripe: which is better for stablecoin payments?"
- "Security" → "Is Acme Pay safe? How are funds protected?"

## Comparison table (highly liftable)

```markdown
| | Acme Pay | Stripe |
|---|---|---|
| Stablecoin settlement | Native (USDC/USDT) | Via third party |
| Fee | 0.5%, no monthly | 2.9% + 30¢ |
| Setup time | ~5 min | ~1 day |
```
Keep it honest and accurate — a comparison that overstates gets you distrusted
(and is a legal risk). State your real trade-offs too.

## FAQ block

```markdown
## FAQ
**Does Acme Pay support recurring billing?** Yes — subscriptions via the
/subscriptions endpoint, billed in USDC.

**Which chains are supported?** 8 chains incl. Ethereum, Base, Solana.
```
Pair with `FAQPage` schema below.

## schema.org JSON-LD snippets

Place in `<head>` or end of `<body>`. **Schema must match visible content.**

### Organization (entity definition)
```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "Organization",
  "name": "Acme Pay",
  "url": "https://acmepay.com",
  "description": "Stablecoin checkout API for startups — accept USDC, settle to fiat.",
  "sameAs": [
    "https://twitter.com/acmepay",
    "https://github.com/acmepay",
    "https://www.linkedin.com/company/acmepay"
  ]
}
</script>
```

### FAQPage
```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "FAQPage",
  "mainEntity": [
    {
      "@type": "Question",
      "name": "How much does Acme Pay cost?",
      "acceptedAnswer": { "@type": "Answer",
        "text": "0.5% per transaction, no monthly fee. Volume discounts from $1M/mo." }
    }
  ]
}
</script>
```

### Product / Offer
```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "Product",
  "name": "Acme Pay",
  "description": "Stablecoin checkout API.",
  "brand": { "@type": "Brand", "name": "Acme Pay" },
  "offers": { "@type": "Offer", "priceCurrency": "USD", "price": "0",
    "description": "0.5% per transaction, no monthly fee" }
}
</script>
```

Also useful: `Article` (blog/guides), `HowTo` (step guides), `BreadcrumbList`
(navigation). Validate with a schema validator before shipping.

## Page types AI loves to cite (build the ones you're missing)

- **"What is X"** — the entity/definition page.
- **"X vs Y" / "X alternatives"** — comparisons.
- **"Best X for Y"** — roundups/listicles (be genuinely useful, include yourself
  honestly among real options).
- **"How to <job>"** — task guides with steps.
- **Pricing** — explicit numbers, not "contact us" only.

## The non-negotiable

Everything above is about making a **true** answer easy to find and quote. Fake
schema, hidden text, invented stats, or bot-only content = cloaking/deception.
It's against engine policies, it gets penalized, and it's not in this toolkit.
