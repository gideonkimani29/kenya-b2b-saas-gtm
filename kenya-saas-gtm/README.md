# 🇰🇪 Kenya SaaS GTM Operating System

> An AI-powered Go-To-Market (GTM) Engineering platform for discovering, researching, qualifying, enriching, and engaging B2B SaaS companies in Kenya.

---

# Overview

This repository contains a modular AI GTM system designed to automate the outbound sales workflow using AI agents, structured prompts, Python, LangGraph, Docker, MCP servers, and workflow automation.

The objective is to build a repeatable and scalable outbound engine capable of:

- Finding qualified B2B SaaS companies
- Researching companies using verified sources
- Identifying buying signals
- Enriching company data
- Qualifying prospects
- Generating personalized outreach
- Producing CRM-ready lead records
- Automating outreach workflows

---

# Project Goals

This project aims to demonstrate production-level AI Engineering and GTM Engineering by combining:

- AI Agents
- LLM Engineering
- Prompt Engineering
- Context Engineering
- Lead Intelligence
- Sales Automation
- Workflow Automation
- Docker
- Python
- LangGraph
- MCP Servers

---

# High-Level Workflow

```text
Prospecting
      │
      ▼
Research
      │
      ▼
Enrichment
      │
      ▼
Qualification
      │
      ▼
Personalization
      │
      ▼
Outreach
      │
      ▼
CRM
      │
      ▼
Analytics
```

---

# Repository Structure

```text
kenya-saas-gtm/

├── AGENTS.md
├── CLAUDE.md
├── README.md
├── docker-compose.yml
├── .env.example

├── skills/
├── prompts/
├── schemas/
├── workflows/
├── templates/
├── docs/
├── evaluation/
├── scripts/
├── tests/
└── data/
```

---

# AI Agents

The platform uses specialized AI agents.

| Agent | Responsibility |
|--------|----------------|
| Orchestrator | Coordinates the workflow |
| ICP Agent | Determines customer fit |
| Research Agent | Collects verified company intelligence |
| Enrichment Agent | Builds structured lead profiles |
| Qualification Agent | Scores prospects |
| Personalization Agent | Creates personalized messaging |
| Outreach Agent | Generates outreach campaigns |
| QA Agent | Validates outputs |

---

# Technology Stack

## AI

- Claude Code
- Local LLMs
- LiteLLM

## Programming

- Python

## Agent Frameworks

- LangGraph

## Automation

- n8n

## Containers

- Docker

## Browser Automation

- Playwright

## Data Collection

- Apify

## Integrations

- MCP Servers

---

# Features

## Prospect Discovery

- Company discovery
- Industry filtering
- ICP matching
- Market segmentation

---

## Company Research

- Website analysis
- Product extraction
- Technology detection
- Hiring signals
- Growth indicators

---

## Lead Enrichment

- Company normalization
- Contact enrichment
- Decision-maker identification
- Technology stack detection
- Confidence scoring

---

## Qualification

- ICP scoring
- Buying signal analysis
- Lead prioritization

---

## Personalization

- First-line generation
- Cold email creation
- LinkedIn messages
- Follow-up sequences

---

## Outreach

- CRM-ready exports
- Email sequence generation
- Outreach preparation

---

# Project Philosophy

Research first.

Evidence before assumptions.

Automation before manual work.

Quality before quantity.

Small reusable components.

Structured outputs.

Production-ready engineering.

---

# Coding Standards

- Modular architecture
- Type hints
- Small reusable functions
- Structured JSON outputs
- Documentation first
- Testing where appropriate
- Maintainable code

---

# Data Standards

The system never fabricates information.

Unknown values should be represented as:

```json
null
```

Every important field should include a confidence score when possible.

---

# Workflow Principles

Every workflow follows:

1. Research
2. Verify
3. Structure
4. Personalize
5. Validate
6. Export

---

# Current Roadmap

## Phase 1

- ICP Definition
- Company Discovery
- Website Research

## Phase 2

- Lead Enrichment
- Qualification
- Structured Outputs

## Phase 3

- Personalization
- Outreach Automation
- CRM Integration

## Phase 4

- LangGraph Agents
- MCP Integrations
- Local LLM Support

## Phase 5

- Analytics
- Evaluation
- Continuous Improvement

---

# Future Integrations

- HubSpot
- Attio
- Instantly.ai
- Gmail
- Google Maps
- LinkedIn
- PostgreSQL

---

# Success Metrics

The project measures:

- Lead quality
- Research completeness
- Personalization quality
- Qualification accuracy
- Workflow speed
- Automation coverage
- Reply rate
- Meetings booked

---

# Contributing

Contributions are welcome.

Before submitting changes:

- Keep code modular.
- Document new workflows.
- Update schemas when required.
- Follow the engineering standards in `CLAUDE.md`.
- Respect agent responsibilities in `AGENTS.md`.

---

# License

This project is intended as an educational and portfolio project.

Adapt it to your own GTM workflows, AI engineering projects, or outbound sales systems.