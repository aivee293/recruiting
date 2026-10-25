---
name: market-research
description: "Research labor-market data for a role and location: salary and total-comp benchmarks, talent supply and demand, hiring difficulty, and competing employers. Use when the user asks what a role pays or how hard it will be to hire. Not for packaging a specific candidate's offer (use offer-negotiation) or mapping individual target companies (use talent-mapping)."
---

# Market Research for Recruiting Sourcing

## Purpose

Analyze labor market dynamics to inform sourcing strategy and stakeholder conversations. Provide data-driven insights on compensation ranges, talent supply/demand, hiring difficulty, and market trends. Market research transforms sourcing from guesswork into strategic, evidence-based talent acquisition.

## Research Dimensions

### Compensation Analysis

Build compensation intelligence by triangulating multiple sources:

**Data Sources (by reliability):**
1. **Internal data** - Current employee comp, recent offers (most relevant)
2. **Offer data** - Rejected/accepted offers with candidate feedback
3. **Survey data** - Radford, Mercer, Culpepper, Carta (structured, lagging)
4. **Crowdsourced** - Levels.fyi, Glassdoor, Blind, Payscale (directional, noisy)
5. **Job postings** - Published salary ranges where legally required (Colorado, NYC, CA, EU)
6. **Recruiter intelligence** - Competitive offers seen in market (anecdotal, current)

**Compensation Structure:**
- **Base salary** - Fixed annual pay by level/location
- **Variable/bonus** - Target bonus percentage, attainment rates
- **Equity** - RSU/option grants, vesting schedules, refresh grants
- **Total compensation** - All-in annual value including benefits
- **Sign-on** - One-time payments to offset candidate costs

**Segmentation:**
- By geography (city/region, with cost-of-living adjustments)
- By company stage (startup, growth, enterprise, FAANG)
- By seniority level (junior through executive)
- By specialization (premium for niche skills)

### Talent Supply & Demand

**Supply indicators:**
- LinkedIn talent pool sizes for given search criteria
- Number of "open to work" candidates in the segment
- Active applicant volume on job boards
- Candidate response rates to outreach
- Average time candidates spend on market

**Demand indicators:**
- Number of open roles for the profile (LinkedIn, Indeed, Glassdoor)
- Job posting growth rate over past 6-12 months
- Average time-to-fill for similar roles (industry benchmarks)
- Number of companies actively hiring for the role
- Recruiter activity in the space (InMail volume, outreach frequency)

**Supply/Demand Ratio:**
- **Candidate-driven market** (supply > demand): More candidates than roles; lower urgency, more selectivity
- **Employer-driven market** (demand > supply): More roles than candidates; higher urgency, competitive offers needed
- **Balanced market**: Supply roughly matches demand; standard processes work

### Hiring Difficulty Assessment

Rate hiring difficulty on a scale with these factors:

| Factor | Low Difficulty | High Difficulty |
|--------|---------------|-----------------|
| Pool size | Large (1000+) | Small (<100) |
| Demand | Few competitors hiring | Many competitors hiring |
| Comp expectations | Aligned with budget | Above budget range |
| Location requirements | Remote/flexible | Specific city, in-office |
| Skill rarity | Common skill set | Niche/emerging skills |
| Brand strength | Strong employer brand | Unknown/weak brand |
| Time pressure | Flexible timeline | Urgent fill needed |

### Market Trends

Track and report on:

- **Emerging skills** - New technologies/frameworks gaining adoption
- **Declining skills** - Technologies being deprecated or replaced
- **Workforce shifts** - Remote work trends, gig economy, contractor preferences
- **Regulatory changes** - Pay transparency laws, immigration policy, labor regulations
- **Economic factors** - Layoff trends, funding cycles, hiring freezes/surges
- **Industry movements** - Consolidation, new entrants, pivots

## Research Process

### Step 1: Define Research Scope

Clearly specify:
- Role/function being researched
- Geographic markets of interest
- Seniority range
- Key comparison companies or segments
- Specific questions to answer

### Step 2: Gather Data

Collect data from available sources:
- Web search for recent salary surveys and reports
- LinkedIn for pool sizing and demand signals
- Job boards for posted salary ranges and posting volume
- Industry reports for trends and benchmarks
- Community discussions for qualitative signals

### Step 3: Analyze & Synthesize

- Cross-reference multiple sources to establish ranges
- Identify outliers and understand why they exist
- Note data recency and reliability
- Segment by relevant dimensions (geography, seniority, company type)

### Step 4: Frame Recommendations

- Position findings relative to the hiring company's context
- Highlight trade-offs (e.g., "increasing budget by 15% expands pool 3x")
- Provide actionable recommendations for sourcing strategy
- Flag risks and market challenges

## Output Format

### Market Research Report Structure

**1. Executive Summary**
- Key findings in 3-5 bullet points
- Overall hiring difficulty rating
- Top recommendation

**2. Compensation Landscape**
- Salary ranges by level (P25, P50, P75, P90)
- Total compensation breakdown
- Geographic variations
- Comparison to hiring company's range

**3. Supply & Demand Analysis**
- Estimated talent pool size
- Active demand (competing open roles)
- Supply/demand characterization
- Trend direction (improving or worsening)

**4. Competitive Landscape**
- Top companies hiring for similar roles
- Employer brand comparison
- Compensation positioning
- Unique selling points vs. competitors

**5. Recommendations**
- Sourcing strategy implications
- Compensation positioning advice
- Timeline expectations
- Risk mitigations

## Data Presentation

When presenting compensation data, use clear ranges:

```
Senior Data Engineer - San Francisco Bay Area
┌─────────────────────────────────────────────┐
│ Base Salary                                 │
│ P25: €165,000  P50: €185,000  P75: €210,000│
│                                             │
│ Total Compensation (incl. equity + bonus)   │
│ P25: €220,000  P50: €280,000  P75: €350,000│
└─────────────────────────────────────────────┘
Sources: Levels.fyi, Glassdoor, etc. posted ranges (2026)
```

Always note:
- Data sources and recency
- Sample size where available
- Geographic basis
- Whether ranges are base or total comp

## Additional Resources

### Reference Files

You are **strongly encouraged** to read the reference files

For detailed methodology:
- **`references/data-sources-guide.md`** - Complete guide to compensation and market data sources with access methods
- **`references/report-templates.md`** - Markdown and HTML templates for market research reports
