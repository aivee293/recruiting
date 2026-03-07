---
name: boolean-search
description: This skill should be used when the user asks to "build a Boolean search", "create search strings", "write LinkedIn search", "X-Ray search", "Google dork for candidates", "source on GitHub", "Stack Overflow search", "search operators", "Boolean operators for recruiting", "platform-specific search syntax", or needs to construct candidate search queries for any sourcing platform.
---

# Boolean Search Construction for Talent Sourcing

## Purpose

Construct effective Boolean search strings for candidate sourcing across multiple platforms. Transform job requirements into precise, platform-specific search queries that maximize relevant candidate discovery while minimizing noise.

## Core Methodology

### Step 1: Decompose the Role

Before writing any Boolean string, break the job description into searchable components:

- **Required skills** - Hard technical or domain skills (e.g., "Python", "financial modeling")
- **Role titles** - Current and alternative titles (e.g., "Data Engineer" OR "Data Platform Engineer" OR "ETL Developer")
- **Seniority signals** - Years of experience, leadership keywords, title prefixes
- **Industry/domain** - Sector-specific terminology
- **Location** - Geographic filters where supported
- **Exclusion terms** - Filter out irrelevant results (e.g., NOT "recruiter" NOT "intern")

### Step 2: Build Title Variations

Generate comprehensive title variations including:
- Standard titles and abbreviations
- Emerging/alternative titles
- Adjacent roles with overlapping skills
- Industry-specific title conventions
- International title variations where relevant

### Step 3: Construct Platform-Specific Strings

Each platform has different syntax and capabilities. Adapt the search logic to each platform's operators and constraints.

## Platform Reference

### LinkedIn Recruiter / Sales Navigator

**Operators:** AND, OR, NOT, parentheses `()`, quotes `""`
**Limits:** ~2,500 characters per search field
**Fields:** Keywords, Title, Company, School, Location

**String structure:**
```
Title: ("Senior Data Engineer" OR "Staff Data Engineer" OR "Lead Data Engineer" OR "Principal Data Engineer")
Keywords: (Python OR Scala) AND (Spark OR Databricks OR Airflow) AND ("data pipeline" OR "ETL" OR "data platform")
```

**Tips:**
- Use Title field for role matching, Keywords for skills
- Parentheses group OR conditions before combining with AND
- Quote multi-word phrases: `"machine learning"` not `machine learning`
- NOT operator excludes: `NOT "manager"` removes management roles
- Stack multiple keyword searches to overcome character limits

### Google X-Ray Search

**Operators:** AND (space), OR, `-` (NOT), `""` (exact), `site:`, `intitle:`, `inurl:`, `filetype:`
**No character limit** (practical ~500 words)

**LinkedIn X-Ray pattern:**
```
site:linkedin.com/in/ ("senior data engineer" OR "staff data engineer") AND (Python OR Scala) AND (Spark OR Databricks) -jobs -recruiter -intitle:"hiring"
```

**GitHub X-Ray pattern:**
```
site:github.com ("data engineer" OR "ML engineer") AND (Python AND Spark) -"job" -"careers"
```

**Advanced X-Ray techniques:**
- `site:linkedin.com/in/` targets LinkedIn profiles
- `site:github.com` targets GitHub profiles
- `-site:linkedin.com` excludes LinkedIn from broader searches
- `filetype:pdf` finds uploaded resumes
- Combine with `inurl:` for specific page types
- Use `-intitle:` to exclude job posting pages

### GitHub

**Search URL:** `github.com/search?type=users&q=`
**Operators:** location, language, followers, repos, created
**Profile search fields:** bio, readme, repos, location, gist

**User search pattern:**
```
location:"Berlin" language:Python followers:>10 "data engineer"
```

**Code search for contributors:**
```
"data pipeline" language:python path:README.md
```

**Tips:**
- Filter by `followers:>X` for established engineers
- `repos:>Y` indicates active contributors
- Search repository READMEs for self-descriptions
- Check contribution graphs for activity levels

### Stack Overflow

**Search URL:** `stackoverflow.com/users` or Google X-Ray
**Limited native search** - use X-Ray approach

**X-Ray pattern:**
```
site:stackoverflow.com/users ("data engineer" OR "python developer") AND ("Berlin" OR "Germany")
```

**Tag-based discovery:**
- Identify top answerers in relevant tags (e.g., apache-spark, python-pandas)
- Use `site:stackoverflow.com/users` with location keywords

### Twitter/X

**Search operators:** `from:`, `"exact phrase"`, `OR`, `-` (NOT), `filter:`

**Pattern:**
```
("data engineer" OR "data platform") AND (hiring OR "open to" OR "looking for") -is:retweet
```

**Tips:**
- Search bios separately from tweets
- Use tools like Followerwonk for bio search
- Monitor hashtags: #DataEngineering, #OpenToWork, #TechJobs
- Search for conference speakers and workshop leaders

### Reddit

**Search operators:** `subreddit:`, `flair:`, `author:`, `site:reddit.com`

**X-Ray pattern:**
```
site:reddit.com ("data engineer" OR "ML engineer") ("looking for" OR "resume" OR "portfolio") (subreddit:datascience OR subreddit:dataengineering)
```

**Active subreddits for sourcing:**
- r/cscareerquestions, r/datascience, r/dataengineering
- r/experienceddevs, r/MachineLearning
- Industry-specific subreddits

### Discord & Slack Communities

Not directly searchable - use community-based sourcing:
- Join relevant communities (find via Disboard, Slofile)
- Monitor #introductions, #jobs, #career channels
- Search within communities using platform search
- Build presence before sourcing

---

## Non-Boolean Discovery Sources

Not everything is a Boolean search. These sources use browse, scrape, or direct lookup patterns. They complement Boolean searches and often surface candidates invisible on LinkedIn.

### TheOrg (Org Chart Database)

**URL:** `theorg.com`
**What it is:** Companies voluntarily publish org charts. Shows name, title, reporting line, and sometimes profile photo/bio.
**Sourcing value:** HIGH for sales, executive, and leadership roles. The single best non-LinkedIn source for mapping sales teams by name and title.

**Search patterns:**
```
site:theorg.com/org/<company-name>/org-chart
site:theorg.com "<company name>" "<title keyword>"
```

**Example:**
```
site:theorg.com/org/sosafe-awareness/org-chart
site:theorg.com "SoSafe" "account executive"
```

**Tips:**
- Navigate directly to `theorg.com/org/[company-slug]/org-chart` for the full team view
- Check for recent departures: people listed on TheOrg but absent from the company's LinkedIn page may have left
- Use for mapping reporting lines before outreach (know who the candidate reports to)
- Cross-reference TheOrg titles with LinkedIn profiles to verify currency

### Xing (DACH Professional Network)

**URL:** `xing.com`
**What it is:** German-language professional network with ~21-22M DACH members. Many SME/Mittelstand professionals maintain Xing profiles but not LinkedIn.
**Sourcing value:** HIGH for DACH-specific roles, especially non-tech and mid-market.

**Limitation:** Xing profiles are behind authentication. Google does NOT index individual Xing profiles. `site:xing.com` searches return near-zero results.

**What works:**
- **Native Xing search** (requires account, ideally Premium)
- **Google for company pages:** `site:xing.com/pages/<company-name>`
- **Google for job posts:** `site:xing.com/jobs "<title>" "<location>"`

**What doesn't work:**
- `site:xing.com/profile/` returns nothing useful (auth wall)

**Recommendation:** For any DACH-focused search, get a Xing account. It cannot be replaced by LinkedIn for the SME/Mittelstand segment.

### Employee Directories (RocketReach, Apollo, ZoomInfo, Lusha)

**What they are:** Databases that aggregate employee data from multiple public sources.
**Sourcing value:** MEDIUM. Useful for confirming names, titles, and discovering team members not visible on LinkedIn.

**Search patterns (via Google):**
```
site:rocketreach.co "<company name>" "<title keyword>"
site:apollo.io/companies/<company-slug>/people
```

**Tips:**
- Free tiers show names and titles; contact info requires paid plans
- Cross-reference against LinkedIn to verify currency
- Useful for finding people at small companies with minimal LinkedIn presence
- Apollo and ZoomInfo have stronger filtering for sales/GTM roles

### Company Career and Team Pages

**What they are:** The company's own website.
**Sourcing value:** MEDIUM for intelligence, LOW for individual IC discovery. Leadership is often listed; ICs rarely are.

**Search patterns:**
```
site:<company-domain> team OR "our team" OR "about us" OR "leadership"
site:<company-domain> careers OR jobs "<title keyword>"
```

**What to extract:**
- Leadership chain (who runs sales, engineering, product)
- Active job openings (team size proxy: open roles x 8-10 = approximate team size)
- Office locations and remote policies
- Product descriptions (for understanding what the team sells/builds)
- Press/blog section for recent milestones, funding, layoffs

### Conference and Event Sites

**What they are:** Speaker lists, sponsor pages, and attendee directories from industry events.
**Sourcing value:** HIGH for engineering, executive, and analyst roles. LOW for sales roles (sellers attend but rarely speak).

**Search patterns:**
```
"<conference name>" <year> speaker OR agenda "<title keyword>"
site:<conference-domain> speakers <year>
"<conference name>" "<company name>" attendee OR speaker
```

**Key events by domain:**
- **Cybersecurity:** it-sa (Nuremberg), RSA Conference, Black Hat, DEF CON, DACHsec
- **SaaS/Sales:** SaaStr, Pavilion events, Sales Hacker meetups
- **Engineering:** KubeCon, PyCon, QCon, local tech meetups
- **Data/ML:** NeurIPS, ICML, PyData, Data Council

### Press, News, and Company Blogs

**What they are:** Public articles mentioning individuals by name.
**Sourcing value:** HIGH for push factor intelligence, MEDIUM for individual name discovery.

**Search patterns:**
```
"<company name>" layoff OR restructuring OR "new hire" <year>
"<company name>" "joins as" OR "appointed" OR "promoted" sales OR engineering
"<company name>" "Presidents Club" OR "top performer" OR "employee of"
```

**Tips:**
- Layoff articles sometimes link to affected employees' LinkedIn profiles
- "New hire" press releases name individuals (useful for tracking who joined competitors)
- Company blog "welcome" posts introduce new team members by name

### Professional and Niche Directories

**What they are:** Industry association member lists, translator registries, bar associations, CPA registries, patent databases.
**Sourcing value:** LOW for discovery, HIGH for verification of specific claims (language proficiency, certifications, geographic history).

**Examples:**
- TranslationDirectory.com (translator profiles with native language data)
- Patent databases (USPTO, EPO) for technical contributions
- Certification registries (CISSP, CISM, PMP, CFA)
- University alumni directories (some are public)

---

## Advanced X-Ray Techniques

These techniques exploit how Google indexes LinkedIn's HTML structure, enabling searches that **LinkedIn's own search cannot perform**.

### Natural Language Profile Patterns

LinkedIn profiles contain standardized phrases in their HTML. Search for these exact phrases to filter by attributes LinkedIn doesn't expose as search filters.

**Unemployed / No Current Job:**
```
site:linkedin.com/in -present
→ finds profiles with no current position (at crawl time) or those who hide employment
```

**Years at Current Company:**
```
site:linkedin.com/in "present 4 years" civil engineering manager
→ exact tenure matching
```

**Public Email Addresses:**
```
site:linkedin.com/in "* gmail.com" "oil and gas" "account manager" gmail
→ profiles with visible email addresses (LinkedIn native search cannot search by email domain)
```

**Certifications:**
```
site:linkedin.com/in "verified achievement" "cloud essentials"
→ finds specific certifications (LinkedIn doesn't search Accomplishments section)
```

**Honors & Awards:**
```
site:linkedin.com/in "Honors & Awards"
→ finds profiles with accomplishments (not searchable on LinkedIn)
```

**Academic Grades:**
```
site:uk.linkedin.com/in intitle:ios developer "first class honours"
→ filter by academic achievement
```

**Pronoun-Based Search (diversity sourcing):**
```
site:linkedin.com/in she "she" -intitle:she fintech chief operating officer
```

### The "Graphic" Hack

LinkedIn's HTML includes the word "graphic" near company/school/certification logos. This enables past-employer and alumni searches that LinkedIn Recruiter cannot do natively.

**Currently or previously at a company:**
```
site:linkedin.com/in "ibm graphic"
→ anyone who works or worked at IBM
```

**PAST employees only (no longer there):**
```
site:linkedin.com/in "ibm graphic" -intitle:ibm
→ used to work at IBM but no longer does (intitle: shows current position)
```

**Alumni of a school (not currently employed there):**
```
site:linkedin.com/in "princeton university graphic" -intitle:princeton
```

**Certified professionals:**
```
site:linkedin.com/in "LinkedIn Recruiter Master Graphic"
→ certified LinkedIn Recruiter Masters
```

**Non-English profiles:** translate "graphic" to the appropriate language:
```
site:linkedin.com/in "Graphique Boolean Strings"  (French)
```

### "A-Players" Strings (Recommendation-Based Filtering)

Find candidates with strong professional endorsements — a quality signal LinkedIn doesn't let you filter on.

**Profiles with 5+ recommendations:**
```
site:linkedin.com/in "5..75 people have recommended" inanchor:Digital inanchor:marketing inanchor:manager inanchor:CA
```

**Profiles with 2+ recommendations (wildcard):**
```
site:linkedin.com/in "* people have recommended" inanchor:"registered nurse"
```

**Profiles with exactly 1 recommendation:**
```
site:linkedin.com/in "1 person has recommended" inanchor:"registered nurse"
```

**Profiles with any recommendations:**
```
site:linkedin.com/in "recommendations received" inanchor:"registered nurse"
```

**Filter by who gave the recommendation (boss/supervisor):**
```
site:linkedin.com/in intitle:"Executive Assistant" intext:"recommendations received" ("I" | "he reported" | "she reported") AROUND(3) ("Supervised" | "Managed" | "was his" | "was her" | "manager" | "Supervisor") AROUND(3) ("Directly" | "Direct")
```

### "Precision Unemployed" Strings

Find recently laid-off candidates — many not marked #opentowork either publicly or privately.

**Unemployed since any month in a specific year:**
```
site:linkedin.com/in inanchor:"Accountant" inanchor:CPA "* jan|feb|mar|apr|may|jun|jul|aug|sep|oct|nov|dec 2024 1..20 months|years" -present
```

**Unemployed since specific months:**
```
site:linkedin.com/in inanchor:Software inanchor:Engineer "* jul|aug 2024 1..20 months|years" -present
```

### Connections Range Method (Bypass Result Limits)

Google caps results at ~300 per search. LinkedIn Recruiter caps at ~1,000. Overcome these limits by segmenting searches by connection count ranges, then merging results.

**Pattern — increment connection ranges:**
```
site:linkedin.com/in "Philadelphia Pennsylvania United States 2..50 connections" inanchor:"financial analyst"
site:linkedin.com/in "Philadelphia Pennsylvania United States 51..100 connections" inanchor:"financial analyst"
site:linkedin.com/in "Philadelphia Pennsylvania United States 101..150 connections" inanchor:"financial analyst"
site:linkedin.com/in "Philadelphia Pennsylvania United States 151..200 connections" inanchor:"financial analyst"
...
site:linkedin.com/in "Philadelphia Pennsylvania United States 500* connections" inanchor:"financial analyst"
```

Run each variation, scrape results (e.g., with Instant Data Scraper Chrome extension or ImportFromWeb Google Sheets add-on), and deduplicate to collect thousands of profiles.

### Result Maximization Tips

1. **Don't use OR — search each term separately** and merge results
2. **Vary the terms** — synonyms and alternative phrasings yield different result sets
3. **Repeat keywords** — repeating a keyword changes Google's ranking, surfacing different profiles
4. **Search nearby locations individually** — instead of one city, search each suburb/neighborhood
5. **Add `imagesize:200x200`** — LinkedIn profile photo dimensions; can triple results with minimal overlap
6. **Use connections range segmentation** — bypass the 300-result Google limit

## Best Practices

### String Quality Checklist

- [ ] Title variations cover standard, emerging, and adjacent roles
- [ ] Skills use both full terms and common abbreviations
- [ ] Exclusion terms remove recruiters, job posts, irrelevant roles
- [ ] Parentheses correctly group OR conditions
- [ ] Multi-word phrases are quoted
- [ ] String stays within platform character limits
- [ ] Test search returns relevant results (spot-check first page)

### Iterative Refinement

1. Start broad, review first 20 results
2. Add exclusion terms for noise patterns
3. Tighten skill requirements if too many results
4. Loosen title variations if too few results
5. Document final strings for team reuse

### Output Format

When generating Boolean strings, provide:
1. **Role decomposition** - Skills, titles, seniority, exclusions
2. **Platform-specific strings** - Ready to paste into each platform (LinkedIn Recruiter, Google X-Ray, and at least one non-LinkedIn platform relevant to the role)
3. **Non-LinkedIn discovery queries** - TheOrg lookups, company page scrapes, employee directory searches, conference site searches as applicable
4. **Expected result quality** - Notes on what to expect per source
5. **Refinement suggestions** - How to adjust if results are too broad/narrow

## Additional Resources

### Reference Files

You are **stongly encouraged** to read the reference files

For platform-specific advanced techniques:
- **`references/advanced-operators.md`** - Full operator reference per platform with edge cases, including AROUND(n), inanchor:, imagesize:, emoji search, country subdomains, and keyword repetition
- **`references/industry-title-maps.md`** - Common title variations by industry and function
- **`references/xray-recipes.md`** - Ready-to-use compound X-Ray string templates for common sourcing scenarios
