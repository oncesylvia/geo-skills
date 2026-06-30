# Page-type specs — what AI cites and how to build each

Each page must be genuinely useful and honest. Use `answer-ready-content` for the
structure (answer-first, headings, schema). Build the ones you're missing for
high-intent prompts; don't mass-produce thin pages.

## Comparison — "X vs Y"
- **Wins prompts**: "X vs Y", "is X better than Y".
- **Build**: a fair feature/price/use-case table; state where the competitor is
  better too (credibility + legal safety); a clear "choose X if… / choose Y if…"
  summary. Schema: `Article` + the comparison table in HTML.

## Alternatives / "best <category>"
- **Wins**: "<competitor> alternatives", "best <category> tools".
- **Build**: an honest roundup of real options including competitors; include
  yourself fairly, not as a forced #1. Genuinely useful lists get cited; rigged
  ones get distrusted.

## "Best X for <use case / segment>"
- **Wins**: "best <category> for <startups / enterprise / industry>".
- **Build**: segment-specific recommendations with the criteria that matter to
  that segment.

## Glossary / "what is <term>" (highest ROI, most overlooked)
- **Wins**: "what is <term>", definition queries — huge volume, easy to own.
- **Build**: one short page per key term: a crisp first-sentence definition, then
  context, related terms, an example. `DefinedTerm` / `Article` schema. Build a
  glossary hub linking them.

## Use-case / solution pages
- **Wins**: "<category> for <industry/job>", "how to <job>".
- **Build**: the problem, your approach, a concrete example/outcome, a CTA.

## FAQ hub
- **Wins**: long-tail question queries.
- **Build**: every real buyer question, answer-first, grouped; `FAQPage` schema.

## Pricing
- **Wins**: "<brand> pricing", "how much is <category>".
- **Build**: explicit numbers and what's included. "Contact us"-only pricing is
  invisible to AI — publish at least a representative range.

## Integration pages
- **Wins**: "<product> + <tool>", "does <product> work with <tool>".
- **Build**: one page per key integration: what it does, setup, a screenshot.

## Statistics / original research (link magnet)
- **Wins**: "<topic> statistics", and earns inbound links/citations.
- **Build**: real data you can share (a survey, your aggregate metrics);
  citable, dated, with methodology. Others cite it → you become a source.

## Quality bar for every page
- [ ] Answers the target question in the first 1-2 sentences.
- [ ] Specific, sourced, honest (including trade-offs).
- [ ] Matching schema.org (no fake markup).
- [ ] Server-rendered + crawlable.
- [ ] Interlinked + in llms.txt + sitemap.
- [ ] Not one of 200 near-duplicate programmatic pages.
