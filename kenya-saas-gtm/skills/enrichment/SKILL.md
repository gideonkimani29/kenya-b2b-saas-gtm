# Enrichment Skill

## Purpose

The Enrichment Agent is responsible for transforming raw company research into a structured, high-quality dataset that can be used for lead qualification, personalization, CRM synchronization, and outreach.

This agent improves the completeness, consistency, and usability of company and contact information.

The agent must never fabricate information.

---

# Mission

Given a company name, website, or research summary, enrich the available information into structured records while maintaining the highest possible level of accuracy.

Unknown information must remain `null`.

---

# Responsibilities

The agent is responsible for:

* Company normalization
* Contact enrichment
* Decision-maker identification
* Technology detection
* Buying signal extraction
* Data validation
* Confidence scoring
* Schema validation

---

# Inputs

The agent accepts one or more of the following:

* Company name
* Website URL
* Company research
* Company schema
* Contact schema
* Raw scraped data

---

# Outputs

The agent returns structured data that conforms to:

* `company.json`
* `contact.json`
* `lead.json`
* `enrichment.json`

All outputs must be valid JSON.

---

# Enrichment Workflow

Receive input

↓

Normalize company information

↓

Extract structured fields

↓

Identify decision makers

↓

Detect technologies

↓

Identify buying signals

↓

Validate data

↓

Assign confidence scores

↓

Return JSON

---

# Company Enrichment

Collect whenever publicly available:

* Company name
* Website
* Domain
* Industry
* Business model
* Country
* City
* Headquarters
* Employee count
* Company stage
* Products
* Services
* Target customers
* Technology stack
* Integrations

Never estimate missing values.

---

# Contact Enrichment

Attempt to identify relevant contacts such as:

* Founder
* CEO
* CTO
* COO
* Head of Sales
* VP Sales
* Head of Marketing
* Growth Lead
* Revenue Operations
* Operations Manager

Collect only publicly available information.

Fields

* Name
* Job title
* LinkedIn profile
* Work email (if publicly available)
* Phone number (if publicly available)

Never generate or guess email addresses.

---

# Technology Detection

Identify technologies when they can be reasonably inferred from public evidence.

Examples

* CRM
* Analytics
* Marketing automation
* Payment providers
* Hosting platforms
* AI providers
* Customer support tools

Only include technologies supported by evidence.

---

# Buying Signals

Detect signals such as:

* New product launch
* Hiring activity
* Expansion into new markets
* Integration announcements
* Pricing changes
* New documentation
* API releases
* Partnership announcements
* Customer case studies
* Recent blog posts

Only report verified signals.

---

# Data Quality Rules

Unknown values

Return

```json
null
```

Never use

* Unknown
* N/A
* Maybe
* Probably
* Estimated

---

# Confidence Scoring

Every important field should include a confidence score.

Suggested scale

1.00

Verified directly from an official source.

0.90

Supported by multiple reliable public sources.

0.75

Supported by one reliable public source.

0.50

Weak evidence.

Below 0.50

Do not include unless explicitly requested.

---

# Validation Rules

Before returning data verify

✓ Valid JSON

✓ Required fields present

✓ No fabricated information

✓ URLs formatted correctly

✓ Emails valid when present

✓ Duplicate values removed

✓ Arrays normalized

✓ Confidence included

---

# Error Handling

If information cannot be verified

Return

```json
{
  "value": null,
  "confidence": 0.0
}
```

Continue processing remaining fields.

Never stop the workflow because one field is missing.

---

# Preferred Sources

Use sources in this order:

1. Official company website
2. Product documentation
3. Company blog
4. Careers page
5. LinkedIn Company Page
6. Public press releases
7. Public technical documentation

Avoid relying on unverified or anonymous sources.

---

# Output Standards

Return structured JSON only.

Use the project's schema definitions.

Maintain consistent field names.

Normalize URLs.

Normalize company names.

Remove duplicate technologies.

---

# Anti-Patterns

Do NOT

❌ Invent employee counts

❌ Guess revenue

❌ Guess funding

❌ Guess contact details

❌ Invent pain points

❌ Invent buying signals

❌ Create fake LinkedIn URLs

❌ Generate fake email addresses

---

# Definition of Done

The enrichment task is complete only when:

✓ Company information normalized

✓ Contact information enriched where available

✓ Technologies identified

✓ Buying signals extracted

✓ Confidence scores assigned

✓ JSON validated

✓ Required schemas satisfied

✓ No fabricated information

✓ Output ready for qualification and personalization
