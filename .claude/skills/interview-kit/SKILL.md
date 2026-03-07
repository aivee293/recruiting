---
name: interview-kit
description: "This skill should be used when the user asks to create scorecard, build rubric, interview questions for, screening guide, phone screen script, behavioral questions, question bank, calibration exercise, rating scale, competency rubric, interview prep, interviewer training, or needs to build evaluation tools for any interview stage."
---

# Interview Kit for Recruiting

## Purpose

Build the evaluation toolkit interviewers need: scorecards with competency rubrics, rating scales, question banks, screening scripts, and calibration exercises. Everything structured to produce consistent, evidence-based hiring decisions.

## Scorecard Architecture

One scorecard per interview stage, not one per role. Each stage assesses different things — don't dilute by cramming everything into a single form.

**Structure per scorecard:**

- **3-5 competencies** relevant to the specific interview stage
- Each competency includes:
  - Definition (what it means in context of this role)
  - Behavioral indicators per rating level
  - 2-3 suggested questions with follow-up probes
  - Evidence capture field (what interviewers should write down)
- **Overall stage recommendation:** 1 (Strong No) / 2 (No) / 3 (Mixed) / 4 (Yes) / 5 (Strong Yes)
- **Free-text evidence field** for each competency — force interviewers to write down what they observed, not just circle a number
- **Separate "gut feeling" from structured assessment** — capture instinct in its own field, but never let it override evidence-based ratings

**Design rules:**

- **Skills** (role-specific): each stage assesses different skills. Minimize overlap across the interview loop.
- **Traits** (company values): all traits appear in *every* stage with different observation prompts per stage. This produces cross-stage trend data for the Job Match Score. Without traits in every kit, you get sparse ratings and unreliable score aggregation.
- The recruiter screen handles logistics, motivation, and deal-breakers
- Technical rounds handle domain expertise and problem-solving approach
- Behavioral rounds handle collaboration, leadership, and values
- Final/bar-raiser rounds handle culture add and overall calibration

## Rating Scale

Use Teamtailor's fixed 1-5 scale. This is the default for all scorecards and rubrics. Scorecards must use the same labels interviewers see in the ATS so there's zero mental translation.

| Rating | Label | Meaning |
|--------|-------|---------|
| 5 | Strong Yes | Exceeds the bar. Would advocate to hire. |
| 4 | Yes | Clearly meets the bar. Confident advancing. |
| 3 | Mixed | Some positive signals, some concerns. Needs discussion in debrief. |
| 2 | No | Below the bar. Specific concerns identified. |
| 1 | Strong No | Clear disqualifier observed. |

**Scoring math (Teamtailor):** 5=100%, 4=75%, 3=50%, 2=25%, 1=0%. Weighted by skill/trait importance (Low/Medium/High). No score = 0%.

**Watch out for "Mixed" (3) becoming the default.** Brief interviewers that 3 means "I saw both good and bad signals and can articulate them," not "I don't know." If they can't decide, they need to write down what they observed and pick a side in debrief.

## Competency Rubric Design

For each competency on a scorecard, define what each rating level looks like with specific, observable behaviors. Vague rubrics ("shows good communication") produce vague ratings.

**Template:**

```markdown
### [Competency Name]
**Definition:** [What this competency means in context of this role]

| Rating | Behavioral Indicators |
|--------|----------------------|
| 5 — Strong Yes | [Specific observable behaviors that demonstrate excellence] |
| 4 — Yes | [Behaviors that meet the bar] |
| 3 — Mixed | [Behaviors that show both positive and negative signals] |
| 2 — No | [Behaviors that fall below the bar] |
| 1 — Strong No | [Clear disqualifiers] |

**Suggested questions:**
1. [Question] → Follow-up: [Probe]
2. [Question] → Follow-up: [Probe]

**Evidence to capture:** [What interviewers should write down]
```

**Rubric quality checklist:**

- Are the behavioral indicators specific enough that two interviewers would rate the same answer similarly?
- Is there a clear difference between adjacent rating levels?
- Do the indicators describe *behaviors*, not *traits*? ("Explained the trade-offs between X and Y" not "Is a good communicator")
- Are the "1 — Strong No" indicators actual disqualifiers, not just "didn't do well"?
- Can an interviewer realistically observe these behaviors in a 45-60 minute interview?

## Question Frameworks

| Framework | Structure | Best For | Example |
|-----------|-----------|----------|---------|
| STAR-Based Behavioral | "Tell me about a time when..." | Past behavior prediction | "Tell me about a time you had to push back on a stakeholder" |
| Situational | "What would you do if..." | Hypothetical problem-solving | "What would you do if your team disagreed on the technical approach?" |
| Technical Deep-Dive | "Walk me through how..." | Domain expertise | "Walk me through how you'd design a rate limiter" |
| Case-Based | "Here's a scenario..." | Strategic thinking | "Here's our current metrics dashboard. What would you change?" |
| Values-Based | "What does X mean to you?" | Culture alignment | "What does ownership mean to you? Give me an example." |
| Craft-Based | "Show me how you..." | Practical skill demonstration | "Show me how you'd refactor this code" |

**When to use which:**

- **Behavioral (STAR)** — Default for most competencies. Past behavior is the best predictor of future behavior. Use for leadership, collaboration, conflict resolution, execution.
- **Situational** — When the candidate may not have direct experience (career changers, stretch roles). Also good for testing judgment in novel scenarios.
- **Technical Deep-Dive** — For assessing depth of domain knowledge. The "walk me through" framing reveals not just knowledge but how they think.
- **Case-Based** — For product, strategy, and GTM roles. Give real (anonymized) company data and see how they analyze it.
- **Values-Based** — For culture/values interviews. The "give me an example" follow-up is critical — without it, you get rehearsed platitudes.
- **Craft-Based** — For roles where you can observe the actual work (design, coding, writing). Live work samples beat hypotheticals.

**Question quality checklist:**

- Does it assess a specific competency (not just "tell me about yourself")?
- Can the candidate answer with a concrete example?
- Does it have follow-up probes that go deeper?
- Would you get different answers from strong vs weak candidates?
- Is it fair across different backgrounds and experiences?
- Does it avoid requiring knowledge of a specific company, tool, or methodology?

## Screening Guide Structure

Phone screens are pass/fail qualification gates, not deep assessments. The goal: confirm must-haves, surface deal-breakers, sell the opportunity, and decide whether to advance.

```markdown
# Screening Guide: [Role Title]

## Pre-Screen Checklist
- [ ] Reviewed candidate's resume/profile
- [ ] Checked role brief for must-haves and deal-breakers
- [ ] Confirmed comp range authorization
- [ ] Prepared sell points from brief.md

## Opening (2 min)
[Script: introduction, agenda setting, put candidate at ease]

## Qualification Questions (10 min)
[Must-have verification questions — binary pass/fail]
1. [Question] — Looking for: [criteria]
2. [Question] — Looking for: [criteria]

## Exploratory Questions (10 min)
[Deeper questions about experience, motivation, career goals]
1. [Question] — Green flag: [X] | Red flag: [Y]
2. [Question] — Green flag: [X] | Red flag: [Y]

## Role Pitch (5 min)
[Key sell points tailored to what the candidate cares about]

## Candidate Questions (5 min)
[Time for their questions — note what they ask, it reveals priorities]

## Logistics (3 min)
[Next steps, timeline, comp expectations, availability]

## Evaluation
| Criteria | Rating | Evidence |
|----------|--------|----------|
| [Must-have 1] | Pass/Fail | |
| [Must-have 2] | Pass/Fail | |
| Motivation/Interest | High/Med/Low | |
| Communication | Strong/Adequate/Weak | |
| Overall | Advance/Hold/Reject | |

**Red flags observed:**
**Sell points that resonated:**
**Candidate questions/concerns:**
**Notes for next interviewer:**
```

**Screen design principles:**

- Front-load deal-breaker questions — if they fail a must-have, you can end gracefully in 10 minutes
- Always sell, even if you're going to reject — candidates talk to other candidates
- Note what excites the candidate — pass this to the hiring manager for interview prep
- "Hold" means "I need more information" — specify exactly what the next step should clarify

## Calibration Exercises

Calibration aligns the hiring manager and interview panel on what "good" looks like *before* interviews begin. Without calibration, you get inconsistent ratings and wasted interview slots.

**Pre-calibration (async, before session):**

1. Share the scorecard and rubric with the HM and interviewers
2. Provide 2-3 anonymized example profiles (one strong, one borderline, one weak)
3. Each person independently rates the profiles using the scorecard
4. Record ratings before the session — no changing after seeing others' scores

**Calibration session (30-45 min):**

1. Reveal ratings side-by-side — focus on disagreements, not agreements
2. For each disagreement: "What did you see that led to that rating?"
3. Refine rubric language where indicators were interpreted differently
4. Align on must-haves vs nice-to-haves — often the biggest source of disagreement
5. Agree on what "4 — Yes" means specifically for this role
6. Document decisions in the scorecard/rubric

**Output:**

- Refined must-haves and deal-breakers
- Calibrated rubric with clarified behavioral indicators
- Shared language for ratings (what "5 — Strong Yes" means for this role)
- Any competencies that got added, removed, or re-weighted

**When to calibrate:**

- Before any interviews begin (mandatory)
- After the first 3-5 candidates (mid-search recalibration)
- When interviewers consistently disagree on ratings
- When the HM rejects candidates the panel recommended (misalignment signal)

## Artifact Ownership (Single Source of Truth)

Interview artifacts have distinct responsibilities. Do not duplicate content across files:

- **`interview-plan.md`** = architect's view. Describes WHAT each stage assesses, WHY the process is designed this way, advance/reject criteria, and competency coverage matrix. Does NOT contain interview questions, rubrics, or detailed evaluation criteria.
- **`scorecards.md`** = operator's manual for evaluation. Contains the full competency rubrics, behavioral indicators per rating level, interview questions with probes, green/red flags, and evidence capture prompts. One scorecard section per stage.
- **`screening-guide.md`** = operator's manual for the recruiter screen specifically. Full call script, question flow, persona-based pitch variants, pass/fail logic.
- **`take-home-exercise.md`** = candidate-facing brief + internal evaluation criteria for async exercises.
- **`teamtailor-setup.md`** = ATS configuration guide. Mirrors scorecards.md structure but formatted for copy-paste into Teamtailor interview kits.

When building scorecards, the questions and rubrics live HERE (in scorecards.md). The interview-plan.md should list competencies assessed and point to scorecards.md as the source of truth, not duplicate the questions.

## Output Formats

Standard output structure when generating scorecards for a role:

```markdown
# Scorecards: [Role Title]
**Created:** [Date] | **Based on:** interview-plan.md

## Stage: [Stage Name]
**Format:** [Interview type] | **Duration:** [X min]
**Interviewer:** [Name/Role]

### Competencies Assessed

#### 1. [Competency Name]
**Definition:** [What we mean by this]
| Rating | Behavioral Indicators |
|--------|----------------------|
| 5 — Strong Yes | [Indicators] |
| 4 — Yes | [Indicators] |
| 3 — Mixed | [Indicators] |
| 2 — No | [Indicators] |
| 1 — Strong No | [Indicators] |

**Questions:**
1. [Question] → Probe: [Follow-up]
2. [Question] → Probe: [Follow-up]

**Evidence:** [What to write down]

[Repeat for each competency]

### Stage Recommendation
- [ ] 5 — Strong Yes
- [ ] 4 — Yes
- [ ] 3 — Mixed
- [ ] 2 — No
- [ ] 1 — Strong No

**Key evidence for recommendation:**
**Concerns to flag for debrief:**
**What the next interviewer should probe:**
```

**Naming convention:** Save to `roles/[role-name]/scorecards.md`. If a role needs separate files per stage, use `roles/[role-name]/scorecards/[stage-name].md`.

## Teamtailor Kit Generation

When building scorecards, also produce the corresponding Teamtailor kit specification in `roles/[role-name]/teamtailor-setup.md`. Follow the patterns in `references/teamtailor-setup.md` for structure and conventions.

**Every stage's kit must include:**
- The stage-specific **skills** (blue) with spoken questions
- **All company traits** (yellow) with stage-appropriate questions. Prefer observation prompts (rated post-call from transcript, zero call time) for traits that surface naturally in conversation. Use spoken behavioral questions when a trait is hard to observe passively in that stage's format. Either way, each question links to its parent trait so the rating feeds the Job Match Score. Source trait definitions, positive behaviors, and anti-patterns from `your company culture code`.
- Kit instructions written as interviewer training (call flow, scoring timing, must-ask vs optional)
- Standalone questions (Logistics, Candidate Questions) as unlinked items

**The `teamtailor-setup.md` file covers:**
- Job Evaluation section setup (skills + traits + weights)
- One kit per stage with full question specifications
- Stage assignment mapping
- Migration checklist for implementation

This is the ATS translation layer. `scorecards.md` defines *what* to assess and *how* to rate it. `teamtailor-setup.md` defines *how to build it in Teamtailor* so the Job Match Score calculates correctly.

## Reference Files

You are **stongly encouraged** to read the reference files

- **`references/scorecard-templates.md`** — Complete scorecard examples by role family and interview stage, ready to customize.
- **`references/teamtailor-setup.md`** — ATS setup patterns: Job Evaluation section, interview kits, observation prompts, kit-to-stage assignment, scoring math, and the trait-at-every-stage rule. Read this before generating any `teamtailor-setup.md` for a role.
