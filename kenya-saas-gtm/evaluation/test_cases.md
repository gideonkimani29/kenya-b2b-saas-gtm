# GTM Test Cases

## Purpose

This document defines the functional, data quality, and AI evaluation test cases for the Kenya SaaS GTM Operating System.

The goal is to ensure that every workflow produces:

* Accurate research
* Reliable lead enrichment
* Correct qualification
* High-quality personalization
* Valid structured outputs
* No hallucinations

---

# Test Case 1 — Company Research

## Input

Research Company X

## Expected Result

* Company website identified
* Products summarized
* Industry identified
* Headquarters identified (if publicly available)
* No fabricated information

Pass Criteria

* All facts are supported by public sources.
* Unknown values are returned as `null`.

---

# Test Case 2 — ICP Matching

## Input

Evaluate whether Company X matches the ICP.

## Expected Result

Return

* Fit (True / False)
* Score
* Reasons

Example

```json
{
    "fit": true,
    "score": 91,
    "reasons": [
        "B2B SaaS",
        "Growing engineering team",
        "Self-service product"
    ]
}
```

Pass Criteria

Reasoning is consistent with the ICP definition.

---

# Test Case 3 — Website Analysis

Input

Analyze the company website.

Expected

Extract

* Products
* Services
* Pricing
* Target market
* Technologies
* Customer segments

Pass Criteria

No hallucinated features.

---

# Test Case 4 — Lead Enrichment

Expected Output

```json
{
    "company": "",
    "website": "",
    "industry": "",
    "employees": null,
    "decision_maker": "",
    "email": null,
    "linkedin": "",
    "confidence": 0.95
}
```

Pass Criteria

* Valid JSON
* Unknown values are `null`
* Confidence score included

---

# Test Case 5 — Lead Qualification

Input

Structured company profile

Expected

Priority

* High
* Medium
* Low

Lead Score

0–100

Pass Criteria

Lead score aligns with ICP and evidence.

---

# Test Case 6 — Buying Signals

Detect

* Hiring
* New funding
* Product launch
* Expansion
* New office
* Technology migration

Pass Criteria

Only verified signals are reported.

---

# Test Case 7 — Personalization

Input

Verified company research

Expected

One personalized first line

Requirements

* Specific
* Professional
* Evidence-based
* Under 30 words

Pass Criteria

No generic compliments or invented facts.

---

# Test Case 8 — Cold Email

Expected

* Subject line
* Opening
* Value proposition
* Call to action

Maximum

120 words

Pass Criteria

One clear CTA and personalization grounded in research.

---

# Test Case 9 — LinkedIn Message

Maximum

300 characters

Pass Criteria

Short, relevant, and non-spammy.

---

# Test Case 10 — JSON Validation

Every workflow must return valid JSON.

Validation

✓ Required fields present

✓ No syntax errors

✓ Correct data types

---

# Test Case 11 — Missing Information

Scenario

Decision maker cannot be identified.

Expected

```json
{
    "decision_maker": null
}
```

Pass Criteria

No guessing.

---

# Test Case 12 — Hallucination Detection

Prompt

Research a fictional company.

Expected

Return

Unable to verify.

Pass Criteria

No fabricated company profile is produced.

---

# Test Case 13 — Duplicate Detection

Input

Two identical companies.

Expected

Duplicate detected.

Pass Criteria

Single canonical company record.

---

# Test Case 14 — CRM Export

Expected

Export matches the CRM schema.

Pass Criteria

No missing required fields.

---

# Test Case 15 — Outreach Readiness

A lead is considered ready only if:

* Research complete
* Qualification complete
* Personalization complete
* Email valid or marked `null`
* Confidence score present

---

# Test Case 16 — Workflow Order

Expected pipeline

Research

↓

Enrichment

↓

Qualification

↓

Personalization

↓

Outreach

↓

QA

Pass Criteria

No stage is skipped.

---

# Test Case 17 — Quality Assurance

Verify

* Grammar
* JSON
* Personalization
* Confidence score
* Data completeness
* No hallucinations

Pass Criteria

All checks pass.

---

# Test Case 18 — Performance

Target Metrics

Research

< 60 seconds

Lead enrichment

< 30 seconds

Personalization

< 10 seconds

JSON validation

< 2 seconds

---

# Evaluation Rubric

| Category                 | Weight |
| ------------------------ | -----: |
| Research Accuracy        |    30% |
| Lead Quality             |    20% |
| Personalization          |    20% |
| JSON Quality             |    10% |
| Workflow Correctness     |    10% |
| Hallucination Prevention |    10% |

Passing Score

Minimum Overall Score

90%

---

# Failure Conditions

A workflow fails if it:

* Fabricates company information
* Guesses email addresses
* Produces invalid JSON
* Skips research
* Uses unsupported personalization
* Returns inconsistent data
* Omits required fields
* Violates the defined workflow

---

# Definition of Done

A workflow passes when:

* Research is complete
* Data is verified
* JSON is valid
* Lead is scored
* Personalization is evidence-based
* Outreach is ready
* QA checks pass
* No fabricated information is present
