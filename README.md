# Claude Code PM Skills

20 production-ready skills for Product Managers using Claude Code.

No fluff. No generic prompts. Real PM workflows you can run with a `/command`.

## What's inside

### Discovery & Strategy
| Skill | What it does |
|-------|-------------|
| `/product-teardown` | Analyze any product: business model, UX decisions, growth loops, moat |
| `/competitor-scan` | Competitive landscape scan with positioning map and white space analysis |
| `/user-interview-prep` | Research brief with hypotheses, interview guide, and Mom Test-compliant questions |
| `/feedback-analyzer` | Classify raw feedback (CSV or text) by theme, sentiment, urgency + patterns |
| `/market-sizing` | TAM/SAM/SOM estimation with top-down + bottom-up methodology |
| `/persona` | Behavioral user personas that drive product decisions — not marketing fluff |

### Build & Ship
| Skill | What it does |
|-------|-------------|
| `/prd` | Concise PRD (1-2 pages max) that forces clarity on problem, users, scope, metrics |
| `/user-stories` | Feature → user stories with acceptance criteria, edge cases, dependencies |
| `/technical-translator` | Translate eng docs (API specs, RFCs) into PM-actionable language |
| `/release-notes` | Git commits or tickets → user-facing release notes. B2B, B2C, or internal tone |
| `/launch-checklist` | Product-specific go-to-market checklist with timing and owners |
| `/roadmap` | Priorities → structured Now/Next/Later roadmap with themes, dependencies, trade-offs |

### Measure & Decide
| Skill | What it does |
|-------|-------------|
| `/ab-test-design` | Full experiment design: hypothesis, metrics, sample size, guardrails, success criteria |
| `/metrics-analyzer` | Analyze CSV data — trends, anomalies, segments, insights in plain English |
| `/prioritize` | Score features with RICE, ICE, or custom framework. Ranked table + rationale |
| `/decision-doc` | Structured decision: options, trade-offs, recommendation, reversibility |
| `/okr-writer` | Business goals → OKRs with measurable Key Results and anti-goals |

### Communicate
| Skill | What it does |
|-------|-------------|
| `/stakeholder-update` | Raw notes → polished update (email, Slack, or deck bullets) |
| `/meeting-prep` | 1-page brief: context, objectives, key questions, decisions expected |
| `/retro-facilitator` | Run or synthesize a retro (4Ls, Start/Stop/Continue, Sailboat) |

## Install

### Option 1: Copy individual skills

```bash
# Clone the repo
git clone https://github.com/Mehdibargach/claude-code-pm-skills.git

# Create the Claude Code skills directory if needed
mkdir -p ~/.claude/skills

# Copy the skills you want to your Claude Code skills directory
cp -r claude-code-pm-skills/skills/prd ~/.claude/skills/
cp -r claude-code-pm-skills/skills/decision-doc ~/.claude/skills/
# ... etc
```

### Option 2: Copy all skills

```bash
git clone https://github.com/Mehdibargach/claude-code-pm-skills.git
mkdir -p ~/.claude/skills
cp -r claude-code-pm-skills/skills/* ~/.claude/skills/
```

### Option 3: Plugin install (coming soon)

```bash
/plugin marketplace add Mehdibargach/claude-code-pm-skills
/plugin install claude-code-pm-skills
```

After installing, restart Claude Code. Type `/` to see your new skills.

## Usage

Each skill is triggered with a `/command`:

```
/prd A tool that helps PMs prioritize features using AI-assisted scoring

/product-teardown Notion

/ab-test-design Moving the CTA button above the fold on the pricing page

/feedback-analyzer /path/to/customer-feedback.csv

/decision-doc Should we build our own auth system or use Auth0?
```

Skills auto-detect context. If you paste a CSV and ask Claude to analyze feedback, it may trigger `/feedback-analyzer` automatically.

## Design principles

- **Opinionated, not generic.** Each skill pushes back on vague inputs and forces specificity.
- **1-2 pages max.** Density over length. No 20-page PRDs.
- **PM workflows, not prompts.** These are multi-step processes with structured outputs — not one-shot prompts you could type yourself.
- **Plug and play.** No dependencies. No API keys. Copy the folder, use the skill.

## Contributing

Found a bug? Want to improve a skill? PRs welcome.

Want to add a new skill? Follow the format in any existing `SKILL.md` and submit a PR.

## Author

**Mehdi Bargach** — Builder PM | AI Products | Ex-Disney, Ex-TF1+

- [LinkedIn](https://linkedin.com/in/mehdibargach)

## License

MIT — use it, fork it, share it.
