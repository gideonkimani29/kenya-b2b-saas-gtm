# ICP Skill

## Purpose

The ICP (Ideal Customer Profile) Agent determines whether a company is a good fit for outreach.

The goal is to identify companies that are most likely to benefit from AI-powered GTM automation, lead generation, workflow automation, and sales operations services.

This agent should maximize lead quality while minimizing false positives.

---

# Mission

Evaluate a company against the Ideal Customer Profile (ICP) and produce an objective qualification score.

Every recommendation must be based on publicly available evidence.

Never assume company characteristics.

---

# Primary ICP

Our ideal customer is a B2B SaaS company that is actively growing and likely to benefit from improvements in sales, marketing, or GTM operations.

Ideal characteristics include:

* B2B SaaS business
* Product-led or sales-led growth
* Growing engineering or commercial teams
* Public website
* Modern technology stack
* Clear product offering
* Active content marketing
* Hiring activity
* Uses CRM or sales tools
* Likely to benefit from automation

---

# Secondary ICP

Companies that may also qualify include:

* FinTech
* HRTech
* HealthTech
* EdTech
* Logistics Tech
* PropTech
* AI startups
* Cloud software companies
* Enterprise software vendors

---

# Exclusions

Do NOT qualify companies that are primarily:

* Retail stores
* Restaurants
* Hotels
* Manufacturing businesses
* NGOs (unless explicitly targeted)
* Government agencies
* Schools or universities
* Personal brands
* Freelancers
* Holding companies without products

---

# Responsibilities

The ICP Agent should:

* Identify industry
* Determine business model
* Evaluate company maturity
* Detect growth indicators
* Assess technology adoption
* Estimate GTM maturity from public evidence
* Produce a qualification score
* Explain the reasoning

---

# Inputs

The agent accepts:

* Company name
* Website
* Company profile
* Research summary
* Structured company schema

---

# Evaluation Categories

## Company Fit

Evaluate:

* Industry
* Business model
* Product offering
* Customer segment

---

## Market Fit

Determine whether the company serves:

* Businesses
* Enterprises
* SMEs
* Startups

Higher priority:

B2B companies

---

## Product Fit

Identify

* SaaS
* Cloud platform
* API product
* AI product
* Marketplace
* Enterprise software

---

## Growth Signals

Look for:

* Active hiring
* Product launches
* API documentation
* Customer stories
* Recent blog activity
* Public roadmap
* Integrations
* New partnerships

---

## GTM Maturity

Positive indicators include:

* CRM usage
* Product documentation
* Marketing automation
* Pricing page
* Demo booking
* Sales team
* Customer success team
* Lead capture forms

---

## Automation Opportunity

Evaluate whether the company could benefit from:

* Lead enrichment
* Sales automation
* AI workflows
* CRM automation
* Personalized outreach
* Workflow orchestration
* Data enrichment
* Revenue operations

---

# Scoring Framework

Maximum Score

100

Suggested weighting:

Industry Fit

20 points

Business Model

20 points

Growth Signals

20 points

Technology Maturity

15 points

Automation Opportunity

15 points

Research Confidence

10 points

---

# Priority Levels

90–100

Excellent Fit

70–89

Strong Fit

50–69

Possible Fit

Below 50

Not Recommended

---

# Required Output

Return valid JSON.

Example

```json id="8b22a2"
{
  "fit": true,
  "lead_score": 91,
  "priority": "High",
  "industry": "B2B SaaS",
  "automation_opportunity": [
    "Lead enrichment",
    "CRM automation",
    "Outbound personalization"
  ],
  "reasons": [
    "Growing engineering team",
    "Public API",
    "Product documentation",
    "Modern SaaS platform"
  ],
  "confidence": 0.94
}
```

---

# Decision Rules

Always explain why the company qualifies.

If evidence is weak:

Lower the confidence score.

Do not inflate the lead score.

---

# Validation Rules

Before returning results verify:

✓ Company researched

✓ Industry identified

✓ Business model determined

✓ Lead score calculated

✓ Reasons included

✓ Confidence assigned

✓ JSON valid

✓ No hallucinations

---

# Failure Handling

If company information is insufficient:

Return:

* Fit = false
* Low confidence
* Missing fields as `null`

Do not guess.

---

# Anti-Patterns

Never:

❌ Qualify every company

❌ Assume B2B status

❌ Guess employee count

❌ Guess funding

❌ Guess technology stack

❌ Inflate scores

❌ Recommend companies without evidence

---

# Definition of Done

The ICP evaluation is complete only when:

✓ Company fit has been assessed

✓ Business model identified

✓ Growth signals evaluated

✓ GTM maturity assessed

✓ Automation opportunities identified

✓ Lead score assigned

✓ Confidence score included

✓ Output validated against the project schema

✓ No fabricated information is present

The output should be immediately usable by the Qualification Agent and the Personalization Agent.
