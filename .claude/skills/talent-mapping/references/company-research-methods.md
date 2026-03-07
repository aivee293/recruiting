# Company Research Methods for Talent Mapping

## Company Profile Research

### Company Page & Digital Presence

**TheOrg (theorg.com):**

- Org charts: name, title, reporting line, team structure, tenure
- Companies voluntarily publish; coverage varies but HIGH for funded tech/SaaS companies
- Best non-LinkedIn source for mapping sales teams by name and title
- Navigate directly to `theorg.com/org/[company-slug]/org-chart` for full team view
- Cross-reference with LinkedIn: people on TheOrg but absent from company's LinkedIn page may have left
- X-Ray: `site:theorg.com/org/<company-name>/org-chart` or `site:theorg.com "<company name>" "<title keyword>"`

**LinkedIn Company Page:**

- Headcount by function (People tab → filter by department)
- Growth trend: compare current headcount to 6-12 months ago
- Key people: leadership chain and team members
- Job postings: active openings indicate growth areas and priorities

**XING Company Page (DACH region):**

- Employee count and department breakdown for German-speaking markets
- Particularly strong for SME/Mittelstand companies underrepresented on LinkedIn
- Job postings section with local market roles
- Limitation: individual profiles behind auth wall; `site:xing.com/profile/` returns nothing useful
- What works via Google: `site:xing.com/pages/<company-name>` and `site:xing.com/jobs "<title>" "<location>"`

**Employee Directories (RocketReach, Apollo, ZoomInfo, Lusha):**

- Aggregated employee data from multiple public sources
- Useful for confirming names, titles, and discovering team members not visible on LinkedIn
- X-Ray: `site:rocketreach.co "<company name>" "<title keyword>"` or `site:apollo.io/companies/<company-slug>/people`
- Free tiers show names and titles; contact info requires paid plans
- Apollo and ZoomInfo have stronger filtering for sales/GTM roles

**Company Website:**

- "About Us" / "Team" page for leadership and org structure
- Careers page for open roles, team descriptions, and benefits
- Press/News section for recent milestones, funding, and expansions
- Product pages to understand what teams build and sell
- "Customers" or "Case Studies" page for market positioning signals

**Conference and Event Sites:**

- Speaker lists, sponsor pages, and attendee directories from industry events
- HIGH for engineering, executive, and analyst roles; LOW for sales (attendees, not speakers)
- Search: `"<conference name>" <year> speaker OR agenda "<title keyword>"` or `site:<conference-domain> speakers <year>`
- Key DACH/EU events by domain:
  - Cybersecurity: it-sa (Nuremberg), RSA Conference, Black Hat, DACHsec
  - SaaS/Sales: SaaStr, Pavilion events, Sales Hacker meetups
  - Engineering: KubeCon, PyCon, QCon, local tech meetups
  - Data/ML: NeurIPS, ICML, PyData, Data Council

**Press, News, Company Blogs (for individual discovery):**

- Push factor intelligence: layoffs, restructuring, leadership changes
- Individual name discovery: "new hire" press releases, company blog "welcome" posts, award announcements
- Search: `"<company name>" layoff OR restructuring <year>`, `"<company name>" "joins as" OR "appointed" sales OR engineering`
- Company blogs with "welcome [Name]" posts are a direct sourcing signal

### Financial & Corporate Data

**Company Registries (for headcount and legal structure):**

- Handelsregister (Germany) — company type, directors, registered address
- Camera di Commercio / Registro Imprese (Italy) — company data, financial filings
- Companies House (UK) — filings, directors, headcount category
- KvK / Handelsregister (Netherlands) — company details and filings
- Infogreffe / Societe.com (France) — financial data and company structure

**Financial Intelligence:**

- Annual reports (public companies) — segment revenue, headcount disclosures, growth areas
- Bundesanzeiger (Germany) — financial disclosures for German companies
- EDGAR / SEC filings (US-listed) — 10-K filings reveal org structure and headcount
- Revenue estimates from industry reports to size sales/GTM teams

**Funding & Growth Stage:**

- Dealroom.co — EU-focused startup and scale-up database, funding rounds, headcount trends
- Crunchbase — funding history, company size, investors, growth signals
- PitchBook — detailed funding, valuations, comparable companies
- EU-Startups, Tech.eu — European startup ecosystem news and funding rounds

### Employer Reputation & Culture

**Review Platforms:**

- Kununu (DACH region) — employee reviews, salary data, culture ratings (equivalent of Glassdoor for Germany/Austria/Switzerland)
- Glassdoor — reviews, salary data, interview process, CEO approval
- Blind / TeamBlind — anonymous professional network, compensation data, candid company reviews (strong in tech)
- Comparably — culture scores, compensation, diversity data
- Indeed Reviews — broader coverage including non-tech and operational roles

**Awards & Rankings:**

- Great Place to Work (country-specific lists)
- LinkedIn Top Companies (by country)
- Deloitte Fast 500 / Inc 5000 Europe — high-growth companies
- Financial Times FT1000 (Europe's fastest growing companies)
- Industry-specific awards (e.g., SaaS Awards, Stevie Awards for Sales & Customer Service)
- "Best Employer" lists by country (Focus Best Employers in Germany, Handelsblatt rankings)

### Job Postings Analysis

Applicable across all functions — not just tech:

- **Volume:** Number of open roles by department signals team size and growth investment
- **Recurrence:** Same role posted repeatedly = retention issues or sustained growth
- **Requirements:** Reveal tech stack, tools, processes, team structure, and reporting lines
- **Compensation:** Posted ranges where legally required (increasingly mandatory in EU)
- **Seniority distribution:** Ratio of junior vs. senior openings indicates team maturity
- **Location patterns:** Which offices or remote policies for each function

**Job Board Sources:**

- LinkedIn Jobs — broadest coverage
- StepStone (DACH, Benelux) — strong for mid-market and enterprise roles
- Indeed (multi-country) — high volume, broad coverage
- Glassdoor Jobs — integrated with review data
- Welcome to the Jungle (France, expanding EU) — startup and tech-forward companies
- The Hub (Nordics) — Nordic startup ecosystem
- Angel.co / Wellfound — startup roles globally
- Function-specific boards (see below)

---

## Function-Specific Research Sources

### Technology & Engineering

**Tech Stack Discovery:**

- BuiltWith / StackShare — actual technologies in use (verified by web crawling)
- GitHub Organization — public repos, active contributors, languages, project activity
- Engineering Blog / Tech Blog — team structure, architecture decisions, tools, culture
- Stack changes or migrations signal new hiring needs and skill gaps

**Community Signals:**

- GitHub contributor graphs for open-source activity
- Stack Overflow top answerers in relevant tags
- Conference speaker lists (QCon, KubeCon, PyCon, local meetups)
- Tech podcast guests and blog authors

**Sizing Engineering Teams:**

- GitHub Org method: active contributors ≈ 20-40% of total engineering team (commonly observed ratio; no single authoritative source)
- Job posting ratio: open eng roles ≈ 10-15% of eng team size (standard HR planning benchmark)
- Engineering blog output: a rough directional signal only — no reliable industry benchmark exists for author-to-team ratios

### Sales & Revenue

**SaaS/B2B Intelligence:**

- G2 / TrustRadius / Capterra — product reviews reveal company size, customer base, and competitive positioning
- Competitor product pages — pricing tiers indicate market segment (SMB vs. enterprise)
- Partnership pages — technology and channel partners indicate GTM model
- Case studies — customer logos, deal sizes, and use cases reveal sales motion

**Sales Team Sizing Signals:**

- Number of AE job postings × 8-10 ≈ current AE team size (derived from 10-15% open roles benchmark)
- Number of SDR/BDR postings × 5-8 ≈ current SDR team size (SDR median annual turnover is ~40%, so higher posting-to-team ratio; *Bridge Group 2025, n=351*)
- SDR-to-AE ratio: 1 SDR per 2.4 AEs is the median (*Bridge Group 2025*)
- LinkedIn Sales Nav: search company + "Account Executive" or "Sales" in title
- Sales leader LinkedIn posts often mention team size ("proud of my 30-person team")
- G2 review volume as proxy for customer base size → implies sales team proportionality

**Sales Community & Events:**

- Pavilion (formerly Revenue Collective) member directories
- SaaStr speakers and attendees
- Sales Hacker community participants
- President's Club mentions on LinkedIn
- Industry conferences where the company exhibits (booth size ≈ GTM investment)

### Marketing

**Marketing Team Research:**

- Company blog output volume → implies content team size
- Social media presence and posting frequency → social/comms team
- Paid ad volume (SEMrush, SimilarWeb) → performance marketing team
- Event sponsorship frequency → event marketing presence
- PR/press coverage volume → comms team activity

**Marketing-Specific Sources:**

- SEMrush / Ahrefs / SimilarWeb — digital marketing investment and traffic
- Podcast directories — company-hosted podcasts indicate content marketing investment
- Webinar/event platforms — frequency of hosted events

**Sizing Marketing Teams:**

- Blog output: a full-time writer produces ~4-6 posts/month at ~3.5h per post (*Orbit Media 2025, n=808*). Divide monthly blog volume by 4-6 for a rough content writer headcount estimate
- 54% of B2B orgs with dedicated content teams have 2-5 people; 67% of SaaS companies use at least one freelancer (*CMI/MarketingProfs 2025, n=980*)
- Marketing job postings × 8-10 ≈ total marketing team (derived from 10-15% open roles benchmark)

### Customer Success

**CS Team Research:**

- Customer review platforms (G2, TrustRadius) — review recency and response patterns indicate CS engagement
- Support documentation quality and coverage → CS/support team investment
- Community forums — company-run user communities indicate CS investment
- NPS scores mentioned in marketing materials

**Sizing CS Teams** (*Gainsight 2024 CS Index + TSIA 2024 + Forth & Scale 2025*):

- Median ARR per CSM: ~€1.3M; top quartile: ~€3.9M (*Gainsight 2024, n=250+*)
- High-touch (enterprise): 10-50 accounts per CSM, €2-5M ARR managed
- Mid-touch (mid-market): 50-100 accounts per CSM, €2-5M ARR managed
- Low-touch/tech-touch (SMB): 100-500+ accounts per CSM, €1-2M ARR managed
- CS spend as % of ARR: median ~8% (*SaaS Capital 2025*)
- Account load increases at later stages due to digital CS automation, not higher manual workload

### Product & Design

- Dribbble / Behance — design team output and style
- Product Hunt — launch frequency and product evolution
- User conference recordings — product vision presentations
- Design system documentation (public) — team maturity signal

### Executive & Leadership

- Board composition (annual reports, company website)
- Advisory board members (Crunchbase, LinkedIn)
- Press interviews and keynote appearances
- Industry association board memberships
- Patent filings — research leadership and technical direction

---

## Pool Sizing Techniques

### LinkedIn Headcount Method

1. Search LinkedIn for `company:"Company Name" title:"[Role]"`
2. Count results (LinkedIn shows approximate count)
3. Adjust for title variations (multiply by 1.3-1.5x)
4. Adjust for platform coverage by market (*DataReportal/NapoleonCat 2025*):
   - Netherlands ~93%, UK ~82-87% penetration → minimal adjustment needed
   - Nordics ~41-67%, France ~57% → moderate adjustment (1.3-1.5x)
   - Germany ~30-34%, Austria ~24% → significant adjustment (2-3x); cross-reference with XING (~21-22M DACH members)
   - Switzerland ~73% → moderate adjustment
   - Note: "members" ≠ active users; actual active usage is significantly lower on both LinkedIn and XING
5. For DACH roles: cross-reference with XING company page headcount. LinkedIn has overtaken XING in practical relevance as of 2025, but many SME/Mittelstand profiles remain XING-only

### Job Posting Ratio Method

1. Count current job postings for the function
2. Industry average: open roles ≈ 10-15% of team size
3. Formula: `team_size ≈ open_roles / 0.12`
4. Adjust for growth stage (startups post more relative to size)
5. Adjust for function: sales roles tend to have higher posting-to-team ratios than engineering

### Event & Conference Method

1. Check speaker lists and attendee companies from relevant events
2. Count representatives from each target company
3. No reliable industry benchmark exists for speaker-to-team-size ratios (*Bizzabo 2025, HockeyStack 2025 — neither tracks this metric*)
4. Use as a **directional signal**, not a sizing formula:
   - More speakers/sponsors from a company → larger, more invested team in that function
   - Exhibitor booth size correlates with GTM investment level
   - Events are rated the #1 GTM channel across nearly all ARR bands (*High Alpha 2025*)
   - ~40% of B2B companies have event teams of 5+ people (*Bizzabo 2025, n=1,500+*)

### Revenue-Based Sizing (for GTM roles)

1. Estimate company revenue (from annual reports, Dealroom, Crunchbase, press)
2. Apply benchmarked industry ratios:

**GTM headcount as % of total** (*Forth & Scale 2025, synthesizing OpenView/KeyBanc/PitchBook, n=372*):

| Stage | Sales % | Marketing % | CS % | **GTM Total** |
|---|---|---|---|---|
| Seed | 10.5% | 11.2% | 7.8% | **29.5%** |
| Series A | 15.4% | 13.8% | 8.3% | **37.5%** |
| Series B | 19.7% | 14.9% | 9.2% | **43.8%** |
| Series C+ | 22.3% | 15.2% | 10.8% | **48.3%** |
| Public | 24.1% | 14.8% | 11.6% | **50.5%** |

**AE quota benchmarks** (*KeyBanc/Sapphire 2024, n=104; Bridge Group 2024*):

- Median new ARR per AE: ~€300K; median AE quota: ~€700K
- SMB AE quota: €360-€480K
- Mid-market AE quota: €650-€810K
- Enterprise AE quota: €1.2-€1.4M
- Median quota attainment: 70-75%
- Caveat: these are US-sourced benchmarks; EU quotas are typically 10-25% lower

**Within the GTM org** (derived from Forth & Scale 2025):

- Marketing = 29-38% of GTM headcount (larger share at earlier stages, shrinks as Sales scales)
- Sales = 36-48% of GTM headcount (grows with stage)
- CS = 21-26% of GTM headcount (relatively stable)

### GitHub Organization Method (for tech roles)

1. Check company's GitHub org (if public)
2. Count active contributors in relevant repositories
3. Adjust: public contributors = 20-40% of total team
4. Note: Many companies have minimal public presence

### Triangulation

Always use 2-3 methods and take the median:

- LinkedIn headcount + Job posting ratio + One function-specific signal
- If estimates diverge significantly, investigate why
- Note confidence level:
  - **High:** 3 sources agree within 20%
  - **Medium:** 2 sources agree
  - **Low:** single source only

---

## Benchmark Sources

Industry reports referenced for sizing formulas above. Refresh annually.

| Source | Coverage | Key Metrics |
|---|---|---|
| **KeyBanc/Sapphire SaaS Survey** (annual, n=104) | US private SaaS, median ~€24M ARR | AE quota, ARR/AE, GTM efficiency |
| **Forth & Scale SaaS Growth Benchmarks** (2025, n=372) | Synthesizes OpenView, KeyBanc, PitchBook | Headcount % by function and stage |
| **Bridge Group SDR Metrics Report** (2025, n=351) | US B2B sales development | SDR tenure (1.9yr), turnover (40%), SDR:AE ratio (1:2.4), quota by segment |
| **Gainsight Customer Success Index** (2024, n=250+) | CS organizations globally | ARR/CSM (€1.3M median), accounts/CSM, CS spend as % ARR |
| **TSIA CS Benchmark** (2024) | Enterprise CS | CSM ratios, CS org structure |
| **Orbit Media Blogger Survey** (2025, n=808) | Content marketers | 3.5h/post, ~4-6 posts/month per writer |
| **CMI/MarketingProfs B2B Content** (2025, n=980) | B2B marketing teams | Team sizes, content maturity |
| **DataReportal / NapoleonCat** (2025) | LinkedIn penetration by country | DACH ~30-34%, UK ~82-87%, NL ~93% |
| **SaaS Capital Spending Benchmarks** (2025) | Private B2B SaaS | CS ~8% of ARR, selling costs ~15% of ARR |
| **Bizzabo State of Events** (2025, n=1,500+) | B2B event marketing | Event team sizes, channel effectiveness |
| **High Alpha SaaS Benchmarks** (2024-2025, n=800+) | B2B SaaS | Headcount allocation, top GTM channels |

Note: Most benchmark data is US-sourced. For EU markets, apply a 10-25% discount to quota and compensation figures. Headcount ratios are more transferable across markets.
