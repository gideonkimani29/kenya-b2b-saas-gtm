# Personalization Skill

## Purpose

The Personalization Skill transforms verified company and contact research into relevant, evidence-based personalization that improves outbound engagement.

The goal is to make every outreach message feel researched, thoughtful, and relevant without fabricating information or relying on generic compliments.

Personalization should demonstrate an understanding of the prospect's business, not just mention their company name.

---

# Mission

Generate personalized insights that help start meaningful conversations with decision-makers.

Every personalization must be supported by publicly available evidence.

Never invent facts to make a message appear more personalized.

---

# Responsibilities

The Personalization Skill is responsible for:

* Analyzing company research
* Identifying personalization opportunities
* Extracting business context
* Connecting observations to business value
* Generating opening lines
* Suggesting value propositions
* Highlighting relevant pain points
* Preparing structured personalization data

---

# Inputs

The skill accepts:

* Company profile
* Contact profile
* Lead profile
* Research summary
* Buying signals
* Technology stack
* ICP evaluation

---

# Outputs

Return structured JSON containing:

* Personalized opening
* Key observations
* Relevant pain points
* Suggested value proposition
* Confidence score

The output should integrate with:

* outreach.json
* lead.json

---

# Workflow

Receive company research

↓

Review company profile

↓

Review contact profile

↓

Identify verified observations

↓

Generate personalization

↓

Validate

↓

Return structured output

---

# Personalization Sources

Prefer information from:

1. Official company website
2. Product pages
3. Documentation
4. Blog posts
5. Careers page
6. Public customer stories
7. Press releases
8. Public technical documentation

---

# Strong Personalization Signals

Good personalization includes:

* Product launch
* New feature announcement
* API documentation
* Hiring activity
* Customer success stories
* New integrations
* Pricing changes
* Public roadmap
* Engineering blog
* Industry specialization

---

# Weak Personalization

Avoid relying on:

* Company name only
* Generic compliments
* Location alone
* Industry alone

These should not be the primary personalization.

---

# Personalization Framework

Step 1

Identify one verified observation.

↓

Step 2

Explain why it matters.

↓

Step 3

Connect it to a relevant challenge or opportunity.

↓

Step 4

Introduce a relevant solution.

---

# Opening Line Rules

The opening should:

* Reference one verified fact.
* Be natural.
* Be specific.
* Stay under 30 words.

Examples of acceptable approaches:

* Mention a recent product update.
* Reference a published case study.
* Mention a new integration.
* Refer to hiring activity.

Do not use generic praise.

---

# Pain Point Identification

Infer only reasonable, role-relevant challenges based on public information.

Examples:

* Manual sales workflows
* CRM inefficiencies
* Lead qualification bottlenecks
* Time-consuming research
* Repetitive administrative work

Do not claim knowledge of internal problems.

---

# Value Proposition

Suggest value that aligns with the observed context.

Examples:

* Improve lead quality
* Reduce manual research
* Automate repetitive GTM tasks
* Increase outbound efficiency
* Improve personalization at scale
* Streamline CRM workflows

---

# Writing Style

Professional

Helpful

Specific

Concise

Evidence-based

Respectful

Conversational

---

# Never Do

❌ Invent product launches

❌ Guess company priorities

❌ Assume funding status

❌ Assume employee count

❌ Guess revenue

❌ Use exaggerated praise

❌ Write generic openings

❌ Fabricate pain points

---

# Output Format

Return valid JSON.

Example

```json id="bkkd1p"
{
  "opening_line": "I noticed your team recently published API documentation for your platform.",
  "observation": "Public API documentation",
  "pain_points": [
    "Scaling outbound efficiently",
    "Maintaining CRM data quality"
  ],
  "value_proposition": "Automating lead research and personalization for your sales team.",
  "confidence": 0.94
}
```

---

# Validation Checklist

Before returning the response verify:

✓ Observation is publicly verifiable

✓ Opening is under 30 words

✓ No generic compliments

✓ Pain points are reasonable and not presented as facts

✓ Value proposition aligns with the observed context

✓ JSON is valid

✓ Confidence score included

✓ No hallucinations

---

# Error Handling

If research is insufficient:

* Return a neutral personalization.
* Avoid unsupported references.
* Leave unavailable fields as `null` where appropriate.
* Lower the confidence score.

Do not invent information to improve the message.

---

# Success Metrics

The Personalization Skill is successful when:

* The personalization is grounded in verified research.
* The opening feels relevant and natural.
* The value proposition matches the prospect's context.
* Outputs are reusable across email, LinkedIn, and call scripts.
* JSON validates successfully.

---

# Definition of Done

The personalization task is complete only when:

✓ Company research has been analyzed

✓ At least one verified observation has been identified

✓ Opening line generated

✓ Relevant value proposition created

✓ Reasonable pain points suggested

✓ Confidence score assigned

✓ Output validated against project schemas

✓ No fabricated information

✓ Ready for use by the Outreach Skill
