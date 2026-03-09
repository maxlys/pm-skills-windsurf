# Workflow: analyze-cohorts

> Perform cohort analysis on user data — retention curves, feature adoption, and engagement trends
**Input:** <data file or description of what to analyze>

---

# Cohort Analysis

Analyze user retention and engagement patterns by cohort. Upload your data or describe what you need, and get retention curves, feature adoption trends, and actionable insights.

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

## Step 1: Accept Data or Define Analysis

Two paths:
- **With data**: User uploads a CSV/spreadsheet with user-level data (user_id, signup_date, activity_date, event_type, etc.)
- **Without data**: User describes the analysis they need → generate the SQL query and analysis framework

### Step 2: Define Cohorts

Ask:
- What defines a cohort? (signup week/month, acquisition channel, plan tier, first feature used)
- What is the retention event? (login, core action, any activity, purchase)
- What time granularity? (daily, weekly, monthly)
- What time range?

### Step 3: Analyze

Apply the **cohort-analysis** skill:

**If data is provided:**
- Process the data using Python (pandas) to create cohort tables
- Calculate retention rates per cohort per period
- Generate retention curves
- Identify patterns: improving/declining cohorts, seasonal effects, anomalies
- Compare feature adoption across cohorts

**If describing an analysis:**
- Design the cohort analysis framework
- Generate SQL queries to extract the data
- Create a template spreadsheet for the analysis
- Define the metrics and visualization approach

### Step 4: Generate Report

```
## Cohort Analysis: [Description]

**Date**: [today]
**Cohort definition**: [e.g., signup month]
**Retention event**: [e.g., completed a project]
**Granularity**: [weekly/monthly]

### Retention Table
| Cohort | Size | Week 1 | Week 2 | Week 3 | ... | Week 12 |
|--------|------|--------|--------|--------|-----|---------|

### Key Findings
1. **[Finding]** — [supporting data]
2. ...

### Cohort Comparison
- **Best-performing cohort**: [which, why]
- **Worst-performing cohort**: [which, why]
- **Trend**: [improving/declining/stable over time]

### Retention Benchmarks
| Period | Your Rate | Industry Benchmark | Gap |
|--------|----------|-------------------|-----|

### Recommendations
1. [What to investigate or change based on findings]
2. ...

### Follow-Up Queries
[SQL queries for deeper investigation]
```

If data was provided, save analysis as both markdown report and CSV/spreadsheet.

### Step 5: Offer Next Steps

- "Want me to **segment this further** by another dimension?"
- "Should I **set up metrics alerts** based on these retention thresholds?"
- "Want me to **design experiments** to improve retention for the weakest cohort?"

## Notes

- Cohort analysis is only as good as the retention event definition — push for a meaningful action, not just "logged in"
- Early cohorts often look different due to founding user bias — note this when comparing
- If retention is calculated using a Python script, save the script so the user can re-run with new data
- Seasonal effects can masquerade as trends — flag if cohort differences might be calendar-driven
