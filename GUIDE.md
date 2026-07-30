# The PM Skills Guide

Everything you need to go from zero to running your first skill in under 5 minutes.

---

## What is a Claude Code Skill?

A skill is a reusable command you can trigger inside Claude Code by typing `/skill-name`.

Think of it like this:
- Without a skill: you type a long prompt, explain the format you want, specify the structure, hope Claude gets it right
- With a skill: you type `/prd My product idea` and get a structured, opinionated PRD every single time

Each skill is a small file (`SKILL.md`) that tells Claude exactly how to think, what process to follow, and what format to output. You don't need to write prompts. You just provide the subject.

**That's it.** No API keys. No dependencies. No setup beyond copying a folder.

---

## Installation

### Step 1: Open your terminal

You need a terminal app. On Mac, open **Terminal** (search for it in Spotlight). On Windows, use **PowerShell** or **Git Bash**.

### Step 2: Clone the repo

```bash
git clone https://github.com/Mehdibargach/claude-code-pm-skills.git
```

This downloads all 20 skills to your computer.

### Step 3: Copy the skills to Claude Code

```bash
mkdir -p ~/.claude/skills
cp -r claude-code-pm-skills/skills/* ~/.claude/skills/
```

This copies every skill into the folder where Claude Code looks for them.

> **Only want a few skills?** Copy them individually:
> ```bash
> cp -r claude-code-pm-skills/skills/prd ~/.claude/skills/
> cp -r claude-code-pm-skills/skills/decision-doc ~/.claude/skills/
> ```

### Step 4: Restart Claude Code

Quit Claude Code completely and reopen it. The skills load on startup.

### Step 5: Verify

Type `/` in Claude Code. You should see your new skills in the autocomplete list alongside any skills you already had.

**If you don't see them**, check:
- The folder `~/.claude/skills/` exists and contains subfolders (one per skill)
- Each subfolder contains a `SKILL.md` file
- You restarted Claude Code after copying

---

## How to use a skill

Every skill follows the same pattern:

```
/skill-name [your input]
```

That's it. Type the slash command, add your context, hit enter. Claude does the rest.

### Your first skill — try this now

Copy and paste this into Claude Code:

```
/decision-doc Should we build our own auth system or use Auth0?
```

You'll get a structured decision document with options, trade-offs, a recommendation, and a reversibility assessment — in about 30 seconds.

### Tips for better results

1. **Be specific.** `/prd A tool for PMs` will give you a generic PRD. `/prd A Slack bot that summarizes unread channels every morning and highlights action items` will give you something you can actually use.

2. **Add context.** Most skills get better when you provide constraints. `/ab-test-design Moving the CTA above the fold. Current conversion is 3.2%, 800 daily visitors` gives Claude the numbers it needs to calculate sample sizes.

3. **Paste raw data.** Several skills accept messy input and structure it for you. `/stakeholder-update` works best when you paste your actual messy notes. `/feedback-analyzer` can take pasted customer quotes or a CSV file path.

4. **Chain skills together.** Use `/persona` first, then feed the output into `/prd`, then into `/user-stories`. The skills are designed to work together.

---

## All 20 Skills — Cheat Sheet

### Discovery & Strategy

| Command | What to type | What you get |
|---------|-------------|--------------|
| `/product-teardown` | A product name | Business model, UX decisions, growth loops, moat, weaknesses |
| `/competitor-scan` | A market or product category | Competitor table, positioning map, white space opportunities |
| `/user-interview-prep` | A research question | Hypotheses, 30-min interview guide, Mom Test questions |
| `/feedback-analyzer` | Pasted feedback or path to CSV | Themes, sentiment, urgency, patterns, recommendations |
| `/market-sizing` | A product or market description | TAM/SAM/SOM with top-down + bottom-up math and sources |
| `/persona` | A product description | 2-4 behavioral personas with goals, pain points, anti-persona |

### Build & Ship

| Command | What to type | What you get |
|---------|-------------|--------------|
| `/prd` | A product idea or feature | 1-2 page PRD: problem, users, scope, metrics, risks |
| `/user-stories` | A feature description | User stories with acceptance criteria, edge cases, dependencies |
| `/technical-translator` | An engineering doc or API spec | PM-friendly explanation of what it means for product and users |
| `/release-notes` | Git commits, tickets, or raw notes | User-facing release notes in B2B, B2C, or internal tone |
| `/launch-checklist` | A product or feature description | Pre-launch, launch day, post-launch checklist with owners and timing |
| `/roadmap` | A list of features or priorities | Now/Next/Later roadmap with themes, dependencies, trade-offs |

### Measure & Decide

| Command | What to type | What you get |
|---------|-------------|--------------|
| `/ab-test-design` | What you want to test | Full experiment: hypothesis, metrics, sample size, success criteria |
| `/metrics-analyzer` | CSV data or pasted numbers | Trends, anomalies, segments, top 3 actionable insights |
| `/prioritize` | A list of features | RICE-scored ranked table with cut line and rationale |
| `/decision-doc` | A decision to make | Options, trade-offs, recommendation, reversibility assessment |
| `/okr-writer` | A business goal | OKRs with measurable Key Results and anti-goals |

### Communicate

| Command | What to type | What you get |
|---------|-------------|--------------|
| `/stakeholder-update` | Raw notes, bullet points, anything messy | Polished update (email, Slack, or deck bullets) with TL;DR |
| `/meeting-prep` | A meeting topic or agenda | 1-page brief: context, objectives, key questions, decisions needed |
| `/retro-facilitator` | Retro notes or a format request | Grouped themes, prioritized action items, or a blank retro board |

---

## Examples

### Example 1: From idea to PRD in 30 seconds

**You type:**
```
/prd A browser extension that highlights AI-generated content on any webpage
and shows a confidence score
```

**You get:** A structured PRD with the problem statement ("users can't distinguish AI-generated from human-written content"), target users (journalists, researchers, content reviewers), MVP scope, success metrics with targets, explicit exclusions, and open risks.

---

### Example 2: Messy notes to stakeholder update

**You type:**
```
/stakeholder-update Search v2 shipped Monday. 3 of 5 endpoints live.
p95 latency at 340ms, target was 300ms. Blocked on infra team for Redis
upgrade. Need VP Eng decision on whether to delay remaining endpoints
or ship with higher latency. Mobile team starts integration next week.
2 bugs found in prod, both P2, being fixed.
```

**You get:** A clean email with subject line, TL;DR ("Search v2 is live with 3/5 endpoints. Need a decision on latency trade-off by Friday."), progress bullets with specifics, blockers with named asks, and next week priorities.

---

### Example 3: Prioritize a backlog

**You type:**
```
/prioritize SSO for enterprise, mobile app v1, Slack integration,
onboarding wizard, API rate limiting, dark mode, bulk CSV import,
in-app analytics dashboard
```

**You get:** A RICE-scored table ranking all 8 features, a cut line showing what to do now vs. next vs. later, rationale for the top 3 and bottom 3, and caveats about what the framework doesn't capture (strategic bets, dependencies).

---

### Example 4: Design an A/B test

**You type:**
```
/ab-test-design Moving the pricing page CTA from below the feature
comparison table to a sticky header. Current conversion rate is 3.2%,
page gets 800 daily visitors.
```

**You get:** A structured hypothesis ("If we move the CTA to a sticky header, conversion will increase by 15-20% because..."), primary and guardrail metrics, sample size calculation, estimated duration, success criteria, and a pre-launch QA checklist.

---

## Troubleshooting

### "I type /skill-name and nothing happens"

- Make sure you restarted Claude Code after copying the skills
- Check that `~/.claude/skills/[skill-name]/SKILL.md` exists
- The skill name must match the folder name exactly

### "The output is too generic"

Your input is probably too vague. Compare:
- Bad: `/prd A productivity tool`
- Good: `/prd A Slack bot that sends a daily digest of unread channels to each user, highlighting messages where they were mentioned or assigned an action item`

More context = better output. Add constraints, numbers, audience, and goals.

### "The skill asks me a question instead of giving me output"

Some skills push back when the input is too thin to produce useful output. This is by design — a vague PRD is worse than no PRD. Answer the question and the skill will proceed.

### "I only want some skills, not all 20"

Copy only the folders you want:
```bash
cp -r claude-code-pm-skills/skills/prd ~/.claude/skills/
cp -r claude-code-pm-skills/skills/prioritize ~/.claude/skills/
```

Each skill is independent. No skill depends on another.

### "I want to customize a skill"

Edit the `SKILL.md` file directly. It's just a markdown file with instructions. Change the process, the output format, the rules — whatever you need. Your changes persist across sessions.

---

## FAQ

**Do I need an API key?**
No. Skills run inside Claude Code using your existing Claude subscription.

**Do skills work offline?**
Most skills work offline. Two exceptions: `/product-teardown`, `/competitor-scan`, and `/market-sizing` use web search to gather data, so they need an internet connection.

**Can I share a customized skill with my team?**
Yes. A skill is just a folder with a SKILL.md file inside. Share the folder, have your teammates drop it into their `~/.claude/skills/` directory.

**Do skills send my data anywhere?**
No. Skills are local instructions. Your data stays in your Claude Code session — nothing is sent to external services beyond what Claude Code already does.

**Can I use skills with Claude on the web (claude.ai)?**
No. Skills are a Claude Code feature (the CLI tool). They don't work on claude.ai.

**How do I update skills when new versions come out?**
Pull the latest changes from the repo and copy again:
```bash
cd claude-code-pm-skills
git pull
cp -r skills/* ~/.claude/skills/
```

**Can I create my own skills?**
Absolutely. Create a folder in `~/.claude/skills/`, add a `SKILL.md` file following the same format as any existing skill, and restart Claude Code. Check any skill in this repo for the template.
