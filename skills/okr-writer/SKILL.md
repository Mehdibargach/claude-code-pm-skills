---
name: okr-writer
description: Turn business goals into structured OKRs with measurable Key Results, linked initiatives, alignment check, and anti-goals. Takes a strategic priority and outputs ready-to-use OKRs.
argument-hint: "[business goal or strategic priority]"
allowed-tools: Read, Write
---

# OKR Writer

Transform vague business goals into tight, measurable OKRs. No vanity metrics, no sandbagged targets, no objectives that read like tasks.

## Process

1. **Parse the goal.** Understand what the business is trying to achieve and the time horizon (default: quarterly).
2. **Write the Objective.** Qualitative, inspiring, and time-bound. It answers "where do we want to go?" — not "what will we do?"
3. **Define Key Results.** 3-5 measurable outcomes. Each must have a specific number. They answer "how will we know we got there?"
4. **Link Initiatives.** What activities will move the Key Results? These are the actual work items.
5. **Check alignment.** How does this OKR connect to the company or team-level goal above it?
6. **Define anti-goals.** What is explicitly out of scope? This prevents scope creep and misaligned effort.

## Output Format

```
## OKR: [Quarter/Period]

### Objective
[One sentence. Qualitative. Inspiring. Clear direction. Time-bound.]

### Key Results
| # | Key Result | Baseline | Target | How to Measure |
|---|-----------|----------|--------|----------------|
| KR1 | [Specific measurable outcome] | [current] | [target] | [data source] |
| KR2 | [Specific measurable outcome] | [current] | [target] | [data source] |
| KR3 | [Specific measurable outcome] | [current] | [target] | [data source] |
| KR4 | [Specific measurable outcome] | [current] | [target] | [data source] |

### Initiatives
| Initiative | Moves KR | Owner | Effort |
|-----------|----------|-------|--------|
| [What we'll do] | KR1, KR2 | [team/person] | [S/M/L] |
| [What we'll do] | KR2 | [team/person] | [S/M/L] |
| [What we'll do] | KR3, KR4 | [team/person] | [S/M/L] |

### Alignment
- **Company goal this supports:** [Which higher-level goal]
- **How it connects:** [One sentence — the causal link]

### Anti-Goals
- [What this objective is NOT about]
- [What we will explicitly NOT do this quarter]
- [Adjacent area we are choosing to deprioritize]
```

## Rules

- Objectives are outcomes, not outputs. "Launch feature X" is a task. "Become the preferred tool for [persona]" is an objective.
- Key Results must have numbers. "Improve retention" is not a KR. "Increase 30-day retention from 45% to 55%" is.
- Targets should be ambitious but not delusional. A good KR has roughly a 70% chance of being hit. If you are 100% confident, the target is too low.
- Each KR must specify how it will be measured and where the data comes from. If you cannot measure it, it is not a KR.
- 3-5 Key Results max. More than 5 means the Objective is too broad — split it.
- Initiatives are NOT Key Results. Initiatives are what you do. Key Results are what happens as a consequence.
- Anti-goals are mandatory. Every OKR implicitly deprioritizes something — name it explicitly to prevent drift.
- If the input goal is too vague ("grow the business"), ask for specifics: which segment, which metric, what time frame.
- Do not write OKRs for more than one Objective at a time unless explicitly asked. Focus beats breadth.
