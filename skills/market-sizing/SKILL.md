---
name: market-sizing
description: TAM/SAM/SOM estimation for any product or market. Takes a product/market description and returns structured market sizing with sources, assumptions, and confidence ranges.
argument-hint: "[product or market description]"
allowed-tools: Read, WebFetch, WebSearch, Write
---

# Market Sizing

Produce a rigorous TAM/SAM/SOM estimate that a PM can use in a pitch deck, strategy doc, or investment memo. The goal is defensible numbers with transparent assumptions — not inflated vanity metrics.

## Process

1. **Define the market** — Restate the input as a clear market definition: what product category, who is the buyer, what problem is being solved. Distinguish between the broad market and the specific segment.
2. **Research data points** — Use WebSearch to find industry reports, public filings, analyst estimates, census data, and any credible source. Prioritize recent data (last 2 years). Note every source.
3. **Calculate TAM (Total Addressable Market)** — Use top-down (industry report size) AND bottom-up (number of potential customers x average revenue per customer) if possible. If both methods yield different numbers, show both and explain the gap.
4. **Calculate SAM (Serviceable Addressable Market)** — Apply geographic, segment, and capability filters. Be specific about what's excluded and why.
5. **Calculate SOM (Serviceable Obtainable Market)** — Estimate realistic market capture in the first 1-3 years. Factor in competition, go-to-market approach, and growth benchmarks from comparable companies.
6. **Stress-test assumptions** — Provide a range (conservative / base / optimistic) for at least SOM.

## Output Format

### Market Definition
One paragraph: what market, who buys, what problem, geographic scope.

### TAM (Total Addressable Market)

**Top-down:** $X based on [source]. Calculation: [show the math].
**Bottom-up:** $X based on [number of customers] x [ARPU]. Calculation: [show the math].
**Selected TAM:** $X — [explain which estimate you trust more and why].

### SAM (Serviceable Addressable Market)

**Filters applied:**
- Geographic: [filter]
- Segment: [filter]
- Other: [filter]

**SAM:** $X ([X%] of TAM). Calculation: [show the math].

### SOM (Serviceable Obtainable Market)

| Scenario | SOM | Assumptions |
|----------|-----|-------------|
| Conservative | $X | ... |
| Base | $X | ... |
| Optimistic | $X | ... |

**Methodology:** [explain how you estimated capture rate — comparable company benchmarks, market share logic, etc.]

### Key Assumptions

| # | Assumption | Impact if Wrong | Confidence |
|---|-----------|-----------------|------------|
| 1 | ... | ... | High/Med/Low |
| 2 | ... | ... | High/Med/Low |

### Sources
Numbered list of every source used, with URLs when available.

### Confidence Level
One paragraph: overall confidence in these numbers (High / Medium / Low) and what would increase confidence (e.g., "primary research with 20 target buyers would validate the ARPU assumption").

## Rules

- Always show the math. Every number must trace back to a source or a calculation.
- Never use a single data point without cross-referencing. If only one source exists, flag it as low confidence.
- Bottom-up estimates are generally more trustworthy than top-down for niche markets. Say so when relevant.
- SOM should be grounded in reality: comparable company growth rates, typical market penetration for the GTM model, etc. Do not just pick an arbitrary percentage of SAM.
- Round numbers appropriately. Do not write "$4,237,891" — write "$4.2M". False precision erodes credibility.
- Write in English.
- Keep the entire output under 2 pages. Investors and execs skim — make every line count.
- Be opinionated: if the market is too small to build a venture-scale business, say so. If the sizing depends on a shaky assumption, call it out.
- If you cannot find reliable data for a critical input, flag it and provide a placeholder range rather than guessing.
