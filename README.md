# Recruiting Toolkit

A talent sourcing and recruiting orchestration system built on [Claude Code](https://docs.anthropic.com/en/docs/claude-code). 11 specialized AI agents and 16 skills produce hiring deliverables across the full candidate pipeline: job descriptions, candidate personas, Boolean search strings, outreach sequences, interview scorecards, offer strategies, and post-close retrospectives. All output is markdown or self-contained HTML. No build tools, no dependencies.

## How It Works

The toolkit divides recruiting into two agent domains, split at the pipeline handoff point:

```
 SOURCING DOMAIN                          TALENT PARTNER DOMAIN
 Identified → Interested                  Screening → Offer → Close
 ┌──────────────────────────┐             ┌────────────────────────────────┐
 │ senior-sourcing-specialist│             │ senior-talent-partner          │
 │ persona-builder           │             │ interview-architect            │
 │ lead-researcher           │      ──►    │ evaluation-specialist          │
 │ outreach-specialist       │             │ offer-strategist               │
 │                           │             │ hiring-quality-analyst         │
 └──────────────────────────┘             └────────────────────────────────┘

 Pipeline stages:
 Identified → Contacted → Responded → Interested → Screening → Submitted to HM → Interview → Offer
 ◄──────────── sourcing ──────────────►  ◄──────────── talent partner ─────────────────────────────►

 Shared agents: market-analyst · lead-researcher · report-generator
```

Your Claude Code session is the orchestrator. It launches agents directly, runs independent agents in parallel, and chains dependent agents sequentially. Agents cannot spawn other agents — the main session manages all coordination.

## Repository Structure

```
recruiting/
├── .claude/
│   ├── agents/              # 11 agent definitions (YAML frontmatter + markdown body)
│   ├── skills/              # 16 skill modules (each has SKILL.md + references/)
│   ├── rules/               # Orchestration rules, anti-AI-slop rules
│   ├── templates/           # brief.md intake template
│   ├── data/                # Shared research: companies/, market/, sector-companies.md
│   └── settings.local.json  # Claude Code environment config (gitignored)
├── roles/                   # Per-role work products (created per search)
├── reports/                 # Multi-role reports and dashboards
├── CLAUDE.md                # Project architecture and agent instructions
├── LICENSE                  # MIT
└── .gitignore
```

Each role gets its own directory under `roles/` with a standard set of deliverables:

```
roles/[role-name]/
├── brief.md                 # Intake notes, pipeline tracking, search log
├── jd.md                    # Job description
├── persona.md               # Target candidate persona
├── sourcing-plan.md         # Channel strategy and timeline
├── talent-map.md            # Target companies and pool sizing
├── search-strings.md        # Ready-to-paste Boolean search strings
├── outreach-sequence.md     # Multi-touch outreach cadence
├── interview-plan.md        # Process overview, stage breakdown, competency matrix
├── scorecards.md            # Per-stage scorecards with rubrics
├── screening-guide.md       # Phone screen script with questions
├── candidate-evaluation.md  # Cross-candidate comparison and recommendation
├── offer-brief.md           # Package, negotiation strategy, closing plan
├── quality-surveys.md       # Quality of hire and experience surveys
├── onboarding-checklist.md  # Pre-boarding timeline and welcome comms
├── candidates/              # Individual candidate dossiers
└── reports/                 # Pipeline updates, dashboards, retrospectives
```

## Agents

| Agent | Domain | What It Does |
|-------|--------|-------------|
| `senior-sourcing-specialist` | Sourcing | JD writing, Boolean searches, talent mapping, sourcing plans |
| `persona-builder` | Sourcing | Builds candidate personas from JDs and stakeholder context |
| `outreach-specialist` | Sourcing | Multi-channel outreach sequences, personalized messages, response handling |
| `senior-talent-partner` | Talent Partner | Intake facilitation, HM calibration, screening, pipeline coordination |
| `interview-architect` | Talent Partner | Interview process design, scorecards, screening guides, question banks |
| `evaluation-specialist` | Talent Partner | Transcript scoring, feedback synthesis, candidate comparison, debrief |
| `offer-strategist` | Talent Partner | Offer construction, negotiation tactics, counter-offer defense |
| `hiring-quality-analyst` | Talent Partner | QoH surveys, retrospectives, silver medalists, onboarding handoff |
| `market-analyst` | Shared | Compensation benchmarks, talent supply/demand, hiring trends |
| `lead-researcher` | Shared | Individual candidate deep-dives, background research, fit assessment |
| `report-generator` | Shared | Stakeholder reports, HTML dashboards with Chart.js, pipeline updates |

Agents trigger automatically based on what you ask. Requesting a JD launches the sourcing specialist. Pasting an interview transcript launches the evaluation specialist. See `.claude/rules/agents.md` for the full auto-trigger table.

## Skills

Skills are domain knowledge modules that auto-inject into agents via YAML frontmatter. You don't call them manually — each agent loads the skills it needs at startup.

| Skill | Purpose |
|-------|---------|
| `jd-writing` | Job description creation, rewriting, and improvement |
| `boolean-search` | Platform-specific search strings (LinkedIn, X-Ray, GitHub, Stack Overflow) |
| `candidate-outreach` | Outreach frameworks, channel playbooks, sequence templates |
| `talent-mapping` | Concentric circle company mapping, pool sizing |
| `market-research` | Compensation data sources, report templates |
| `persona-research` | Candidate motivation frameworks, persona templates |
| `sourcing-plan` | Full sourcing strategy generation |
| `interview-design` | Interview process architecture, stage types, competency mapping |
| `interview-kit` | Scorecards, rubrics, question banks, screening scripts |
| `candidate-evaluation` | Transcript scoring, feedback synthesis, comparison matrices |
| `offer-negotiation` | Offer construction, negotiation tactics, closing strategies |
| `candidate-comms` | Stage-based candidate communications, rejection frameworks |
| `hiring-quality` | QoH surveys, retrospectives, onboarding checklists |
| `stakeholder-reporting` | Report and dashboard templates |
| `stop-slop` | AI writing pattern removal for professional prose |
| `skill-creator` | Guide for creating new skills |

## Getting Started

### Prerequisites

- [Claude Code CLI](https://docs.anthropic.com/en/docs/claude-code) with an active subscription or API key or Claude Desktop

That's it. No npm, pip, or build step.

### Setup

1. Clone the repository:

```bash
git clone <repo-url> && cd recruiting
```

2. Create your company context file:

```bash
cp .claude/talent-sourcing-template.local.md .claude/talent-sourcing.local.md
```

Edit `.claude/talent-sourcing.local.md` with your company details — name, industry, locations, EVP, target companies, and compensation philosophy. This file is gitignored.

3. Open Claude Code in the repo directory:

```bash
claude
```

4. Start working. Agents activate automatically based on your request:

```
> We need to hire a Senior Data Engineer for the Berlin office.

# This triggers:
# 1. senior-sourcing-specialist → writes the JD
# 2. persona-builder + market-analyst → run in parallel
# 3. senior-sourcing-specialist → search strings, talent map, sourcing plan
# 4. lead-researcher → candidate deep-dives
# 5. outreach-specialist → outreach sequences
```

## Role Lifecycle

Each role's status is tracked in `brief.md` YAML frontmatter. Agents check this before starting work.

```
intake → active → paused | on-hold → offer → closed-filled | closed-cancelled
```

| Status | Sourcing Agents | Talent Partner Agents |
|--------|----------------|----------------------|
| `intake` | Persona-builder only | Intake facilitation |
| `active` | All available | All available |
| `paused` / `on-hold` | No new sourcing | No new interviews |
| `offer` | No new sourcing | Offer strategist, onboarding |
| `closed-filled` | None | Retrospective, QoH surveys, silver medalists |
| `closed-cancelled` | None | Retrospective only |

## Pipeline Stages

Pipeline state lives in each role's `brief.md`. Both agents and the user update it.

| Stage | Definition |
|-------|-----------|
| Identified | Candidate found and added to target list |
| Contacted | Outreach sent (any channel) |
| Responded | Candidate replied (positive, negative, or neutral) |
| Interested | Positive response — willing to explore |
| Screening | Recruiter screen completed |
| Submitted to HM | Profile sent to hiring manager for review |
| Interview | In interview process |
| Offer | Offer extended |

## Configuration

### Company Context

`.claude/talent-sourcing.local.md` stores your company-specific settings as YAML frontmatter. This file is gitignored so each user maintains their own. It includes:

- Company name, industry, and locations
- Employee value proposition (EVP)
- Preferred sourcing channels and tools
- Target companies (top 20 for Boolean generation)
- Compensation philosophy
- Reporting preferences

### Shared Research Data

`.claude/data/` stores research not tied to a specific role:

- `sector-companies.md` — company names from your sector (human input, seed for agents)
- `companies/` — agent-researched company intelligence profiles
- `market/` — compensation and talent supply/demand data by function, geography, and year

## ATS Integration

Teamtailor is the ATS. No API is available — integration works through CSV import:

1. Export candidates from Teamtailor as CSV
2. Drop the file into `roles/[role-name]/`
3. An agent parses the CSV and updates the pipeline table in `brief.md`

Delete or archive the CSV after import.

## License

MIT — see [LICENSE](LICENSE). Copyright 2026 Carlo Pezzuto.
