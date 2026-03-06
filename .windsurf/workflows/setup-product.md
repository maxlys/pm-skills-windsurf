# Workflow: setup-product

> Add one or more products to the context folder, creating a dedicated folder with a product overview and an empty requirements file for each.

---

## Purpose

Use this workflow to document a product and add it to `context/products/`. Run it when setting up a new product or adding a product to an existing workspace. Can be repeated for multiple products in one session.

---

## Step 1: Gather Product Information

Ask: "Do you have a link — such as a product page, landing page, or doc — I can pull information from? (Optional — skip if not)"

### Option A: Link provided

Fetch the URL and extract as much of the following as possible:
- Product name
- Problem it solves
- Target user
- Core features
- Current stage

Present what you found to the user:
"Here's what I extracted for this product. Please review and correct anything that's off, and fill in anything I couldn't find."

Show a draft of each field and wait for the user to confirm or correct. For any fields that could not be extracted (stage, key metrics), ask the user directly.

### Option B: No link provided

Ask the following questions one at a time:
- What is the product name?
- What problem does it solve and for whom?
- What are its core features?
- What is the current stage? (e.g. in development, launched, mature, sunset)
- Are there any key metrics for this product? (e.g. users, revenue, retention)

---

## Step 2: Create Product Folder and Files

> **IMPORTANT: Each product MUST have its own dedicated subfolder. Never create product files directly inside `context/products/`. Always create the folder first, then the files inside it.**

The required output structure for each product is:

```
context/
└── products/
    └── <product-name>/          ← create this folder first
        ├── <product-name>.md    ← then create this file inside it
        └── requirements.md      ← then create this file inside it
```

Follow these steps in order:

**1. Create the folder** `context/products/<product-name>/`

**2. Create the file** `context/products/<product-name>/<product-name>.md` inside that folder, populated with the answers collected above:

```
# <Product Name>

## Problem it solves
<answer>

## Target user
<answer>

## Core features
<answer>

## Current stage
<answer>

## Key metrics
<answer>
```

**3. Create the file** `context/products/<product-name>/requirements.md` inside the same folder, as an empty placeholder:

```
# <Product Name> — Requirements

<!-- Paste any existing requirements, specs, or briefs here. This file is optional. -->
```

Confirm: "Folder and files for <Product Name> created at context/products/<product-name>/."

---

## Step 3: Add Another Product?

Ask: "Do you want to add another product?"

- If **yes** — repeat from Step 1 for the next product, asking "Do you have a link for your next product? (Optional — skip if not)"
- If **no** — suggest next steps:
  - "Want to run **/setup-context** to complete the full workspace setup?"
  - "Want to run **/discover** to explore opportunities for this product?"
  - "Want to run **/write-prd** to document a feature for this product?"
