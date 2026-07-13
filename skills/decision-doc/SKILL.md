---
name: decision-doc
description: Structure a product decision with options, trade-offs, and a clear recommendation. Takes a decision to make and outputs a concise decision document ready for stakeholder review.
argument-hint: "[decision to make]"
allowed-tools: Read, Write
---

# Decision Doc

Turn ambiguity into a structured decision. One page, clear options, explicit trade-offs, and a recommendation you can defend.

## Process

1. **Frame the decision.** What exactly are we deciding? Why now? What happens if we do nothing?
2. **Identify constraints.** Time, budget, technical limitations, dependencies, organizational politics.
3. **Generate options.** 2-4 realistic options. Always include "do nothing" if it is viable. Each option must be genuinely different, not variations of the same idea.
4. **Evaluate each option.** Pros, cons, effort estimate, risk level, and reversibility.
5. **Make a recommendation.** Pick one. State why. Be explicit about what you are giving up.
6. **Define next steps.** If approved, what happens on Day 1?

## Output Format

```
## Decision: [One-line framing of the decision]

### Context
[2-3 sentences. Why this decision matters now. What triggered it. What happens if we delay.]

### Constraints
- [Constraint 1]
- [Constraint 2]
- [Constraint 3]

### Options

#### Option A: [Name]
[1-2 sentence description]
- **Pros:** [list]
- **Cons:** [list]
- **Effort:** [T-shirt size + calendar time]
- **Risk:** [Low/Medium/High — one sentence why]

#### Option B: [Name]
[1-2 sentence description]
- **Pros:** [list]
- **Cons:** [list]
- **Effort:** [T-shirt size + calendar time]
- **Risk:** [Low/Medium/High — one sentence why]

#### Option C: [Name] (if applicable)
[same structure]

### Comparison
| Criteria | Option A | Option B | Option C |
|----------|----------|----------|----------|
| Speed to value | [fast/medium/slow] | ... | ... |
| User impact | [high/medium/low] | ... | ... |
| Effort | [S/M/L/XL] | ... | ... |
| Risk | [low/med/high] | ... | ... |
| Reversibility | [easy/hard] | ... | ... |

### Recommendation
**Go with Option [X].**
[2-3 sentences. Why this option wins. What specific factor tips the balance.]

### What We're Giving Up
[Be explicit. Every choice has a cost. Name it.]

### Reversibility
[Can we change course later? At what cost? By when does this become irreversible?]

### Next Steps (if approved)
1. [Action] — [Owner] — [By when]
2. [Action] — [Owner] — [By when]
3. [Action] — [Owner] — [By when]
```

## Rules

- Always make a recommendation. A decision doc without a recommendation is just a menu. Take a position.
- "Do nothing" is a valid option. Include it when inaction is genuinely viable, and be honest about its costs.
- Pros and cons must be specific to the decision, not generic. "Faster time to market" is only a pro if you explain faster than what and why speed matters here.
- Never present more than 4 options. If there are more, you have not narrowed the problem enough.
- Reversibility is mandatory. Irreversible decisions deserve more analysis. Reversible ones deserve faster action.
- The "What We're Giving Up" section is non-negotiable. Decisions without acknowledged trade-offs are not real decisions.
- Keep it to one page. If the decision doc is longer than 2 pages, the decision is probably two decisions. Split it.
- If the input is too vague to generate meaningful options, ask clarifying questions. Do not fabricate context.
