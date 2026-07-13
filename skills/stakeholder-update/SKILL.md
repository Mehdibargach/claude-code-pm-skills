---
name: stakeholder-update
description: Turn raw notes into a polished stakeholder update. Supports email, Slack message, or deck bullet points. Takes messy notes and outputs a clear, structured update with TL;DR, progress, blockers, and asks.
argument-hint: "[paste raw notes or context]"
allowed-tools: Read, Write
---

# Stakeholder Update

Transform scattered notes into a crisp stakeholder update. Executives skim — make every sentence earn its place.

## Process

1. **Ingest raw notes.** Read the input — meeting notes, bullet points, pasted Slack threads, status updates, whatever the user provides.
2. **Identify the format.** Default is email. User can request: email, Slack message, or deck bullets. Adjust tone and structure accordingly.
3. **Extract key information.** Categorize everything into: progress (shipped/moved), blockers (stuck/needs help), decisions needed (specific asks), and upcoming priorities.
4. **Write the TL;DR.** Two sentences max. The most important thing and the one thing you need from the reader.
5. **Structure the update.** Follow the output format for the chosen medium.
6. **Quantify.** Replace vague statements with specifics. "Good progress" becomes "shipped 3 of 5 planned features."

## Output Format

### Email Format (default)
```
Subject: [Project/Team] Update — [Date or Sprint]

**TL;DR:** [Two sentences. What happened + what you need.]

**Progress**
- [What shipped or moved forward — be specific]
- [What shipped or moved forward]
- [What shipped or moved forward]

**Blockers**
- [What is stuck] — Need [specific help] from [specific person/team]
- [What is stuck] — Need [specific help]

**Decisions Needed**
- [Specific question requiring a yes/no or choice] — Deadline: [date]
- [Specific question] — Deadline: [date]

**Next Week**
- [Priority 1]
- [Priority 2]
- [Priority 3]
```

### Slack Format
```
*[Project] Update — [Date]*

*TL;DR:* [Two sentences]

*Shipped:* [bullet list]
*Blocked:* [bullet list with specific asks]
*Need from you:* [decisions or actions with deadlines]
```

### Deck Bullets Format
```
[Title slide content]
- Key metric: [number]
- Shipped: [list]
- On track / At risk / Blocked: [status]
- Decision needed: [one line]
```

## Rules

- The TL;DR is the most important part. Many readers will stop there. Make it count.
- No jargon. If a technical term is necessary, add a parenthetical explanation.
- Be specific. "Making progress on the API" is useless. "API endpoints 4/6 complete, remaining 2 blocked on auth service migration" is useful.
- Quantify everything possible. Numbers, percentages, dates, counts.
- Blockers must include what you need and from whom. A blocker without an ask is just a complaint.
- Decisions needed must be framed as specific questions with options if possible, not open-ended problems.
- Keep it short. Email: under 200 words. Slack: under 100 words. Deck: under 50 words.
- Do not editorialize or add opinions not present in the raw notes. Synthesize, do not embellish.
- If the raw notes are too thin to write a meaningful update, say so and ask for more context rather than padding.
