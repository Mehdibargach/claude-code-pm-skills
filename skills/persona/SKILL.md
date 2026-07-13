---
name: persona
description: Generate actionable user personas from a product description, user data, or research notes. Not marketing fluff — behavioral personas that drive product decisions.
argument-hint: "[product description, user data, or research notes]"
allowed-tools: Read, Write
---

# Persona Generator

Create user personas that actually influence product decisions. Not stock photos with fake names — behavioral profiles built around goals, pain points, and decision patterns.

## Process

1. **Parse the input.** Read the product description, user research, support tickets, or any context provided.
2. **Identify distinct user segments.** Look for differences in goals, behaviors, technical level, frequency of use, and willingness to pay. Aim for 2-4 personas — more than 4 means you haven't prioritized.
3. **For each persona, define behavioral attributes.** Focus on what they do and why, not demographics.
4. **Rank personas by strategic importance.** Who is the primary user you're building for? Who is secondary? Who are you explicitly NOT building for?
5. **Map personas to product decisions.** How does each persona change what you build?
6. **Save the output** to a file in the current working directory as `personas-[product-name].md`.

## Output Format

### Personas: [Product Name]
**Number of personas:** [N]
**Primary persona:** [name]
**Date:** [date]

---

### Persona 1: [Descriptive Name] (PRIMARY)

**One-line summary:** [Who they are and what they need — one sentence.]

**Goals**
- [Primary goal — what success looks like for them]
- [Secondary goal]

**Pain Points**
- [Current frustration #1 — be specific]
- [Current frustration #2]
- [Current frustration #3]

**Behavior Patterns**
- **Frequency:** [How often they'd use the product]
- **Technical level:** [Novice / Intermediate / Advanced]
- **Decision process:** [How they evaluate and adopt tools — impulse, committee, trial period?]
- **Current solution:** [What they use today and why it's not good enough]

**Key Quote** (representative, not real)
> "[A sentence this person would say that captures their core need]"

**Product Implications**
- [What to build or prioritize FOR this persona]
- [What to avoid or deprioritize]
- [UX consideration specific to their behavior]

---

### Persona 2: [Descriptive Name] (SECONDARY)

[Same structure as above]

---

### Persona Priorities

| Persona | Priority | Why | Build For | Don't Build For |
|---------|----------|-----|-----------|-----------------|
| [name] | Primary | [reason] | [what] | [what] |
| [name] | Secondary | [reason] | [what] | [what] |
| [name] | Excluded | [reason] | — | [what they'd want that you won't do] |

### Anti-Persona: [Name]
**Who they are:** [Description of a user you are explicitly NOT building for]
**Why excluded:** [Strategic reason — not "they're bad users" but "serving them would compromise the core experience"]

## Rules

- 2-4 personas max. If you need more, you haven't made hard enough choices about who you're building for.
- Every persona must be distinct. If two personas would make the same product decisions, merge them.
- No demographics without behavioral relevance. "Age 35, lives in Austin" is useless. "Evaluates tools solo, doesn't need committee buy-in" is useful.
- The anti-persona is mandatory. Knowing who you're NOT building for is as important as knowing who you are.
- Goals must be the user's goals, not your business goals. "Increase our revenue" is not a user goal.
- Pain points must be specific and observable. "Frustrated with the product" is not a pain point. "Spends 30 minutes every Monday manually exporting data to a spreadsheet" is.
- Product Implications must be actionable. Each persona should change at least one product decision.
- If the input doesn't provide enough context to differentiate personas, say so and ask for user research, support data, or behavioral observations.
- Write in English.
