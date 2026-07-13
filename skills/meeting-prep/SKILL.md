---
name: meeting-prep
description: Generate a 1-page meeting brief with context, objectives, key questions, pre-read, expected decisions, and a parking lot. Takes a meeting topic or agenda and outputs a structured prep document.
argument-hint: "[meeting topic or agenda]"
allowed-tools: Read, Write
---

# Meeting Prep

Create a tight, 1-page brief so everyone walks in aligned and walks out with decisions. Meetings without prep are just group therapy.

## Process

1. **Parse the meeting context.** Understand the topic, who is likely in the room, and what triggered the meeting.
2. **Define the objective.** What must the group walk out with? A decision, alignment, a plan, or information shared.
3. **Generate key questions.** 3-5 specific questions the meeting must answer. Not open-ended ("thoughts on X?") but pointed ("do we go with A or B?").
4. **Identify pre-read.** What do attendees need to know before the meeting to avoid wasting time on context-setting.
5. **List expected decisions.** What choices will be made in this meeting, and who has the final call.
6. **Set the parking lot.** What topics are adjacent but explicitly out of scope for this meeting.

## Output Format

```
## Meeting Brief: [Topic]
**Date:** [if provided] | **Duration:** [if provided] | **Type:** [Decision / Alignment / Brainstorm / Review]

### Context
[1-2 sentences. Why this meeting is happening now. What triggered it.]

### Objective
Walk out with: [specific deliverable — a decision on X, alignment on Y, a plan for Z]

### Key Questions to Answer
1. [Specific, answerable question]
2. [Specific, answerable question]
3. [Specific, answerable question]
4. [Specific, answerable question] (if needed)
5. [Specific, answerable question] (if needed)

### Pre-Read
Attendees should review before the meeting:
- [Document/data/context + why it matters]
- [Document/data/context + why it matters]
- [Key number or fact to have in mind]

### Decisions Expected
| Decision | Options | Decision Maker |
|----------|---------|---------------|
| [What needs deciding] | [A vs. B vs. C] | [Who has final call] |
| [What needs deciding] | [A vs. B] | [Who has final call] |

### Parking Lot (do NOT discuss)
- [Topic that will derail this meeting]
- [Adjacent but separate concern — schedule a follow-up]
- [Interesting but not urgent]

### Suggested Agenda (if time is provided)
| Time | Topic | Owner |
|------|-------|-------|
| [5 min] | Context + objective | [facilitator] |
| [15 min] | [Key question 1-2] | [relevant person] |
| [15 min] | [Key question 3-4] | [relevant person] |
| [10 min] | Decision + next steps | [facilitator] |
| [5 min] | Recap + action items | [facilitator] |
```

## Rules

- The objective must be concrete. "Discuss the roadmap" is not an objective. "Decide Q3 priorities and assign owners" is.
- Key questions must be answerable in the meeting. If a question requires research that has not been done, it belongs in the pre-read as an action item, not in the meeting.
- Every meeting must have at least one expected decision. If there are no decisions to make, question whether the meeting should be an email instead. Say this explicitly.
- The parking lot is not optional. Every meeting has scope creep risk. Name the likely tangents upfront.
- Pre-read must be specific. "Review the doc" is useless. "Read sections 2-3 of the PRD, focus on the trade-offs table" is useful.
- Keep the entire brief to one page. If it is longer, the meeting scope is too broad — suggest splitting.
- If the input is just a meeting title with no context, ask 2-3 clarifying questions rather than guessing.
- Suggest a time allocation only if the meeting duration is provided.
