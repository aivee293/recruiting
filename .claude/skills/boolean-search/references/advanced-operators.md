# Advanced Boolean Operators by Platform

## LinkedIn Recruiter / Sales Navigator

### Field-Specific Operators

**Title Field:**

- Exact match: `"Senior Data Engineer"`
- OR grouping: `("Senior" OR "Staff" OR "Lead") AND "Data Engineer"`
- NOT exclusion: `"Data Engineer" NOT "Manager" NOT "Director"`
- Character limit: ~2,500 per field

**Keywords Field:**

- Full Boolean support
- Searches across: headline, summary, experience descriptions, skills
- Does NOT search: recommendations, endorsements, publications

**Company Field:**

- Exact match only: `"Google"` or `"Alphabet"`
- No OR grouping in company field on some plans
- Use Keywords for company-name-based searching if needed

**School Field:**

- Exact name: `"MIT"` or `"Massachusetts Institute of Technology"`
- Limited Boolean support

### Advanced Techniques

**Nested Boolean:**

```
("data engineer" OR "data platform engineer") AND (Python OR Scala) AND (Spark OR Databricks OR "Apache Beam") NOT ("junior" OR "intern" OR "recruiter")
```

**Proximity-like patterns (not native, but effective):**

- Use phrase variations: `"5 years experience"` OR `"5+ years"` OR `"five years"`
- Combine title + keywords for precision:
  - Title: `"Senior Data Engineer"`
  - Keywords: `Spark AND Python AND (AWS OR GCP)`

**Saved Searches:**

- Save each variation as a separate alert
- Create narrow (high-precision) + broad (high-recall) versions
- Set weekly alerts for passive monitoring

### Limitations

- No wildcard support (`*`) in LinkedIn Boolean
- No NEAR/proximity operator
- Case insensitive by default
- Maximum search results cap (~2,500 profiles viewable)

---

## Google X-Ray

### Core Operators

| Operator | Function | Example |
|----------|----------|---------|
| `site:` | Limit to domain | `site:linkedin.com/in/` |
| `intitle:` | Word in page title | `intitle:"data engineer"` |
| `inurl:` | Word in URL | `inurl:github.com` |
| `inanchor:` | Word in link anchor text | `inanchor:"software engineer"` |
| `filetype:` | File type | `filetype:pdf resume` |
| `""` | Exact phrase | `"machine learning engineer"` |
| `-` | Exclude | `-jobs -careers -"job posting"` |
| `OR` | Either term | `Python OR Scala` |
| `\|` | OR alternative (no spaces) | `engineer\|developer` |
| `*` | Wildcard | `"senior * engineer"` |
| `..` | Number range | `"5..10 years experience"` |
| `AROUND(n)` | Proximity (within n words) | `director AROUND(2) engineering` |
| `imagesize:` | Image dimensions | `imagesize:200x200` |

### Country-Specific LinkedIn X-Ray

LinkedIn uses 2-letter country code subdomains. Target specific countries:

```
site:uk.linkedin.com/in   (United Kingdom)
site:de.linkedin.com/in   (Germany)
site:nl.linkedin.com/in   (Netherlands)
site:fr.linkedin.com/in   (France)
site:in.linkedin.com/in   (India)
site:ca.linkedin.com/in   (Canada)
site:au.linkedin.com/in   (Australia)
site:br.linkedin.com/in   (Brazil)
```

**Example - UK CFOs:**

```
site:uk.linkedin.com/in intitle:CFO -intitle:assistant
```

**Alternative:** Use Google's Advanced Search page and set the "region" filter instead of country subdomains.

### Other LinkedIn Directory X-Rays

Beyond profiles (`/in/`), you can X-Ray other LinkedIn sections:

```
site:linkedin.com/company    (company pages)
site:linkedin.com/jobs       (job listings)
site:linkedin.com/pulse      (articles/publications)
site:linkedin.com/posts      (posts)
```

**Find recent jobs with low competition:**

```
site:linkedin.com/jobs/view sourcer "be among the first 25 applicants" -"no longer"
```

### X-Ray Search Patterns

**LinkedIn Profile X-Ray:**

```
site:linkedin.com/in/ "data engineer" (Python OR Scala) (Spark OR Databricks) "Berlin" -jobs -recruiter
```

**LinkedIn with seniority:**

```
site:linkedin.com/in/ ("senior" OR "staff" OR "lead" OR "principal") "data engineer" Python -"hiring" -"recruiter" -"talent"
```

**GitHub Profile X-Ray:**

```
site:github.com "data engineer" (Python AND Spark) "Berlin" -"job" -"careers" -"hiring"
```

**Resume X-Ray:**

```
filetype:pdf ("data engineer" OR "data platform") (Python AND Spark) "Berlin" resume
```

**Stack Overflow X-Ray:**

```
site:stackoverflow.com/users "data engineer" ("Berlin" OR "Germany") (python OR spark)
```

### AROUND(n) Proximity Operator

Finds pages where two keywords appear within `n` words of each other. Powerful for title matching and experience filtering.

**Basic syntax:**

```
<keyword1> AROUND(n) <keyword2>
```

**Title matching:**

```
director AROUND(2) engineering
→ matches: "Director of Engineering", "Engineering Director", "Director, Civil Engineering"
```

**Years at current company:**

```
site:linkedin.com/in present AROUND(3) "2..6 years" intitle:devops intitle:manager Toronto
```

**GPA search:**

```
site:linkedin.com/in "GPA" AROUND(2) 4.0
→ matches: "GPA 4.0", "4.0 GPA", "GPA: 3.49/4.0"
```

**Location from profile (member location):**

```
site:linkedin.com/in "connections" AROUND(5) "greater chicago area" intitle:engineer intitle:meta
```

**Past work locations:**

```
site:linkedin.com/in "connections" AROUND(5) "san francisco" "month OR months OR year OR years" AROUND(4) "chicago" intitle:engineer
```

**Multi-AROUND(n) Method** - chain multiple proximity operators for complex natural language queries:

```
site:linkedin.com/in inanchor:product inanchor:manager "3..35" AROUND(2) "years" AROUND(10) "experience" AROUND(10) "Product Manager"|"product management" AROUND(10) "technical|digital|software"
```

**Tips:**

- Use tight values (1-3) for word pairs that should be adjacent
- Use loose values (5-15) for concepts that should appear in the same paragraph
- Combine with `inanchor:` and natural language phrases for precision
- Works in Google, not available in LinkedIn native search

---

### inanchor: Operator (Anchor Text Search)

In HTML, an "anchor" is a clickable link. The `inanchor:` operator finds pages that other pages link to using your search term in the link text.

**Why this matters for LinkedIn:** LinkedIn's public directories (`/pub/dir/`) contain links to profiles where the anchor text includes:

- Member name
- Profile headline
- Member location
- Most recent job (current or past)
- Latest school attended

This lets you search things **LinkedIn Recruiter cannot search natively**: headlines, true current location, latest company.

**Headline search:**

```
site:linkedin.com/in inanchor:healthcare -intitle:healthcare inanchor:payments -intitle:payments
```

**#OpenToWork headline search:**

```
site:linkedin.com/in #opentowork inanchor:opentowork technical recruiter -intitle:opentowork
```

**Current location (US):**

```
site:linkedin.com/in inanchor:"boise, id" intitle:CPA
site:linkedin.com/in inanchor:"orange county" inanchor:java developer
site:linkedin.com/in inanchor:"greater new york"
```

**Current location (non-US):**

```
site:nl.linkedin.com/in inanchor:amsterdam investigative journalist OSINT
site:nl.linkedin.com/in intitle:sales inanchor:"Noord-Holland"
```

**Latest school search:**

```
site:linkedin.com/in "oxford" inanchor:oxford -intitle:oxford physics phd "string theory"
```

**Latest company (including people with no current job):**

```
intitle:CPWA® intitle:CFP® site:linkedin.com/in inanchor:"morgan stanley"
```

**People who moved between companies:**

```
site:linkedin.com/in inanchor:amazon inanchor:google intitle:amazon
→ people who recently moved from Google to Amazon
```

**People who moved between cities:**

```
site:linkedin.com/in inanchor:"chicago il" inanchor:"san francisco ca"
```

**Find hiring managers:**

```
site:linkedin.com/in inanchor:"hiring devops" "hiring devops"
```

**Find people with unique names (no duplicates):**

```
site:linkedin.com/in -"see others named"
```

**Beyond profiles - company search by location/industry:**

```
site:linkedin.com/company inanchor:chicago inanchor:"Technology, Information and Internet"
```

---

### imagesize: Operator (More Results Hack)

Adding `imagesize:200x200` (LinkedIn profile photo dimensions) to searches can significantly increase unique results with minimal overlap.

```
site:linkedin.com/in manager "hiring devops"                    → ~297 results
site:linkedin.com/in manager "hiring devops" imagesize:200x200  → ~737 results (only ~91 overlap)
```

Use this when you want to maximize the number of unique profiles found.

---

### Emoji & Accented Character Search

LinkedIn's native search cannot search for emojis or accented characters, but Google can.

**Phone numbers by area code:**

```
site:linkedin.com/in 📞212
```

**Country expats (flag emojis):**

```
intitle:🇳🇱 site:linkedin.com/in   (likely NL expats)
intitle:🇩🇪 site:linkedin.com/in   (likely DE expats)
```

**LGBTQ+ community members:**

```
intitle:🌈 site:linkedin.com/in
```

**Accented names:**

```
site:linkedin.com/in intitle:María
site:linkedin.com/in intitle:René
```

---

### Exclusion Patterns

Standard noise exclusions for recruiting X-Ray:

```
-jobs -careers -"job posting" -"job description" -"we are hiring" -"apply now" -intitle:"hiring" -intitle:"careers" -recruiter -"talent acquisition"
```

### Wildcard Usage

Google's `*` matches any single word:

```
"senior * engineer" site:linkedin.com/in/
```

Matches: "senior software engineer", "senior data engineer", "senior ML engineer"

Also useful for matching any number:

```
"* people have recommended" → matches "5 people have recommended", "12 people have recommended"
```

### Number Range

```
"2..6 years" → matches any number from 2 to 6 followed by "years"
"5..75 people have recommended" → matches profiles with 5 to 75 recommendations
```

Note: Number range (`..`) can be inconsistent in Google for general text, but works well with LinkedIn's standard profile phrases.

### Pipe Operator (Inline OR)

The `|` (pipe) works as an inline OR without spaces, useful in compact queries:

```
"month|months|year|years" → matches any of the four words
"technical|digital|software" → matches any of the three words
```

### Keyword Repetition Technique

Repeating search keywords yields different result sets with only partial overlap, effectively giving you more unique profiles per query.

```
site:www.linkedin.com/in intitle:"associate partner"                               → 299 results
associate partner site:www.linkedin.com/in intitle:"associate partner"              → 297 results (162 overlap)
partner partner partner site:www.linkedin.com/in intitle:"associate partner"        → 294 results (196 overlap with above two)
Total unique across all three: ~525 profiles
```

Run each variation and scrape/merge results to maximize coverage.

---

## GitHub

### User Search Syntax

**Base URL:** `https://github.com/search?type=users&q=`

| Qualifier | Example | Description |
|-----------|---------|-------------|
| `location:` | `location:"San Francisco"` | User's listed location |
| `language:` | `language:python` | Languages in repositories |
| `followers:` | `followers:>50` | Minimum followers |
| `repos:` | `repos:>10` | Minimum public repos |
| `created:` | `created:>2015-01-01` | Account age |
| `fullname:` | `fullname:"Jane Smith"` | Full name search |

**Advanced User Search:**

```
location:"Berlin" language:python followers:>20 "data engineer"
```

### Repository-Based Sourcing

Search repositories to find contributors:

```
"data pipeline" language:python stars:>100
```

Then check contributor profiles.

### README-Based Discovery

People describe themselves in profile READMEs:

```
"data engineer" "Berlin" path:README.md
```

Source: <https://docs.github.com/en/search-github/github-code-search/understanding-github-code-search-syntax>

---

## Stack Overflow

### Tag-Based Discovery

Find top answerers by tag:

1. Navigate to tag page (e.g., stackoverflow.com/tags/apache-spark)
2. Click "Top Answerers"
3. Filter by time period
4. Review profiles for location and professional info

### X-Ray Approach (Preferred)

```
site:stackoverflow.com/users ("data engineer" OR "data scientist") ("Berlin" OR "Germany")
```

---

## Twitter/X

### Search Operators

| Operator | Example | Description |
|----------|---------|-------------|
| `from:` | `from:username` | Tweets from user |
| `"phrase"` | `"data engineer"` | Exact phrase |
| `OR` | `term1 OR term2` | Either term |
| `-` | `-retweet` | Exclude |
| `filter:links` | `filter:links` | Only tweets with links |
| `min_faves:` | `min_faves:10` | Minimum likes |
| `since:` | `since:2025-01-01` | Date filter |

### Bio Search

Twitter doesn't support native bio search. Use:

- Followerwonk (followerwonk.com) for bio search
- Google X-Ray: `site:twitter.com "data engineer" "Berlin"`

### Hashtag Monitoring

Track industry hashtags for active professionals:

- #DataEngineering, #DataPipelines
- #MachineLearning, #MLOps
- #OpenToWork, #Hiring
- Conference-specific hashtags

---

## Reddit

### Search Operators

```
site:reddit.com ("data engineer" OR "ML engineer") ("resume" OR "portfolio" OR "looking for") (subreddit:datascience OR subreddit:dataengineering)
```

### Key Subreddits for Sourcing

**Engineering:** r/cscareerquestions, r/experienceddevs, r/programming
**Data:** r/datascience, r/dataengineering, r/MachineLearning
**Design:** r/userexperience, r/webdesign, r/UI_Design
**Product:** r/ProductManagement
**General:** r/jobs, r/careerguidance

### Useful Threads

Search for recurring threads:

- "Resume review" threads
- "What's your salary" threads
- "I just got laid off" threads
- "Looking for opportunities" threads
