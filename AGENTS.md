# AGENTS.md

This document defines how Codex, Claude Code, and project-specific agents should use Rasen.

Rasen is the Growth OS for IYASAKA. It turns multiple products into clear offers, landing pages, lead magnets, content, sales scripts, delivery templates, and weekly improvement loops.

## Current Phase

Rasen is currently in the implementation and operating-design phase.

Do not assume that Rasen is already a full MCP server or SaaS product.

Current intended use:

```text
GitHub Markdown / YAML repository
  ↓
Codex / Claude Code reads and updates structured files
  ↓
Human reviews sales-critical outputs
  ↓
Campaigns are run manually or semi-manually
  ↓
Reusable patterns are later MCP/SaaS candidates
```

## Repository Role

Rasen is the top-level revenue orchestration repository.

Project repositories manage product implementation, code, technical specifications, and delivery work.

Rasen manages revenue-side context:

- product definitions
- product prioritization
- Hormozi-style offer design
- LP copy
- lead magnets
- diagnosis forms
- content plans
- sales scripts
- delivery templates
- metrics
- weekly reviews
- campaign learning

## Cross-Repository Model

Use this separation:

```text
Rasen repo
  = offer, growth, sales, content, campaign, and feedback loop

Project repo
  = product implementation, technical design, code, issue execution, delivery artifacts
```

A project-specific agent should read Rasen when it needs business context.

Example:

```text
omotenasu-ai repo
  ↓ reads
rasen/products/omotenasu-ai/product.yaml
rasen/framework/*
rasen/prompts/*
  ↓ creates or updates
LP, offer, campaign, or project implementation tasks
```

## Project Repo Connection

Each project repo may include a small `rasen.yaml` file at its root.

Example:

```yaml
rasen_product_id: omotenasu-ai
growth_os_repo: watchout/rasen
current_stage: offer_design
primary_offer: 30日AI客室コンシェルジュ導入パック
owner: IYASAKA
human_approval_required: true
```

If a project repo has `rasen.yaml`, the agent should treat Rasen as the source of truth for growth-side context.

## Core Files To Read First

When working inside this repository, read in this order:

1. `README.md`
2. `FRAMEWORK.md`
3. `products/index.yaml`
4. Target product: `products/{product_id}/product.yaml`
5. Relevant framework module under `framework/`
6. Relevant prompt under `prompts/`
7. Relevant campaign under `campaigns/`
8. Existing metrics or weekly reports if present

## Product Workflow

For each product, follow this sequence:

```text
1. Product Kernel
2. Market Lens
3. Offer Compiler
4. Asset Factory
5. Lead Engine
6. Sales Pipeline
7. Delivery System
8. Feedback Loop
```

Do not skip directly to content generation unless the offer is clear.

## Prioritization Rule

When multiple products exist, do not deepen all products at once.

Default flow:

```text
1. Register all products thinly with product.yaml
2. Score products using prompts/score-products.md
3. Pick top 1-3 products
4. Deepen only the top product first
5. Run a 30-day campaign
6. Record learnings
7. Expand to the next product
```

## Current Focus Product

The current first focus product is:

```text
products/ai-risk-diagnosis/
```

Its current campaign is:

```text
campaigns/2026-06-ai-risk-diagnosis/
```

Prioritize this product before expanding to OmotenasuAI, Mieru Board, weak current maintenance, Haishin Plus, or Haleimo.

## Agent Roles

### 1. Priority Scorer

Reads all product definitions and ranks products by:

- short-term monetization
- price potential
- recurring revenue potential
- existing assets
- sales accessibility
- future strategic value
- implementation burden

Uses:

```text
prompts/score-products.md
```

### 2. Offer Architect

Turns a product into a Hormozi-style offer.

Uses:

```text
prompts/compile-offer.md
```

Outputs:

```text
products/{product_id}/offer.md
```

### 3. LP Writer

Creates landing page copy after the offer is clear.

Uses:

```text
prompts/generate-lp.md
```

Outputs:

```text
products/{product_id}/lp.md
```

### 4. Content Generator

Creates X posts, note outlines, and short video scripts.

Uses:

```text
prompts/generate-posts.md
```

Outputs:

```text
campaigns/{campaign_id}/posts.md
```

### 5. Campaign Planner

Creates 30-day sales campaigns.

Uses:

```text
prompts/create-campaign.md
```

Outputs:

```text
campaigns/{campaign_id}/campaign-brief.md
```

### 6. Sales Operator

Creates sales scripts, qualification rules, objection handling, and follow-up templates.

Outputs:

```text
products/{product_id}/sales-script.md
products/{product_id}/objections.md
```

### 7. Delivery Designer

Creates delivery templates, report formats, and next-offer paths.

Outputs:

```text
products/{product_id}/delivery-template.md
products/{product_id}/next-offer.md
```

### 8. Weekly Reviewer

Reviews campaign performance and recommends improvements.

Uses:

```text
prompts/weekly-review.md
```

Outputs:

```text
reports/weekly/{date}-{campaign_id}.md
```

## Human Approval Gates

The agent must not perform or finalize the following without explicit human approval:

- sending DMs
- sending proposals
- changing prices
- promising deadlines
- making guarantee claims
- using customer names
- publishing case studies
- signing contracts
- sending invoices
- accepting scope changes
- making legal, tax, financial, or compliance claims
- presenting unverified achievements as facts

The agent may draft these items, but should mark them as:

```text
HUMAN APPROVAL REQUIRED
```

## Claims and Evidence Rules

When writing LPs, offers, posts, or proposals:

- Do not invent customer results.
- Do not claim verified case studies unless they exist.
- Separate facts, assumptions, and hypotheses.
- Use cautious wording for untested offers.
- Prefer beta, pilot, diagnostic, or review language when the offer is still being validated.
- Avoid overpromising implementation results for diagnostic products.

## Sales Safety Rules

For platform-based sales such as Fiverr or Upwork:

- Do not automate final submission.
- Do not move conversations outside the platform unless rules allow and the human approves.
- Keep scope, deliverables, and expectations documented.
- Prioritize safety and quality over response speed and volume.
- If a request contains unclear external links or unusual requirements, ask for the key details to be pasted into the platform conversation.

## File Update Rules

### Product Definitions

Update `product.yaml` when core assumptions change:

- target
- pain
- offer seed
- price seed
- lead magnet
- backend offer
- CTA

### Offer Files

Update `offer.md` when:

- the target changes
- objections appear repeatedly
- pricing changes
- bonuses change
- the campaign message changes

### LP Files

Update `lp.md` only after `offer.md` is stable enough to support it.

### Campaign Files

Every campaign should have:

- campaign brief
- posts
- DM or outreach script if needed
- weekly reviews
- final retrospective

### Metrics Files

Each product should eventually have:

```text
products/{product_id}/metrics.md
```

Track:

- posts
- impressions if available
- replies
- leads
- calls
- proposals
- orders
- revenue
- objections
- customer voice
- next actions

## Default Execution Order For Codex / Claude Code

When asked to work on Rasen, default to this order:

```text
1. Check products/index.yaml
2. Identify target product
3. Read product.yaml
4. Read relevant campaign brief if it exists
5. Generate or update offer.md
6. Generate or update lp.md
7. Generate or update lead-magnet.md
8. Generate or update diagnosis-form.md
9. Generate or update sales-script.md
10. Generate or update delivery-template.md
11. Generate or update campaign posts
12. Create weekly review template
```

## First Recommended Task

For the current state of the repository, the next recommended task is:

```text
Use prompts/compile-offer.md to create products/ai-risk-diagnosis/offer.md.
```

Then:

```text
Use prompts/generate-lp.md to create products/ai-risk-diagnosis/lp.md.
```

Then:

```text
Use prompts/generate-posts.md to create campaigns/2026-06-ai-risk-diagnosis/posts.md.
```

## Future MCP Direction

Rasen may later become a Growth OS MCP.

Potential tools:

```text
list_products
score_products
get_product_context
compile_offer
generate_lp
generate_campaign
review_metrics
create_project_tasks
```

Do not implement MCP before the Markdown/YAML workflow has produced real learning from at least one campaign.

## Definition of Done For Rasen MVP

Rasen MVP is usable when:

- all major products have product.yaml
- one focus product has offer.md
- one focus product has lp.md
- one campaign has posts.md
- one lead magnet exists
- one sales script exists
- one delivery template exists
- one weekly review has been completed
- at least one real customer reaction or sales conversation has been recorded
