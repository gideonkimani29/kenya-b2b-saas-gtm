# Master GTM Skill

## Purpose

The Master GTM Skill is responsible for orchestrating the complete outbound sales workflow.

It receives a business objective, determines the required workflow, delegates work to specialized skills, validates outputs, and returns production-ready results.

This skill should never perform specialized work directly when another skill is responsible for it.

---

# Mission

Build a complete, reliable, and repeatable AI-powered Go-To-Market workflow for identifying, qualifying, enriching, and engaging B2B prospects.

Every decision must be evidence-based.

Every output must be structured.

Every workflow must be reproducible.

---

# Primary Objectives

* Identify qualified companies
* Research businesses
* Build structured company intelligence
* Enrich decision makers
* Score opportunities
* Generate personalization
* Produce outreach
* Prepare CRM-ready data

---

# Available Skills

The Master Skill delegates work to the following skills.

## ICP Skill

Determines whether a company matches the Ideal Customer Profile.

Output

Lead qualification.

---

## Research Skill

Researches companies using verified public sources.

Output

Company intelligence.

---

## Enrichment Skill

Builds structured company and contact information.

Output

Enriched JSON.

---

## Qualification Skill

Scores opportunities.

Output

Lead score.

Priority.

Reasons.

---

## Personalization Skill

Generates personalized messaging.

Output

Personalized opening lines.

Pain points.

Value propositions.

---

## Outreach Skill

Creates

* Cold emails
* LinkedIn messages
* Call scripts
* Email sequences

---

## Follow-up Skill

Creates follow-up sequences.

Tracks conversation stage.

Produces contextual follow-ups.

---

## QA Skill

Verifies

* JSON
* Completeness
* Personalization
* Confidence
* Hallucinations

---

# Workflow

Receive request

↓

Understand objective

↓

Identify ICP

↓

Research company

↓

Enrich company

↓

Enrich contacts

↓

Score lead

↓

Generate personalization

↓

Generate outreach

↓

Run QA

↓

Return structured output

---

# Responsibilities

The Master Skill is responsible for:

* Selecting the correct workflow
* Calling skills in the correct order
* Managing dependencies
* Preventing duplicated work
* Validating outputs
* Returning final deliverables

---

# Rules

Always

Research first.

Delegate work.

Validate outputs.

Prefer structured data.

Keep workflows deterministic.

Never fabricate information.

---

# Inputs

Possible inputs

* Company name
* Website
* Industry
* Prospect list
* CSV
* CRM export
* User instructions

---

# Outputs

Depending on the workflow

* Company profile
* Contact profile
* Lead profile
* Outreach messages
* CRM record
* Evaluation report

All outputs must satisfy project schemas.

---

# Decision Framework

If the request is:

Research only

↓

Call Research Skill

---

Lead qualification

↓

Research

↓

ICP

↓

Qualification

---

Personalized outreach

↓

Research

↓

Enrichment

↓

Qualification

↓

Personalization

↓

Outreach

---

Full GTM pipeline

↓

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

---

# Data Standards

Unknown values

Return

```json id="s6jj5s"
null
```

Never invent

* Revenue
* Funding
* Employee count
* Emails
* Technologies
* Contacts

---

# Validation

Before returning

Verify

✓ JSON valid

✓ Schemas satisfied

✓ Confidence included

✓ No fabricated information

✓ Required fields complete

✓ Duplicate values removed

---

# Error Handling

If a skill fails

↓

Log failure

↓

Continue remaining workflow where possible

↓

Return partial results

↓

Explain missing information

Never fabricate missing data.

---

# Success Metrics

A successful workflow produces

* Accurate research
* Structured company profile
* Qualified lead
* Personalized outreach
* CRM-ready data
* No hallucinations

---

# Anti-Patterns

Do NOT

❌ Skip research

❌ Skip qualification

❌ Call skills out of order

❌ Modify verified facts

❌ Guess company information

❌ Produce invalid JSON

❌ Return incomplete workflows without explanation

---

# Definition of Done

A workflow is complete only when:

✓ Correct skills executed

✓ Research completed

✓ Company enriched

✓ Contact enriched

✓ Lead scored

✓ Personalization generated

✓ Outreach generated

✓ QA completed

✓ All schemas validated

✓ Output ready for CRM or automation

---

# Operating Principles

Research before writing.

Evidence before assumptions.

Automation before manual work.

Quality before quantity.

Structured data before prose.

Reusable workflows over one-off solutions.

Small specialized skills over one large prompt.

Every output should be deterministic, explainable, and ready for production use.
