---
name: agent-ready
description: Make your business not just citable but actionable by AI agents — clean machine-readable product/pricing data, public APIs, an MCP server, and agentic-commerce readiness so agents can compare, recommend, and transact with you. Use when someone asks "how do I make my product work with AI agents", "agentic commerce readiness", "MCP for my business", "let AI agents buy/book from us", or wants to prepare for AI that acts, not just answers. The frontier of GEO.
---

# Agent-ready (the frontier of GEO)

GEO so far = getting AI to **mention** you. The next step, already arriving, is AI
**acting** — agents that browse, compare, choose, and **transact** on a user's
behalf. Being citable gets you into the consideration set; being **agent-ready**
gets you chosen and completed. This skill prepares a business for that.

Read `shared/references/geo-principles.md`,
`shared/references/geo-governance.md`, and `shared/references/ai-engines.md`
first. This is a fast-moving frontier — standards are emerging and not settled;
treat recommendations as directional and verify current specs. Be honest about
that uncertainty rather than overselling.

## The agent-readiness layers

### 1. Machine-readable facts (the table stakes)
Agents act on structured data, not marketing prose.
- Clean, current **product, pricing, availability, and policy** data in
  structured form (schema.org `Product`/`Offer`, JSON feeds, an API).
- Consistent across every surface an agent might read (site, listings, feeds) —
  contradictions make agents drop you.
- This overlaps with `answer-ready-content` schema but goes further: the *facts*
  must be queryable and trustworthy, not just present in prose.

### 2. A programmatic interface (so an agent can do more than read)
- A documented **public API** for the actions that matter (search catalog, check
  price/availability, create a quote/booking/order).
- Clear, machine-readable **docs** (OpenAPI), and a great `llms.txt` pointing to
  them.
- Consider an **MCP server** exposing safe, read-or-act tools to AI clients —
  increasingly how agents connect to a business.

### 3. Transactability (so an agent can complete)
- A path for an agent (with user authorization) to **complete an action** —
  checkout, booking, sign-up — with clear auth, confirmation, and limits.
- Watch the **emerging agentic-commerce / agent-payment standards** and protocols;
  align as they stabilize. (This is exactly the space agentic-payment
  infrastructure addresses.)

### 4. Trust & control (so you stay safe)
- Authentication and authorization for agent actions; rate limits; audit logs.
- Clear policies an agent can read (returns, fees, terms).
- Guardrails: agents act on *your* data — keep it accurate, and never expose
  actions you don't want automated.

## How to run it

1. **Assess** where the business is across the four layers (most are at layer 1).
2. **Start with facts**: get product/pricing/availability clean, structured, and
   consistent — the cheapest, highest-value step.
3. **Expose docs/API** if agents need to *do* something; add `llms.txt` → docs;
   consider MCP for the read/act tools that are safe.
4. **Plan transactability** deliberately with auth + limits; don't bolt on
   payments without controls (see `geo-governance.md`).
5. **Stay current**: the standards are moving — revisit as they settle.

## Output

- A readiness assessment across the four layers + the next concrete step.
- The cheapest high-value move (almost always: clean, consistent structured
  product/pricing data).
- An honest note on what's stable vs. still-emerging in agentic commerce.

## Bilingual / 出海 (中文)

国内 agent 生态(各家助手/小程序/支付)与海外不同,但四层逻辑一致:**先把
产品/价格/库存做成机器可读且一致**,再谈接口与交易。跨境尤其注意支付与合规
(见 `geo-governance.md`)。

## Refuse / push back when

- Asked to expose transaction/payment actions without auth, limits, or the user's
  authorization → refuse; that's a security and compliance risk. Build the
  controls first.
- Asked to overstate that "agentic commerce is solved" → be honest: it's an
  emerging frontier; prepare the foundations, don't oversell certainty.
