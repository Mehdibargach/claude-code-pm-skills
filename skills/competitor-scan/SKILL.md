---
name: competitor-scan
description: Quick competitive landscape scan for any product or market. Takes a product/market description and returns a competitive map with positioning, gaps, and opportunities.
argument-hint: "[market or product description]"
allowed-tools: Read, WebFetch, WebSearch, Write
---

# Competitor Scan

Perform a rapid competitive landscape analysis. The goal is to give a PM a clear picture of who's playing in a space, how they're positioned, and where the openings are.

## Process

1. **Parse the input** — Extract the core market/product being analyzed. Identify the category, target customer, and key value proposition.
2. **Research competitors** — Use WebSearch to find direct competitors (same category, same customer) and indirect competitors (different approach, same job-to-be-done). Aim for 5-8 competitors. Check product pages, pricing pages, and recent coverage via WebFetch when needed.
3. **Analyze positioning** — For each competitor, determine: who they target, what they lead with, how they price, and what users complain about.
4. **Map the landscape** — Identify the two most differentiating axes in this market (e.g., self-serve vs. enterprise, horizontal vs. vertical). Describe where each player sits.
5. **Find gaps** — Look for underserved segments, missing features that keep coming up in reviews, or pricing tiers nobody covers.
6. **Synthesize** — Write a tight competitive brief.

## Output Format

### Market Overview
One paragraph: what this market is, estimated maturity (emerging / growing / mature / declining), and the dominant business model.

### Competitor Table

| Competitor | Positioning | Target Customer | Strengths | Weaknesses | Pricing Model |
|-----------|-------------|-----------------|-----------|------------|---------------|
| ... | ... | ... | ... | ... | ... |

### Positioning Map
Describe the two axes chosen and where each competitor falls. Use a text-based 2x2 if it helps clarity.

### White Space Opportunities
Bullet list of 3-5 gaps or underserved areas with a one-line explanation each.

### Key Takeaway
One paragraph: the single most important insight a PM should walk away with.

## Rules

- Prioritize direct competitors over tangential ones. If in doubt, include them but flag as indirect.
- Always check pricing pages — "Contact us" is valid data, note it as enterprise/opaque pricing.
- Do not invent data. If you cannot find reliable info on a competitor, say so explicitly.
- Keep the entire output under 2 pages. Density over length.
- Write in English.
- Be opinionated: rank competitors by threat level, call out who is winning and why.
- If the market has fewer than 3 competitors, flag it as a blue ocean and shift focus to adjacent markets and substitutes.
