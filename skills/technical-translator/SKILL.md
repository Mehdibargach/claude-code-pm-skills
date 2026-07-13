---
name: technical-translator
description: Translate a technical document (API spec, architecture doc, RFC, eng proposal) into PM-friendly language. What it means for the product and users.
argument-hint: "[path to technical document]"
allowed-tools: Read, Write
---

# Technical Translator

Read a technical document and translate it into language a PM can act on. Not dumbed down — translated. The goal is to preserve nuance while making it actionable for product decisions.

## Process

1. Read the technical document at the provided file path.
2. Identify the core technical concepts, decisions, and trade-offs.
3. Translate each into product and user impact.
4. Flag what the PM must understand versus what is nice-to-know context.
5. Surface decisions the PM needs to make or influence.
6. List questions the PM should bring to engineering.
7. Save the output to a file in the current working directory as `translated-[original-filename].md`.

## Output Format

### TL;DR
1-2 sentences. What is this document about and why should the PM care?

### What This Means for the Product
- How does this change what we can build?
- Does this open new capabilities or close off options?
- Does this affect our roadmap or timelines?
- Any impact on product architecture or platform strategy?

### What This Means for Users
- Will users notice anything? (Performance, UI changes, new features, breaking changes)
- Does this affect specific user segments differently?
- Any migration, downtime, or behavior changes users need to know about?
- Impact on user data, privacy, or security?

### Key Decisions the PM Needs to Make
For each decision:
- What is the decision?
- What are the options?
- What are the trade-offs (in product terms, not technical terms)?
- What is the engineering team's recommendation and why?

### Questions to Ask Engineering
- Clarifying questions the PM should bring to the next sync
- "What happens if..." scenarios that aren't addressed in the doc
- Timeline and resource implications to validate

### Risks
- Technical risks translated to product impact ("If the migration fails, users will experience X")
- Timeline risks
- Dependency risks
- Things the doc assumes that might not be true

### Glossary (if needed)
- Technical terms used in the document with plain-language definitions
- Only include terms the PM will encounter again — skip one-off jargon

## Rules

- Do not dumb down. Translate. A PM reading this should understand the nuance, not a watered-down version.
- Clearly separate what the PM MUST understand (affects decisions) from nice-to-know context.
- When translating trade-offs, always frame them in terms of user impact, timeline impact, or cost impact.
- If the technical document is ambiguous, flag the ambiguity rather than guessing.
- Preserve the original document's structure references so the PM can go back to the source for specific sections.
- If the document contains code, don't reproduce the code — explain what it does and why it matters.
- Never invent product implications that aren't supported by the technical content.
