---
name: claude-for-legal-review
description: >
  Review a vendor agreement, NDA, or SaaS subscription against your playbook.
  Identifies the agreement structure from titles, routes to the right review skill
  (vendor-agreement-review, nda-review, saas-msa-review), and integrates the output
  into a single memo. Use when the user says "review this contract", "check this
  MSA", "is this NDA okay", "look at this SaaS agreement", or attaches an inbound
  agreement for review. From the Anthropic claude-for-legal plugin marketplace.
argument-hint: '[file path | Drive link | CLM ID | paste text]'
---

# /review

Reviews an inbound agreement against the playbook in `~/.claude/plugins/config/claude-for-legal/commercial-legal/CLAUDE.md`. Identifies the agreement structure from titles, selects the appropriate skill(s), and — if confirm_routing is enabled — checks with the user before proceeding.

## Instructions

1. **Load `~/.claude/plugins/config/claude-for-legal/commercial-legal/CLAUDE.md`.** If placeholders present, stop and prompt: "Run `/commercial-legal:cold-start-interview` first — I need to learn your playbook before I can review against it."

   Also read `~/.claude/plugins/config/claude-for-legal/commercial-legal/CLAUDE.md` → `## Review preferences` → `confirm_routing`. If the field is missing, treat it as `true`.

2. **Get the agreement:** From file path, Drive link, CLM ID, or pasted text. If none provided, ask.

3. **Read the document structure — titles first.**

   Before reading the body, extract:
   - The main agreement title (e.g., "Master Services Agreement", "Non-Disclosure Agreement")
   - All exhibit, schedule, addendum, and attachment titles (e.g., "Exhibit A — Data Processing Addendum", "Schedule 1 — Subscription Order Form", "Annex B — Service Level Agreement")

   This is the routing signal. Do not rely on body keywords alone — a 40-page MSA with "confidential" throughout is not an NDA.

4. **Select the skill(s) based on document structure.**

   Map each identified document or section to a skill:

   | Document / section title contains | Skill |
   |---|---|
   | Non-Disclosure, NDA, Confidentiality Agreement (as the *main* agreement) | **nda-review** |
   | Master Services Agreement, Professional Services, Statement of Work, Consulting Agreement | **vendor-agreement-review** |
   | Subscription, SaaS, Cloud Services, Order Form with auto-renewal, Software License with recurring fees | **saas-msa-review** (overlay on vendor-agreement-review) |
   | Data Processing Addendum, DPA, Data Processing Agreement (as exhibit or standalone) | note for **vendor-agreement-review** → data protection section |
   | Service Level Agreement, SLA (as exhibit) | note for **saas-msa-review** → SLA section |

   Multiple skills may apply. Common combinations:
   - MSA + DPA exhibit → vendor-agreement-review, with DPA noted
   - SaaS subscription + Order Form + SLA exhibit → saas-msa-review (covers all three)
   - MSA + Order Form with auto-renewal → vendor-agreement-review + saas-msa-review overlay

   When the structure is genuinely ambiguous after reading titles (e.g., a document titled "Agreement" with no exhibits listed), read the first two pages of the body to resolve it — then stop and route.

5. **Confirm routing if enabled.**

   If `confirm_routing` is `true` in `~/.claude/plugins/config/claude-for-legal/commercial-legal/CLAUDE.md` (or field is absent):

   ```
   I'm going to review this as: [agreement type(s)].

   Documents identified:
   - [Main agreement title] → [skill]
   - [Exhibit A title] → [how it will be handled]
   - [Exhibit B title] → [how it will be handled]

   Sound right? (yes / no — or tell me what I got wrong)
   ```

   Wait for confirmation before proceeding. If the user corrects the routing, apply their instruction and proceed.

   If `confirm_routing` is `false`: proceed silently. Log the routing decision at the top of the review memo so the user can see what was applied.

6. **Run the skill(s).** Follow each skill's workflow fully. If multiple skills apply, run them in sequence and integrate the output into a single memo — don't produce separate memos.

7. **Check for escalations:** If any issue exceeds the reviewer's authority per the `~/.claude/plugins/config/claude-for-legal/commercial-legal/CLAUDE.md` matrix, invoke **escalation-flagger** to route and draft the ask.

8. **Offer follow-ups:**
   - Stakeholder summary for the business owner
   - Redline .docx with tracked changes
   - CLM record creation (if connected)
   - Add to renewal register (if auto-renewal found)

## Configuring confirm_routing

Add to `~/.claude/plugins/config/claude-for-legal/commercial-legal/CLAUDE.md` → `## Review preferences`:

```markdown
## Review preferences

confirm_routing: true   # Set to false to skip routing confirmation and proceed automatically
```

The cold-start interview should ask about this preference. Default is `true` — confirmation on. As trust builds, the user can set it to `false`.

## Examples

```
/claude-for-legal-review vendor-msa.pdf
```

```
/claude-for-legal-review https://drive.google.com/file/d/ABC123
```

```
/claude-for-legal-review
[paste agreement text]
```

## Output

Full review memo per the skill's format. Routing decision logged at the top. Deviation-by-deviation, specific redline language, named approver. Saved where `~/.claude/plugins/config/claude-for-legal/commercial-legal/CLAUDE.md` → House style says work product goes.

## Review Categories

### Vendor Agreement Review

- **Standard terms** (term, termination, renewal)
- **Limitation of liability** (caps, exclusions, mutual vs. one-way)
- **Insurance requirements** (amounts, carriers, proof)
- **Indemnification** (what's covered, notice and defense)
- **IP ownership** (pre-existing, work product, license grants)
- **Confidentiality** (definition, term, exceptions)
- **Regulatory compliance** (export control, sanctions, compliance certifications)
- **Data protection** (DPA, cross-border transfers, sub-processors)
- **Service level agreements** (availability, response times, remedies)
- **Payment terms** (invoice timeline, payment methods, dispute resolution)
- **Audit rights** (audit triggers, notification, frequency limits)
- **Subcontracting** (restrictions, notice, approval rights)

### NDA Review

- **Scope and definition** (what counts as confidential)
- **Permitted use** (permitted purposes, restrictions)
- **Permitted disclosure** (who can access, legal compulsion exception)
- **Residual knowledge clause** (typical in tech, can be problematic)
- **Return or destruction** (timing, certification required)
- **Survival period** (how long after agreement ends)
- **Mutual vs. one-way** (asymmetric obligations)
- **Non-use covenant** (whether permitted or just non-disclosure)
- **Exceptions and carve-outs** (standard: public domain, independently developed, received from third party)

### SaaS Subscription Review

- **Auto-renewal and termination** (renewal date, termination notice deadline, how to cancel)
- **Service availability** (SLA targets, measurement, remedies)
- **Data access at termination** (export rights, duration, format)
- **Security and compliance** (certifications, audit rights, incident notification)
- **Pricing and price adjustments** (rate cards, escalation clauses, caps)
- **Usage limits** (per-seat, per-transaction, API rate limits)
- **Change management** (feature changes, deprecation notice periods)
- **Beta features** (separate SLA, liability, confidentiality terms)
- **Order form hierarchy** (which document wins in conflicts)
- **Support and maintenance** (hours, response times, included vs. paid)

### Escalation Triggers

Escalate to commercial counsel if agreement includes:
- **Unusual liability allocation** (uncapped, one-way in vendor's favor)
- **Broad indemnity from vendor** (covers our customers, third parties)
- **Non-standard IP ownership** (vendor claims rights to our work)
- **Regulatory obligations** (export control, sanctions, data residency)
- **Unusual audit rights** (on-site, no notice, unlimited frequency)
- **Non-standard confidentiality** (asymmetric, overly broad survival)
- **Auto-renewal traps** (short notice period, unclear cancellation)
- **Force majeure clauses** (very broad, unusual pandemic carve-outs)

---

## Related Skills (from claude-for-legal marketplace)

This skill is part of the Anthropic commercial-legal plugin. Related skills in the same plugin:

- **nda-review** - Focused review of non-disclosure agreements
- **vendor-agreement-review** - Master services agreements and vendor contracts
- **saas-msa-review** - SaaS subscriptions and cloud service agreements
- **escalation-flagger** - Routes escalations to the right approver per your authority matrix
- **amendment-history** - Tracks contract amendments over time
- **renewal-tracker** - Monitors auto-renewal dates and termination deadlines
- **stakeholder-summary** - Creates business-friendly summaries for non-lawyers

To access the full claude-for-legal plugin marketplace with all legal domains (privacy, product, corporate, employment, litigation, regulatory, AI governance, IP, and more), see https://github.com/anthropics/claude-for-legal.

---

## Plugin Configuration

The full commercial-legal plugin includes:

- **Cold-start interview** (`/commercial-legal:cold-start-interview`) - Learns your company's legal playbook, authority matrix, and preferences
- **Customization** (`/commercial-legal:customize`) - Calibrates review standards to your risk tolerance and vendor profile
- **Matter workspace** (`/commercial-legal:matter-workspace`) - Organizes contracts, amendments, and related documents per matter
- **House style** - Defines how your work product is formatted, where it's stored, and how it's reviewed internally

Requires initial setup via `/commercial-legal:cold-start-interview`.
