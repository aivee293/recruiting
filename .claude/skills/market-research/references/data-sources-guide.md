# Compensation & Market Data Sources Guide

## Tier 0: Internal Verified Data

## Tier 1: Structured Survey Data

### Radford (Aon)

- **Coverage:** Tech industry, global
- **Data:** Base, bonus, equity by level and function
- **Access:** Paid subscription, requires participation
- **Reliability:** High (verified employer data)
- **Lag:** 6-12 months

### Mercer

- **Coverage:** Multi-industry, global
- **Data:** Total compensation, benefits, job architecture
- **Access:** Paid, participation-based
- **Reliability:** High
- **Lag:** 6-12 months

### Culpepper

- **Coverage:** Tech and life sciences
- **Data:** Salary, equity, bonus practices
- **Access:** Paid
- **Reliability:** High
- **Lag:** 6-12 months

### Carta Total Comp

- **Coverage:** VC-backed startups
- **Data:** Equity grants, valuations, salary
- **Access:** Free/paid tiers
- **Reliability:** High for startup equity data
- **Lag:** 3-6 months

## Tier 2: Crowdsourced Data

### Levels.fyi

- **Coverage:** Tech companies, engineering focus
- **Data:** Total compensation with breakdown, by company and level
- **Access:** Free
- **Reliability:** Medium-High (self-reported, but verified by community)
- **Lag:** Near real-time
- **Best for:** Big Tech and established companies

### Glassdoor

- **Coverage:** Broad, multi-industry
- **Data:** Salary ranges, reviews, interview data
- **Access:** Free (with account)
- **Reliability:** Medium (self-reported, variable quality)
- **Lag:** Variable
- **Best for:** Directional ranges, company comparison

### Blind (Teamblind)

- **Coverage:** Tech, verified employees
- **Data:** Compensation discussions, offer comparisons
- **Access:** Free (requires work email verification)
- **Reliability:** Medium (anecdotal but from verified employees)
- **Lag:** Real-time
- **Best for:** Current offer data, negotiation intel

### Payscale

- **Coverage:** Broad, multi-industry
- **Data:** Salary ranges by role, location, experience
- **Access:** Free basic, paid detailed
- **Reliability:** Medium
- **Best for:** Quick directional ranges

## Tier 3: Job Posting Data

### Pay Transparency Laws (Primary Source)

Locations requiring salary ranges in job postings:

- **Colorado** (since 2021)
- **New York City** (since 2022)
- **California** (since 2023)
- **Washington State** (since 2023)
- **EU Pay Transparency Directive** (implementation by 2026)

### Scraping Job Boards

- Search for target role on Indeed, LinkedIn, Glassdoor
- Filter to locations with pay transparency
- Collect posted ranges
- Note: Ranges are often broad, use P25-P75 as realistic band

### How to Use Job Posting Data

1. Collect 15-20 postings with salary ranges
2. Remove outliers (top and bottom 10%)
3. Calculate P25, P50, P75 from remaining
4. Note: Posted ranges typically span 20-30% from min to max
5. Midpoint of posted range ≈ target salary

## Tier 4: Qualitative / Anecdotal

### Recruiter Intelligence

- Talk to recruiters in the space
- Attend recruiting community events
- Join sourcing Slack/Discord communities
- Track offer acceptance/rejection patterns

### Candidate Feedback

- Record expectations shared during screens
- Track counter-offer amounts
- Note competitive offers candidates share
- Build internal comp intelligence database

## Demand Data Sources

### Job Boards

- **Indeed:** Total postings for role title + location
- **LinkedIn Jobs:** Open roles count, posting trends
- **Glassdoor:** Posting volume and growth
- **Built In:** Tech-specific posting data

### Trend Analysis

- **Google Trends:** Search interest for role titles over time
- **LinkedIn Economic Graph:** Hiring rate data (if accessible)
- **Bureau of Labor Statistics (BLS):** Occupational outlook data
- **Stack Overflow Survey:** Annual developer survey with trends

### Competitor Intelligence

- Track competitor career pages
- Monitor their LinkedIn job posts
- Note sponsorship and event presence
- Watch for mass hiring or layoff announcements

## Using Multiple Sources

### Triangulation Method

1. Gather data from at least 3 sources
2. Weight by reliability: Internal verified/Ravio (4x) > Survey (3x) > Crowdsourced (2x) > Job Posts (1x)
3. Calculate weighted ranges
4. Present P25/P50/P75 with sources and confidence
5. When Ravio data exists for the exact role/geography, anchor on Ravio percentiles and use other sources to validate or explain deviations

### Data Recency Rules

- Survey data older than 12 months: Inflate by 3-5% annually
- Job posting data older than 6 months: Treat as directional only
- Crowdsourced data older than 3 months: Still relevant but note age
- Always note the date of each data point

### Red Flags in Data

- Single source only → Low confidence, note limitation
- Wide spread between sources → Market in flux, present range
- No data for exact role → Use closest proxy, note adjustment
- Data from different geography → Apply cost-of-living adjustments
