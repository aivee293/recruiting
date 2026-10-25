---
name: hiring-quality
description: "Measure and improve hiring after a role closes: quality-of-hire, hiring-manager and candidate-experience surveys, search retrospectives, silver-medalist lists, and pre-boarding/onboarding checklists. Use when a role is filled or cancelled, or the user asks what went well or how good the hire was. Not for live pipeline reporting (use stakeholder-reporting)."
---

# Hiring Quality for Recruiting

## Purpose

Close the feedback loop on hiring: measure quality of hire, capture hiring manager and candidate experience, run search retrospectives, manage silver medalists, and coordinate onboarding handoff. This is the "learn and improve" engine of the recruiting function.

## Quality of Hire Framework

**What to measure:**

| Metric | Source | Timing | Benchmark |
|--------|--------|--------|-----------|
| Hiring Manager Satisfaction | HM survey | 30/60/90 days | >4.0/5.0 |
| New Hire Performance Rating | Performance review | 6/12 months | Meets/Exceeds expectations |
| Ramp Time to Productivity | HM assessment | 90 days | Within expected range per role |
| Retention | HRIS data | 6/12/24 months | >85% at 12 months |
| New Hire Engagement | Engagement survey | 90 days | Equal to or above team avg |

**Survey cadence:** 30-day check-in → 60-day deeper dive → 90-day full assessment

**Question design principles:**

- Mix quantitative (1-5 scale) with qualitative (open-ended)
- Ask about specific behaviors, not general impressions
- Include a "would you hire this person again?" question (strongest single QoH predictor)
- Correlate QoH scores back to upstream signals: source of hire, interviewer scores, time-in-process

**Correlation analysis:** Track which sourcing channels, interviewers, and process steps predict high QoH. Over time, this reveals:

- Which sources produce the best hires (not just the most hires)
- Which interviewers are most predictive
- Whether time-in-process correlates with hire quality
- Which competencies from scorecards best predict on-the-job performance

## HM Experience Survey

**5 default dimensions:**

1. **Communication** — "The recruiter kept me informed throughout the process" (1-5)
2. **Intake Quality** — "The recruiter understood the role requirements after our intake meeting" (1-5)
3. **Candidate Identification** — "The candidates presented matched what I was looking for" (1-5)
4. **Scheduling & Pace** — "The process moved at an appropriate pace" (1-5)
5. **Overall Satisfaction** — "I would work with this recruiter again on a future search" (1-5)

**When to send:** Within 1 week of offer acceptance or role closure

**Response collection:** Anonymous optional, but recommend named for actionable feedback

**Trend analysis:** Track scores over time per recruiter, per department, per role type

## Candidate Experience Survey

**Stage-appropriate surveys — different questions by outcome:**

| Candidate Status | Survey Focus | Timing |
|-----------------|-------------|--------|
| Hired | End-to-end experience, decision factors | Day 1-3 |
| Rejected at screen | Speed, communication quality, respect | 3 days after rejection |
| Rejected after interview | Fairness, feedback quality, would they reapply | 3 days after rejection |
| Rejected at final round | Depth of experience, closure quality | 3 days after rejection |
| Withdrew | Why they withdrew, what could change their mind | 1 day after withdrawal |

**Candidate NPS:** "On a scale of 0-10, how likely are you to recommend applying at [Company] to a friend?"

- Promoters (9-10), Passives (7-8), Detractors (0-6)
- Track per department, per recruiter, over time
- Segment by outcome (hired vs rejected) — expect hired to score higher, but rejected should still be >6

**Anonymity:** Always anonymous for rejected candidates. Named is fine for hired candidates.

## Retrospective Framework

**When to run:** After every closed search (filled or cancelled). Non-negotiable.

**Who attends:** Recruiter, hiring manager, lead interviewer(s). 30-45 minutes.

**Retro agenda:**

1. **Timeline review** (5 min) — actual vs target, where time was lost
2. **What worked** (10 min) — effective sourcing channels, good interview stages, strong collaborators
3. **What didn't work** (10 min) — wasted effort, poor-quality channels, process friction, calibration misses
4. **Calibration accuracy** (5 min) — did the initial persona match the hired candidate? If not, what changed?
5. **Source effectiveness** (5 min) — which channels produced candidates that advanced? Which were noise?
6. **Process friction** (5 min) — scheduling delays, interviewer availability, tool issues
7. **Lessons & action items** (5 min) — 3 specific things to do differently next time

**Output format:** Save to `roles/[role-name]/reports/retrospective.md`

## Silver Medalist Management

**Definition:** Candidates who scored "Hire" or "Strong Hire" but didn't get the offer (e.g., another candidate was selected, role was cancelled, timing didn't work).

**Identification criteria:**

- Final-round candidate with overall "Hire" recommendation
- Withdrawn candidate who expressed continued interest
- Candidate who declined offer but remained warm

**What to capture (in candidate file):**

- Date identified as silver medalist
- Strengths summary
- Roles they'd be good for
- Preferred re-engagement timing
- Last contact date
- Nurture status

**Nurture cadence:**

| Timing | Action | Channel |
|--------|--------|---------|
| Immediately | Thank them, tell them they were strong, ask permission to stay in touch | Phone/Email |
| 1 month | Share relevant company news or content | Email |
| 3 months | Check in on career status, mention any new roles | Email/LinkedIn |
| 6 months | Deeper re-engagement if new role opens | Phone |
| Trigger: new matching role | Immediate priority outreach | Phone + Email |

**Re-engagement triggers:**

- New role opens matching their profile
- Candidate posts job-seeking signals (LinkedIn status, profile updates)
- Company milestone (funding, launch, expansion) that changes the opportunity
- Their current employer has layoffs or negative news

## Onboarding Handoff

**Pre-boarding checklist (offer accepted → day 1):**

- Equipment ordered and configured
- System access provisioned (email, Slack, tools)
- Welcome email sent (from hiring manager)
- Buddy assigned and briefed
- First-week schedule created
- Team introduction prepared
- Hiring manager prep (expectations discussion, 30/60/90 alignment)

**Recruiter-to-HR handoff protocol:**

- Transfer: offer details, candidate preferences, start logistics, any special arrangements
- Warm introduction: connect new hire with HR/People partner
- Final recruiter touchpoint: "Welcome! Here's who handles what from here"

**Timeline:**

| Timing | Action | Owner |
|--------|--------|-------|
| Offer + 1 day | Welcome email from HM | Hiring Manager |
| Offer + 3 days | Equipment/access request | Recruiter → IT |
| Offer + 1 week | Buddy assignment | Hiring Manager |
| Day -5 | Pre-boarding email with logistics | HR/Recruiter |
| Day -2 | Confirm everything is ready | Recruiter |
| Day 1 | Welcome, orientation, team intro | HM + HR + Buddy |
| Day 7 | Recruiter check-in | Recruiter |
| Day 30 | QoH survey (round 1) | Recruiter |

## Cross-Role Analytics

**Metrics to track across all roles:**

| Metric | Formula | Target |
|--------|---------|--------|
| Time-to-Fill | Days from opening to offer acceptance | Role-dependent |
| Source Effectiveness | % of hires per source channel | Track trend |
| Conversion Rate (per stage) | Candidates advancing / candidates entering stage | Track by role family |
| Offer Acceptance Rate | Offers accepted / offers extended | >80% |
| Diversity Pipeline | % underrepresented at each stage | Track drop-off points |
| Cost-per-Hire | Total recruiting costs / hires | Role-dependent |
| Interview-to-Offer | Interviews conducted / offers extended | <5:1 |

**Identify systemic issues:**

- If screening pass rate is >80%, you're not sourcing aggressively enough
- If screening pass rate is <30%, persona/targeting is off
- If HM rejection rate >50%, calibration needed
- If offer decline rate >30%, comp positioning needs review
- If source X produces most hires but worst retention, reconsider

## Reference Files

You are **strongly encouraged** to read the reference files

- **`references/survey-templates.md`** — Ready-to-use survey question sets for QoH, HM experience, and candidate experience.
- **`references/retrospective-guide.md`** — Step-by-step retro facilitation guide with examples.
- **`references/onboarding-checklists.md`** — Pre-boarding checklist templates by role family.
