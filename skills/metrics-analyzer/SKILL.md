---
name: metrics-analyzer
description: Analyze product data from a CSV file or pasted data. Finds trends, anomalies, segments, and actionable insights. Ask questions about your data in plain English.
argument-hint: "[path to CSV or paste data]"
allowed-tools: Read, Write, Bash
---

# Metrics Analyzer

Turn raw product data into insights. No dashboards — just clear answers to "what happened, why, and what should we do about it."

## Process

1. **Load the data.** Read the CSV file or parse pasted data. Identify columns, data types, date ranges, and row count.
2. **Understand structure.** Detect date columns, metric columns (numeric), and dimension columns (categorical). Identify the grain (daily, weekly, per-user, per-transaction).
3. **Compute summary statistics.** For each key metric: mean, median, min, max, standard deviation, and recent trend direction.
4. **Detect trends.** Compare recent period vs. prior period. Calculate week-over-week and month-over-month changes. Flag anything moving more than 10% as notable.
5. **Flag anomalies.** Identify data points more than 2 standard deviations from the mean. Check for sudden drops, spikes, or flatlines.
6. **Segment analysis.** If dimension columns exist, break metrics by segment. Find which segments are driving overall changes.
7. **Generate insights.** Synthesize findings into 3 actionable insights ranked by business impact.

## Output Format

## Data Summary
- **Rows:** [N] | **Columns:** [N] | **Date range:** [start] to [end]
- **Grain:** [daily/weekly/per-user/etc.]
- **Key metrics found:** [list]
- **Dimensions found:** [list]

## Key Metrics Overview
| Metric | Current | Prior Period | Change | Trend |
|--------|---------|-------------|--------|-------|
| [metric] | [value] | [value] | [+/-X%] | [up/down/stable] |

## Trends
- **[Metric 1]:** [Direction] [magnitude] over [time period]. [One sentence context.]
- **[Metric 2]:** [Direction] [magnitude] over [time period]. [One sentence context.]

## Anomalies
- **[Date/period]:** [What happened] — [metric] was [value] vs. expected [value]. Possible cause: [hypothesis].

## Segment Breakdown
| Segment | [Metric] | vs. Average | Notable |
|---------|----------|-------------|---------|
| [segment] | [value] | [+/-X%] | [yes/no + why] |

## Top 3 Insights
1. **[Insight title]:** [What the data shows] — [Why it matters] — [Suggested action]
2. **[Insight title]:** [What the data shows] — [Why it matters] — [Suggested action]
3. **[Insight title]:** [What the data shows] — [Why it matters] — [Suggested action]

## Recommended Next Analysis
- [What to dig into next and why]

## Rules

- Always start by showing the data summary so the user can confirm the data loaded correctly.
- Use Bash with Python (pandas) for any computation. Do not eyeball numbers — calculate them.
- Trends must include magnitude ("up 12%"), not just direction ("going up").
- Every anomaly must include a hypothesis for the cause, even if speculative. Label speculative causes clearly.
- Insights must be actionable. "Revenue is up" is an observation. "Revenue is up 15% driven by Segment X — double down on acquisition there" is an insight.
- If the data is messy (missing values, inconsistent formats), clean it and report what you did.
- If the data is too small for meaningful analysis (under 30 data points), say so explicitly.
- Do not generate charts — describe what a chart would show in words. The user can visualize later.
- If the user asks a specific question about the data, answer that question FIRST, then provide the broader analysis.
- Save the analysis to a file in the current working directory as `metrics-analysis-[date].md`.
