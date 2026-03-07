---
name: sourcing-plan
description: Create a comprehensive sourcing strategy for a role - channels, communities, keywords, target companies
---

# Sourcing Plan Generator

Create a comprehensive, actionable sourcing plan for the specified role. The plan defines where to source, how to prioritize channels, which communities to target, and what the overall strategy should be.

**Input:** $ARGUMENTS - either a role name/description or a path to a JD file.

## Process

### Step 1: Understand the Role

If $ARGUMENTS is a file path, read the JD. If it's a role name, ask clarifying questions:
- What level/seniority?
- What team/department?
- What location(s)?
- Any specific requirements?

Check `.claude/talent-sourcing.local.md` for company context, preferred channels, and existing templates.

### Step 2: Ensure Candidate Persona Exists

A persona is required before building the sourcing plan. Check for `roles/[role-name]/persona.md`.

- **If persona exists:** Read it and use it to inform channel selection, company targeting, and messaging strategy.
- **If persona doesn't exist:** Flag this as a blocker. The main conversation should launch persona-builder before proceeding with the sourcing plan. Do not build a persona inline — the persona-builder agent has the frameworks and templates for this.

### Step 3: Identify Sourcing Channels

Rank channels by expected effectiveness for this specific role:

**Direct sourcing channels:**
- LinkedIn Recruiter / Sales Navigator
- TheOrg org charts (HIGH for sales/GTM and executive roles; public, scrapeable)
- Xing (DACH market; requires account for deep search; HIGH for SME/Mittelstand)
- GitHub / GitLab (for technical roles)
- Portfolio sites (for design/creative roles)
- Google X-Ray across platforms (LinkedIn, GitHub, Stack Overflow, TheOrg, Xing)
- Employee directories (RocketReach, Apollo, ZoomInfo; name + title confirmation)
- Company career and team pages (leadership discovery, team sizing via open roles)
- Press, news, company blogs (push factors: layoffs, restructuring, new hires)

**Community channels:**
- Relevant Slack/Discord communities
- Reddit communities
- Professional associations
- Alumni networks

**Event channels:**
- Conferences and meetups
- Hackathons and competitions
- Webinars and workshops
- Industry trade shows

**Content channels:**
- Tech blogs and publications
- Podcast guests
- YouTube/Twitch creators
- Newsletter authors

**Referral channels:**
- Internal employee referrals
- External network referrals
- Alumni referrals from target companies
- Advisor/investor networks

### Step 4: Map Target Companies

Using the talent-mapping skill, create a prioritized target company list:
- Circle 1: Direct competitors
- Circle 2: Adjacent companies
- Circle 3: Transferable talent sources

### Step 5: Define Search Strategy

For each prioritized channel:
- Specific search approach
- Boolean strings or search queries to use
- Expected volume and quality
- Time investment estimate

### Step 6: Create Timeline

Sequence weekly activities by **company-fit tier**, not just by channel. Target companies where candidates are most likely to join (based on company-size fit, push factors, and comp positioning) in week 1, then expand to lower-probability pools in later weeks. This front-loads conversion rate and generates early pipeline momentum. Channel diversity still matters, but within each week, prioritize outreach to high-fit companies before broad sweeps.

Week-by-week sourcing plan:
- Week 1: [Highest-fit companies and channels, both primary geographies if parallel]
- Week 2: [Expansion to medium-fit companies, community channels]
- Week 3: [Community engagement]
- Week 4: [Assessment and pivot]

## Output

Generate a complete sourcing plan document and save it to the appropriate role directory. If a role directory doesn't exist, suggest creating one:

```
roles/[role-name]/sourcing-plan.md
```

### Sourcing Plan Structure

```markdown
# Sourcing Plan: [Role Title]
**Created:** [Date]
**Hiring Manager:** [If known]
**Target Start Date:** [If known]
**Priority:** [High/Medium/Low]

## Candidate Persona Summary
[Brief persona description]

## Channel Strategy

### Priority 1 (Start Immediately)
| Channel | Approach | Expected Yield | Time/Week |
|---------|----------|---------------|-----------|

### Priority 2 (Week 2+)
| Channel | Approach | Expected Yield | Time/Week |
|---------|----------|---------------|-----------|

### Priority 3 (If Needed)
| Channel | Approach | Expected Yield | Time/Week |
|---------|----------|---------------|-----------|

## Target Companies
[Concentric circle map]

## Search Strings
[Ready-to-use Boolean strings per platform]

## Weekly Plan
[Week-by-week activities]

## Success Metrics
- Target pipeline size: [number]
- Target response rate: [percentage]
- Target time-to-fill: [weeks]

## Risks & Mitigations
[Identified challenges and backup plans]
```
