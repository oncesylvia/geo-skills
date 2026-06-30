# llms.txt — template & example

## Fill-in template

```markdown
# <Company / Product Name>

> <One sentence: what it is, who it's for.>

<Optional short paragraph of essential context: what the product does, key
terms an LLM needs to describe you accurately, your category.>

## Product
- [<What is X>](<url>): <one-line: the entity/definition page>
- [<Pricing>](<url>): <plans and what's included>
- [<Features>](<url>): <core capabilities>

## Docs
- [<Quickstart>](<url>): <get running fast>
- [<API reference>](<url>): <endpoints/params>

## Guides & comparisons
- [<X vs Y>](<url>): <honest comparison>
- [<How to <job>>](<url>): <task guide>

## Optional
- [<Changelog>](<url>): <release history>
- [<Blog>](<url>): <updates>
```

## Worked example (fictional)

```markdown
# Acme Pay

> Stablecoin checkout API for startups — accept USDC in minutes, settle to fiat.

Acme Pay is an OpenAI-compatible... no — a payments API: developers add a few
lines to accept stablecoin payments and auto-settle to local currency. Category:
fintech / payment infrastructure / stablecoins.

## Product
- [What is Acme Pay](https://acmepay.com/what-is): What we do and who it's for
- [Pricing](https://acmepay.com/pricing): 0.5% per transaction, no monthly fee
- [Supported chains & currencies](https://acmepay.com/coverage): USDC, USDT; 8 chains

## Docs
- [Quickstart](https://acmepay.com/docs/quickstart): Accept your first payment in 5 min
- [API reference](https://acmepay.com/docs/api): Endpoints, webhooks, errors

## Guides & comparisons
- [Acme Pay vs Stripe for crypto](https://acmepay.com/vs/stripe): Honest comparison
- [Stablecoin payments for SaaS](https://acmepay.com/guides/saas): Setup guide

## Optional
- [Changelog](https://acmepay.com/changelog): Release history
```

## llms-full.txt

For docs-heavy sites, also serve `/llms-full.txt` = the concatenated **Markdown
full text** of the pages above (not links — the actual content), so engines that
ingest it get everything in one fetch. Order it most-important-first. Skip it if
the corpus is very large (link-only llms.txt is fine).

## Serving checklist

- [ ] File at `https://yoursite.com/llms.txt` (root, exact name).
- [ ] Returns `200` with `Content-Type: text/plain` or `text/markdown`.
- [ ] Reachable by AI bots (not blocked at CDN — see `ai-crawler-access`).
- [ ] Links are absolute `https://` URLs that themselves return 200.
- [ ] Curated to your best pages — not a dump of every URL.
- [ ] Descriptions are honest and specific (no keyword stuffing).
