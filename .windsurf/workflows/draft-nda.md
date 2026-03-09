# Workflow: draft-nda

> Draft a Non-Disclosure Agreement between two parties with jurisdiction-appropriate clauses
**Input:** <parties and context>

---

# NDA Drafting

Draft a professional Non-Disclosure Agreement customized to your situation. Covers information types, jurisdiction, term, and clearly marks clauses that need legal review.

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

## Step 1: Gather Context

Ask:
- Who are the parties? (company names and roles)
- Mutual or one-way NDA?
- What information is being protected? (trade secrets, code, business data, customer data)
- Jurisdiction? (state/country for governing law)
- Duration? (how long should confidentiality last)
- Any specific concerns? (non-compete, non-solicit, IP ownership)

### Step 2: Draft the NDA

Apply the **draft-nda** skill:

Generate a complete NDA covering:
- Parties and recitals
- Definition of confidential information (with specific examples)
- Obligations of the receiving party
- Exclusions (public knowledge, independent development, etc.)
- Term and survival
- Return/destruction of materials
- Remedies
- Governing law and jurisdiction
- Standard boilerplate (severability, entire agreement, amendments)

### Step 3: Deliver

```
## Non-Disclosure Agreement

[Full NDA text with marked sections]

### Clauses Requiring Legal Review
| Clause | Why It Needs Review | Consideration |
|--------|-------------------|--------------|

### Plain-Language Summary
[What this NDA means in simple terms for non-lawyers]
```

Save as markdown. Offer to export as DOCX for signing.

## Notes

- This is a starting point — always recommend review by qualified legal counsel
- Mark any clause that involves significant legal risk with a ⚠️ flag
- Include plain-language annotations so non-lawyers understand what they're agreeing to
- Mutual NDAs are generally preferred — they're fairer and faster to negotiate
