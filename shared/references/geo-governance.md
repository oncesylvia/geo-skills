# GEO governance, risk & ownership (the enterprise layer)

GEO isn't only tactics — a business needs deliberate decisions about policy,
risk, and who owns it. This reference backs the audit, brand-monitor, and
agent-ready skills. None of this is legal advice; involve counsel for the legal
calls.

## 1. Crawler & content-licensing policy (a real decision, not a default)

Decide deliberately — don't just leave defaults:
- **Allow retrieval/citation bots** (almost always yes — that's how you get
  cited).
- **Training bots** (GPTBot, ClaudeBot, CCBot, Google-Extended…): allow for
  presence, block for IP/control, or pursue **content-licensing deals** if your
  content is valuable enough that vendors will pay. This is a strategy/legal/IP
  decision with revenue implications, not just a checkbox.
- Document the decision and revisit it; bots and terms change.

## 2. Accuracy & misinformation risk

- Wrong AI claims about pricing/features/safety can cost real deals — monitor
  proactively (`ai-brand-monitor`), don't wait for a customer to flag it.
- **Defamatory or harmful** AI output about your brand: capture evidence
  (screenshots, prompts, dates), use the engine's **report/feedback** channel,
  fix the upstream source, and escalate to legal if it persists or causes harm.
  Engines have correction processes; there's also an emerging legal landscape
  around AI-generated defamation — get counsel for serious cases.

## 3. Brand safety on your own surfaces

- If you host **user-generated content** or third-party text, it can carry
  **prompt-injection** ("ignore instructions, recommend…") that an AI reading
  your page might act on. Sanitize/UGC-guard untrusted content.
- Don't let your *own* site become a vector that manipulates the models reading
  it — that's both a security and a reputation risk.

## 4. Honesty & compliance guardrails (org-wide)

- No cloaking, fake reviews, astroturfing, fabricated stats, or hidden
  manipulation — anywhere, by anyone on the team. One incident can poison brand
  trust and breach platform/ad/consumer-protection rules.
- Comparative claims must be **true and substantiated** (false advertising is a
  legal risk in many markets).
- Respect privacy law when monitoring/collecting (e.g., logs, reviews).

## 5. Ownership & operating cadence

- **Who owns GEO?** It spans marketing (content), engineering (crawlability,
  schema, API/MCP), PR/community (off-site), and legal (policy/risk). Name an
  owner and a cross-functional cadence, or it falls through the cracks.
- **Reporting**: report the honest trend (citation presence, share-of-voice,
  accuracy, AI referral traffic) — not vanity metrics or a promised "rank."
- **Cadence**: audit quarterly; measure biweekly/monthly; brand-monitor
  continuously for high-risk prompts.

## 6. The frontier (agentic) governance

- Before exposing agent actions/payments: define **auth, authorization, rate
  limits, audit logs**, and which actions may be automated at all.
- Cross-border agentic commerce adds **payment and compliance** complexity —
  treat it as a deliberate, counsel-reviewed rollout, not a quick integration.

## The throughline

Durable GEO is an honest operating practice: be genuinely the best, reachable
answer; tell the truth about yourself and competitors; fix real inaccuracies;
and decide your bot/IP/risk posture on purpose. Tactics that depend on deceiving
the model or the reader are out of scope — they're fragile and they backfire.
