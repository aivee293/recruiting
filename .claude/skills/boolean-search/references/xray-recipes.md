# X-Ray Search Recipes

Ready-to-use compound X-Ray string templates for common sourcing scenarios. Adapt the placeholder values (in `<angle brackets>`) to your specific search.

## Recipe 1: Current Employees at a Specific Company

Find people who currently work at a target company with a specific title.

```
site:linkedin.com/in intitle:<company> intitle:"<job title>"
```

**Example — Netflix ML Engineers:**
```
site:linkedin.com/in intitle:netflix intitle:"machine learning"
```

Note: `intitle:` matches the LinkedIn page title, which contains the **current** job title and company.

---

## Recipe 2: Past Employees (Alumni Sourcing)

Find people who **used to** work at a company but no longer do.

```
site:linkedin.com/in "<company> graphic" -intitle:<company>
```

**Example — Ex-Google engineers:**
```
site:linkedin.com/in "google graphic" -intitle:google intitle:engineer
```

The "graphic" hack matches LinkedIn's HTML near company logos. `-intitle:` removes people who currently list that company.

---

## Recipe 3: Past Employees of Company A Now at Company B

```
site:linkedin.com/in inanchor:<company_B> inanchor:<company_A> intitle:<company_B>
```

**Example — People who moved from Google to Amazon:**
```
site:linkedin.com/in inanchor:amazon inanchor:google intitle:amazon
```

---

## Recipe 4: People Who Relocated Between Cities

```
site:linkedin.com/in inanchor:"<city_A>" inanchor:"<city_B>"
```

**Example — Moved between Chicago and San Francisco:**
```
site:linkedin.com/in inanchor:"chicago il" inanchor:"san francisco ca"
```

---

## Recipe 5: A-Players (Recommendation-Based)

Find candidates with strong professional endorsements.

**With 5+ recommendations in a specific role and location:**
```
site:linkedin.com/in "5..75 people have recommended" inanchor:<title_word1> inanchor:<title_word2> inanchor:<state_abbr>
```

**Example — Digital Marketing Managers in California with 5+ recs:**
```
site:linkedin.com/in "5..75 people have recommended" inanchor:Digital inanchor:marketing inanchor:manager inanchor:CA
```

---

## Recipe 6: Recently Unemployed Candidates

Find people who left their job in a specific time window (many not marked #opentowork).

```
site:linkedin.com/in inanchor:<title_word1> inanchor:<title_word2> "* <month_abbreviations> <year> 1..20 months|years" -present
```

**Example — Software Engineers who left Jul-Aug 2024:**
```
site:linkedin.com/in inanchor:Software inanchor:Engineer "* jul|aug 2024 1..20 months|years" -present
```

**Example — Accountants unemployed since any month in 2024:**
```
site:linkedin.com/in inanchor:"Accountant" inanchor:CPA "* jan|feb|mar|apr|may|jun|jul|aug|sep|oct|nov|dec 2024 1..20 months|years" -present
```

---

## Recipe 7: Tenure-Based Filtering

Find people with a specific number of years in their current role.

```
site:linkedin.com/in present AROUND(3) "<min>..<max> years" intitle:<title> <location>
```

**Example — DevOps Managers in Toronto, 2-6 years in role:**
```
site:linkedin.com/in present AROUND(3) "2..6 years" intitle:devops intitle:manager Toronto
```

---

## Recipe 8: Experience-Based with Proximity (Multi-AROUND)

Find people with a minimum number of years of experience in a specific domain. Uses chained `AROUND(n)` operators for natural language matching.

```
site:linkedin.com/in inanchor:<title_word1> inanchor:<title_word2> "<min>..<max>" AROUND(2) "years" AROUND(10) "experience" AROUND(10) "<role_or_domain>"
```

**Example — Product Managers with 3+ years experience in data:**
```
site:linkedin.com/in inanchor:product inanchor:manager "3..35" AROUND(2) "years" AROUND(10) "experience" AROUND(10) "Product Manager"|"product management" AROUND(10) "technical|digital|software" "Data science"|collection|management|analytics
```

---

## Recipe 9: #OpenToWork Headline Search

Find candidates with #opentowork in their headline (not just the profile badge).

```
site:linkedin.com/in #opentowork inanchor:opentowork <role keywords> -intitle:opentowork
```

**Example — Technical Recruiters open to work:**
```
site:linkedin.com/in #opentowork inanchor:opentowork technical recruiter -intitle:opentowork
```

---

## Recipe 10: Certified Professionals

Find people with specific certifications (LinkedIn doesn't search the Accomplishments section natively).

```
site:linkedin.com/in "verified achievement" "<certification name>"
```

**Example — Cloud Essentials certified:**
```
site:linkedin.com/in "verified achievement" "cloud essentials"
```

**Example — LinkedIn Recruiter Master certified:**
```
site:linkedin.com/in "LinkedIn Recruiter Master Graphic"
```

---

## Recipe 11: Country-Specific Executive Search

Target specific countries using LinkedIn's subdomain structure.

```
site:<country_code>.linkedin.com/in intitle:<title> <keywords>
```

**Example — UK-based iOS developers with first class honours:**
```
site:uk.linkedin.com/in intitle:ios developer "first class honours"
```

**Example — Netherlands-based sales professionals in Noord-Holland:**
```
site:nl.linkedin.com/in intitle:sales inanchor:"Noord-Holland"
```

---

## Recipe 12: Hiring Manager Discovery

Find managers who have "hiring" in their headline.

```
site:linkedin.com/in inanchor:"hiring <role>" "hiring <role>"
```

**Example — Managers hiring for DevOps:**
```
site:linkedin.com/in inanchor:"hiring devops" "hiring devops"
```

---

## Recipe 13: Grand Finale (Compound Multi-Signal Search)

Combine multiple techniques for ultra-precise targeting. This example finds:
- Software Engineers/Developers in the US
- Currently at a FAANG company
- 1-9 years in their current role
- Previously worked at Microsoft or Nvidia
- Have 2+ LinkedIn recommendations

```
site:www.linkedin.com/in (inanchor:meta | inanchor:facebook | inanchor:apple | inanchor:amazon | inanchor:netflix | inanchor:google) "microsoft graphic" | "nvidia graphic" inanchor:software inanchor:engineer | inanchor:developer "* people have recommended" "present 1..9 year|years"
```

**Breakdown of each component:**
- `site:www.linkedin.com/in` → US LinkedIn profiles
- `(inanchor:meta | inanchor:facebook | ...)` → currently at FAANG
- `"microsoft graphic" | "nvidia graphic"` → previously at Microsoft or Nvidia
- `inanchor:software inanchor:engineer | inanchor:developer` → headline contains role
- `"* people have recommended"` → has 2+ recommendations
- `"present 1..9 year|years"` → 1-9 years in current role

**To scale this beyond 300 results**, add connections range segmentation:
```
... "500* connections"
... "451..500 connections"
... "401..450 connections"
... (continue decrementing)
```

---

## Recipe 14: Public Email Discovery

Find profiles with visible email addresses (LinkedIn doesn't search by email domain).

```
site:linkedin.com/in "* <email_domain>" "<industry>" "<role>" <domain_keyword>
```

**Example — Oil & Gas Account Managers with Gmail addresses:**
```
site:linkedin.com/in "* gmail.com" "oil and gas" "account manager" gmail
```

---

## Recipe 15: Resume X-Ray (PDF)

Find uploaded resumes on the web.

```
filetype:pdf ("<role1>" OR "<role2>") (<skill1> AND <skill2>) "<location>" resume
```

**Example — Data Engineer resumes in Berlin:**
```
filetype:pdf ("data engineer" OR "data platform") (Python AND Spark) "Berlin" resume
```

---

## Scaling Tip: Connections Range Template

To collect thousands of profiles for any search, append connection ranges and run each separately:

```
"<City State Country> 2..50 connections" <your_search>
"<City State Country> 51..100 connections" <your_search>
"<City State Country> 101..150 connections" <your_search>
"<City State Country> 151..200 connections" <your_search>
"<City State Country> 201..300 connections" <your_search>
"<City State Country> 301..400 connections" <your_search>
"<City State Country> 401..500 connections" <your_search>
"<City State Country> 500* connections" <your_search>
```

Scrape each variation's results and deduplicate. Tools: Instant Data Scraper (Chrome extension), ImportFromWeb (Google Sheets add-on).
