---
name: prd
description: Generate a concise, structured PRD from a product idea. NOT a 20-page doc — 1-2 pages that force clarity.
argument-hint: "[product idea or feature description]"
allowed-tools: Read, Write
---

# PRD Generator

Generate a sharp, actionable Product Requirements Document from a product idea or feature description. This is not a bloated enterprise PRD — it's 1-2 pages that force you to make decisions.

## Process

1. Read the provided product idea or feature description carefully.
2. Identify ambiguities and force clarity on each one — do not leave things vague.
3. Structure the PRD using the output format below.
4. Write for an audience of engineers, designers, and stakeholders who need to start building.
5. Save the PRD to a file in the current working directory as `prd-[product-name].md`.

## Output Format

### Problem
- Who has this problem? (Be specific — not "users" but "mid-market SaaS ops teams managing 50+ integrations")
- How do they solve it today?
- Why is that solution painful?

### Target Users
- Primary persona with context (role, company size, technical level, frequency of use)
- What triggers them to need this?

### Solution
- What we are building (concrete, specific)
- What we are NOT building (explicit exclusions — this is where most PRDs fail)
- Key user flows (numbered, sequential)

### Success Metrics
- Primary metric (the one number that tells you this worked)
- Secondary metrics (2-3 max)
- Each metric must be measurable and have a target

### Scope
- MVP (what ships first — the smallest thing that delivers value)
- V2 (what comes next if MVP succeeds)
- Out of scope (things that will come up but are explicitly deferred)

### Risks & Open Questions
- Technical risks
- Product risks (will users actually want this?)
- Dependencies (what could block us?)
- Open questions that need answers before or during build

## Rules

- Max 2 pages. If it's longer, you haven't made enough decisions.
- No fluff. Every sentence must add information or make a decision.
- Every section must be specific enough to start building from. "Improve user experience" is not specific.
- Use concrete examples over abstract descriptions.
- If the input is too vague to write a clear PRD, list what questions need answers first before writing.
- The "What we are NOT building" section is mandatory and must contain real exclusions.
- Success metrics must include numbers or measurable targets — "improve retention" is not a metric.
- Write in English.
