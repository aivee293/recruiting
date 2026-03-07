---
name: offer-negotiation
description: "This skill should be used when the user asks to make an offer, offer package, negotiate salary, counter-offer, closing strategy, comp package, how to close, offer construction, negotiate equity, sign-on bonus, total compensation, offer letter, verbal offer, candidate wants more, competing offer, or needs to construct, present, negotiate, or defend an offer for any role level."
---

# Offer Negotiation for Recruiting

## Purpose

Construct competitive offer packages, design negotiation strategies, and close candidates. Bridge the gap between what the company can offer and what the candidate wants.

## Offer Construction

Components of a total compensation package:

| Component | Description | Typical Levers |
|-----------|-------------|---------------|
| Base Salary | Fixed annual compensation | Market data, internal equity, candidate expectations |
| Variable/Bonus | Performance-based pay (% of base) | Target %, accelerators, guarantee period |
| Equity/Stock | RSUs, options, phantom stock | Grant size, vesting schedule, refresh policy |
| Sign-On Bonus | One-time payment to close | Forfeit clawback, offset lost comp from current role |
| Benefits | Health, retirement, PTO, perks | Often fixed by policy, but highlight value |
| Relocation | Moving support | Lump sum vs managed, temporary housing |
| Title | Job title and level | Sometimes more important than comp to the candidate |
| Start Date | Flexibility on timing | Garden leave, notice period accommodation |
| Remote/Flexibility | Work arrangement | Full remote, hybrid schedule, location flexibility |
| Professional Development | Learning budget, conferences | Annual budget, sabbatical policy |
| Accelerated Review | Earlier-than-standard review cycle | 6-month review instead of 12 |

**Creative levers (when base is capped):**
- Accelerated equity vesting (1-year cliff to 6-month cliff)
- Guaranteed bonus for year 1
- Professional development budget
- Additional PTO
- Flexible start date to optimize tax year
- Title upgrade (if level-appropriate)
- Accelerated performance review (6 months instead of 12)

## Market Positioning

Where to position offers relative to market data:

| Strategy | Positioning | When to Use |
|----------|------------|-------------|
| Lead | Top 25% of market (P75+) | Critical hires, scarce skills, passive candidates |
| Match | Median market (P50) | Standard hires, active candidates, abundant talent |
| Lag | Below median (P25-P50) | Strong non-comp value prop (mission, equity upside, growth) |

Rule: Always know where your offer sits relative to market before presenting it. Use market-analyst data from `.claude/data/market/` if available.

## Negotiation Strategy

### BATNA Analysis (Best Alternative to Negotiated Agreement)

- **Candidate's BATNA:** competing offers, current role, promotion timeline, other options
- **Company's BATNA:** other candidates in pipeline, ability to re-open search, urgency
- The party with the stronger BATNA has more leverage

### Concession Sequencing

1. Start with the full package — present total comp, not just base
2. Understand their priority — what matters most? (base, equity, title, flexibility)
3. Lead with your strongest non-monetary differentiators first
4. If negotiating base: move in decreasing increments (shows approaching ceiling)
5. Link concessions: "If we can get to X on base, would you sign today?"
6. Never negotiate against yourself — wait for their counter
7. Use sign-on bonus to bridge gaps without setting permanent base precedent

### Anchoring

- Set the first number when possible (the verbal offer is your anchor)
- Frame the offer in terms of total compensation, not just base
- Highlight elements they didn't expect (equity upside, unique benefits)

### Deadline Management

- Give a reasonable exploding offer window (5-7 business days standard)
- Be firm but fair: "I want to give you time to decide, but we're moving quickly on this"
- Never issue ultimatums that you're not willing to enforce
- If they need more time, ask why — often reveals a competing process or concern you can address

## Counter-Offer Defense

### Pre-Seeding Doubt (during interview process, before offer)

- "If you get to the offer stage, your current employer may counter. Have you thought about how you'd handle that?"
- "What would need to change at [Current Company] for you to want to stay? And if they could change it, why haven't they already?"
- Data point: 50-80% of candidates who accept counter-offers leave within 18 months anyway

### When Counter-Offer Happens

- Don't panic — this is normal and expected
- Ask: "What specifically did they offer?" (understand the full picture)
- Reframe: "If they valued you this much, why did it take your resignation to show it?"
- Address the real motivation: "You started this process for reasons beyond money. Have those reasons changed?"
- Share statistics: counter-offer acceptance outcomes, trust dynamics, career progression
- Never bad-mouth the current employer
- Give them space: "Take the weekend. This is a big decision."

## Closing Tactics

- **Trial close:** "If we can get to [specific terms], would you accept?" — use early and often
- **Summary close:** Summarize the full value proposition (comp + opportunity + team + growth)
- **Deadline pressure:** "We'd love to have your answer by [date] so we can plan the team's Q2 roadmap with you in mind"
- **Stakeholder engagement:** Connect candidate with future peers, skip-levels, or exec sponsors
- **Last-minute cold feet:** This is about fear, not the offer. Go back to their original motivations.
- **Partner/family concerns:** Offer to address questions, highlight quality of life benefits, be respectful

## Offer Communications

### Verbal Offer Script (phone call)

1. Build excitement: "I have some news I've been looking forward to sharing..."
2. Confirm interest: "Before I share details, are you still excited about [the team/mission]?"
3. Present the package component by component (start with the strongest element)
4. Pause for reaction — don't fill the silence
5. Ask: "How does that feel?" (not "What do you think?")
6. Next steps: "I'll send the written details today. Take [X days] to review."

### Written Offer Structure

- Subject line: "Your Offer from [Company] — [Role Title]"
- Open with genuine excitement
- Package summary table (all comp components)
- Benefits highlights (top 3-5 most relevant)
- Start date and logistics
- Decision timeline
- Contact info for questions

## Output Format

Standard structure for offer-brief.md:

```markdown
# Offer Brief: [Candidate Name] — [Role Title]
**Date:** [Date] | **Prepared by:** [Name]

## Candidate Context
- **Current comp:** [If known — base, bonus, equity, total]
- **Expectations stated:** [What they've said they want]
- **Competing offers:** [Known alternatives]
- **Key motivators:** [Why they're exploring — growth, impact, comp, culture]
- **Potential objections:** [What might hold them back]

## Proposed Package
| Component | Amount | Market Position | Notes |
|-----------|--------|----------------|-------|
| Base | | P[X] | |
| Variable/Bonus | | | |
| Equity | | | Vesting schedule |
| Sign-On | | | Clawback terms |
| **Total Year 1** | **$X** | | |
| **Total Annualized** | **$Y** | | |

## Negotiation Strategy
**BATNA analysis:**
- Candidate's alternatives: [X]
- Our alternatives: [X]
- Leverage assessment: [Candidate/Company/Balanced]

**Concession plan:**
1. If they push on [X], we can offer [Y]
2. Maximum movement: [Floor/ceiling for each component]
3. Walk-away threshold: [When we pass]

**Counter-offer defense:**
- Pre-seeding done? [Yes/No]
- Likely counter-offer scenario: [X]
- Response strategy: [X]

## Closing Plan
- **Verbal offer:** [Date] by [Who]
- **Written offer:** [Date]
- **Decision deadline:** [Date]
- **Stakeholder touchpoints:** [Who contacts candidate and when]
- **Backup candidate:** [Name, readiness level]

## Risk Assessment
| Risk | Likelihood | Mitigation |
|------|-----------|------------|
| [Risk 1] | High/Med/Low | [Action] |
```

## Reference Files

You are **stongly encouraged** to read the reference files

- **`references/negotiation-playbook.md`** — Scenario-based scripts for common negotiation situations.
- **`references/comp-packaging.md`** — Total comp calculator frameworks, equity explanation templates, offer letter patterns.
