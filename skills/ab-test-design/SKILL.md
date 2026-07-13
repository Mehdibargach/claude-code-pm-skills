---
name: ab-test-design
description: Design a complete A/B test or experiment from a hypothesis. Takes what you want to test and outputs a full experiment design with hypothesis, metrics, sample size, duration, and success criteria.
argument-hint: "[what you want to test]"
allowed-tools: Read, Write, Bash
---

# A/B Test Design

Design a rigorous, actionable experiment plan from a test idea. No hand-waving — every section must be specific enough for an engineer to implement and an analyst to evaluate.

## Process

1. **Clarify the test idea.** Parse the input to identify: the change being tested, the user segment affected, and the business context.
2. **Formulate the hypothesis.** Use the structured format: If we [change], then [metric] will [direction] by [amount] because [reason].
3. **Define metrics.** Pick ONE primary metric (the decision metric), 2-3 secondary metrics (supporting evidence), and 2-3 guardrail metrics (what must not degrade).
4. **Design variants.** Describe Control (current state) and Treatment(s) with enough detail to build.
5. **Estimate sample size.** Based on baseline conversion rate, minimum detectable effect (MDE), statistical significance (95%), and power (80%).
6. **Estimate duration.** Based on sample size and daily traffic. Flag if duration exceeds 4 weeks (test validity risk).
7. **Define success criteria.** How will you call the test — statistical significance threshold, practical significance threshold, and how to handle mixed results.
8. **Identify risks.** What could invalidate the test or cause harm.

## Output Format

## Experiment: [Name]

### Hypothesis
If we [specific change], then [primary metric] will [increase/decrease] by [X%]
because [causal reasoning based on user behavior].

### Metrics
| Type | Metric | Baseline | Target |
|------|--------|----------|--------|
| Primary | [metric] | [current value] | [target value] |
| Secondary | [metric] | [current value] | — |
| Secondary | [metric] | [current value] | — |
| Guardrail | [metric] | [current value] | Must not drop below [threshold] |
| Guardrail | [metric] | [current value] | Must not drop below [threshold] |

### Variants
- **Control:** [Exact current experience]
- **Treatment:** [Exact change — specific enough to build]

### Sample Size & Duration
- MDE: [X%]
- Baseline rate: [X%]
- Required sample per variant: [N]
- Estimated duration: [X days/weeks] at [Y daily visitors]
- Traffic allocation: [50/50 or other split + rationale]

### Success Criteria
- Call winner if: [primary metric] reaches p < 0.05 AND practical lift >= [X%]
- Call inconclusive if: [conditions]
- Stop early if: [guardrail metric] degrades by more than [X%]

### Risks & Mitigations
- [Risk 1]: [Mitigation]
- [Risk 2]: [Mitigation]

### Pre-Launch Checklist
- [ ] QA both variants on all platforms
- [ ] Tracking events firing correctly
- [ ] Randomization unit confirmed (user/session/device)
- [ ] Exclusion criteria defined (internal users, bots)

## Rules

- The hypothesis MUST include a predicted magnitude. "Will improve" is not a hypothesis — "will increase by 5-10%" is.
- One primary metric only. If you cannot pick one, the test is not ready.
- Guardrail metrics are mandatory. Every test can break something.
- If the estimated duration exceeds 4 weeks, flag it and suggest ways to reduce (narrower audience, larger MDE, higher traffic page).
- Always specify the randomization unit (user-level, not session-level, in most cases).
- Use Bash with Python to calculate sample size when baseline rate and MDE are known.
- If the input is vague, ask clarifying questions before designing. Do not guess.
- Be opinionated about what makes a good test. Push back on tests that are too small to detect, too broad to learn from, or testing something that should just be shipped.
