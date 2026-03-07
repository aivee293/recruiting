---
name: interview-design
description: "This skill should be used when the user asks to design interview process, interview stages, interview structure, assessment plan, interview flow, how many rounds, interview pipeline, what interviews to run, stage design, or needs to architect a multi-stage interview process for any role family or seniority level."
---

# Interview Design for Recruiting

## Purpose

Architect multi-stage interview processes that reliably assess must-have competencies while respecting candidate time and interviewer bandwidth. Cover the full design lifecycle: competency extraction, stage sequencing, interviewer assignment, timeline planning, and candidate communication.

## Process Design Principles

1. **Every stage must assess at least one must-have competency** from the JD/persona — no "meet and greet" rounds that don't produce signal
2. **No competency should be assessed only once** — critical competencies need 2+ signal points across different stages and interviewers to reduce single-evaluator bias
3. **Total interview time should scale with seniority** — IC roles: 3-5 hours total, Manager: 5-7 hours, Director+: 7-10 hours. Exceeding these ranges signals process bloat.
4. **Front-load deal-breakers** — assess the hardest-to-find requirements first so you fail fast on mismatches and don't waste candidate or interviewer time
5. **Candidate experience matters** — communicate the full timeline upfront, provide prep materials before each stage, minimize ghosting windows (no silence > 48 hours between stages)
6. **Each interviewer should have a distinct assessment area** — minimize overlap between interviewers. Overlap wastes interviewer bandwidth and frustrates candidates who repeat themselves.
7. **Include at least one practical/work-sample assessment for technical roles** — structured work samples are the strongest predictor of job performance (r=0.54 vs. r=0.38 for unstructured interviews)
8. **Structured > unstructured** — every stage should have a rubric, defined competencies, and advance/reject criteria before the first candidate enters the process
9. **Debrief before deciding** — interviewers submit independent written feedback before the group debrief to prevent anchoring bias
10. **Iterate the process** — after every 5 hires (or quarterly), review pass-through rates by stage, interviewer calibration, and candidate feedback to identify broken stages

## Stage Types & Formats

| Format | Best For | Duration | Competencies Assessed | Notes |
|--------|----------|----------|-----------------------|-------|
| Recruiter Screen | All roles | 30 min | Culture fit, motivation, logistics, comp expectations | Gate-keep on deal-breakers (location, comp, timeline). Not a technical assessment. |
| Hiring Manager Screen | All roles | 45-60 min | Role fit, leadership alignment, strategic thinking, career trajectory | HM evaluates "would I want this person on my team" holistically. |
| Technical Deep-Dive | Engineering, Data, DevOps | 60 min | Domain expertise, problem-solving approach, depth of knowledge | Conversational, not whiteboard. Probe depth on resume claims. |
| Behavioral Interview | All roles | 45-60 min | Soft skills, leadership, collaboration, conflict resolution, adaptability | Use STAR framework. Prepare 4-6 questions mapped to specific competencies. |
| Live Coding / Pair Programming | Engineering (IC) | 60-90 min | Coding ability, communication, real-time problem solving, debugging | Use realistic problems, allow IDE/Google. Pair format > silent whiteboard. |
| System Design | Engineering (Senior+) | 60 min | Architecture thinking, trade-off analysis, scalability, system reasoning | Calibrate scope to level — Senior: component design, Staff+: full system. |
| Take-Home Assignment | Engineering, Design, Data | 2-4 hrs | Depth of thought, code/design quality, self-direction, documentation | Respect candidate time — cap at 4hrs, pay for longer exercises. Provide clear rubric. |
| Case Study / Presentation | Product, GTM, Executive | 60 min | Strategic thinking, communication, analytical rigor, stakeholder influence | Give 48-72hrs prep time. Provide context packet. Evaluate thinking, not polish. |
| Portfolio Review | Design, Marketing, Content | 45-60 min | Design quality, decision-making rationale, craft, process thinking | Ask "why" more than "what." Focus on process and constraints, not just output. |
| Panel Interview | Senior+, Cross-functional roles | 60 min | Cross-functional alignment, executive presence, communication breadth | Max 4 panelists. Assign question areas in advance. One moderator keeps time. |
| Bar Raiser / Culture Interview | All roles (Senior+) | 45 min | Values alignment, long-term fit, raising the bar, judgment | Interviewer is outside the hiring team. Veto power on culture misalignment. |
| Reference Calls | All roles (final stage) | 30 min each | Performance validation, working style, red flag confirmation | Do 3 minimum. Ask specific behavioral questions, not "would you rehire them." |

## Competency-to-Stage Mapping Methodology

The goal is a clean mapping from what the JD/persona says you need to which interview stage will assess it.

**Step 1: Extract competencies**
Pull must-have and nice-to-have competencies from the JD and persona. Group them:

- **Technical depth** — domain knowledge, tools, languages, systems
- **Behavioral** — collaboration, communication, conflict resolution, leadership
- **Cultural** — values alignment, working style, adaptability
- **Strategic** — decision-making, prioritization, business acumen, vision

**Step 2: Assign to interview formats**
Each competency category maps naturally to certain formats:

| Category | Best assessed by |
|----------|-----------------|
| Technical depth | Technical Deep-Dive, Live Coding, System Design, Take-Home |
| Behavioral | Behavioral Interview, Panel, Reference Calls |
| Cultural | Bar Raiser, HM Screen, Recruiter Screen |
| Strategic | Case Study, System Design, HM Screen, Panel |

**Step 3: Ensure coverage**
Build a competency matrix — rows are competencies, columns are stages. Every must-have should have an "X" in at least 2 columns. If a must-have only appears once, either add it to another stage's rubric or add a stage.

**Step 4: Eliminate redundancy**
If 3+ stages assess the same competency but nothing assesses another, rebalance. Each stage should have a primary competency that is its unique contribution to the signal.

**Step 5: Validate with the hiring manager**
Walk the HM through the competency matrix before launching the process. Confirm: "Are these the right must-haves, and do you trust this process to surface them?"

## Process Templates by Role Family

High-level templates showing standard stage sequences. Detailed versions with competency mappings, interviewer guidance, and rubrics are in references.

**Engineering IC (Mid-Senior):**
Recruiter Screen → Technical Screen → System Design or Live Coding → Behavioral → HM Final

**Engineering IC (Staff+):**
Recruiter Screen → HM Screen → System Design → Technical Deep-Dive → Cross-functional Behavioral → Leadership/Bar Raiser

**Engineering Manager:**
Recruiter Screen → HM Screen → Technical Assessment (lighter) → Leadership Scenarios → Team Simulation → Skip-Level/Bar Raiser

**Product Management:**
Recruiter Screen → HM Screen → Product Case Study → Analytical/Metrics → Cross-functional Behavioral → Executive/Bar Raiser

**Design:**
Recruiter Screen → HM Screen → Portfolio Review → Design Challenge → Cross-functional Collaboration → Bar Raiser

**GTM (Sales/CS/Marketing):**
Recruiter Screen → HM Screen → Role Play/Mock Pitch → Case Study/Metrics → Cultural → Executive/Bar Raiser

**Executive/Director+:**
Recruiter Screen → HM/Exec Screen → Strategic Case → Cross-functional Panels → Board/Leadership → Reference Deep-Dives

**Data/ML Engineering:**
Recruiter Screen → Technical Screen → ML/Data Deep-Dive → System Design (data pipelines) → Behavioral → HM Final

**DevOps/SRE/Platform:**
Recruiter Screen → Technical Screen → Infrastructure Design → Incident Response Scenario → Behavioral → HM Final

For complete stage-by-stage breakdowns, competency matrices, and interviewer guidance, see **`references/process-templates.md`**.

## Interviewer Assignment Principles

1. **Match interviewer expertise to assessment area** — the system design interviewer should be a strong systems thinker, the behavioral interviewer should be trained in structured behavioral interviewing
2. **Include at least one peer-level interviewer** — candidates need to assess "would I want to work with these people" and peers give the most realistic signal on day-to-day collaboration
3. **Include at least one cross-functional interviewer for Senior+ roles** — tests communication across team boundaries and reduces echo-chamber hiring
4. **Assign a trained bar raiser for Director+ hires** — someone outside the hiring chain with veto power on culture fit and bar-raising
5. **Never have the same person conduct back-to-back interviews with one candidate** — fatigue and anchoring bias compound
6. **Consider diversity in the interview panel** — diverse panels reduce groupthink, signal inclusion to candidates, and produce better hiring decisions
7. **Train interviewers before they interview** — shadow 2-3 interviews, then reverse-shadow 2-3 before going solo. No untrained interviewers on live candidates.
8. **Limit interviewer load** — no one should conduct more than 4-5 interviews per week. Interviewer fatigue degrades signal quality.

## Timeline & Logistics

**Target completion times (first screen to offer):**

| Role Level | Target Timeline | Max Acceptable |
|------------|----------------|----------------|
| IC (Mid) | 2 weeks | 3 weeks |
| IC (Senior) | 2 weeks | 3 weeks |
| IC (Staff+) | 2-3 weeks | 4 weeks |
| Manager | 3 weeks | 4 weeks |
| Director+ | 3-4 weeks | 5 weeks |
| Executive | 4-6 weeks | 8 weeks |

**Scheduling rules:**
- Schedule within 48 hours of each advancement decision
- Offer same-week or next-week slots for every stage
- If a candidate is in active processes elsewhere, compress the timeline — ask directly
- For on-site days, batch 3-4 interviews with breaks between (not back-to-back-to-back)

**Candidate communication touchpoints:**
- After application/sourcing: process overview with stage count, estimated timeline, and what to expect
- Before each stage: interviewer name and role, topic areas, any prep materials, logistics (link, location, duration)
- Between stages: advancement decision within 48 hours, next stage scheduling immediate
- After final: decision within 48-72 hours, detailed feedback if rejected (at minimum: where they were strong and where gaps existed)

**Debrief protocol:**
- All interviewers submit written scorecards within 24 hours of their interview
- Group debrief within 24-48 hours of the final interview
- Scorecards submitted before debrief (prevent anchoring)
- Hiring manager makes the final call, but must address dissenting opinions explicitly

## Output Format

**Single source of truth rule:** `interview-plan.md` is the architect's view: it describes WHAT each stage assesses, WHY, and the advance/reject criteria. It does NOT contain interview questions, rubrics, or detailed evaluation criteria. Those belong in the operator files:
- `screening-guide.md` for the recruiter screen (Stage 1 typically)
- `take-home-exercise.md` for async exercises
- `scorecards.md` for all other stages
- `teamtailor-setup.md` for ATS kit configuration

Each stage in `interview-plan.md` should list competencies assessed and then POINT to the relevant operator file. Never duplicate questions across files; every update should only require changing one file.

When generating an interview plan for a role, produce this structure and save to `roles/[role-name]/interview-plan.md`:

```markdown
# Interview Plan: [Role Title]
**Created:** [Date] | **Updated:** [Date]
**Role:** [Title] | **Level:** [Seniority]
**Total interview time:** [X hours across Y stages]
**Target timeline:** [X weeks recruiter screen to offer]

## Process Overview
| Stage | Format | Interviewer(s) | Competencies Assessed | Duration | Advance Criteria |
|-------|--------|----------------|----------------------|----------|-----------------|

## Competency Coverage Matrix
| Competency (from JD/Persona) | Priority | Stage 1 | Stage 2 | Stage 3 | ... |
|------------------------------|----------|---------|---------|---------|-----|

## Stage Details
### Stage 1: [Name]
**Format:** [Type] | **Duration:** [X min] | **Interviewer:** [Name/Role]
**Purpose:** [What this stage determines]
**Competencies assessed:** [List]
**Full questions, rubrics, and evaluation criteria:** See [`scorecards.md`](scorecards.md), Stage N section. / See [`screening-guide.md`](screening-guide.md).
**Advance if:** [Criteria]
**Reject if:** [Criteria]

[Repeat for each stage]

## Candidate Communication Plan
- After application/sourcing: [What to send]
- Before each stage: [Prep materials]
- Between stages: [Timeline communication]
- After final: [Decision timeline]

## Logistics
- **Scheduling coordinator:** [Name]
- **Interview format:** [Remote/On-site/Hybrid]
- **Tools:** [Video platform, whiteboard tool, coding platform]
```

## Reference Files

You are **stongly encouraged** to read the reference files

- **`references/format-library.md`** — Detailed descriptions of each interview format with strengths, weaknesses, when to use, when to avoid, and implementation tips.
- **`references/process-templates.md`** — Complete process templates by role family and seniority level with competency mappings, timelines, and interviewer assignment guidance.
