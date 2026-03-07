# Talent Pool Sizing Techniques

## Overview

Accurate pool sizing answers: "How many people could potentially fill this role?" This informs sourcing strategy, timeline expectations, and stakeholder communication.

## Sizing Frameworks

### Total Addressable Pool (TAP)

Everyone who could theoretically do the job:

- All people with the right title/skills globally or in target geo
- Includes those not looking, not reachable, not interested
- Useful for: Market sizing, understanding total landscape

### Serviceable Available Pool (SAP)

People you can actually reach and engage:

- Subset of TAP who are on reachable platforms
- Have public profiles or are in accessible communities
- Located in target geography or open to target arrangement
- Useful for: Setting realistic pipeline expectations

### Qualified Available Pool (QAP)

People who match and might move:

- Subset of SAP who match hard requirements
- Show signals of potential interest (passive or active)
- Within compensation range
- Useful for: Forecasting pipeline conversion

### Formula

```
TAP → SAP (÷ 3-5x) → QAP (÷ 3-5x)

Example:
TAP: 5,000 (all Senior Data Engineers in Germany)
SAP: 1,200 (on LinkedIn, profile visible, in target cities)
QAP: 300 (match requirements, reasonable comp alignment, not locked in)
```

## Sizing Methods

### Method 1: LinkedIn Search Count

1. Build Boolean search matching role requirements
2. Run on LinkedIn Recruiter (shows result count)
3. This is roughly SAP
4. Adjust: +20% for non-LinkedIn professionals
5. QAP estimate: SAP × 0.25 (roughly 25% are viable)

### Method 2: Company-by-Company Build-Up

1. List target companies (20-50 companies)
2. Estimate relevant team size at each
3. Sum totals
4. This captures a subset of TAP focused on named targets
5. Useful for: Focused searches, executive roles

### Method 3: Market Data Extrapolation

1. Find industry reports on function headcount
2. Filter by geography and seniority
3. Apply company type weighting
4. Cross-reference with LinkedIn data
5. Useful for: Broad market sizing, leadership presentations

### Method 4: Community Size Proxy

1. Count members in relevant Slack/Discord/Reddit communities
2. Estimate professional overlap (many people in multiple communities)
3. Deduplicate estimate: unique_people ≈ total_memberships × 0.4
4. Filter by location/seniority
5. Useful for: Niche roles, emerging fields

## Conversion Rate Benchmarks

### Outreach Response Rates

Well-benchmarked from large-scale platform data:

| Channel | Reply Rate (any) | Interest Rate (positive) | Source |
|---------|-----------------|-------------------------|--------|
| **Email sequence (3-4 touches)** | 19-23% | 6-13% | *Gem Fall 2024 (4M+ sequences); Ashby 2024 (500K+ sequences)* |
| **Single email (no follow-up)** | 11-15% | ~5-7% | *Gem Fall 2024* |
| **LinkedIn InMail (recruiting)** | 18-25% avg; 35-40% top | ~7-12% | *LinkedIn Talent Solutions 2024* |

**Key modifiers:**
- Personalized outreach: **+47%** response vs. generic templates (*Gem 2024*)
- Send on Behalf Of hiring manager (SOBO): **+50%** replies (*Gem 2024*)
- 4-email sequence vs. single email: **2x** replies, **+68%** interest (*Gem 2024*)
- InMail message length sweet spot: under 400 characters → **+22%** response (*LinkedIn 2024*)
- Messages of 101-150 words (~10 sentences) perform best for email (*Gem 2024*)

**By role type (email reply rates):**
- Business roles: 18.7% (*Ashby 2024, 500K+ sequences*)
- Technical roles: 19.4%, reaching 28% by message 4 (*Ashby 2024; Gem 2024*)
- Legal & Recruiting: highest reply rates (*Ashby 2024*)
- Finance: lowest reply rates (*Ashby 2024*)

**By company size of target candidate:**
- Candidates at companies <250 employees: 23% reply rate (*Gem 2024*)
- Candidates at large enterprises: 35.6% reply rate (*Gem 2024*)

**InMail response by industry** (*SendIQ/Outreach.io 2024*):
- Technology & SaaS: 22-28% avg, best campaigns 35-42%
- Professional & Financial Services: 15-20% avg, best campaigns 28-35%
- Manufacturing & Industrial: 18-24% avg, best campaigns 30-38%
- Healthcare & Pharma: 16-22% avg, best campaigns 25-32%

### Hiring Funnel Passthrough Rates

**Application-to-interview by source** (*Ashby 2025, 38M applications across 93K jobs*):
- Internal candidates: 42%
- Agency candidates: 42%
- Referred candidates: 40%
- Sourced candidates: higher than inbound (exact % not published separately)
- Inbound applicants: significantly lower (implied 2-3%)

**Interview-to-offer rate** (*Ashby Recruiter Productivity 2024, 31M applications*):
- Technical candidates: ~7%
- Business candidates: ~9%
- All sources average: 36% (*CareerPlug 2024, 10M+ applications* — note: measures final-round, not all interview stages)

**Offer acceptance rate:**
- Business roles: 84% (*Ashby 2024, 230K offers*)
- Technical roles: 73% (*Ashby 2024*)
- All roles: 82-84% (*Gem 2025-2026, 1.2-1.3M hires*)
- Overall trend: improving since 2021 (was 76-77%, now 82-84%)

### Sourced-to-Hire Ratio

**How many sourced candidates per hire?**

No single benchmark report publishes this as one end-to-end number. The synthesized estimate from multiple sources:

| Metric | Range | Derivation |
|--------|-------|-----------|
| **Contacted → Hired** | ~50-100 per hire | Synthesized from Gem + Ashby + practitioner data |
| **Interested (positive reply) → Hired** | ~8-15 per hire | Derived from 6-13% interest rate × downstream conversion |
| **Submitted to HM → Hired** | ~3-5 per hire | Practitioner consensus; consistent with 25-40% onsite-to-offer × 80%+ acceptance |

**Supporting data points:**
- Sourced candidates are **5-8x more likely to be hired** than inbound applicants (*Gem 2025-2026, 165M applications*)
- Overall application-to-hire rate: 0.5% (*Gem 2025*); sourced implied ~2.5-4%
- Sourcing generates ~2% of applications but **7-22% of hires** depending on company size (*Gem 2025*)
- Smallest companies (1-249 FTE): 22.5% of hires are sourced (*Gem 2025*)
- 46% of sourced hires are **rediscovered** from existing CRM/ATS (*Gem 2026*, up from 29% in 2021)

### Mid-Funnel Gap (Transparency Note)

The stages between "interested" and "offer" — screen completion, HM submission, interview scheduling — are **not publicly benchmarked** by any major ATS or sourcing platform for sourced candidates specifically. Ashby and Gem track this internally but only publish aggregated or source-combined passthrough rates. The mid-funnel estimates below are practitioner consensus, not cited from a single report:

- Interested → Screen completed: ~80-90% (sourced candidates have higher show rates than inbound)
- Screened → Submitted to HM: ~50-70% (depends on sourcer-recruiter alignment and role specificity)
- Submitted → Interview: ~60-80% (HM rejection rates vary widely by company)

### Benchmark Sources

| Source | Sample Size | Key Metrics |
|--------|------------|-------------|
| **Gem Recruiting Benchmarks 2025** (2021-2024 data) | 140M applicants, 1.3M hires | Sourced 5x more likely hired, 0.5% app-to-hire, 84% OAR |
| **Gem Recruiting Benchmarks 2026** (2021-2025 data) | 165M applications, 1.2M hires | Sourced 8x more likely hired, 82% OAR, 46% rediscovered |
| **Gem Email Outreach Benchmarks Fall 2024** | 4M+ outreach sequences | 22.6% reply, 12.6% interest, sequence vs. single email lift |
| **Ashby Candidate Sourcing Report 2024** | 500K+ email sequences | 86% open, 19% reply, 37.7% interest among responders |
| **Ashby Offer Acceptance Report 2024** | 230K offers, 2021-2024 | 73% tech / 84% business OAR, improving trend |
| **Ashby Recruiter Productivity 2024** | 31M applications, 95K jobs | 7% tech / 9% business interview-to-offer |
| **Ashby Referrals Report 2025** | 38M applications, 93K jobs | 40-42% app-to-interview for referred/agency/internal |
| **LinkedIn Talent Solutions 2024** | Platform-wide | 18-25% InMail response, 35-40% top campaigns |
| **Employ/Jobvite Recruiter Nation 2024** | 22,000+ customers | 8.4% app-to-interview, 36.2% interview-to-offer, 41-43d TTF |
| **CareerPlug Recruiting Metrics 2024** | 10M+ applications | 2% app-to-interview, 36% interview-to-hire, 180 applicants/hire |
| **SmartRecruiters Benchmarks 2025** | 8.8M job ads | Tech: 110 applicants/hire, 48d TTH, 77% OAR |
| **SHRM Recruiting Benchmarks 2025** | 2,371 respondents | 44d median TTF, ~91% OAR, 20 reqs/recruiter |

These vary significantly by role difficulty, company brand, compensation competitiveness, and outreach quality.

## Communicating Pool Size to Stakeholders

**Do:**

- Present ranges, not exact numbers
- Explain methodology briefly
- Include conversion assumptions
- Show trade-offs ("If we expand to remote, pool grows 5x")

**Don't:**

- Present a single number as definitive
- Conflate TAP with QAP
- Ignore location and compensation constraints
- Promise timeline based on pool size alone

**Template:**

```
For [Role] in [Geography]:
- Total addressable pool: ~X,000 professionals
- Reachable pool: ~X00 with active profiles
- Qualified & likely to engage: ~X0-X00

Based on typical conversion rates, we should plan to identify
X0-X00 candidates to generate 3-5 qualified submissions.
Estimated timeline: X-X weeks of active sourcing.
```
