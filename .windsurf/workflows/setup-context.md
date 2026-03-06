# Workflow: setup-context

> Guide a first-time user through completing all context files — company overview, products, and per-product competitive analysis.

---

## Purpose

This workflow populates the `context/` folder so that all other PM workflows have the background they need to produce relevant, tailored outputs. Run this once when setting up a new workspace.

---

## Step 1: Welcome & Explain

Greet the user and explain what you're about to do:

"Welcome! I'll guide you through setting up your PM context files. This takes about 10 minutes and will make every other workflow — PRDs, strategy, discovery, competitive analysis — much more relevant to your specific company and products. We'll fill in three things: your company overview, your product(s), and a competitive analysis for each product."

Ask if they're ready to begin.

---

## Step 2: Company Overview

Tell the user: "Let's start with your company."

Invoke `/setup-company` and let it run until the company overview is saved. Then proceed to Step 3.

---

## Step 3: Products

Tell the user: "Now let's document your product(s)."

### Step 3a: Extract from website (if available)

If a company website URL was provided in Step 2, re-fetch it and attempt to extract a list of products or product lines. Look for product names, descriptions, and any feature or pricing pages that describe individual offerings.

If products are found, present them to the user:

"Based on your website, I found the following products:
- **[Product A]** — [one-line description]
- **[Product B]** — [one-line description]
- ...

Would you like to:
1. **Proceed with these** — I'll create context files for each one
2. **Add them manually** — use /setup-product to enter details yourself
3. **Mix** — proceed with some and skip others"

Wait for the user's choice:

- **Proceed with extracted products** — for each product, follow this order exactly: (1) create the folder `context/products/<product-name>/`, (2) create `context/products/<product-name>/<product-name>.md` inside it populated with extracted details, (3) create `context/products/<product-name>/requirements.md` inside it as an empty placeholder. Never create files directly in `context/products/` — each product must have its own subfolder. Confirm each product as it's saved. Then ask if there are additional products to add; if yes, invoke `/setup-product`.
- **Add manually** — invoke `/setup-product` and let it run until the user is done.
- **Mix** — let the user indicate which extracted products to keep, create files for those, then invoke `/setup-product` for any remaining products they want to add manually.

### Step 3b: No website available

If no company website was provided in Step 2, invoke `/setup-product` directly and let it run until the user is done adding products.

### Both paths

Once complete, tell the user: "You can always add more products later by running **/setup-product**."

Then proceed to Step 4.

---

## Step 4: Competitors (per product)

Tell the user: "Now let's map the competitive landscape for each of your products."

Repeat the following for every product documented in Step 3:

Tell the user: "Let's look at competitors for **<Product Name>**."

### Step 4a: Run competitive analysis

Invoke `/competitive-analysis` using the product name, problem it solves, and target user from Step 3 as input.

Attempt to research and identify competitors automatically using web search.

### Step 4b: Present results

Present the full competitive analysis output to the user. Then ask:

"Here's what I found for **<Product Name>**. Does this look accurate? You can:
- **Accept** it as-is
- **Edit** specific competitors or fields
- **Add** competitors that are missing
- **Remove** any that aren't relevant"

Wait for the user's response. Apply any requested edits before proceeding.

### Step 4c: Fallback — if product information cannot be found

If web research returns insufficient results (product is too early-stage, niche, or not indexed), tell the user:

"I couldn't find enough public information about the competitive landscape for **<Product Name>**. Let me ask you a few questions instead."

Then walk the user through the following questions, mirroring what `/competitive-analysis` would produce:

1. Who are the top 3–5 direct competitors for this product? (same category, same buyer)
2. Are there any indirect competitors solving the same problem a different way?
3. For each competitor, ask:
   - How do they position themselves and who do they target?
   - What are their main strengths — where do they win?
   - What are their weaknesses — where do they fall short or get complaints?
   - What is their pricing model and price point (if known)?
   - Any recent moves — new features, funding, pivots?
4. Where does your product differentiate most clearly from each of them?
5. What do you see as the biggest competitive threats for this product?

Use the answers to produce the same competitive analysis format as `/competitive-analysis` Step 4, then present it to the user for review and edits as in Step 4b.

### Step 4d: Save

Once the user is satisfied, append the finalised competitive landscape to `context/products/<product-name>/<product-name>.md` under a new section:

```
## Competitive Landscape
<competitive analysis output>
```

Confirm: "Competitive landscape for <Product Name> saved."

Repeat Steps 4a–4d for each remaining product.

---

## Step 5: Summary & Next Steps

Show a summary of what was completed:

```
Context setup complete:
✓ context/company-overview.md
✓ context/products/<product-name>/<product-name>.md (one per product, includes competitive landscape)
✓ context/products/<product-name>/requirements.md (one per product, empty placeholder)
```

Then suggest relevant next steps:
- "Want to run **/discover** to explore opportunities for one of your products?"
- "Want to run **/strategy** to define your product strategy?"
- "Want to run **/write-prd** to document a feature you're already planning?"
