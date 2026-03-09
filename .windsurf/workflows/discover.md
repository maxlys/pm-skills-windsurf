# Workflow: discover

> Run a full product discovery cycle — from ideation through assumption mapping to experiment design
**Input:** <product or feature idea>

---

# Full Discovery Cycle

Run a structured product discovery process that moves from divergent thinking to focused validation. This command chains multiple skills into a single end-to-end workflow.

## Workflow

### Step 0: Load Context

**Stage 1 — Product selection (read folder names only, do not read file contents yet)**

Read only the folder names inside `context/products/` to build the product list.

Ask the user: "Which product is this for?"

Present the options:
- One entry per product folder found in `context/products/`
- **All products**
- **Other**

Wait for the user's selection.

**Stage 2 — Load relevant context only (after selection)**

- **Specific product selected** — read `context/company-overview.md` and all files inside `context/products/<product-name>/`
- **All products selected** — read `context/company-overview.md` and all files in every folder inside `context/products/`
- **Other selected** — read `context/company-overview.md` only, then ask: "Please describe the product or area you want to focus on." Use the description as context for the rest of the workflow.

---

## Step 1: Understand the Discovery Context

Determine whether this is:
- **Existing product** — continuous discovery on a known product with real users
- **New product** — initial discovery for a concept without validated demand

Ask the user:
- What are you exploring? (product idea, feature area, opportunity space)
- What do you already know? (prior research, customer feedback, data)
- What decisions will this discovery inform? (build/kill, prioritize, pivot)

Accept context from uploaded files (research, PRDs, transcripts, data), links, or conversation.

### Step 2: Brainstorm Ideas (Divergent Phase)

Apply the **brainstorm-ideas-existing** or **brainstorm-ideas-new** skill:

- Generate ideas from PM, Designer, and Engineer perspectives
- Present the top 10 ideas with brief rationale
- Ask the user to select 3-5 ideas to carry forward, or accept all

**Checkpoint**: "Here are 10 ideas. Which ones should we stress-test? Pick 3-5, or I can carry all forward."

### Step 3: Identify Assumptions (Critical Thinking Phase)

For each selected idea, apply the **identify-assumptions-existing** or **identify-assumptions-new** skill:

- Surface assumptions across risk categories:
  - **Value**: Will users want this?
  - **Usability**: Can users figure it out?
  - **Feasibility**: Can we build it?
  - **Viability**: Does the business case work?
  - **Go-to-Market** (new products only): Can we reach and convert users?
- Use devil's advocate multi-perspective analysis
- Compile a master list of all assumptions across all ideas

### Step 4: Prioritize Assumptions (Focus Phase)

Apply the **prioritize-assumptions** skill:

- Map assumptions on an Impact × Risk matrix
- Identify the "leap of faith" assumptions — high impact, high uncertainty
- Rank assumptions by test priority
- Group related assumptions that can be tested together

**Checkpoint**: "Here are your riskiest assumptions. Which ones feel most critical to validate first?"

### Step 5: Design Experiments (Validation Phase)

For the top-priority assumptions, apply **brainstorm-experiments-existing** or **brainstorm-experiments-new** skill:

- Design 1-2 experiments per critical assumption
- For existing products: A/B tests, fake doors, prototypes, user tests, data analysis
- For new products: XYZ hypotheses, pretotypes, landing pages, concierge MVPs
- Include success criteria, timeline, and effort for each
- Sequence experiments by dependency and effort

### Step 6: Create Discovery Plan

Compile everything into a discovery plan document:

```
## Discovery Plan: [Topic]

**Date**: [today]
**Product Stage**: [existing/new]
**Discovery Question**: [what we're trying to learn]

### Ideas Explored
[Summary of brainstormed ideas with brief descriptions]

### Selected Ideas for Validation
[3-5 ideas carried forward with rationale]

### Critical Assumptions
| # | Assumption | Category | Impact | Uncertainty | Priority |
|---|-----------|----------|--------|-------------|----------|

### Validation Experiments
| # | Tests Assumption | Method | Success Criteria | Effort | Timeline |
|---|-----------------|--------|-----------------|--------|----------|

### Experiment Details
[For each experiment: hypothesis, setup, measurement, decision criteria]

### Discovery Timeline
Week 1: [experiments]
Week 2: [experiments]
Week 3: [analysis and decision]

### Decision Framework
- If [experiment] succeeds → proceed to [next step]
- If [experiment] fails → [pivot/kill/investigate further]
```

Save the plan as a markdown file to the user's workspace.

### Step 7: Offer Next Steps

- "Want me to **create a PRD** for the top idea?"
- "Should I **design an interview script** to supplement these experiments?"
- "Want me to **set up metrics** to track the experiments?"
- "Should I **estimate effort** and create user stories for the MVP?"

## Notes

- This is a 15-30 minute structured workflow — let the user know upfront
- At each checkpoint, the user can redirect, skip, or go deeper
- If the user has research data, pull insights from it before brainstorming
- The discovery plan should be a living document — offer to update it as experiments run
- For new products, emphasize desirability validation before feasibility
- For existing products, check if there's usage data that can inform assumptions
