# Exercise 1: Stakeholder Management

> You're partnering with a hiring manager in one of our markets for a key role. They have a very high bar and a long list of must-have requirements. The salary budgeted can't be increased, even though the market data suggests it's below what these candidates earn. Three weeks in, they've rejected every candidate you've sent, with feedback like "not quite right" or "not senior enough." How do you handle this? Walk me through what you'd do, what you'd say to them, and how you'd decide when to push back versus adapt.

The underlying problem is that the hiring manager wants a candidate the budget can't buy, and nobody has said so plainly yet. "Not quite right" doesn't tell me what to change. Sending more profiles won't fix either of these, so I'd stop the volume and reset the search.

Each step notes in brackets where it comes from in this toolkit.

---

## Step 1: Recognise the trigger

The scenario hits two warning rules at once [`CLAUDE.md`, the hiring-manager section]:

- **HM rejection rate above 50%** at "Submitted to HM" means it's time for a calibration session. We're at 100%.
- **No candidates past Screening after 3 weeks** means escalate to the hiring manager. We're at three weeks.

The talent partner guidance also says to recalibrate after the first 3–5 candidates if a pattern appears, not to keep sending profiles [`.claude/agents/senior-talent-partner.md`]. So I stop sending and reset.

## Step 2: Prepare before the conversation

- **Sort the rejections by theme.** Look for the gap between the candidate persona and what the HM actually expects [`senior-talent-partner.md`]. If my submissions missed the brief, I own that first.
- **Count the must-haves.** If there are more than 5, some are nice-to-haves in disguise [`jd-writing`, the requirement-inflation check]. A "long list of must-haves" fails this test straight away. The brief template has three must-have slots for a reason [`.claude/templates/brief.md`].
- **Check the feedback quality.** "Not quite right" is exactly what the bias checklist flags: a rating with no behavioural example behind it, based on gut feel rather than what was observed [`candidate-evaluation/references/bias-checklist.md`].
- **Get market data.** Pull pay benchmarks and pool size. "Pay expectations above the budget range" is a named hiring-difficulty factor in the toolkit [`market-research`]. Never invent pay figures. If the data isn't available, say so [`CLAUDE.md`, fallback behaviour].

## Step 3: The calibration session (30–45 min)

Based on the toolkit's calibration exercise [`interview-kit`, Calibration Exercises]:

1. **Beforehand:** send the HM 2–3 anonymised profiles (one strong, one borderline, one weak). They rate each one on the 1–5 scale before the meeting, with no changing scores afterwards.
2. **In the room:** compare their ratings with mine and focus on where we disagree. For each one: *"What did you see that led to that rating?"*
3. **Make the vague feedback specific:**
   > "When you said Ana wasn't senior enough, what specifically was missing? Give me something she'd have needed to have done."
4. **Use the persona questions** [`persona-research`, HM interview]:
   > "Describe the best person you've worked with in this role." / "What would make someone fail here?"
5. **Agree what a "4 — Yes" means for this role** in concrete terms, and write it down.

**What I'd say about pay.** The toolkit's market guidance is to show trade-offs, e.g. "increasing budget by 15% expands the pool 3x" [`market-research`]. Budget is fixed here, so I'd turn it around:

> "Of the people who meet all of these must-haves, most earn above our range. Budget can't move, so the things we can move are requirements and timeline. If you dropped one must-have, which one would roughly double the pool?"

## Step 4: Record the changes in the brief

The session ends with written changes, not just verbal agreement [`templates/brief.md`]:

- **Must-haves cut to three.** The rest move to nice-to-have.
- **"Explicitly NOT required" filled in.** This section of the template exists precisely for HM wish-list items.
- **"What success looks like" at 3, 6 and 12 months.** Every remaining must-have has to connect to one of these outcomes, otherwise it moves down.
- **HM preferences filled in** (what wins them over, what puts them off), so the unwritten criteria get written.
- **A Calibration Log entry:** date, trigger ("8 of 8 rejected, 3 weeks"), key changes, attendees.

Then the persona gets refreshed so sourcing targets the new profile [`CLAUDE.md` / `persona-builder`].

## Step 5: When to push back and when to adapt

The test is evidence versus preference:

| Adapt | Push back |
|---|---|
| The feedback cites specific behaviour and is consistent across candidates | The feedback is vague ("didn't feel right"), so press for specifics |
| The requirement connects to a 3/6/12-month outcome in the brief | The requirement doesn't connect to any outcome, so it's a nice-to-have in disguise |
| The HM has context I lack (team gaps, a past failed hire) | Subjective criteria like "culture fit" or "seniority" with nothing concrete behind them, which carry bias risk [`bias-checklist`] |
| My submissions really missed the brief (I own that) | The bar can't be met at this budget according to market data |

For "culture fit":

> "Which specific value or behaviour do you mean? We want to evaluate culture add, not culture clone."

I don't push back on how high the bar is. I push back on the **combination** of bar, budget and timeline, because only two of the three can hold. The HM gets to choose which two, knowingly.

## Step 6: Follow through, and escalate if needed

- Send a small calibration batch against the new criteria, and log each stage move in `brief.md` [`senior-talent-partner.md`].
- If rejections continue after recalibration, escalate to the HM's manager or HR business partner with data: the rejection pattern, the pay gap, time-in-stage, cost of the empty seat. Present it as a decision about requirements, budget or timeline, not a complaint about the person.
- **Flag the next risk early:** a below-market hire makes it likely that the toolkit's rule that an **offer acceptance rate under 70%** triggers a review of pay positioning fires at offer stage [`CLAUDE.md`]. Setting expectations now avoids a surprise later.
- **Don't under-level quietly to fit the budget.** If the role is brought down to match the pay, make it deliberate: retitle it and adjust the job description. Otherwise we hire someone into a job sized above them.

---

**Where the toolkit doesn't help:** it has no explicit escalation-to-leadership playbook and no list of non-cash levers when the budget is fixed (title, scope, remote flexibility, sign-on from a different budget line, learning budget, process speed). Those parts come from general practice.
