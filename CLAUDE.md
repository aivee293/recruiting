# Philosophy

Agent-first design, parallel execution, plan before action.

**Key Principles:**

1. **Agent-First**: Delegate recruiting tasks to specialized agents (skills auto-load via frontmatter)
2. **Parallel Execution**: Use Task tool with multiple agents when possible for independent operations
3. **Plan Before Execute**: Use Plan Mode for complex operations

---

## What This Is

A **talent sourcing and recruiting toolkit** — agents and skills that produce sourcing deliverables (personas, talent maps, Boolean search strings, outreach sequences, stakeholder reports) and recruiting deliverables (interview processes, scorecards, candidate evaluations, offer strategies, quality measurement, onboarding handoff). All output is markdown or self-contained HTML. Primary sourcing platforms: LinkedIn, GitHub, Stack Overflow, Google X-Ray.

---

## Architecture

All agent/skill catalogs, trigger rules, parallel execution patterns, and dependency ordering: `.claude/rules/agents.md`

### Work Product Directory Structure

All deliverables are saved to a role-based directory structure (created on first use):

```directory
roles/[role-name]/
├── brief.md               ← intake notes, search log, living context (human + agent)
├── jd.md                  ← job description
├── sourcing-plan.md       ← channel strategy & timeline
├── talent-map.md          ← target companies & pool sizing
├── persona.md             ← candidate persona
├── search-strings.md      ← ready-to-paste Boolean strings
├── outreach-sequence.md   ← multi-touch outreach cadence
├── interview-plan.md      ← process overview, stage breakdown, competency matrix
├── scorecards.md          ← one scorecard per stage with competency rubrics
├── screening-guide.md     ← phone screen script with questions and evaluation
├── candidate-evaluation.md ← cross-candidate comparison and hiring recommendation
├── offer-brief.md         ← proposed package, negotiation strategy, closing plan
├── quality-surveys.md     ← QoH, HM experience, candidate experience survey sets
├── onboarding-checklist.md ← pre-boarding checklist, timeline, welcome comms
├── candidates/            ← individual candidate research (dossiers)
└── reports/               ← stakeholder deliverables
    ├── pipeline-week-NN.md          ← e.g., pipeline-week-06.md
    ├── market-insights-YYYY-MM.md   ← e.g., market-insights-2026-02.md
    ├── dashboard.html               ← self-contained Chart.js dashboard (updated in place)
    └── retrospective.md             ← post-search retrospective with lessons learned
```

Brief template: `.claude/templates/brief.md` — copy to `roles/[role-name]/brief.md` per role.

Multi-role reports go to a top-level `reports/` directory.

### Shared Data

`.claude/data/` stores shared seed data and agent research not tied to a specific role:

```directory
.claude/data/
├── sector-companies.md                    ← human input (company names)
├── companies/                             ← company profiles (agent-researched)
│   └── [company-name].md                  ← e.g., crowdstrike.md
└── market/                                ← market research (agent-researched)
    └── [function]-[geography]-[year].md   ← e.g., data-engineer-eu-2026.md
```

- **`sector-companies.md`** — company names scraped from the sector (human input). Agents use as seed.
- **`companies/`** — company intelligence profiles. Naming: `[company-name].md` (lowercase, hyphenated).
- **`market/`** — compensation, talent supply/demand, competitive landscape. Naming: `[function]-[geography]-[year].md`.

**Write rule:** Agents propose saving to `data/`; user confirms. Agents always check `data/` for prior research before starting new work.

The YAML `target_companies` in `talent-sourcing.local.md` is the curated top-20 for quick Boolean generation. `data/` is the full directory.

### Role Lifecycle

Each role's status is tracked in `brief.md` YAML frontmatter (`status` field). This is the source of truth.

```
intake → active → paused | on-hold → offer → closed-filled | closed-cancelled
```

| Status | Meaning | Sourcing agents | Talent partner agents |
|--------|---------|----------------|----------------------|
| `intake` | Gathering requirements, building brief | Persona-builder may run. No sourcing. | senior-talent-partner available for intake facilitation. |
| `active` | Actively sourcing and engaging | All sourcing agents available. | All talent partner agents available (interview-architect, evaluation-specialist, etc.). |
| `paused` | Temporarily stopped (timing, budget) | No new sourcing. Reports still available. | No new interviews. Existing evaluations still available. |
| `on-hold` | Blocked by external dependency | Same as paused. | Same as paused. |
| `offer` | Candidate in offer stage | No new sourcing. Outreach-specialist available for closing. | offer-strategist and hiring-quality-analyst (onboarding checklist) available. |
| `closed-filled` | Role filled | No agent work. | hiring-quality-analyst: retrospective, QoH surveys, silver medalists, onboarding handoff. report-generator: final reports. |
| `closed-cancelled` | Role cancelled | No agent work. | hiring-quality-analyst: retrospective only. |

**Creating a new role directory:**

```bash
mkdir -p roles/[role-name]/candidates roles/[role-name]/reports
```

Then copy the brief template: `.claude/templates/brief.md` → `roles/[role-name]/brief.md`. Fill during intake meeting.

**Agents must check `status`** in `brief.md` before starting work. Do not source for paused, on-hold, or closed roles unless the user explicitly overrides.

### Pipeline Tracking

Pipeline state lives in each role's `brief.md` under the **Current Status** section. The pipeline table there is the source of truth — agents and the user both update it.

**Pipeline stages (in order):**

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

**Updating pipeline:**

- When you tell an agent "I contacted 5 candidates" or "3 responded," the agent updates the pipeline table in `brief.md`.
- After generating outreach sequences or completing candidate research, agents remind the user to update counts once outreach is sent.
- Track conversion rates between stages to identify bottlenecks (report-generator uses these for dashboards).
- Record the date of each update in the Search Log section of the brief.

**Pipeline ownership:**

| Stage Range | Orchestrator | Agents Available |
|-------------|-------------|-----------------|
| Identified → Interested | senior-sourcing-specialist | persona-builder, outreach-specialist, lead-researcher |
| Screening → Offer | senior-talent-partner | interview-architect, evaluation-specialist, offer-strategist |
| closed-filled / closed-cancelled | senior-talent-partner | hiring-quality-analyst, report-generator |

**Pipeline health signals (sourcing):**

- Response rate < 10% → review messaging (outreach-specialist)
- Interested rate < 30% of responses → review targeting (persona-builder)
- No candidates past Screening after 3 weeks → escalate to hiring manager

**Pipeline health signals (talent partner):**

- Time-in-stage > 5 days at Screening → candidate may lose interest — accelerate process
- HM rejection rate > 50% at Submitted to HM → calibration needed — schedule HM alignment session
- Offer acceptance rate < 70% → review comp positioning (offer-strategist + market-analyst)
- No decision within 48h of final round → schedule debrief immediately

### ATS Integration (Teamtailor — Import Only)

Teamtailor is the ATS. No API is available. Integration works via CSV import into the toolkit.

**Import workflow:**

1. Export candidates from Teamtailor as CSV (candidate bank or per-job export with custom columns)
2. Drop the CSV file into `roles/[role-name]/` (e.g., `roles/*/teamtailor-export.csv`)
3. Agent parses the CSV and:
   - Updates the pipeline table in `brief.md` with current counts per stage
   - Optionally creates candidate stub files in `candidates/` for further research

**Stage mapping** (Teamtailor → toolkit pipeline):

| Teamtailor Stage Type | Toolkit Pipeline Stage |
|----------------------|----------------------|
| New | Identified |
| In progress | Contacted / Screening (depends on sub-stage) |
| Hired | Offer (accepted) |
| Rejected | — (not tracked in pipeline) |

Teamtailor uses customizable sub-stages within stage types. When parsing a CSV, map the actual column values to the closest toolkit stage. If the mapping is ambiguous, ask the user.

**Recommended Teamtailor export columns:** Name, Email, Phone, LinkedIn, Job title, Stage, Source, Tags, Created date, Last activity date.

**After import:** Delete or archive the CSV — don't leave raw exports in the role directory long-term.

---

## Agent & Skill Delegation

For recruiting and sourcing tasks, the **main conversation orchestrates** agent launches directly. Subagents cannot spawn other subagents (platform constraint). Skills are auto-injected into each agent via its YAML `skills:` frontmatter — do NOT instruct agents to call `Skill()`.

Two domain expert groups divide the pipeline:

- **Sourcing domain** (Identified → Interested): `senior-sourcing-specialist`, `persona-builder`, `market-analyst`, `lead-researcher`, `outreach-specialist`
- **Talent partner domain** (Screening → Offer → closed): `senior-talent-partner`, `interview-architect`, `evaluation-specialist`, `offer-strategist`, `hiring-quality-analyst`
- **Shared agents**: `market-analyst`, `lead-researcher`, `report-generator` (available to either domain)

The main conversation chains agents phase by phase (sequential for dependent ops, parallel for independent ops). See `.claude/rules/agents.md` for the full workflow phases, dependency table, and auto-trigger rules.

**Scope gate:** Non-recruiting tasks (file operations, configuration questions, general discussion) skip agent orchestration entirely. Only activate recruiting agents when the task involves hiring, candidates, roles, or recruiting deliverables.

---

### Company Configuration

`.claude/talent-sourcing.local.md` stores per-user company context (YAML frontmatter): company name, industry, locations, EVP, preferred sourcing channels, compensation philosophy, target companies, and reporting preferences. This file is gitignored (`.local.md`). Agents read this file to tailor their output.

### Fallback Behavior

When web search is unavailable or returns poor results:

- Note the gap explicitly in deliverables: "market data unavailable — estimates based on [source/reasoning]"
- Proceed with available information rather than blocking the workflow
- Never fabricate market data, compensation figures, or candidate details
- Flag sections that need verification when web access is restored

---

## Communication

**Voice:**

- Think out loud through problems — show the reasoning chain that led to a decision
- Express uncertainty directly: "I think", "I'm not sure about this", "my best guess"
- State trade-offs: "I see three approaches... going with option 2 because..."
- Flag risks proactively: "Watch out for edge case X"
- Suggest multiple approaches when the choice isn't obvious
- Admit knowledge gaps: "Let me research that"

**Brevity boundary:** Thinking out loud means showing *why* you chose an approach, not explaining what the approach is. If you'd skip the explanation talking to a peer recruiter, skip it here. Show your reasoning, not your knowledge.

**Prohibited:**

- Social validation: "You're absolutely right!", "Great question!"
- Weasel-word stacking: "might potentially perhaps"
- Agreement phrases that consume tokens without value
- Emotional acknowledgments or conversational pleasantries
