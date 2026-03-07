---
name: candidate-evaluation
description: "This skill should be used when the user asks to evaluate candidates, compare candidates, debrief, hiring decision, candidate comparison, synthesize feedback, candidate ranking, who should we hire, summarize interviews, interview debrief, candidate assessment, score this transcript, metaview transcript, score this screen, score this interview, rate this candidate, transcript evaluation, interview scoring, or needs to aggregate interview feedback, score an interview transcript against a scorecard, facilitate hiring decisions, or compare candidates against each other."
---

# Candidate Evaluation for Recruiting

## Purpose

Synthesize multi-interviewer feedback into evidence-based hiring recommendations. Reduce bias, surface gaps, and produce structured candidate comparisons that hiring managers can act on.

## Transcript Scoring (Single Candidate, Single Stage)

When the user pastes a Metaview transcript (or any interview transcript), produce two files:

### Required Inputs

1. **Transcript** (pasted by user or saved to file)
2. **Stage scorecard**: `roles/[role-name]/scorecards.md` (the rubric with questions, probes, green/red flags)
3. **Teamtailor kit setup**: `roles/[role-name]/teamtailor-setup.md` (kit structure, question names, instruction text)
4. **Candidate context** (if available): `roles/[role-name]/candidates/[name]-outreach.md` or dossier

### Output 1: Teamtailor Scorecard (`candidates/[name]-teamtailor-scorecard.md`)

Maps 1:1 to the interview kit's questions and skills/traits. This is what gets entered into Teamtailor.

**Structure (per question in kit order):**

```markdown
## Q[N]: [Question as asked or as written in the kit]

**[Candidate]'s answer:**
[Summarize what was actually said. Include key quotes.]

**Probe: [Probe text from scorecard]**
[Was it asked? What was the answer? If not asked, note "Not asked" and the impact.]

**Note:** [Analytical note: what this tells us, what's missing, how it compares to the rubric's green/red flags]
```

**After all questions, include:**

- **Logistics section** (comp, availability, notice period, other processes, language)
- **Candidate questions section** (what they asked, assessment of quality)
- **Culture value ratings table** (each trait: rating + key evidence)
- **Summary table for Teamtailor entry** (one-line per question/competency with rating + note)
- **Teamtailor Comment** (blockquote summary for pasting into the kit's comment section on the candidate card)

**Rating scale:** Use the role's scale (typically 1-5 for Teamtailor). Rate against the green/red flags in the scorecard, not against other candidates.

### Output 2: Screen Evaluation (`candidates/[name]-screen-evaluation.md`)

The analytical narrative for recruiter/HM decision-making. Grouped by competency theme, not by kit question order.

**Structure:**

```markdown
# Recruiter Screen Evaluation: [Name]

[Header: role, candidate, location, current role, screen date, interviewer, source, profile type]

## Profile vs. Target Persona
[How does this candidate map to the defined personas? Where do they fit, where do they diverge?]

## Competency Ratings
### [N]. [Competency Group]: [Rating] ([Label])
**Evidence for:** [Bullet points with quotes/specifics]
**Evidence against:** [Bullet points with quotes/specifics]
**Why [Rating]:** [Analytical justification]

## Stage Recommendation: [Rating] ([Label])
### Must-Have Gate Check
[Checklist of pass/fail gates]

### Red Flags
[Numbered list of concerns with evidence]

### Sell Points That Resonated
### Notes for [Next Interviewer] (Stage [N] Prep)
[Numbered actionable items: what to test, what to probe, what to watch for]

## Process Gaps (Interviewer Calibration)
[What the interviewer missed: unasked probes, accepted vague answers, skipped questions]
```

### Scoring Rules

1. **Score against the rubric, not your impression.** Use the green/red flags from `scorecards.md` as the primary rating input.
2. **"Not asked" is not "no signal."** If a probe was skipped, note it as a process gap. Rate the competency based on whatever evidence exists, but flag the confidence as low.
3. **Vague answers get low ratings.** "Yeah, I can do that" without specifics is a 2, not a 3. The scorecard instruction text often warns about this explicitly.
4. **Evaluate interviewer execution.** The Process Gaps section is not optional. It's the calibration feedback loop that improves future screens.
5. **Compare to persona, not to other candidates.** The Profile vs. Target Persona section anchors the evaluation in the role requirements, not relative performance.
6. **Observation prompts get scored from the full transcript.** Traits marked "NOT a spoken question" in the kit are rated by reviewing the entire conversation, not a single answer.

### Naming Convention

- `candidates/[firstname-lastname]-teamtailor-scorecard.md`
- `candidates/[firstname-lastname]-screen-evaluation.md`

For stages beyond the recruiter screen, replace "screen" with the stage name (e.g., `[name]-roleplay-evaluation.md`).

---

## Feedback Synthesis Method (Multi-Candidate)

Step-by-step process for turning raw interview feedback into a structured evaluation:

1. **Collect all scorecard data** per candidate per stage
2. **Aggregate competency ratings** across interviewers — don't average ratings. Instead, identify consensus vs disagreement. A 4/5 and 2/5 is not a 3/5 — it's a disagreement that needs discussion.
3. **Extract key evidence** (quotes, examples) for each competency — ratings without evidence are opinions, not assessments
4. **Identify patterns** across the interview panel:
   - Consistent strengths (multiple interviewers, multiple stages)
   - Consistent concerns (same signal from different angles)
   - Mixed signals (disagreement between interviewers on the same competency)
5. **Flag competencies with insufficient data** — if only one interviewer assessed a competency, the signal is thin. Note this as a gap.
6. **Produce a structured summary** with evidence backing every claim — no unsupported assertions

## Decision Framework

How to go from aggregated feedback to a hire/no-hire decision.

### Hire/No-Hire Matrix

| Must-Have Competencies | Nice-to-Have Competencies | Recommendation |
|----------------------|--------------------------|----------------|
| All met (Lean Yes+) | Most met | Strong Hire |
| All met (Lean Yes+) | Few met | Hire (with development plan) |
| Most met, 1 borderline | Most met | Conditional Hire (depends on gap criticality) |
| Any must-have at No Hire | N/A | No Hire |
| Mixed signals on must-haves | N/A | Additional assessment needed |

### Confidence Levels

- **High** — 3+ interviewers agree, strong evidence, no major gaps in assessment coverage
- **Medium** — General agreement but some mixed signals, adequate evidence overall
- **Low** — Significant disagreement between interviewers, thin evidence, key competency untested

## Candidate Comparison Matrix

Weighted comparison methodology for evaluating multiple candidates against each other and the bar.

1. List must-have competencies (weight: 3x) and nice-to-haves (weight: 1x)
2. Rate each candidate on each competency using aggregated scorecard data
3. Calculate weighted scores
4. Produce a visual matrix comparing candidates side-by-side
5. Don't let the math override judgment — use the matrix to surface the conversation, not end it

### Template

```markdown
| Competency | Weight | Candidate A | Candidate B | Candidate C |
|------------|--------|-------------|-------------|-------------|
| [Must-have 1] | 3 | [Rating + evidence] | [Rating + evidence] | [Rating + evidence] |
| [Must-have 2] | 3 | | | |
| [Must-have 3] | 3 | | | |
| [Nice-to-have 1] | 1 | | | |
| [Nice-to-have 2] | 1 | | | |
| **Weighted Total** | | **X** | **Y** | **Z** |
```

### Rating Scale

Use a consistent scale across all competencies:

| Rating | Label | Meaning |
|--------|-------|---------|
| 4 | Strong Yes | Exceeds the bar, strong evidence |
| 3 | Lean Yes | Meets the bar, adequate evidence |
| 2 | Lean No | Below the bar, or insufficient evidence |
| 1 | Strong No | Clearly does not meet the bar |

## Bias Mitigation

Common evaluation biases and how to counteract them during feedback synthesis and debriefs.

| Bias | What It Looks Like | Mitigation |
|------|-------------------|------------|
| Halo Effect | One strong signal colors the entire assessment | Evaluate each competency independently, use scorecard structure |
| Anchoring | First interviewer's opinion dominates the debrief | Independent scorecards before debrief, most junior interviewer speaks first |
| Similarity Bias | "They remind me of myself" / "culture fit" as proxy for likeness | Focus on specific behavioral evidence, not gut feeling |
| Contrast Effect | Comparing candidates to each other instead of the bar | Always compare to the job requirements, not to other candidates |
| Recency Bias | Last interview or most recent candidate carries the most weight | Structured debrief covers all stages equally |
| Confirmation Bias | Seeking evidence that confirms the initial impression | Require contradictory evidence for every strong opinion |
| Horn Effect | One weak signal colors the entire assessment negatively | Check if the concern is actually a must-have or a nice-to-have |

For a complete pre-debrief, during-debrief, and post-debrief bias checklist, see **`references/bias-checklist.md`**.

## Debrief Facilitation

How to run an effective hiring debrief that produces a clear, evidence-based decision.

### Pre-Debrief

- All interviewers submit scorecards before the meeting — no late submissions, no filling them in during the debrief
- Recruiter aggregates feedback and identifies areas of agreement and disagreement
- Prepare the agenda with specific discussion points (focus time on disagreements, not consensus)

### Debrief Agenda (45-60 min)

1. **Ground rules (5 min)** — Evidence-based only, no "vibes", most junior speaks first
2. **Per-competency review (25-35 min)** — Walk through each competency, share evidence, discuss disagreements
3. **Gap identification (5 min)** — What wasn't assessed? Do we need another round?
4. **Overall recommendation (10 min)** — Each interviewer states their recommendation with rationale
5. **Decision (5 min)** — HM makes the final call with input from the panel

### Ground Rules

- No one says "culture fit" without specifying which behavior they observed
- Disagree with evidence, not opinions
- Junior interviewers speak before senior ones (prevents anchoring)
- "I don't know" is a valid assessment — better than guessing
- Stay on the competency being discussed — don't jump ahead or revisit unless explicitly reopened

## Output Format

Standard structure for candidate evaluation deliverables saved to `roles/[role-name]/reports/`.

```markdown
# Candidate Evaluation: [Role Title]
**Date:** [Date] | **Evaluator:** [Name]
**Candidates evaluated:** [N]

## Comparison Matrix
[Weighted comparison table]

## Individual Summaries

### [Candidate Name]
**Overall:** Strong Hire / Hire / No Hire / Strong No Hire
**Confidence:** High / Medium / Low

**Strengths (with evidence):**
- [Strength 1]: [Evidence from interview stage X]

**Concerns (with evidence):**
- [Concern 1]: [Evidence from interview stage Y]

**Gaps in assessment:**
- [Competency not sufficiently tested]

**Interviewer consensus:**
| Interviewer | Stage | Recommendation | Key Evidence |
|-------------|-------|---------------|--------------|
| [Name] | [Stage] | [Recommendation] | [Evidence] |

[Repeat for each candidate]

## Recommendation
**Recommended hire:** [Name] — [Rationale with evidence]
**Runner-up:** [Name] — [Why they're close but not recommended]
**Silver medalists:** [Names of qualified candidates who could fill future roles]

## Debrief Notes
[Key discussion points, disagreements resolved, action items]
```

## Reference Files

You are **stongly encouraged** to read the reference files

- **`references/decision-frameworks.md`** — Weighted scorecard method, bar-raiser approach, portfolio hiring, consensus vs veto models.
- **`references/bias-checklist.md`** — Pre-debrief and during-debrief bias check questions.
