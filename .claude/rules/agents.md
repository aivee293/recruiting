# Agent Orchestration

> **Platform constraint:** Subagents cannot spawn other subagents. The main conversation (Claude Code session) is the orchestrator — it launches agents directly, chains results between phases, and runs independent agents in parallel. "Orchestrator" agents (senior-sourcing-specialist, senior-talent-partner) are domain experts that do hands-on work; they do NOT spawn sub-agents at runtime.
>
> **Skills are auto-injected via frontmatter.** Each agent's `skills:` field in its YAML frontmatter causes the full skill content to be loaded into the agent's context at startup. Do NOT instruct agents to call `Skill()` — it's redundant.

## Available Agents (launch from main conversation)

| Agent | Purpose | When to Use |
| ----- | ------- | ----------- |
| senior-sourcing-specialist | Domain expert — sourcing strategy, Boolean searches, talent mapping, JD writing, hands-on sourcing work | Any single-phase sourcing task (JD, search strings, talent map, sourcing plan) |
| lead-researcher | Individual candidate deep-dives, dossiers, fit assessment | Candidate research, background checks, shortlist comparison |
| outreach-specialist | Multi-channel outreach sequences, personalized messages, response handling | Writing outreach, follow-ups, nurture sequences, handling replies |
| persona-builder | Candidate persona development from JDs and stakeholder context | New role kickoff, sourcing misalignment, persona refinement |
| market-analyst | Compensation benchmarks, talent supply/demand, hiring trends | Salary questions, market sizing, headcount justification |
| report-generator | Stakeholder reports, HTML dashboards, pipeline updates | Weekly updates, hiring manager reports, visual dashboards |
| senior-talent-partner | Domain expert — intake facilitation, HM calibration, pipeline coordination, interview/offer strategy | Any single-phase mid-to-bottom funnel task (intake, calibration, screening, pipeline updates) |
| interview-architect | Interview process design, scorecards, screening guides, question banks | Interview setup, scorecard creation, screening guide development |
| evaluation-specialist | Transcript scoring, feedback synthesis, candidate comparison, debrief facilitation | Transcript pasted for scoring, after interviews, hiring decisions, candidate comparison |
| offer-strategist | Offer construction, negotiation strategy, counter-offer defense, closing | Offer stage, negotiation, closing |
| hiring-quality-analyst | QoH surveys, retrospectives, silver medalists, onboarding handoff | Post-close activities, quality measurement, onboarding |

## Available Skills (context injection via Skill tool)

| Skill | Purpose | When to Use |
| ----- | ------- | ----------- |
| jd-writing | Job description writing, rewriting, and improvement | Creating or improving JDs for any role family |
| boolean-search | Platform-specific search string construction | Building LinkedIn, X-Ray, GitHub, Stack Overflow queries |
| candidate-outreach | Outreach frameworks, channel playbooks, sequence templates | Before writing any outreach content |
| talent-mapping | Concentric circle company mapping, pool sizing | Identifying target companies and talent pools |
| market-research | Compensation data sources, report templates | Market analysis, comp benchmarking |
| persona-research | Candidate motivation frameworks, persona templates | Building or refining candidate personas |
| sourcing-plan | Full sourcing strategy generation | Creating a new sourcing plan for a role |
| stakeholder-reporting | Report and dashboard templates | Before generating reports or dashboards |
| stop-slop | AI writing pattern removal | Editing any user-facing prose |
| interview-design | Interview process architecture, stage types, competency mapping | Designing interview processes for any role |
| interview-kit | Scorecards, rubrics, question banks, screening scripts, calibration | Building interview evaluation tools |
| candidate-evaluation | Transcript scoring, feedback synthesis, comparison matrices, debrief frameworks, bias mitigation | Scoring transcripts, evaluating and comparing candidates |
| offer-negotiation | Offer construction, negotiation tactics, counter-offer defense, closing | Building and negotiating offers |
| candidate-comms | Stage-based candidate communications, rejection frameworks, offer scripts | Any candidate communication during interview process |
| hiring-quality | QoH surveys, HM/candidate experience surveys, retrospectives, onboarding | Post-close quality measurement and improvement |

## When to Launch an Agent vs. Use a Skill Inline

Each agent starts with a fresh context and loads 2–5 skills (roughly 15–50 KB of instructions) before doing any work. That cost is worth paying for multi-step deliverables, not for quick questions.

**Handle inline with the matching skill (no agent):**

- Single, self-contained requests: rewrite an InMail, tweak one Boolean string, answer a comp question from existing `data/market/` research, draft one rejection email, review a JD paragraph
- Follow-up edits to a deliverable that already exists in `roles/[role-name]/`
- Questions about the toolkit itself (scope gate — see CLAUDE.md)

**Launch an agent when the request produces or substantially rewrites a file deliverable**, needs fresh web research, or is one phase of a multi-phase workflow:

| Request | Agent | Precondition |
| ------- | ----- | ------------ |
| New role opened, JD requested | senior-sourcing-specialist (jd-writing) | brief.md or HM requirements available |
| Persona needed for a new role | persona-builder | JD exists |
| Full sourcing plan, talent map, or search-string set | senior-sourcing-specialist | persona.md exists |
| Candidate dossier on a named person | lead-researcher | Role exists and research purpose is recruiting (see lead-researcher privacy rules) |
| Outreach sequence for a role | outreach-specialist | persona.md exists |
| New market/comp research (no recent file in `data/market/`) | market-analyst | — |
| Pipeline report or dashboard | report-generator | Pipeline data exists in brief.md |
| Interview process design | interview-architect (with senior-talent-partner for HM calibration) | JD + persona exist |
| Scorecards or screening guide | interview-architect | JD + persona exist |
| Interview transcript to score | evaluation-specialist | scorecards.md exists (otherwise score against JD and say so) |
| Candidate comparison or debrief | evaluation-specialist | Feedback for 2+ candidates |
| Offer package or negotiation plan | offer-strategist | Evaluation decision made |
| Retrospective, QoH surveys, silver medalists, onboarding checklist | hiring-quality-analyst | Role status is closed-* or offer accepted |

**Status changes are user-reported.** The toolkit cannot observe Teamtailor, inboxes, or calendars. When the user reports a status change ("Maria accepted", "role is closed", "3 candidates moved to screening"), update `brief.md` and **suggest** the relevant next step (e.g. "Want me to run the retrospective and silver-medalist list?") rather than launching agents unprompted.

When unsure whether a request warrants an agent, do the small version inline and offer the full deliverable.

## Routing Rule

Pipeline stage determines which domain expert or specialist to launch:
- **Identified → Interested:** sourcing-domain agents (`senior-sourcing-specialist`, `persona-builder`, `market-analyst`, `lead-researcher`, `outreach-specialist`)
- **Screening → Offer:** talent-partner-domain agents (`senior-talent-partner`, `interview-architect`, `evaluation-specialist`, `offer-strategist`)
- **closed-filled / closed-cancelled:** `hiring-quality-analyst`
- **Shared agents** (`market-analyst`, `lead-researcher`, `report-generator`) can be launched from either domain

When a request doesn't clearly map to a pipeline stage, use context: sourcing/search/outreach tasks → sourcing-domain agents; interview/evaluation/offer/close tasks → talent-partner-domain agents.

## Parallel Task Execution

When the main conversation launches more than one agent, run independent ones in parallel (one message, multiple Task calls):

```markdown
# GOOD: Main conversation launches independent agents in parallel

Main conversation launches in one message:
1. Task(persona-builder): Build candidate persona from JD
2. Task(market-analyst): Research compensation and talent supply
(both need only the JD — no dependency between them)

# GOOD: Parallel research on shortlisted candidates

Main conversation launches N lead-researchers in parallel:
1. Task(lead-researcher): Research candidate A
2. Task(lead-researcher): Research candidate B
3. Task(lead-researcher): Research candidate C

# GOOD: Parallel interview setup

Main conversation launches in one message:
1. Task(interview-architect): Design interview process and scorecards
2. Task(market-analyst): Research compensation benchmarks for offer planning
(both need only the JD + persona — no dependency between them)

# BAD: Sequential when independent

Building persona, THEN researching market, THEN mapping companies
→ Persona and market research have no dependency — launch together

# BAD: Offer before evaluation

Launching offer-strategist before evaluation-specialist has produced candidate-evaluation.md
→ Offer depends on evaluation decision — run sequentially
```

## Workflow Phases (Main Conversation Orchestrates)

The main conversation chains agents phase by phase. Each agent receives its required inputs via the prompt. Agents with skills in their YAML frontmatter get those skills auto-injected — no `Skill()` calls needed.

**Sourcing domain:**

```tree
Main conversation
    Phase 0 → senior-sourcing-specialist  (JD writing — needs brief)
    Phase 1 → persona-builder ║ market-analyst  (parallel — both need brief + JD)
    Phase 2 → senior-sourcing-specialist  (search strings, talent map, sourcing plan — needs persona)
    Phase 3 → lead-researcher × N  (parallel — needs candidate names from Phase 2)
    Phase 4 → outreach-specialist  (needs persona + dossiers)
    Phase 5 → report-generator  (needs all artifacts)
```

**Talent partner domain:**

```tree
Main conversation
    Phase 0 → senior-talent-partner  (intake facilitation — needs brief)
    Phase 1 → interview-architect ║ market-analyst  (parallel — needs brief + JD + persona)
    Phase 2 → senior-talent-partner  (screening loop — iterative per candidate)
              → evaluation-specialist  (after each round's feedback)
    Phase 3 → offer-strategist  (needs candidate-evaluation.md + market data)
    Phase 4 → report-generator  (needs all artifacts)
    Phase 5 → hiring-quality-analyst  (post-close — retro, surveys, onboarding)
```

## Dependency Ordering

When an agent's input depends on another agent's output, run them sequentially. Wait for the dependency to complete before launching the dependent agent. The main conversation manages this — check if the required file exists in `roles/[role-name]/` before launching the next phase.

**Key dependencies:**

| Delegated Agent | Requires | Produces |
| --------------- | -------- | -------- |
| senior-sourcing-specialist (jd-writing) | brief.md or HM requirements | jd.md |
| persona-builder | brief.md + JD | persona.md |
| market-analyst | brief.md + JD | market data |
| senior-sourcing-specialist (direct) | persona.md | search-strings.md, talent-map.md, sourcing-plan.md |
| lead-researcher | candidate names | candidates/*.md |
| outreach-specialist | persona.md + candidates/*.md | outreach-sequence.md |
| report-generator | all role artifacts | reports/ |
| interview-architect | brief.md + JD + persona | interview-plan.md, scorecards.md, screening-guide.md |
| evaluation-specialist | candidates/*.md + scorecards.md + interview-plan.md | candidate-evaluation.md |
| offer-strategist | candidate-evaluation.md + market data + candidates/[name].md | offer-brief.md |
| hiring-quality-analyst | all role artifacts (post-close) | retrospective.md, quality-surveys.md, onboarding-checklist.md |

**Rules:**

- Main conversation orchestrates all agent launches — agents cannot spawn other agents (platform constraint)
- Skills are auto-injected via each agent's YAML `skills:` frontmatter — do NOT instruct agents to call `Skill()`
- Never launch an agent before its required inputs exist — check the dependency table above
- When in doubt, check if the file it needs is already in `roles/[role-name]/`
- Check `brief.md` YAML `status` field before starting work — do not source for paused, on-hold, or closed roles
- After actions that change pipeline counts (outreach sent, responses received, candidates screened), update the pipeline table in `brief.md`
- Use the routing rule: Identified→Interested → sourcing-domain agents; Screening→Offer → talent-partner-domain agents; post-close → hiring-quality-analyst
