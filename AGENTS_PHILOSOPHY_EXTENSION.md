# AGENTS Philosophy Extension

This document extends `AGENTS.md` with IYASAKA Philosophy, Need-First Principle, and Outward Mindset Guard.

When working on Rasen, agents should read this file together with `AGENTS.md`.

## Required Additional Reading

Before creating or editing sales-critical outputs, read:

1. `framework/00_iyasaka-philosophy.md`
2. `framework/00a_need-first-principle.md`
3. `framework/10_outward-mindset-guard.md`

## Operating Assumption

IYASAKA has deep practical AI experience.
That experience is a strength only when it is converted into practical value for people and companies that need help.

Do not assume customers are behind, careless, or less capable because they have not deeply adopted AI.
Assume they have real constraints, existing responsibilities, limited time, and practical concerns.

## Need-First Rule

Do not start from:

- AI tools
- MCP
- agent architecture
- RAG
- automation frameworks
- product structure
- internal excitement

Start from:

- who needs help
- what situation they are in
- what result would make their work easier
- what small version can be useful now
- where that person can be reached
- how quickly the need can be validated

## Default Workflow Extension

Before the normal Rasen workflow, run:

```text
0. Read philosophy files
1. Identify who needs the output
2. Identify the current situation or pain
3. Define the desired result
4. Define the smallest useful version
5. Decide delivery channel and validation speed
6. Then proceed to Product Kernel / Offer / LP / Campaign
```

## Preferred Guarded Prompts

When available, use these guarded prompts instead of the older base prompts:

- Product scoring: `prompts/score-products-need-first.md`
- Offer generation: `prompts/compile-offer-with-guards.md`
- Need-first review: `prompts/run-need-first-check.md`
- Weekly review: `prompts/weekly-review-with-philosophy.md`

## Agent Review Checklist

Before finalizing any offer, LP, content, DM, sales script, proposal, or delivery template, verify:

```md
## Need-First Check
- Who needs this:
- Situation / pain:
- Desired result:
- Smallest useful version:
- Delivery channel:
- Validation speed:
- What not to build yet:

## Outward Mindset Check
- Customer reality:
- Customer risk:
- Customer effort reduced:
- Not-target / do-not-sell condition:
- Claim / guarantee safety:
- Is this needed, or just impressive:
```

## Block Conditions

Return `NEEDS REVISION` instead of finalizing if:

- the target customer is unclear
- the customer situation is unclear
- the output starts from technology rather than need
- the product is impressive but not clearly useful
- the customer cannot realistically use it
- the offer depends on unverified claims
- the customer is framed as ignorant or behind
- the plan overbuilds before validating the need

## Final Rule

```text
Convert technical depth into respect, usefulness, speed, and results.
```
