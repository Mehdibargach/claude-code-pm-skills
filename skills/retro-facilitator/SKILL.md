---
name: retro-facilitator
description: Facilitate a team retrospective. Generate a retro board with prompts (4Ls, Start-Stop-Continue, Sailboat formats) or synthesize retro notes into grouped themes and prioritized action items.
argument-hint: "[retro format: 4Ls, start-stop-continue, sailboat, or paste notes to synthesize]"
allowed-tools: Read, Write
---

# Retro Facilitator

Two modes: GENERATE a retro board with prompts, or SYNTHESIZE raw retro notes into themes and actions. Retros without actions are just venting sessions.

## Process

### Mode Detection
- If the input is a format name (4Ls, start-stop-continue, sailboat) → GENERATE mode
- If the input is pasted notes, bullet points, or raw feedback → SYNTHESIZE mode
- If unclear, ask.

### GENERATE Mode
1. **Select format.** Parse which retro format the user wants.
2. **Create sections.** Build the board structure for that format with section descriptions.
3. **Add seed prompts.** 2-3 starter questions per section to get the team thinking.
4. **Add facilitation tips.** How to run each section effectively.
5. **Suggest time allocation.** Based on a 60-minute retro by default.

### SYNTHESIZE Mode
1. **Ingest notes.** Read all raw input — sticky notes, bullet points, free-form text.
2. **Group into themes.** Cluster related items. Name each theme clearly.
3. **Prioritize themes.** Rank by frequency (how many people mentioned it) and impact (how much it affects the team).
4. **Generate action items.** Each action must have: what, who, and by when.
5. **Identify patterns.** If context from previous retros is available, flag recurring themes.

## Output Format

### GENERATE Mode
```
## Retro Board: [Format Name]
**Duration:** 60 minutes | **Team size:** [adjust if specified]

### Format Overview
[2-3 sentences explaining this retro format and when it works best.]

### Section 1: [Name]
**What goes here:** [description]
**Seed prompts:**
- [Specific question to spark discussion]
- [Specific question to spark discussion]
- [Specific question to spark discussion]
**Facilitation tip:** [How to run this section]

### Section 2: [Name]
[same structure]

### Section 3: [Name]
[same structure]

### Section 4: [Name] (if applicable)
[same structure]

### Time Allocation
| Phase | Duration | Notes |
|-------|----------|-------|
| Check-in | 5 min | Quick round — one word for the sprint |
| Individual writing | 10 min | Silent, everyone adds stickies |
| Group & discuss | 25 min | Read, cluster, vote on top themes |
| Action items | 15 min | Assign owners and deadlines |
| Close | 5 min | One takeaway per person |

### Facilitation Tips
- [Tip about creating psychological safety]
- [Tip about keeping discussion productive]
- [Tip about ensuring actions get assigned]
```

### SYNTHESIZE Mode
```
## Retro Synthesis: [Date/Sprint]

### Themes (ranked by frequency + impact)

#### Theme 1: [Name] (mentioned by [N] people)
- [Grouped item]
- [Grouped item]
- [Grouped item]
**Root cause:** [One sentence hypothesis]

#### Theme 2: [Name] (mentioned by [N] people)
- [Grouped item]
- [Grouped item]
**Root cause:** [One sentence hypothesis]

#### Theme 3: [Name]
[same structure]

### Action Items
| # | Action | Owner | Due | Theme |
|---|--------|-------|-----|-------|
| 1 | [Specific, actionable task] | [person] | [date] | Theme 1 |
| 2 | [Specific, actionable task] | [person] | [date] | Theme 2 |
| 3 | [Specific, actionable task] | [person] | [date] | Theme 1 |

### Patterns (if prior retro context available)
- **Recurring:** [Theme that keeps appearing] — previous actions may not have been effective
- **New:** [Theme appearing for the first time] — investigate
- **Resolved:** [Theme from last retro that did not appear] — actions worked

### Team Health Signal
[One sentence summary: is the team trending better, worse, or stable based on these notes?]
```

## Supported Formats

### 4Ls
- **Loved:** What went well that we want to keep doing
- **Learned:** What we discovered or gained insight on
- **Lacked:** What was missing or insufficient
- **Longed For:** What we wish we had

### Start-Stop-Continue
- **Start:** What should we begin doing
- **Stop:** What should we stop doing
- **Continue:** What is working and should keep going

### Sailboat
- **Wind (propelling us):** What is pushing us forward
- **Anchor (holding us back):** What is slowing us down
- **Rocks (risks ahead):** What could hurt us
- **Island (destination):** Where we are trying to get to

## Rules

- In GENERATE mode, seed prompts must be specific to the team context if provided. Generic prompts like "what went well?" waste everyone's time.
- In SYNTHESIZE mode, every theme must have at least one action item. Themes without actions are just observations.
- Action items must be specific and assigned. "Improve communication" is not an action. "Schedule a 15-min daily sync for the next 2 weeks — owned by [person]" is.
- Do not create more than 5 themes when synthesizing. If there are more, merge the smaller ones.
- Maximum 5 action items. Teams that leave retros with 10 actions complete zero of them.
- Always include a team health signal in SYNTHESIZE mode. The point of retros is continuous improvement — track the direction.
- If notes are too sparse to synthesize meaningfully (fewer than 5 items), say so and suggest the team needs to create more psychological safety for honest feedback.
