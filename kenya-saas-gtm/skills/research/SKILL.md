# Research Skill

## Purpose

The Research Skill is responsible for collecting accurate, structured, and verifiable information about companies and their publicly available business activities.

It serves as the foundation of the GTM pipeline by producing high-quality company intelligence that downstream skills can trust.

This skill must prioritize accuracy over completeness.

Unknown information should remain `null`.

---

# Mission

Research companies using publicly available information and transform unstructured content into structured intelligence.

Every finding must be supported by evidence.

Never fabricate facts or speculate about company operations.

---

# Responsibilities

The Research Skill is responsible for:

* Company discovery
* Company normalization
* Website analysis
* Product research
* Industry classification
* Technology identification
* Growth signal detection
* Public information extraction
* Source attribution
* Confidence scoring

---

# Inputs

The skill accepts one or more of:

* Company name
* Website URL
* Domain
* CSV row
* CRM record
* Lead record
* User query

---

# Outputs

Return structured data compatible with:

* company.json
* lead.json
* enrichment.json

All outputs must be valid JSON.

---

# Research Workflow

Receive input

↓

Normalize company identity

↓

Locate official website

↓

Research public sources

↓

Extract structured information

↓

Identify products and services

↓

Detect technology signals

↓

Identify growth signals

↓

Assign confidence

↓

Validate output

↓

Return JSON

---

# Research Categories

## Company Identity

Collect when publicly available:

* Company name
* Website
* Domain
* Logo URL (optional)
* Description

---

## Business Information

Identify:

* Industry
* Sub-industry
* Business model
* Primary customers
* Geographic markets
* Headquarters

---

## Products & Services

Identify:

* Core products
* Core services
* Product categories
* Pricing model (if public)
* Free trial availability (if public)

---

## Technology Stack

Look for evidence of:

* CRM
* Marketing automation
* Analytics
* AI tools
* Payment providers
* Customer support software
* Hosting platforms
* Public APIs

Only include technologies supported by evidence.

---

## Growth Signals

Examples include:

* Hiring activity
* New product launches
* API releases
* Documentation updates
* Blog activity
* Partnerships
* Customer case studies
* Events
* Public roadmap updates

---

## Public Resources

Locate where available:

* Homepage
* Blog
* Documentation
* Careers page
* Pricing page
* API documentation
* Help center
* LinkedIn company page

---

# Preferred Sources

Use sources in the following order:

1. Official website
2. Product documentation
3. Blog
4. Careers page
5. Help center
6. Public API documentation
7. Official LinkedIn company page
8. Official press releases

Avoid relying on unverified third-party sources when official information is available.

---

# Research Rules

Only collect information that is publicly available.

If information cannot be verified:

Return `null`.

Do not estimate values.

---

# Confidence Scoring

Suggested scale

1.00

Verified directly from the official company website.

0.90

Verified by multiple reliable public sources.

0.75

Supported by one reliable source.

0.50

Weak evidence.

Below 0.50

Exclude unless explicitly requested.

---

# Data Normalization

Normalize:

* Company names
* URLs
* Domains
* Technology names
* Product names
* Industry labels

Remove duplicate values.

---

# Validation Rules

Before returning verify:

✓ Company identified

✓ Website verified

✓ Industry classified

✓ Products extracted

✓ Sources recorded

✓ Confidence assigned

✓ JSON valid

✓ Required schema fields present

---

# Error Handling

If research fails:

Return partial results.

Use `null` for unavailable fields.

Explain which fields could not be verified.

Never fabricate information.

---

# Anti-Patterns

Never:

❌ Guess employee count

❌ Guess funding

❌ Guess revenue

❌ Guess customer count

❌ Invent technologies

❌ Invent products

❌ Invent partnerships

❌ Invent company priorities

❌ Produce unsupported claims

---

# Success Metrics

The Research Skill succeeds when:

* Company identity is verified
* Information is evidence-based
* Structured output is complete where possible
* Confidence reflects evidence quality
* Output integrates cleanly with downstream skills

---

# Integration

The Research Skill provides input to:

Research

↓

Enrichment

↓

ICP

↓

Qualification

↓

Personalization

↓

Outreach

↓

Follow-up

↓

CRM Export

---

# Definition of Done

The research task is complete only when:

✓ Company identity verified

✓ Official website identified

✓ Business information extracted

✓ Products and services documented

✓ Technology signals identified where supported

✓ Growth signals collected where available

✓ Public resources located

✓ Confidence scores assigned

✓ Sources recorded

✓ Output validated against project schemas

✓ No fabricated information

✓ Data is ready for enrichment and qualification

---

# Operating Principles

Evidence before assumptions.

Official sources before third-party sources.

Structured data before narrative.

Accuracy before completeness.

Reproducibility before convenience.

Every research result should be traceable, explainable, and reusable across the entire GTM pipeline.
