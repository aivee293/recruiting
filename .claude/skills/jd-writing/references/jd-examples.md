# JD Examples: Annotated

Good JD excerpts annotated with what makes them effective. Organized by section, mapped to the universal JD structure. Add your own examples to each section over time.

## Recommended Reading

External references that shaped this skill's approach:

- **[Copywriting for Recruiters — Good Ad vs Bad Ad](https://www.copywritingforrecruiters.com/blog/can-you-tell-the-difference-between-a-good-ad-and-a-bad-ad/)** — Side-by-side transformation of a Marketing Manager JD. Demonstrates frustration hooks and engagement-over-description framing.
- **[Copywriting for Recruiters — What Candidates Really Want](https://www.copywritingforrecruiters.com/blog/what-do-candidates-really-want/)** — LinkedIn research + heatmap data on how candidates actually read JDs. Source for the information priority hierarchy (title/salary/location → benefits → role clarity → fit → apply).
- **[Copywriting for Recruiters — JD vs Job Advert](https://www.copywritingforrecruiters.com/blog/heres-another-example-of-the-difference-between-a-job-description-and-a-job-advert/)** — The conceptual distinction between internal job descriptions and candidate-facing job adverts. Shows how to rewrite from company-centric to candidate-centric.

---

## Example 1: Backend Engineering (Senior)

### The Opportunity

> Our API gateway handles 2.3B requests/day across 12 regions. The current architecture was designed for 10x less traffic — and it shows. You'll own the redesign: new routing layer, smarter rate limiting, and a migration path that doesn't take the platform down.

**Why this works:**
- **Concrete scale signal** (2.3B requests/day, 12 regions) — candidates immediately gauge the complexity level
- **Honest about the problem** ("it shows") — signals intellectual honesty, not just marketing
- **Clear ownership** ("you'll own the redesign") — autonomy level is explicit
- **Technical hook** (routing, rate limiting, migration) — right candidates self-identify, wrong ones self-select out

### What You'll Do

> - Redesign the API gateway routing layer to handle 10x current traffic with sub-10ms p99 latency
> - Build a rate limiting system that's fair to customers and protects backend services — the current approach is a blunt global throttle
> - Lead the migration from the monolithic gateway to the new architecture without downtime (we have 99.99% SLA commitments)
> - Partner with the platform team (4 engineers) on the observability story — traces, metrics, and alerting that actually help on-call
> - Contribute to engineering-wide technical decisions through our RFC process

**Why this works:**
- **Outcomes with metrics** (10x, sub-10ms, 99.99%) — shows what success looks like
- **Honest framing** ("blunt global throttle") — doesn't pretend everything is perfect
- **Shows collaboration model** (platform team, RFC process) — candidates understand how they'll work
- **5 bullets, not 15** — focused, each one substantial

### What You'll Bring

> **You'll thrive here if you have:**
> - Designed and operated high-throughput, low-latency systems in production (not just read about them)
> - Strong opinions about API design, formed by shipping APIs that real customers depend on
> - Experience with at least one: Go, Rust, or C++ at the systems level (our gateway is Go, but the thinking transfers)
> - Debugged gnarly distributed systems issues — network partitions, cascading failures, clock skew
>
> **Bonus points:**
> - You've contributed to or maintained an open-source networking/proxy project
> - Experience with service mesh architectures (Envoy, Istio, Linkerd)
> - You've done a zero-downtime migration at scale before and know where the dragons are

**Why this works:**
- **"Not just read about them"** — filters for practitioners, warmly
- **Transferable framing** ("Go, but the thinking transfers") — doesn't exclude Rust/C++ systems engineers
- **"Where the dragons are"** — speaks the candidate's language, signals the team has taste
- **4 must-haves, 3 nice-to-haves** — tight, each one meaningful

---

## Example 2: GTM / Account Executive (Enterprise)

### The Opportunity

> We sell to CISOs and security teams at companies with 5,000+ employees. Average deal size is $380K ARR, 4-6 month cycle. Our product replaces 3-4 point solutions — the pitch is consolidation and better signal, not "yet another tool." You'll own 8-12 named enterprise accounts in DACH.

**Why this works:**
- **Buyer, deal size, cycle length** — an AE can instantly assess fit
- **Positioning clarity** ("consolidation, not yet another tool") — candidates understand the sales motion
- **Territory specificity** (8-12 named accounts, DACH) — no ambiguity about scope
- **Honest framing** — doesn't claim "unlimited earnings" or "blue sky territory"

### What You'll Do

> - Own the full sales cycle for 8-12 enterprise accounts — from prospecting through close, with $1.5M+ annual quota
> - Build multi-threaded relationships across security, IT, and procurement — our champions are technical, but the budget holder is the CISO or VP Infrastructure
> - Run technical demos alongside SE support — you'll need enough product depth to lead the first 30 minutes yourself
> - Develop territory plans with marketing (ABM campaigns, executive events) — you'll have budget and support, but you drive the strategy
> - Contribute to sales playbook development — we're 15 AEs, not 150, so your wins shape how everyone sells

**Why this works:**
- **Revenue specificity** ($1.5M+ quota) — no hiding the target
- **Multi-threading explicitly stated** — signals complex enterprise sales, not transactional
- **"You'll need enough product depth"** — honest about the technical bar
- **"Not 150, so your wins shape..."** — shows stage and influence opportunity

### What You'll Bring

> **Must-haves:**
> - Closed $300K+ enterprise software deals — you know what a 4-6 month cycle with multiple stakeholders feels like
> - Sold to security or IT buyers (CISO, VP Security, VP Infrastructure) — you understand their world, priorities, and buying process
> - Prospected your own pipeline alongside inbound — this isn't a role where leads arrive fully qualified
> - Professional fluency in German and English — most champions communicate in German, contracts go through English-speaking legal
>
> **Nice-to-haves:**
> - Cybersecurity domain knowledge (endpoint, SIEM, SOAR, or adjacent)
> - Experience selling platform consolidation plays (replacing multiple vendors)
> - MEDDPICC or similar qualification framework in your DNA, not just on your resume

**Why this works:**
- **Deal size and cycle as proof** — not "enterprise experience" but the specific shape of deal
- **Language requirement is justified** (explains why both languages matter)
- **"Not just on your resume"** — signals the team cares about real methodology adoption
- **Honest about prospecting** — doesn't promise pure inbound paradise

---

## Example 3: Product Manager (Senior)

### The Opportunity

> Our billing system serves 23,000 customers across 14 pricing models. When pricing changes go wrong, revenue literally stops. You'll own the product strategy for billing and monetization — deciding what we charge, how we charge it, and making sure the systems behind it actually work at scale.

**Why this works:**
- **Stakes are clear** ("revenue literally stops") — immediate gravity
- **Scope is defined** (billing + monetization, not "the product")
- **Decision authority explicit** ("deciding what we charge") — this is a PM who owns strategy, not just writes tickets

### What You'll Do

> - Define the product roadmap for billing and monetization — you'll own the vision and priority calls, presenting directly to the CEO and CFO
> - Partner with engineering (team of 8) to ship billing features that handle $200M+ in annual transaction volume without breaking
> - Design pricing experiments — new models, packaging changes, upgrade/downgrade flows — and measure revenue impact
> - Translate finance requirements (rev rec, tax compliance, multi-currency) into product specs that engineers don't hate reading
> - Talk to customers weekly about how they buy, what pricing friction they experience, and what would make them upgrade

**Why this works:**
- **Decision scope explicit** ("you'll own the vision and priority calls")
- **Stakeholder access clear** (CEO, CFO, engineering, customers)
- **"Specs that engineers don't hate reading"** — personality, signals collaboration values
- **Customer contact frequency stated** (weekly) — sets expectations for customer-facing work

### What You'll Bring

> **Must-haves:**
> - Shipped billing, payments, or monetization features at a B2B SaaS company — you've dealt with the complexity of recurring revenue systems
> - Can hold your own in pricing conversations with finance and in technical conversations with engineers — you don't need to code, but you need to understand system constraints
> - Experience running pricing experiments and measuring business outcomes (not just feature adoption)
>
> **Nice-to-haves:**
> - Worked with multi-currency or international billing
> - Familiarity with rev rec standards (ASC 606) or subscription billing platforms (Stripe Billing, Chargebee, Zuora)
> - Have strong opinions about PLG pricing, formed by doing it

**Why this works:**
- **Domain-specific** (billing/monetization, not generic "product experience")
- **3 must-haves** — extremely tight, each one genuinely required
- **"Can hold your own"** — describes the actual capability, not a credential
- **"Strong opinions, formed by doing it"** — signals the team values practitioners over theorists

---

## Adding Your Own Examples

To add examples to this file:

1. **Copy the structure** — each example has: The Opportunity, What You'll Do, What You'll Bring
2. **Add "Why this works" annotations** for each section — explain what makes it effective, not just that it's good
3. **Name the role family** in the heading — helps with pattern matching
4. **Keep excerpts, not full JDs** — this is a reference for learning, not a template library

Suggested additions:
- Data / ML role
- Design / UX role
- Executive / leadership role
- Entry-level / early-career role

---

## Example 4: Operations / Finance (Head of FP&A)

### The Opportunity

> We've grown from EUR 8M to EUR 45M ARR in three years without a dedicated FP&A function. Our CFO has been building models in spreadsheets between board meetings. You'll build financial planning and analysis from scratch — the models, the processes, and eventually the team.

**Why this works:**
- **Revenue context** (EUR 8M to 45M) — candidates gauge company stage and complexity immediately
- **Honest gap** ("spreadsheets between board meetings") — signals the problem without sugarcoating
- **Build-from-scratch framing** — attracts entrepreneurial finance people, filters those who want established processes
- **Scope trajectory** (models → processes → team) — shows growth path

### What You'll Do

> - Build the company's first financial planning and analysis function — forecasting models, budget processes, variance analysis, and board reporting
> - Own the annual planning cycle: work with every department head to build bottoms-up plans, challenge assumptions, and present trade-offs to the exec team
> - Create the metrics framework that connects operational KPIs to financial outcomes — we track ARR and burn, but the middle layer (unit economics, cohort analysis, payback periods) is thin
> - Partner with the CFO on fundraising preparation — investor materials, scenario modeling, and due diligence readiness
> - Hire your first analyst within 6 months as the function matures

**Why this works:**
- **Function-building outcomes**, not accounting tasks
- **Cross-functional scope explicit** (every department head, exec team, CFO, investors)
- **Honest about what's missing** ("the middle layer is thin") — signals they know what they don't have
- **Hiring path** (first analyst in 6 months) — growth is concrete, not promised vaguely

### What You'll Bring

> **Must-haves:**
> - Built or significantly scaled an FP&A function at a SaaS company (you've gone from "we have a spreadsheet" to "we have a planning process")
> - Can build financial models that non-finance leaders actually use — your models change decisions, not just document them
> - SaaS metrics fluency: ARR, NRR, CAC:LTV, payback period, gross margin, Rule of 40 — you think in these natively
> - Comfortable presenting to board members and investors — not just preparing the slides, but owning the narrative
>
> **Nice-to-haves:**
> - Experience at a European SaaS company navigating multi-country revenue recognition
> - Have been through a Series B or C fundraise on the finance side
> - SQL proficiency — you can pull your own data without waiting for the data team

**Why this works:**
- **Stage-specific** ("spreadsheet to planning process") — not generic FP&A experience
- **"Models that change decisions"** — describes impact, not activity
- **Board comfort as must-have** — transparent about the exposure level
- **SQL as nice-to-have** — practical signal about data maturity, positioned correctly
