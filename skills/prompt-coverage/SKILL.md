---
name: prompt-coverage
description: Map the full set of prompts your buyers ask AI across the journey, and measure your share-of-voice against competitors across that whole space (not just a few queries). Use when someone asks "what questions are buyers asking AI in my category", "share of voice in AI search", "which AI prompts should I win", "build a prompt map", or wants a strategic view of AI visibility instead of spot checks. The strategy layer above geo-measure.
---

# Prompt coverage & share-of-voice

`geo-measure` tracks a handful of target questions. This skill is the **strategy
layer above it**: map the *whole* prompt space your buyers use across the
journey, see where you appear vs. competitors (share-of-voice), and decide which
prompts are worth winning. Citations on the wrong prompts don't drive business.

Read `shared/references/ai-engines.md` and `shared/references/geo-principles.md`
first. See `references/prompt-taxonomy.md` for the framework.

## Step 1 — Build the prompt map

Enumerate how buyers actually ask AI in your category, by journey stage:

- **Awareness / problem** — "how do I <solve problem>", "why is <pain> happening"
- **Solution / category** — "best way to <do job>", "tools for <use case>",
  "what is <category>"
- **Comparison / consideration** — "best <category> for <segment>",
  "<competitor> alternatives", "<A> vs <B>", "is <approach> worth it"
- **Decision / brand** — "<brand> pricing", "is <brand> good", "<brand> vs <X>"
- **Post-purchase** — "how to <do task> with <product>", "<product> not working"

Generate the realistic phrasings for each (vary wording — engines are sensitive).
Prioritize prompts with **buying intent**, not just volume.

## Step 2 — Measure share-of-voice across the map

For each prompt, run the engines and record **who** gets cited/recommended —
you, which competitors, which third-party sources. Then compute a simple
share-of-voice: in your priority prompt set, what % do you appear in vs. each
competitor? (Use the `geo-measure` tracker, extended with a competitor column.)

## Step 3 — Find the strategic gaps

- **High-intent prompts you're absent from** → priority targets.
- **Prompts a competitor dominates** → run `citation-gap` on those.
- **Prompts where a third-party (Reddit/roundup) owns the answer** → `earn-mentions`.
- **Whole prompt clusters with no good answer anywhere** → green-field: create the
  definitive page (→ `citable-pages`).

## Step 4 — Prioritize

Rank target prompts by **intent × winnability × your current absence**. Don't
chase low-intent or already-won prompts. Output a focused roadmap, not a list of
500 queries.

## Output

- The prompt map (journey stage × prompts) for the category.
- A share-of-voice read: you vs. each competitor across the priority set.
- A ranked **target-prompt roadmap** with the move for each (which skill).
- Honesty note: share-of-voice is sampled and probabilistic — track the trend,
  don't report it as a precise rank.

## Bilingual / 出海 (中文)

国内买家的提问习惯、用词、引擎都不同——单独建一套中文 prompt map(豆包/文心/元宝)。
出海:中英两套提示词地图各自测 share-of-voice,别合并。

## Refuse / push back when

- Asked to mass-produce thin pages for every prompt (programmatic AI-slop) →
  refuse; target high-intent prompts with genuinely useful pages, not spam.
