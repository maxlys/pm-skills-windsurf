# Workflow: competitive-analysis

> Analyze the competitive landscape — identify competitors, compare strengths and weaknesses, find differentiation opportunities
**Input:** <your product or market>

---

# Competitive Landscape Analysis

Research and analyze your competitive landscape. Identifies direct and indirect competitors, maps positioning, and surfaces differentiation opportunities.

## Workflow

### Step 0: Load Context

Read `context/company-overview.md` to understand the company.

Then read the folder names inside `context/products/` to get the list of available products.

Ask the user: "Which product is this for?"

Present the options:
- One entry per product folder found in `context/products/`
- **All products**
- **Other**

Wait for the user's selection, then:

- **Specific product selected** — read all files in `context/products/<product-name>/` for context
- **All products selected** — read all files in every folder inside `context/products/` for context
- **Other selected** — ask: "Please describe the product or area you want to focus on." Use the description as context for the rest of the workflow.

---

## Step 1: Understand the Competitive Context

Ask:
- What is your product? What category does it compete in?
- Any specific competitors you want analyzed? Or should I identify them?
- What's the lens? (feature comparison, positioning, pricing, go-to-market)
- What will you use this analysis for? (strategy, sales enablement, investor pitch, product roadmap)

### Step 2: Identify Competitors

Apply the **competitor-analysis** skill:

- Identify 5 direct competitors (same category, same buyer)
- Identify 2-3 indirect competitors (different approach, same job-to-be-done)
- Note emerging/disruptive players if relevant
- Use web research to gather current information

### Step 3: Analyze Each Competitor

For each competitor:
- **Positioning**: How they describe themselves, target audience, key messaging
- **Strengths**: What they do well, where they win
- **Weaknesses**: Where they fall short, common complaints
- **Pricing**: Model and price points (if public)
- **Market traction**: Funding, team size, customer base signals
- **Recent moves**: New features, partnerships, pivots

### Step 4: Generate Competitive Analysis

```
## Competitive Analysis: [Your Product/Market]

**Date**: [today]
**Analyzed**: [count] competitors

### Market Overview
[2-3 sentences on market dynamics, trends, and where it's heading]

### Competitive Landscape
| Competitor | Category | Target | Positioning | Strength | Weakness |
|-----------|----------|--------|------------|----------|----------|

### Feature Comparison Matrix
| Capability | Your Product | Competitor A | Competitor B | Competitor C |
|-----------|-------------|-------------|-------------|-------------|

### Positioning Map
[2x2 matrix showing competitive positioning on key dimensions]

### Differentiation Opportunities
1. **[Opportunity]** — [why it's defensible and valuable]
2. ...

### Competitive Threats
1. **[Threat]** — [what to watch for, recommended response]
2. ...

### Recommendations
- **Double down on**: [your unique advantages]
- **Close the gap on**: [table-stakes features you're missing]
- **Ignore**: [competitor moves that aren't worth responding to]
```

Save as markdown.

### Step 5: Offer Next Steps

- "Want me to **create a battlecard** for sales against a specific competitor?"
- "Should I **develop positioning** that differentiates from the top competitors?"
- "Want me to **identify feature gaps** to close and add to the roadmap?"

## Notes

- Web research is used for current competitor data — results are as fresh as available sources
- Distinguish between "table stakes" (must-have to compete) and "differentiators" (must-have to win)
- Don't just list features — analyze *why* competitors make the choices they make
- Pricing intelligence should note whether pricing is public, usage-based, or requires sales contact
- Update this analysis quarterly — competitive landscapes shift fast
