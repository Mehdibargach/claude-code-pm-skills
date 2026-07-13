---
name: prioritize
description: Score and prioritize a list of features or initiatives using RICE, ICE, or custom frameworks. Takes a feature list and outputs a ranked table with rationale and a recommended cut line.
argument-hint: "[list of features or path to file]"
allowed-tools: Read, Write
---

# Prioritize

Turn a messy backlog into a ranked, defensible priority list. No gut feelings — structured scoring with explicit trade-offs.

## Process

1. **Collect the feature list.** Parse input — either inline list or file. Extract feature names and any context provided.
2. **Select framework.** Default is RICE (Reach, Impact, Confidence, Effort). Alternatives: ICE (Impact, Confidence, Ease) or custom. Ask only if unclear.
3. **Score each feature.** Apply the framework criteria consistently:
   - **Reach:** How many users/accounts will this affect per quarter? (number)
   - **Impact:** How much will this move the target metric per user? (3=massive, 2=high, 1=medium, 0.5=low, 0.25=minimal)
   - **Confidence:** How sure are we about reach and impact estimates? (100%=high, 80%=medium, 50%=low)
   - **Effort:** How many person-months to build? (number)
   - **RICE Score:** (Reach x Impact x Confidence) / Effort
4. **Rank by score.** Sort descending.
5. **Draw the cut line.** Based on available capacity, suggest what to do now, next, and later (or never).
6. **Write rationale.** Explain the top 3 and bottom 3 rankings.

## Output Format

```
## Prioritization: [Context]
**Framework:** [RICE/ICE/Custom]
**Capacity assumption:** [X person-months this quarter, if known]

### Ranked Features
| Rank | Feature | Reach | Impact | Confidence | Effort | Score |
|------|---------|-------|--------|------------|--------|-------|
| 1 | [name] | [N] | [0.25-3] | [50-100%] | [N] | [score] |
| 2 | [name] | [N] | [0.25-3] | [50-100%] | [N] | [score] |
| ... | ... | ... | ... | ... | ... | ... |

### Cut Line
- **Do Now (this quarter):** [Features 1-N]
- **Do Next (next quarter):** [Features N-M]
- **Do Later / Deprioritize:** [Features M+]

### Top 3 Rationale
1. **[Feature]:** Ranks #1 because [specific reason — which factor drives it].
2. **[Feature]:** Ranks #2 because [specific reason].
3. **[Feature]:** Ranks #3 because [specific reason].

### Bottom 3 Rationale
- **[Feature]:** Ranks low because [specific reason — is it low reach? high effort? low confidence?].
- **[Feature]:** [reason]
- **[Feature]:** [reason]

### Caveats
- [What this prioritization does NOT account for — strategic bets, dependencies, political factors, etc.]
- [Any features where confidence is so low the score is unreliable]
```

## Rules

- Every score must be justified, not arbitrary. If you do not have enough context to score, assign Confidence = 50% and flag it.
- Effort estimates must be in the same unit for all features. Default to person-months if not specified.
- Do not inflate scores to make everything look high-priority. The whole point is to create separation.
- If two features have similar scores (within 10%), call it out — the ranking between them is noise, not signal.
- Always include caveats. Frameworks are models, not reality. Name what the model misses.
- If the input list has fewer than 3 items, suggest the user just make a decision — frameworks add overhead on small lists.
- If a feature is clearly a dependency for others, flag it regardless of its individual score.
- Push back on vague features. "Improve onboarding" is not scoreable. "Add a progress bar to the 5-step signup flow" is.
