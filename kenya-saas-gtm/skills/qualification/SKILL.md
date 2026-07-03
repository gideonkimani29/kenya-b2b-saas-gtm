# Qualification Skill

## Purpose

The Qualification Skill evaluates whether a prospect should move forward in the outbound sales pipeline.

Its objective is to convert enriched company and contact information into an objective qualification decision supported by evidence.

The Qualification Skill does not perform research or generate outreach. It evaluates the available data and determines lead quality.

---

# Mission

Analyze company intelligence, contact information, ICP fit, and buying signals to determine whether a lead is worth pursuing.

Every qualification decision must be evidence-based.

Never inflate scores or assume missing information.

---

# Responsibilities

The Qualification Skill is responsible for:

* Evaluating ICP fit
* Reviewing company maturity
* Assessing buying signals
* Measuring automation opportunity
* Prioritizing leads
* Assigning lead scores
* Explaining qualification decisions
* Producing structured qualification output

---

# Inputs

The skill accepts:

* Company profile
* Contact profile
* Enrichment results
* ICP evaluation
* Research summary
* Buying signals
* Technology stack

---

# Outputs

Return structured JSON compatible with:

* lead.json
* evaluation.json
* crm.json

---

# Qualification Workflow

Receive enriched company

↓

Review ICP evaluation

↓

Analyze company profile

↓

Review contact profile

↓

Evaluate buying signals

↓

Calculate lead score

↓

Assign priority

↓

Generate reasoning

↓

Validate output

↓

Return JSON

---

# Qualification Categories

## Industry Fit

Evaluate whether the company operates in a target market.

Examples:

* B2B SaaS
* AI
* FinTech
* HRTech
* HealthTech
* Logistics Tech

---

## Business Model

Determine whether the company serves:

* Businesses
* Enterprises
* SMEs
* Startups

Higher priority:

B2B

---

## Growth Indicators

Examples:

* Active hiring
* Product launches
* API documentation
* Customer stories
* Recent blog activity
* Public roadmap
* Integrations
* Partnerships

---

## Technology Maturity

Positive indicators include:

* CRM usage
* Public API
* Documentation
* Automation tools
* Modern website
* Self-service product
* Customer onboarding

---

## Decision Maker Availability

Evaluate:

* Decision maker identified
* Job title available
* Public LinkedIn profile
* Public work email

Do not penalize a lead solely because contact details are unavailable.

---

## Automation Opportunity

Determine whether the company could benefit from:

* Lead enrichment
* CRM automation
* Workflow automation
* AI-powered prospecting
* Sales operations
* GTM automation
* Personalized outreach

---

# Lead Scoring

Maximum Score

100

Suggested weighting

Industry Fit

20

Business Model

15

Growth Indicators

20

Technology Maturity

15

Automation Opportunity

20

Research Confidence

10

---

# Priority Levels

90–100

High

70–89

Medium

50–69

Low

Below 50

Disqualify

---

# Required Output

Return valid JSON.

Example

```json id="urjlwm"
{
  "qualified": true,
  "lead_score": 88,
  "priority": "High",
  "qualification_reason": [
    "Strong B2B SaaS fit",
    "Hiring engineering talent",
    "Public API documentation",
    "Automation opportunity identified"
  ],
  "recommended_next_step": "Generate personalized outreach",
  "confidence": 0.95
}
```

---

# Decision Rules

A company should qualify only when supported by evidence.

If multiple important fields are missing:

Reduce confidence.

Do not inflate the lead score.

---

# Validation Rules

Before returning results verify:

✓ Company profile reviewed

✓ ICP considered

✓ Buying signals evaluated

✓ Lead score assigned

✓ Priority assigned

✓ Reasoning included

✓ Confidence score included

✓ JSON valid

✓ No hallucinations

---

# Error Handling

If research quality is poor:

Return

* Low confidence
* Partial qualification
* Missing values as `null`

Explain why the qualification is uncertain.

Never fabricate supporting evidence.

---

# Anti-Patterns

Never:

❌ Qualify every company

❌ Inflate scores

❌ Ignore missing research

❌ Guess company maturity

❌ Assume buying intent

❌ Recommend outreach without evidence

❌ Produce inconsistent scoring

---

# Recommended Next Actions

Based on the outcome:

High Priority

→ Personalization Skill

↓

Outreach Skill

---

Medium Priority

→ Manual review

↓

Personalization

↓

Outreach

---

Low Priority

→ Add to nurture list

↓

Monitor for future buying signals

---

Disqualified

→ Archive

↓

Do not generate outreach

---

# Success Metrics

The Qualification Skill succeeds when:

* Lead scores are consistent
* Priority reflects evidence
* Decisions are explainable
* Confidence matches data quality
* Outputs integrate with downstream agents

---

# Definition of Done

The qualification task is complete only when:

✓ Company profile evaluated

✓ Contact profile reviewed

✓ ICP considered

✓ Buying signals assessed

✓ Automation opportunity identified

✓ Lead score calculated

✓ Priority assigned

✓ Reasoning documented

✓ Confidence score included

✓ Output validated against project schemas

✓ No fabricated information

✓ Lead is ready for the next stage of the GTM pipeline
