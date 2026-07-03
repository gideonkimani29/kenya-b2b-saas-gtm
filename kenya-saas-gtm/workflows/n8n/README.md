# n8n Workflows

## Overview

This directory contains all n8n workflows used by the GTM Operating System.

The workflows automate the complete outbound sales process from lead discovery to CRM synchronization.

Each workflow performs one responsibility and can be executed independently or as part of a larger pipeline.

---

# Workflow Order

```
Lead Source
      │
      ▼
01 Lead Ingestion
      │
      ▼
02 Company Research
      │
      ▼
03 Contact Enrichment
      │
      ▼
04 ICP Qualification
      │
      ▼
05 Personalization
      │
      ▼
06 Cold Email Generation
      │
      ▼
07 LinkedIn Outreach
      │
      ▼
08 Follow-up Sequence
      │
      ▼
09 CRM Sync
      │
      ▼
10 Reporting
```

---

# Workflow Descriptions

## 01 Lead Ingestion

Receives companies from:

* CSV
* Google Sheets
* Apollo
* Clay
* Webhook
* API

Output

Normalized company list.

---

## 02 Company Research

Collects

* Website
* Products
* Industry
* Technologies
* Buying signals

Returns

company.json

---

## 03 Contact Enrichment

Finds

* Founder
* CEO
* CTO
* Head of Sales
* Verified contact information (where publicly available)

Returns

contact.json

---

## 04 ICP Qualification

Evaluates

* Company fit
* Industry
* Automation opportunity
* Growth signals

Returns

lead.json

---

## 05 Personalization

Creates

* Opening lines
* Pain points
* Value proposition

Returns

personalization object.

---

## 06 Cold Email Generation

Generates

* Subject
* Cold email
* CTA

Returns

outreach.json

---

## 07 LinkedIn Outreach

Creates

* Connection request
* Follow-up message

---

## 08 Follow-up Sequence

Generates

* Follow-up 1
* Follow-up 2
* Break-up email

---

## 09 CRM Sync

Updates

* HubSpot
* Attio
* Salesforce
* Pipedrive

---

## 10 Reporting

Creates dashboards for:

* Leads processed
* Qualified leads
* Emails generated
* Replies
* Meetings
* Conversion rates

---

# Standards

Every workflow should:

* Have one responsibility
* Produce structured JSON
* Validate input
* Validate output
* Log errors
* Be idempotent where practical
* Return useful error messages

---

# Error Handling

If a workflow fails:

* Log the error
* Preserve successful outputs
* Continue downstream only when safe
* Never fabricate missing data

---

# Naming Convention

```
01_name.json
02_name.json
03_name.json
```

This ensures workflows execute in a predictable order.

---

# Future Integrations

Examples include:

* Gmail
* Outlook
* Instantly
* HubSpot
* Attio
* Clay
* Apollo
* OpenAI
* Claude
* Ollama
* Docker MCP
* GitHub
* Slack
* Discord
* Google Drive
* Google Sheets
* Airtable

---

# Goal

The workflows should automate the complete GTM lifecycle while remaining modular, maintainable, and reusable.
