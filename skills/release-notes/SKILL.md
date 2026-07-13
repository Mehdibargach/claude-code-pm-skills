---
name: release-notes
description: Turn git commits, tickets, or raw notes into user-facing release notes. Adjustable tone (B2B formal, B2C friendly, internal).
argument-hint: "[paste commits/tickets or path to file]"
allowed-tools: Read, Write, Bash
---

# Release Notes Generator

Transform raw engineering artifacts (git commits, Jira tickets, changelogs, raw notes) into polished, user-facing release notes. Write for users, not engineers.

## Process

1. Read the input — either from a provided file path or from pasted commits/tickets in the argument.
2. If a git repository path is provided, use `git log --oneline` (read-only) to extract recent commits.
3. Group changes into categories: New features, Improvements, Bug fixes.
4. Translate each technical change into user-facing language.
5. Infer the tone from context. If not clear, default to B2B Formal.
6. Write the release notes.
7. Save the output to a file in the current working directory as `release-notes-[version-or-date].md`.

## Output Format

### [Release Title — descriptive, not just a version number]
**Version:** [if applicable]
**Date:** [release date]

---

#### New Features
For each feature:
- **[Feature name]** — What it does and why it matters to the user. Not how it was built.

#### Improvements
For each improvement:
- **[What improved]** — What the user will notice is better. Be specific.

#### Bug Fixes
For each fix:
- **[What was fixed]** — Describe the problem the user experienced, not the technical root cause.

---

#### Internal Notes (optional, only if requested)
- Technical details relevant for support teams, CSMs, or internal stakeholders
- Migration notes, feature flags, rollout percentages
- Known issues that weren't fixed in this release

## Tone Guide

**B2B Formal:**
- Professional, clear, concise
- "We've introduced..." / "This release includes..."
- Suitable for enterprise customers, changelog pages

**B2C Friendly:**
- Warm, conversational, benefit-focused
- "You can now..." / "We fixed a bug that..."
- Suitable for consumer apps, in-app changelogs

**Internal:**
- Direct, technical context included
- Can reference ticket numbers, feature flags, team names
- Suitable for Slack updates, internal wikis

## Rules

- Write for USERS, not engineers. Translate every change into user impact.
- "Fixed null pointer exception in auth service" becomes "Fixed an issue where some users couldn't log in."
- "Refactored payment module" becomes an Improvement only if users notice something — otherwise omit it.
- Internal refactors with zero user impact should be omitted from user-facing notes (move to Internal Notes if needed).
- Group related commits into a single release note item. Five commits about the same feature = one bullet point.
- Never expose internal system names, error codes, or infrastructure details in user-facing sections.
- If the tone is not specified, default to B2B Formal.
- Every item must answer: "Why should the user care?"
