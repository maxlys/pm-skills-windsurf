# Workflow: review-resume

> Comprehensive PM resume review against 10 best practices — structure, impact metrics, keywords, and actionable feedback
**Input:** <resume as text or file>

---

# PM Resume Review

Get a thorough resume review against product management best practices. Evaluates structure, impact metrics, keyword optimization, and provides specific improvement suggestions with examples.

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

## Step 1: Accept the Resume

Accept as pasted text, uploaded PDF, or DOCX file. Parse the full content.

### Step 2: Evaluate Against 10 Best Practices

Apply the **review-resume** skill:

1. **Impact Metrics**: Are accomplishments quantified? (revenue, users, conversion rates)
2. **XYZ+S Formula**: "Accomplished [X] as measured by [Y], by doing [Z] using [S skill/tool]"
3. **PM-Specific Language**: Uses product terminology (shipped, led discovery, defined strategy)
4. **Structure & Readability**: Clear sections, consistent formatting, scannable
5. **Keyword Optimization**: Matches common PM job description keywords
6. **Story Arc**: Shows career progression and increasing scope
7. **Brevity**: One page (junior), two pages max (senior). No fluff.
8. **Relevance**: Experience tailored to PM roles, not generic
9. **Technical Credibility**: Demonstrates working with engineering, data, design
10. **Leadership Signals**: Cross-functional influence, stakeholder management, mentoring

### Step 3: Generate Review

```
## Resume Review

**Overall Score**: [X/10]
**Strongest area**: [which best practice]
**Biggest opportunity**: [which best practice]

### Scorecard
| # | Best Practice | Score | Assessment |
|---|-------------|-------|-----------|
| 1 | Impact Metrics | [/10] | [brief assessment] |
| 2 | XYZ+S Formula | [/10] | [brief assessment] |
| ... | ... | ... | ... |

### Top 3 Improvements

**1. [Most impactful change]**
- Current: "[exact text from resume]"
- Suggested: "[improved version]"
- Why: [reasoning]

**2. [Second improvement]**
[same format]

**3. [Third improvement]**
[same format]

### Section-by-Section Feedback
[Specific notes for each resume section: summary, experience, education, skills]

### Missing Elements
[What's absent that should be present for a PM resume]

### Keywords to Add
[PM-relevant keywords missing from the resume that appear in typical job descriptions]
```

### Step 4: Offer Next Steps

- "Want me to **tailor this resume** to a specific job description?"
- "Should I **rewrite specific bullet points** using the XYZ+S formula?"
- "Want me to **generate a cover letter** based on this resume?"

## Notes

- Be specific and constructive — "add metrics" is unhelpful, "change 'improved onboarding' to 'reduced onboarding drop-off by 23% (450 → 347 users/month)'" is actionable
- PM resumes should emphasize outcomes over outputs, influence over authority
- ATS (Applicant Tracking System) optimization matters — mention relevant keywords naturally
- Different PM levels have different expectations: APM = potential, Senior PM = impact, Director+ = scale
