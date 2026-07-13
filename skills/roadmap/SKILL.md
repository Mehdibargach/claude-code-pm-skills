---
name: roadmap
description: Transform a list of priorities, features, or initiatives into a structured product roadmap. Now/Next/Later format with dependencies, effort sizing, and strategic rationale.
argument-hint: "[list of features, priorities, or strategic goals]"
allowed-tools: Read, Write
---

# Roadmap Generator

Turn a messy list of features, priorities, or goals into a clear product roadmap. Not a Gantt chart — a strategic communication tool that shows what you're doing, in what order, and why.

## Process

1. **Ingest the input.** Parse the list of features, initiatives, or goals. Accept inline lists, pasted backlogs, or file paths.
2. **Identify strategic themes.** Group related items into 3-5 themes (e.g., "Onboarding," "Monetization," "Platform stability"). Every item must belong to a theme.
3. **Assign time horizons.** Place each item in Now (this quarter), Next (next quarter), or Later (future / needs validation). Base this on dependencies, effort, and strategic priority — not just urgency.
4. **Map dependencies.** Identify items that block or unlock other items. Flag critical path items.
5. **Size effort.** T-shirt sizing: S (< 2 weeks), M (2-6 weeks), L (6-12 weeks), XL (> 12 weeks).
6. **Write the strategic rationale.** One sentence per time horizon explaining why this sequencing makes sense.
7. **Save the output** to a file in the current working directory as `roadmap-[context].md`.

## Output Format

### Roadmap: [Product/Team/Context]
**Last updated:** [date]
**Planning horizon:** [e.g., Q2-Q4 2026]
**Capacity assumption:** [if known, e.g., 1 team of 5 engineers]

---

### Strategic Themes

| Theme | Description | Key Metric |
|-------|-------------|------------|
| [theme] | [one line] | [what moves if this theme succeeds] |

---

### Now (This Quarter)
**Rationale:** [Why these items first — one sentence.]

| Priority | Item | Theme | Size | Dependencies | Status |
|----------|------|-------|------|-------------|--------|
| 1 | [item] | [theme] | S/M/L/XL | [blocker or "None"] | Not started / In progress |

### Next (Next Quarter)
**Rationale:** [Why these items second — one sentence.]

| Priority | Item | Theme | Size | Dependencies | Confidence |
|----------|------|-------|------|-------------|------------|
| 1 | [item] | [theme] | S/M/L/XL | [what must ship first] | High/Med/Low |

### Later (Future / Needs Validation)
**Rationale:** [Why these are deferred — one sentence.]

| Item | Theme | Size | Why Later |
|------|-------|------|-----------|
| [item] | [theme] | S/M/L/XL | [specific reason: needs data, blocked, low priority, etc.] |

---

### Dependencies Map
- [Item A] → blocks [Item B] (must ship before B can start)
- [Item C] → unlocks [Item D, Item E]

### Key Trade-offs
- **[Trade-off 1]:** [What you chose and what you gave up. Be explicit.]
- **[Trade-off 2]:** [What you chose and what you gave up.]

### What's NOT on the Roadmap
- [Item deliberately excluded] — Reason: [why]

## Rules

- Now/Next/Later is the default format. Do not use dates or sprints unless the user explicitly asks for them.
- Every item must belong to a theme. If an item doesn't fit any theme, question whether it belongs on the roadmap.
- "Later" is not a parking lot. Every item in Later must have a specific reason for deferral — not just "lower priority."
- Dependencies must be explicit. If Item B cannot start until Item A ships, say so.
- The "What's NOT on the Roadmap" section is mandatory. A roadmap that doesn't say no to anything is not a roadmap.
- Size estimates must be consistent. If two items are both "M" they should be roughly the same effort.
- Do not overload Now. If Now has more than 5-6 items, push back — that's not a plan, it's a wish list.
- If the input list has no strategic context, ask what the team's top 1-2 goals are before sequencing. Order without strategy is just a list.
- Write in English.
