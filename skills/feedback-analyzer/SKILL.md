---
name: feedback-analyzer
description: Classify and analyze raw user feedback into themes, sentiment, and actionable insights. Takes pasted feedback text or a path to a CSV file and returns structured patterns and recommendations.
argument-hint: "[paste feedback or path to CSV]"
allowed-tools: Read, Write, Bash, Glob, Grep
---

# Feedback Analyzer

Take raw, messy user feedback and turn it into structured, actionable insights. Works with pasted text, CSV files, or any text-based feedback dump.

## Process

1. **Ingest the feedback** — If a file path is provided, read it. If CSV, parse it using Bash (csvtool, awk, or python). If pasted text, split by logical entries (one per line, or by paragraph).
2. **Classify each piece** — For every feedback entry, assign:
   - **Theme** (e.g., "Onboarding", "Pricing", "Performance", "Missing Feature")
   - **Sentiment** (Positive / Neutral / Negative)
   - **Urgency** (High / Medium / Low — based on language intensity and frequency)
   - **Type** (Bug report / Feature request / Complaint / Praise / Question)
3. **Aggregate patterns** — Count themes, calculate sentiment distribution, identify the top recurring issues.
4. **Surface insights** — Find the non-obvious patterns: themes that correlate, sentiment shifts, signals that suggest churn risk or expansion opportunity.
5. **Write recommendations** — Translate patterns into concrete next steps for a PM.

## Output Format

### Summary Stats
- Total feedback entries: X
- Sentiment breakdown: X% positive, X% neutral, X% negative
- Top theme: [theme] (X mentions)
- Date range (if available): [range]

### Themes Table

| Theme | Count | Sentiment (avg) | Urgency | Example Quote |
|-------|-------|-----------------|---------|---------------|
| ... | ... | ... | ... | "..." |

### Top 3 Patterns
Numbered list. Each pattern includes: what it is, why it matters, and how confident we are (based on volume).

### Recommended Actions

| Priority | Action | Based On | Expected Impact |
|----------|--------|----------|-----------------|
| P0 | ... | ... | ... |
| P1 | ... | ... | ... |
| P2 | ... | ... | ... |

### Raw Classified Data
If fewer than 50 entries, include a full table with each entry classified. If more than 50, save to a file and note the path.

## Rules

- Do not editorialize feedback. Classify what users said, not what you think they meant.
- If a feedback entry touches multiple themes, assign the dominant one but note the secondary theme.
- Urgency is based on language intensity ("broken", "can't use", "blocking" = High) and frequency, not on your opinion of importance.
- Minimum 3 themes required. If all feedback collapses into one theme, split it into sub-themes.
- Always include at least one verbatim quote per theme. Real words beat summaries.
- Write in English.
- Keep analysis output under 2 pages. The raw classified data table can be longer if needed.
- Be opinionated in recommendations: tell the PM what to do first and why, don't just list options.
- If the feedback volume is too small to draw conclusions (fewer than 5 entries), say so explicitly and flag which patterns are weak signals.
