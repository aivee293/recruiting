# Teamtailor Setup Guide

How to configure Teamtailor's evaluation system for any role. This is the ATS-specific translation layer between the toolkit's `scorecards.md` and what interviewers actually see in Teamtailor.

## Core Architecture

Teamtailor has three evaluation surfaces. Use two, skip one.

| Surface | Where | Purpose | Use it? |
|---------|-------|---------|---------|
| **Job Evaluation section** | Job editing mode → Evaluation → Skills and traits | Defines which skills/traits matter for this job. Sets weights (Low/Medium/High). Required for Job Match Score. | **Yes.** |
| **Interview Kit** | Settings → Interview kits, attached to job and stages | Questions nested under skills/traits. Instruction text guides interviewers. Ratings happen here and feed the Job Match Score. | **Yes.** One kit per interview stage. |
| **Job Scorecard** | Separate manual rating form on candidate card | Manual rating of skills/traits directly, independent of kits. | **No.** Creates duplication. Skip entirely. |

**How the Job Match Score works:**

1. Skills/traits must exist in the job's Evaluation section (with weights)
2. Those same skills/traits must also be included in an interview kit
3. Interviewers rate through kits
4. Kit ratings feed the Job Match Score automatically (weighted average across all interviewers)

**Scoring math:**
- Score of 5 = 100% match, 4 = 75%, 3 = 50%, 2 = 25%, 1 = 0%
- Each skill/trait's average score is multiplied by its weight
- No score at all for a skill = treated as lowest score (effectively 0%)
- Averages are across scores given (not across all interviewers). If one person scores a skill 5 and two others don't score it, the average is 5 (not 5/3).

**Extra skills/traits in kits:** You can add skills/traits to a kit that aren't in the job's Evaluation section. These get rated and show in Interview Feedback, but do NOT affect the Job Match Score. Useful for informal assessment.

**Cross-stage aggregation** also happens in the toolkit's `scorecards.md` and in debrief, giving you a richer picture than the Job Match Score alone.

## Skills vs Traits

| Type | Color | Scope | Examples |
|------|-------|-------|---------|
| Skills | Blue | Role-specific. Change per job. | Track Record, Discovery & Value Selling, System Design |
| Traits | Yellow | Company-wide. Same across all jobs. | Trust, Curiosity, Impact (your Culture Code values) |

Define traits once in Teamtailor and reuse across all jobs. Skills are created per role based on the job's competency model. Source trait definitions, positive behaviors, and anti-patterns from `your culture code deck`.

**Overlap rules (skills vs traits):**

- **Skills** minimize overlap across stages. Each stage assesses different skills so the interview loop covers maximum ground without redundancy.
- **Traits** appear in *every* stage. Each stage uses different questions for the same traits, giving the Job Match Score multiple data points per trait from different interviewers and conversation contexts. Prefer observation prompts (rated post-call from transcript, zero call time) for traits that surface naturally in conversation. Use spoken behavioral questions when a trait is hard to observe passively in that stage's format. Without traits in every kit, you get sparse ratings and unreliable score aggregation.
- When building kits: copy all traits into every kit, then select stage-appropriate questions (observation prompts or behavioral) for each trait. Only add the skills that belong to that specific stage.

## Setup Flow

### Step 1: Create Skills & Traits (Admin > Settings > Recruitment)

- **Skills (blue):** Role-specific competencies. Create all skills needed across all stages for the role.
- **Traits (yellow):** Company-wide values. Create once, reuse across all jobs.

### Step 2: Create Questions (Admin > Settings > Recruitment > Questions)

Each question is tied to a parent skill or trait. Build questions as a global library. The "New question" form has these fields:

- **Type:** Leave as "Text" (default).
- **Title:** Short label (e.g., "Career walkthrough + numbers", "Coachability signal"). This is what interviewers see in the kit sidebar.
- **Description:** Full interviewer guidance: the question to ask, probes, green flags, red flags. This is the main content field.
- **Single-line / Multi-line:** Select **Multi-line** for all questions. Interviewers need space to write evidence notes, not one-liners.
- **Make question private:** Leave unchecked unless you want to hide responses from other interviewers.
- **Evaluated skill or trait:** The parent skill or trait this question assesses. Leave blank for standalone questions (Logistics, Candidate Questions).

A single skill can have multiple questions in the library. Different kits pick different questions for the same skill. Example: "Coachability" might have "Coachability signal (behavioral)" for Stage 1 and "Live coaching moment (role play)" for Stage 2.

Questions don't have to be linked to a skill/trait. Unlinked questions (e.g., Logistics, Candidate Questions) work as standalone items in kits.

### Step 3: Add Skills & Traits to the Job (Job > Edit > Evaluation)

In the job editing mode, go to the Evaluation step. Add skills/traits from the dropdown (or create new ones). Set weights: Low, Medium, or High. This step is required for the Job Match Score to calculate.

### Step 4: Create Interview Kits and Attach to the Job

Create kits (or select existing ones) in the job's Evaluation section. If you create a new kit, the job's skills/traits are auto-added. For each kit, select which questions to include per skill/trait via the hamburger menu.

### Step 5: Assign Kits to Stages

Each kit gets assigned to a pipeline stage (Inbox, Reviewing, Interview, Offered, etc.). One kit per stage. Multiple kits in the same job can map to different stages.

## Interview Kit Structure

Each kit has two layers:

### 1. Kit Instructions (top-level rich text field)

Kit instructions serve two purposes: call flow guidance AND interviewer training. For interviewers who are new or inconsistent, the instruction text is their only preparation material. Write them as training, not just guidance: explain *why* each section matters, what good looks like, and what mistakes to avoid.

Paste a call flow overview. Template:

```
Call flow ([duration]):
1. Opening + rapport (2 min)
2. [Company pitch if sourced / skip if inbound] (5-7 min)
3. Questions in kit order ([X] min)
   Must-ask: [list critical skills/traits]
   Ask if time allows: [list optional ones]
4. Logistics + candidate questions (5 min)

Scoring: [N] skills + [N] traits = [total] ratings.
[Scoring timing instruction, e.g., "Score after the call using the transcript."]

[Any stage-specific gates or flags]
```

### 2. Skills/Traits + Question Selection

For each kit:
1. Attach the skills and traits assessed in this specific stage.
2. For each attached skill/trait, click the hamburger menu and select which question(s) from the library to include.

**Skills** should minimize overlap across stages. Avoid assessing the same skill in multiple kits unless the stage probes it differently (e.g., behavioral in Stage 1, live role-play in Stage 2). When the same skill does appear in multiple stages, select different questions per stage.

**Traits** are the exception: include all company traits in every kit with stage-appropriate questions. Prefer observation prompts (zero call time, rated post-call) for traits that surface naturally; use spoken behavioral questions when a trait is hard to observe passively. This is required for meaningful Job Match Score aggregation.

## Observation Prompts (Non-Spoken Questions)

For traits assessed through overall conversation observation rather than a specific question: create a kit question but mark it clearly in the instruction text:

```
NOT a spoken question. Rate after the call using the [transcript tool].

[What to look for across the full conversation]

Green flags: [specific observable behaviors]
Red flags: [specific observable behaviors]
```

**Default scoring pattern: post-call from transcript.** Interviewers should score after the call using their transcript tool (Metaview, Otter, etc.), not during the conversation. This keeps the interviewer present during the call and produces more accurate ratings. Add this instruction to every kit: "Score after the call using the transcript."

Observation prompts add zero call time since they're rated entirely post-call. This makes them ideal for traits, which need assessment at every stage without consuming interview minutes.

Common observation prompts: communication quality, outcome framing, intellectual engagement, resourcefulness signals.

## One Kit for Sourced + Inbound

Do not create separate kits for sourced vs inbound candidates. Use one kit with both variants in the instruction text of questions where the framing differs:

```
SOURCED: [question wording for sourced candidates]

INBOUND: [question wording for inbound candidates]
```

The interviewer picks the right variant during the call. All other questions, probes, and flags stay identical.

## Standalone Questions (No Parent)

Some kit content doesn't map to a skill or trait. Add these at the bottom of the kit, not nested under any header:

- **Logistics:** Comp expectations, availability, notice period, other processes, language requirements. Not scored.
- **Candidate questions:** What the candidate asks. Note-taking only. Signal for engagement quality.

## Kit-to-Stage Assignment

After creating a kit: Jobs -> [Job Name] -> Stages -> find or create the stage -> assign the kit.

One kit per stage. If a stage has multiple interviewers (e.g., panel), they share the same kit but submit independent ratings.

## Checklist: Setting Up a New Role

1. [ ] Create skills (blue) and traits (yellow) in Admin if they don't already exist.
2. [ ] Create questions in Admin, each tied to its parent skill/trait.
3. [ ] In the job's Evaluation section: add skills/traits and set weights (Low/Medium/High).
4. [ ] Create one interview kit per stage. Add kit instructions, select questions per skill/trait.
5. [ ] Add standalone questions (Logistics, Candidate Questions) to kits as unlinked items.
6. [ ] Assign each kit to its stage in the job.
7. [ ] Brief interviewers: "Open kit, follow questions, rate skills/traits in the kit. Do not use the Job Scorecard."

## Rating Scale

Use Teamtailor's 1-5 scale (see `scorecard-templates.md` for the full rubric):

| Rating | Label | Meaning |
|--------|-------|---------|
| 5 | Strong Yes | Exceeds the bar. Would advocate to hire. |
| 4 | Yes | Clearly meets the bar. Confident advancing. |
| 3 | Mixed | Some positive signals, some concerns. |
| 2 | No | Below the bar. Specific concerns. |
| 1 | Strong No | Clear disqualifier. |
