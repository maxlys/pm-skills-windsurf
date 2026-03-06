# Workflow: setup-company

> Populate context/company-overview.md by extracting information from a website or walking the user through questions.

---

## Purpose

Use this workflow to document your company and save it to `context/company-overview.md`. Run it when setting up a new workspace or when company information needs updating.

---

## Step 1: Gather Company Information

Ask: "Do you have a company website I can pull information from, or would you prefer to answer a few questions yourself?"

### Option A: Website provided

Ask for the URL. Fetch the website and extract as much of the following as possible:
- Company name
- What the company does (one sentence)
- Mission or vision
- Business model
- Target customers

Then present what you found to the user:
"Here's what I extracted from your website. Please review and correct anything that's off, and fill in anything I couldn't find."

Show a draft of each field and wait for the user to confirm or correct. For any fields that could not be extracted (stage, size, strategic priorities, key metrics), ask the user directly.

### Option B: Questions

Ask the following questions one at a time. Wait for each answer before moving on:

1. What is your company name?
2. What does your company do — in one sentence?
3. What is your mission or long-term vision?
4. How does your company make money? (e.g. SaaS subscription, marketplace, services)
5. Who are your primary customers?
6. What stage and size is the company? (e.g. Seed, Series A, 50 employees)
7. What are the 2–3 most important company priorities this year?
8. Are there any key metrics you track? (e.g. ARR, MAU, NPS — share rough numbers if comfortable)

---

## Step 2: Save

Once all answers are collected, write them into `context/company-overview.md`, replacing the placeholder comments with the user's actual content.

Confirm: "Company overview saved."

Then suggest next steps:
- "Want to run **/setup-context** to complete the full workspace setup?"
- "Want to run **/add-product** to document your products?"
