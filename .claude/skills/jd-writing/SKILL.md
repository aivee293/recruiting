---
name: jd-writing
description: "This skill should be used when the user asks to write a JD, create a job description, draft job posting, JD for [role], job spec, role description, write a role profile, help me define a role, or needs to create, rewrite, or improve a job description for any function or level."
---

# Job Description Writing

## Purpose

Create compelling, candidate-centric job descriptions that attract the right people and feed downstream sourcing artifacts (personas, search strings, outreach). A JD is not a legal document or internal req — it's the first impression a candidate has of the role and the company.

## Input Routing

This skill works from multiple starting points:

| Input Available | Action |
|----------------|--------|
| `brief.md` exists | Extract role requirements, HM preferences, team context |
| Raw HM requirements dump | Parse into structured components, ask clarifying questions for gaps |
| Existing JD to rewrite | Analyze against quality standards, rewrite weak sections |
| Role title only | Ask focused questions: level, scope, team, impact, key requirements |
| `talent-sourcing.local.md` | Pull company name, EVP, culture signals, comp philosophy |

Always check `talent-sourcing.local.md` for company context before drafting.

## Writing Process

### Step 1: Gather Context

Read all available inputs:
- `roles/[role-name]/brief.md` — intake notes, HM preferences, team structure
- `.claude/talent-sourcing.local.md` — company identity, EVP, compensation philosophy, AI operating principles
- `.claude/data/market/` — relevant market data if available

If the input is sparse, ask clarifying questions. Focus on the gaps that matter most:

**Must-know before writing:**
- What problem does this person solve? (not "what tasks do they do")
- What does success look like in 6-12 months?
- What level of seniority and scope?
- Who do they report to and work with?
- Location/remote policy

**Good-to-know:**
- Team size and stage (building from scratch vs. joining established team)
- Budget/comp range (even approximate)
- Why the role is open (growth, backfill, new function)
- What's the hiring manager's biggest worry about this hire?

### Step 2: Decompose the Role

Break the role into searchable, readable components before writing:

| Component | Question to Answer |
|-----------|-------------------|
| **Title** | What would the right candidate search for? Use market-standard titles, not internal jargon. |
| **Level** | Junior / Mid / Senior / Staff / Principal / Director / VP? Map to clear scope indicators. |
| **Scope** | Individual contributor or people leader? How much autonomy? Decision-making authority? |
| **Team** | Who do they work with daily? What's the team's mission? |
| **Impact** | What changes because this person exists? What doesn't happen without them? |
| **Growth** | Where does this role lead in 2-3 years? |

### Step 3: Draft the JD

Use the universal JD structure below. Write candidate-centric by default — lead with what the candidate gets, not what the company needs.

**Tone decision framework:**

| Context | Lean toward |
|---------|-------------|
| Competitive talent market, passive candidates | Candidate-centric (default) |
| Employer brand is strong, high inbound volume | Balanced |
| Exec/leadership hire | Balanced to company-centric (mission-first) |
| `outreach_tone` in config is `professional-warm`|

### Step 4: Adapt by Role Family

Each section of the JD shifts emphasis depending on the role family. Use the adaptation table:

| Section | Engineering | Data/ML | Product | Design | GTM/Sales | Ops/Finance |
|---------|-------------|---------|---------|--------|-----------|-------------|
| **The Opportunity** | Technical challenge, scale, stack | Data problems, model impact, research vs. applied | Product scope, user impact, market | Design maturity, user research, craft | Market, quota, territory, growth | Process impact, scale, transformation |
| **What You'll Do** | Systems built, problems solved | Pipelines, models, experiments | Decisions owned, roadmap scope | Experiences shaped, research led | Revenue driven, relationships built | Operations improved, risks managed |
| **What You'll Bring** | Skills + tools, not years | Techniques + domain, not degrees | Judgment + track record, not titles | Portfolio + process, not tools | Results + methodology, not tenure | Expertise + frameworks, not certifications |
| **What We Offer** | Tech stack, engineering culture, ownership | Data infrastructure, research culture, publication | Product influence, customer access, autonomy | Design system, research budget, craft culture | Comp plan, territory quality, enablement | Career path, exposure, influence scope |

### Step 5: Inclusive Language Review

Run through each category before finalizing. This is an active editing pass, not a passive checklist.

**Scan for and fix:**

- **Gendered language** — he/she to they, "manpower" to "team", "chairman" to "chair". Check pronouns in example scenarios.
- **Age-coded terms** — remove "digital native", "energetic", "young team", "recent graduate" (unless truly entry-level). Remove "seasoned" or "veteran" (use specific experience instead).
- **Ability-coded terms** — remove unnecessary physical requirements ("stand for long periods" when the role is desk-based). Avoid "strong" as a catch-all.
- **Culture-coded terms** — remove "ninja", "rockstar", "guru", "work hard play hard", "culture fit". Replace with specific behavioral expectations.
- **Requirement inflation** — degree required? Would equivalent experience work? Years of experience exceed the technology's age? Specific tool when the skill is transferable?
- **Exclusionary framing** — "must be" vs "ideally has", "required" vs "preferred". Count must-haves: if more than 5, some are nice-to-haves in disguise.

For the full reference with examples and alternatives, see `references/inclusive-language.md`.

### Step 6: Sensitive Information Review

JDs are public documents. Strip anything a competitor, customer, or journalist shouldn't see. Scan every section for:

- **Financial metrics** — deal sizes/ACV, revenue, ARR, margins, contract values (use "mid-market" or "enterprise" instead of exact figures)
- **Pricing signals** — anything that lets a competitor reverse-engineer packaging or discounting
- **Internal targets** — pipeline coverage ratios, conversion targets, quota numbers, OKRs
- **Headcount plans** — exact growth projections ("scaling from 40 to 450") unless already public (press releases, funding announcements)
- **Strategic timing** — fundraising plans, M&A, unreleased products
- **Customer details** — named contracts with values, unless the customer relationship is already public

**Rule of thumb:** If the data point would be useful in a competitor's sales deck or a journalist's article, remove it. Keep the *signal* (category, scale, motion) while removing the *number*.

When in doubt, flag the line for the user rather than publishing it.

### Step 7: Stop-Slop Pass

Run the `stop-slop` skill rules against the final draft:
- Cut filler phrases and throat-clearing openers
- Break formulaic structures (don't start every bullet the same way)
- Vary rhythm — mix sentence lengths
- Remove anything that sounds like a pull-quote
- Trust the reader: state facts, skip softening

## JD vs. Job Advert

A job description is an internal document — duties, qualifications, reporting lines. A **job advert** is candidate-facing marketing copy that sells the opportunity. This skill writes job adverts, not internal JDs. The distinction matters: internal JDs list what the company needs; job adverts show what the candidate gets.

When rewriting an existing JD, the transformation is usually: strip the internal framing, rewrite around candidate value, and front-load benefits.

## Universal JD Structure

Every JD follows this structure. Sections can be reordered or renamed to match company style, but all components should be present.

**Information priority** (what candidates scan for, in order — per LinkedIn research):
1. Title, salary, location — decides whether they keep reading
2. Personal benefits — "why is this better than where I am now?"
3. Role clarity — what they'll actually do (outcomes, not tasks)
4. Fit assessment — can I do this? (requirements)
5. Response ease — how to apply

### 1. The Opportunity

The hook. 2-4 sentences answering: why does this role exist, and why should someone care?

Most candidates — especially passive ones — skim-read. Research (LinkedIn heatmap studies) shows they decide whether to keep reading within the first 2-3 lines. Front-load what matters: title, location, salary signal, and the hook.

- Lead with impact, not the company's need
- Name the problem space, not generic responsibilities
- Make it specific enough that the wrong candidate self-selects out

**Hook techniques that work:**

- **Frustration hook** — Name what's wrong with their current situation: "If you're tired of being the 'doer' in a rigid marketing machine, this is your chance to be the architect."
- **Scale/problem hook** — Show the challenge: "Our payments infrastructure processes $2B daily across 40 countries. You'll own the reliability layer."
- **Honest-gap hook** — Admit what's broken: "Our CFO has been building models in spreadsheets between board meetings. You'll build FP&A from scratch."
- **Ownership hook** — Lead with autonomy: "You'll decide what we charge, how we charge it, and build the systems behind it."

**Bad:** "We're looking for a talented engineer to join our growing team."

### 2. What You'll Do

5-8 outcomes, not tasks. Frame as "what changes because you're here" not "daily to-do list."

**Rules:**
- Start each bullet with an outcome verb (build, own, lead, design, ship), not a task verb (write, attend, update, maintain)
- Include scope signals: team size, budget, revenue, user count
- Show autonomy level: "you'll decide" vs "you'll contribute to"
- Max 8 bullets — if you need more, the role might be two roles

### 3. AI-First in [Function]

**Required for every JD.** QuoIntelligence is AI-native. Every role should signal how AI shapes the work in that function.

Title the section "AI-First in [Function]" (e.g., "AI-First in Marketing", "AI-First in Engineering"). Open with a one-line framing: AI is an operating principle here.

**Rules:**
- 3-5 principles specific to how AI applies to this role's function
- Pull company-level AI philosophy from `talent-sourcing.local.md` and adapt per function
- Be concrete: "You'll use AI tools to [specific task]" not "We value AI"
- Include product fluency expectation if the role touches customers or positioning
- Include data/measurement principle (decisions based on data, not gut)
- Include responsible AI use (accurate claims, defensible positioning)

**What to avoid:**
- Generic AI hype ("cutting-edge AI", "revolutionary technology")
- Implying AI replaces the person
- Buzzword stacking without concrete expectations
- More than 5 principles (diminishing returns; pick the ones that matter for this function)

### 4. What You'll Bring

Split into must-haves (3-5) and nice-to-haves (3-5). Frame as capabilities, not credentials.

**Rules:**
- Capabilities over credentials: "can design distributed systems" over "10 years Java experience"
- Evidence over claims: "have shipped production ML models" over "strong ML skills"
- Transferable skills over specific tools: "modern data orchestration" over "must know Airflow"
- Each must-have should be genuinely required — if you'd interview someone without it, it's a nice-to-have
- Always include AI fluency as a must-have: active use of AI tools in their function, ability to evaluate new ones critically. Adapt the framing per role family.
- Include one "unfair advantage" nice-to-have that reveals what would make someone exceptional

### 5. What We Offer

Team, culture, growth, comp philosophy. Be specific and honest.

**Rules:**
- Name concrete specifics, not generic perks ("20% time for open source" not "great engineering culture")
- Include comp philosophy or range if authorized (candidates filter on this; omitting it costs applicants)
- Mention team size, reporting structure, collaboration model
- Growth: where does this role lead? What will they learn?

### 6. About [Company]

Brief, honest, differentiated. 2-3 sentences max.

**Rules:**
- What you do, for whom, and why it matters — in plain language
- One differentiator that's actually true (not "we're innovative")
- Traction signal if available (revenue, users, funding, customers)
- Pull from `talent-sourcing.local.md` company context

### 7. How to Apply / The Process (Optional)

If included, set expectations: how many interview stages, timeline, what to prepare.

## Quality Checklist

Before saving the JD, verify:

- [ ] The Opportunity section would make someone stop scrolling
- [ ] "What You'll Do" uses outcomes, not tasks
- [ ] Must-haves are genuinely required (would you reject a perfect candidate missing one?)
- [ ] No requirement inflation (years > technology age, degree when unnecessary)
- [ ] Inclusive language review completed (Step 5)
- [ ] Sensitive information review completed (Step 6)
- [ ] Stop-slop pass completed (Step 7)
- [ ] AI-First section included with function-specific principles
- [ ] Company-specific details pulled from config (not generic placeholders)
- [ ] Total length: 500-800 words (long enough to inform, short enough to read)
- [ ] A qualified candidate can tell within 30 seconds if this role is for them

## Output

Save the completed JD to:

```text
roles/[role-name]/jd.md
```

If the role directory doesn't exist, create it:

```bash
mkdir -p roles/[role-name]/candidates roles/[role-name]/reports
```

## Reference Files

You are **stongly encouraged** to read the reference files

- **`references/anti-patterns.md`** — Before/after examples of common JD mistakes to avoid: vague requirements, task lists, requirement inflation, jargon, and more.
- **`references/inclusive-language.md`** — Comprehensive bias detection checklist organized by type: gendered, age-coded, ability-coded, culture-coded, and requirement inflation.
- **`references/jd-examples.md`** — Annotated examples of effective JD sections across role families, with margin notes explaining what works and why.
