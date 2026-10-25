# Scorecard Templates

Complete scorecard templates by interview stage and role family. Copy and customize for each role — adjust competencies, questions, and behavioral indicators to match the specific job requirements and level.

**Rating Scale (1-5, Teamtailor):**

| Rating | Label | Meaning |
|--------|-------|---------|
| 5 | Strong Yes | Exceeds the bar. Would advocate to hire this person. |
| 4 | Yes | Clearly meets the bar. Confident advancing. |
| 3 | Mixed | Some positive signals, some concerns. Could go either way. |
| 2 | No | Below the bar. Specific, articulable concerns. |
| 1 | Strong No | Clear disqualifier. Would advocate against hiring. |

**Usage:** Select the template that matches the interview stage, then tailor:

1. Replace generic competency descriptions with role-specific language
2. Adjust behavioral indicators to reflect the seniority level
3. Swap questions for ones from the question bank that better fit the role
4. Add role-specific must-haves to the evaluation section
5. **Add company traits to every stage** using the Traits Section template below. Source trait definitions from the culture/values deck referenced by `culture-value-deck` in `.claude/talent-sourcing.local.md`. Each stage needs all traits with stage-appropriate observation prompts or behavioral questions.

**Skills vs Traits in these templates:** The 10 templates (in the files listed below) cover skills (blue in Teamtailor, role-specific competencies). Traits (yellow in Teamtailor, company-wide values) must be added separately to every stage. See the "Traits Section" template below.

## Template Files

Read only the file(s) matching the stages in the interview plan:

| File | Templates |
|------|-----------|
| `scorecards-universal.md` | 1. Recruiter Screen · 4. Behavioral Interview · 10. Bar Raiser / Culture |
| `scorecards-engineering.md` | 2. Technical Deep-Dive · 3. System Design · 5. Live Coding |
| `scorecards-product-gtm.md` | 6. Case Study (Product / GTM) · 9. Sales Role Play |
| `scorecards-leadership.md` | 7. Leadership Assessment (Manager+) |
| `scorecards-design.md` | 8. Portfolio Review |

---

## Traits Section Template (Add to Every Stage)

Add this section after the skills competencies in every stage scorecard. Source all trait definitions, positive behaviors, and anti-patterns from the culture/values deck referenced by `culture-value-deck` in `.claude/talent-sourcing.local.md`.

**In Teamtailor:** Each trait below becomes a yellow trait in the kit. Questions are either observation prompts (rated post-call from transcript) or spoken behavioral questions, depending on whether the trait surfaces naturally in that stage's format.

### Company Traits

#### [Trait Name] (e.g., Trust)

**Definition:** [From culture code — what this trait means at the company]

**Question type:** Observation prompt / Behavioral question (choose per stage)

**Observation prompt version:**
```
NOT a spoken question. Rate after the call using the transcript.

Look for: [specific behaviors from culture code positive indicators]

Green flags: [2-3 observable signals from the conversation]
Red flags: [2-3 anti-patterns from culture code]
```

**Behavioral question version:**
```
[Question that elicits behavior revealing this trait]
→ Probe: [Follow-up]

Green flags: [what a strong answer looks like]
Red flags: [what a weak answer reveals]
```

| Rating | Behavioral Indicators |
|--------|----------------------|
| 5 -- Strong Yes | [Specific behaviors demonstrating excellence on this trait] |
| 4 -- Yes | [Behaviors that meet the bar for this trait] |
| 3 -- Mixed | [Some positive signals, some concerns on this trait] |
| 2 -- No | [Behaviors that fall below the bar on this trait] |
| 1 -- Strong No | [Anti-patterns from culture code observed] |

[Repeat for each company trait]

**Stage-specific guidance:**

- **Recruiter Screen:** Shorter conversation, fewer passive signals. Use a mix of observation prompts (for traits like communication quality, curiosity) and direct behavioral questions (for traits harder to observe in 30 min).
- **Technical Deep-Dive:** Rich passive signals from how candidates explain, collaborate, handle pushback, ask questions. Observation prompts work well for most traits here.
- **Behavioral / Culture Round:** Dedicated time for values exploration. Use behavioral questions ("Tell me about a time...") linked to specific traits. This is where you probe trait depth.
- **Final / Bar Raiser:** Focus observation prompts on cross-cutting patterns. The interviewer has read previous feedback and should probe gaps or inconsistencies in trait signals from earlier stages.
