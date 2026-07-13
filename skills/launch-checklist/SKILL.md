---
name: launch-checklist
description: Generate a complete go-to-market checklist from a product description. Everything you need to launch.
argument-hint: "[product or feature description]"
allowed-tools: Read, Write
---

# Launch Checklist Generator

Generate a complete, product-specific launch checklist from a product or feature description. Covers pre-launch, launch day, and post-launch — with owners, timing, and blocking dependencies.

## Process

1. Read the product or feature description.
2. Identify the type of launch (new product, major feature, minor update, beta) to calibrate checklist depth.
3. Generate a checklist tailored to this specific product — not a generic template.
4. Flag blocking items versus nice-to-have items.
5. Include timing (T-2 weeks, T-1 week, Launch day, T+1 day, T+1 week).
6. Save the output to a file in the current working directory as `launch-checklist-[product-name].md`.

## Output Format

### Launch Overview
- **Product/Feature:** [name]
- **Target launch date:** [date or TBD]
- **Launch type:** New product / Major feature / Minor update / Beta
- **Target audience:** [specific]

---

### Pre-Launch (T-2 weeks to T-1 day)

Each item format: `- [ ] [Specific item] — **Owner:** [role] — **Blocking:** Yes/No — **Due:** [timing]`

#### Internal Readiness
Generate 4-6 items specific to this product covering: engineering sign-off, QA, performance testing (if applicable), rollout strategy, and rollback plan. Only include items relevant to the launch type.

#### Documentation & Support
Generate 3-5 items specific to this product covering: user-facing docs, support team enablement, and internal knowledge base. Tailor to the product's support model.

#### Communications Prep
Generate 3-5 items specific to this product covering: release notes, announcements (channels depend on product), and sales/CS enablement. Only include channels relevant to this product's audience.

---

### Launch Day (T-0)

#### Rollout
Generate 3-5 items covering: deployment, verification, monitoring, and on-call. Tailor to the product's deployment model (staged rollout, feature flag, big bang, etc.).

#### Communications
Generate 3-5 items covering: publishing announcements and notifying internal teams. Only include channels relevant to this product.

#### Monitoring
Generate 3-4 items covering: error rates, performance, user-reported issues, and support volume. Reference specific metrics from the product description.

---

### Post-Launch (T+1 day to T+2 weeks)

#### First 24 Hours
Generate 3-4 items covering: monitoring review, support triage, initial feedback, and rollout expansion decision.

#### First Week
Generate 4-5 items covering: metrics tracking against targets, feedback review, bug triage, full rollout, and retrospective.

#### First Two Weeks
Generate 3-4 items covering: stakeholder metrics review, fast-follow prioritization, roadmap updates, and launch documentation.

---

### Stakeholder Checklist

| Stakeholder | What they need to know | By when | Owner | Status |
|-------------|----------------------|---------|-------|--------|
| [Engineering lead] | [Specific info] | [Date] | [Who tells them] | [ ] |
| [Support team] | [Specific info] | [Date] | [Who tells them] | [ ] |
| [Sales team] | [Specific info] | [Date] | [Who tells them] | [ ] |
| [Executive sponsor] | [Specific info] | [Date] | [Who tells them] | [ ] |
| [Marketing] | [Specific info] | [Date] | [Who tells them] | [ ] |

## Rules

- Be specific to the product. "Prepare marketing materials" is generic. "Draft announcement email highlighting [specific feature benefit] for [specific audience]" is specific.
- Every item must have a clear owner role (not necessarily a name, but a role).
- Clearly mark what is BLOCKING launch versus nice-to-have. A launch should not be held for non-blocking items.
- Include timing relative to launch date (T-2w, T-1w, T-1d, T-0, T+1d, T+1w).
- Adapt the depth to the launch type. A minor bug fix does not need a full GTM checklist. A new product does.
- The stakeholder checklist must include specific information per stakeholder, not just "inform them."
- If the product description is too vague to generate specific checklist items, list what information is needed first.
