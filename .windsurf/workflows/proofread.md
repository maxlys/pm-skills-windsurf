# Workflow: proofread

> Check grammar, logic, and flow in any text — targeted fixes without rewriting
**Input:** <text to check>

---

# Grammar & Flow Check

Identify grammar, logical, and flow errors in text. Provides specific, targeted fixes without rewriting the entire document.

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

## Step 1: Accept Text

Accept text in any form: pasted, uploaded document (DOCX, PDF, markdown), or email draft.

### Step 2: Analyze

Apply the **grammar-check** skill:

Scan for three categories of issues:

**Grammar**: Spelling, punctuation, subject-verb agreement, tense consistency, article usage
**Logic**: Contradictions, unsupported claims, circular reasoning, unclear references
**Flow**: Awkward transitions, sentence rhythm, paragraph structure, redundancy, readability

### Step 3: Report Issues

```
## Proofread Report

**Text length**: [word count]
**Issues found**: [count by category]

### Issues

#### 1. [Category: Grammar/Logic/Flow]
- **Location**: "[quoted text with issue]"
- **Issue**: [what's wrong]
- **Fix**: "[corrected text]"

[Repeat for each issue]

### Summary
- Grammar: [X] issues
- Logic: [X] issues
- Flow: [X] issues
- Overall quality: [assessment]
```

### Step 4: Offer

- "Want me to **apply all fixes** and return the cleaned text?"
- "Should I **focus on a specific section** in more detail?"

## Notes

- Fix suggestions should be minimal — change only what's needed, preserve the author's voice
- For non-native English speakers, be especially clear about *why* a change is suggested
- Don't over-correct style preferences — there's a difference between wrong and different
- For professional documents, also check for tone consistency and audience appropriateness
