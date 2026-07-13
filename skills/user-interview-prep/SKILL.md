---
name: user-interview-prep
description: Generate a complete user research brief with hypotheses, interview guide, and open-ended questions. Takes a research topic or hypothesis and returns a ready-to-use interview kit.
argument-hint: "[research topic or hypothesis]"
allowed-tools: Read, Write
---

# User Interview Prep

Generate a structured research brief and interview guide that a PM can use immediately. The goal is to go into interviews with clear hypotheses, unbiased questions, and a plan to learn — not confirm.

## Process

1. **Clarify the research goal** — Restate the input as a single, testable research question. If the input is vague, sharpen it. A good research goal starts with "Understand..." or "Discover..." — never "Validate..." or "Confirm...".
2. **Surface assumptions** — List 3-5 hypotheses the PM is likely carrying into this research. These are the things that need to be tested, not confirmed.
3. **Design the interview flow** — Structure a 30-minute interview with warm-up, core exploration, and wrap-up sections. Each section has a purpose and time allocation.
4. **Write the questions** — Generate open-ended, non-leading questions. Follow the "Mom Test" principles: ask about their life, not your idea. Ask about the past, not hypothetical futures.
5. **Add observation notes** — Flag what to watch for beyond words: body language, hesitation, workarounds they mention, emotional signals.

## Output Format

### Research Goal
One sentence. Clear, specific, learnable.

### Hypotheses to Test

| # | Hypothesis | How We'll Know If It's True | How We'll Know If It's False |
|---|-----------|---------------------------|-------------------------------|
| 1 | ... | ... | ... |
| 2 | ... | ... | ... |
| 3 | ... | ... | ... |

### Interview Guide

**Warm-up (5 min)** — Build rapport, understand context.
- Question 1
- Question 2

**Core Exploration (20 min)** — Dig into the problem space.
- Question 3
- Question 4
- ...

**Wrap-up (5 min)** — Capture anything missed, get referrals.
- Question N
- "Is there anything I should have asked but didn't?"

### Things to Watch For
Bullet list of behavioral signals, hesitations, or workarounds to note during the interview.

### Anti-Patterns to Avoid
Bullet list of common interviewer mistakes specific to this topic (leading questions, pitching solutions, etc.).

## Rules

- Never write a question that starts with "Would you..." or "Do you think...". These invite hypothetical answers. Ask about past behavior instead.
- Every question must pass the Mom Test: would you get honest, useful data even if you asked your mom?
- No more than 12 questions total. Quality over quantity — each question should earn its place.
- Include at least 2 follow-up prompts per core question (e.g., "Tell me more about that", "What happened next?").
- Write in English.
- Keep the entire output under 2 pages. A PM should be able to print this and bring it to the interview.
- Be opinionated: if a hypothesis seems weak or untestable, call it out and suggest a better one.
- Do not include questions about the PM's product or solution. This is about understanding the problem.
