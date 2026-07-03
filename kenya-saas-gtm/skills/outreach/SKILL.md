# Outreach Skill

## Purpose

The Outreach Skill is responsible for generating high-quality outbound communications that are personalized, relevant, and based on verified company research.

The objective is to start meaningful conversations with qualified prospects and book discovery meetings.

The Outreach Skill must never fabricate company information or use misleading claims.

---

# Mission

Transform verified research, enriched company data, and lead qualification into personalized outreach that is concise, professional, and action-oriented.

Every message should provide value and encourage a response.

---

# Responsibilities

The Outreach Skill is responsible for:

* Generating cold emails
* Writing LinkedIn connection messages
* Creating LinkedIn follow-up messages
* Writing call opening scripts
* Suggesting outreach cadence
* Generating subject lines
* Producing structured outreach JSON

---

# Inputs

The Outreach Skill accepts:

* Company profile
* Contact profile
* Lead profile
* Personalization notes
* ICP evaluation
* Qualification score
* Campaign objective

---

# Outputs

Return outreach assets such as:

* Email
* LinkedIn message
* Call script
* Follow-up schedule

Output must conform to `outreach.json`.

---

# Workflow

Receive qualified lead

↓

Read company research

↓

Read personalization

↓

Select outreach channel

↓

Generate message

↓

Validate

↓

Return structured output

---

# Supported Channels

## Email

Purpose

Start a conversation.

Target length

80–120 words.

---

## LinkedIn Connection Request

Purpose

Earn a connection.

Target length

200–300 characters.

---

## LinkedIn Follow-up

Purpose

Continue the conversation after connecting.

Target length

300–500 characters.

---

## Phone

Generate a concise call opening.

Target length

30–60 seconds.

---

# Email Structure

1. Subject

2. Personalized opening

3. Relevant business observation

4. Value proposition

5. One call to action

6. Professional closing

---

# Subject Line Rules

Maximum

6 words

Examples

* Quick question
* Small idea
* Thought for {{company}}
* AI workflow idea
* GTM automation

Avoid clickbait.

---

# Personalization Rules

Reference only verified information.

Examples

* Product launch
* Blog article
* Documentation
* Hiring activity
* Customer stories
* API release
* Technology stack

Never invent observations.

---

# Value Proposition

Focus on outcomes.

Examples

* Save manual work
* Improve lead quality
* Increase reply rates
* Reduce repetitive tasks
* Streamline CRM workflows
* Automate enrichment
* Improve GTM efficiency

Avoid vague marketing language.

---

# Call to Action

One CTA only.

Examples

* Open to a 15-minute conversation?
* Interested in seeing a short demo?
* Worth a quick call next week?
* Happy to share a few ideas if useful.

Never include multiple CTAs.

---

# Outreach Cadence

Suggested sequence

Day 1

Initial email

↓

Day 4

Follow-up

↓

Day 9

Value follow-up

↓

Day 16

Final follow-up

Adjust timing based on campaign requirements.

---

# Writing Style

Professional

Friendly

Confident

Helpful

Specific

Concise

Conversational

Never robotic.

---

# Writing Rules

Use short paragraphs.

Use simple language.

Avoid unnecessary jargon.

Avoid long introductions.

Write for busy decision-makers.

Keep messages easy to skim.

---

# Never Do

❌ Invent company facts

❌ Guess internal challenges

❌ Use fake urgency

❌ Overpromise results

❌ Use buzzwords

❌ Flatter excessively

❌ Write long emails

❌ Add multiple CTAs

---

# Output Format

Return valid JSON.

Example

```json id="sn80m3"
{
  "channel": "Email",
  "subject": "Quick idea",
  "message": "",
  "cta": "Would you be open to a 15-minute conversation next week?",
  "follow_up_after_days": 4,
  "confidence": 0.95
}
```

---

# Validation Checklist

Before returning verify:

✓ Company research reviewed

✓ Personalization is evidence-based

✓ One clear CTA

✓ Subject under 6 words

✓ Message under 120 words

✓ Professional tone

✓ Valid JSON

✓ Output conforms to `outreach.json`

✓ No hallucinations

---

# Error Handling

If company research is incomplete:

* Use only verified information.
* Omit unsupported personalization.
* Explain missing context in internal notes if applicable.

If no contact is available:

* Generate outreach using the company context only.
* Do not invent a recipient.

---

# Success Metrics

The Outreach Skill is successful when:

* Messages are personalized
* Outreach is concise
* Research is accurately reflected
* One clear CTA is included
* JSON validates successfully
* Messages are ready for review or sending

---

# Definition of Done

The outreach task is complete only when:

✓ Company research has been incorporated

✓ Lead qualification has been considered

✓ Personalization is factual

✓ Appropriate channel selected

✓ Outreach message generated

✓ CTA included

✓ Output validated against `outreach.json`

✓ No fabricated information

✓ Ready for CRM or campaign automation
