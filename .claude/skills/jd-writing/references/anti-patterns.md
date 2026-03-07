# JD Anti-Patterns: Before & After

Common job description mistakes with concrete fixes. Each pattern: what's wrong, why it fails, and how to fix it.

---

## 1. Vague Requirements

Generic qualifications that describe every candidate (or no one).

**Bad:**
> "Excellent communication skills required"

**Why it fails:** Every candidate thinks they communicate well. It filters no one and tells candidates nothing about what communication looks like in this role.

**Good:**
> "You'll present technical trade-offs to non-technical stakeholders weekly, translating system design decisions into business impact for product and leadership teams."

---

## 2. Task Lists Instead of Outcomes

Listing daily activities instead of what the person accomplishes.

**Bad (Engineering):**
> - Write Python code
> - Attend sprint planning meetings
> - Review pull requests
> - Update documentation

**Bad (Operations):**
> - Process invoices
> - Manage vendor relationships
> - Create monthly reports
> - Update the ERP system

**Why it fails:** Describes a to-do list, not a role. Candidates can't gauge the level of impact or autonomy.

**Good (Engineering):**
> - Build production data pipelines serving 10M+ daily events, from ingestion through transformation to serving layer
> - Own the reliability of our real-time analytics stack — you'll decide the architecture, not just implement it

**Good (Operations):**
> - Redesign the procurement workflow to cut vendor onboarding time from 6 weeks to 2 — we're adding 15 new suppliers per quarter and the current process can't keep up
> - Build the financial reporting package that the CFO presents to the board — you'll own accuracy, narrative, and timing

---

## 3. Requirement Inflation

Asking for more experience than the role (or the technology) warrants.

**Bad:**
> "10+ years of Kubernetes experience required"

**Why it fails:** Kubernetes hit 1.0 in 2015. Nobody has 10 years of production Kubernetes experience. Signals the JD writer doesn't understand the technology.

**Good:**
> "Deep experience operating Kubernetes in production — you've dealt with cluster upgrades, networking edge cases, and scaling challenges firsthand."

---

**Bad:**
> "Must have 7+ years of React experience"

**Why it fails:** React was released in 2013. The specific year count gates out people who've been building equivalent UIs in Vue or Angular and could ramp on React in weeks.

**Good:**
> "Strong frontend fundamentals — you've built complex, interactive UIs in a component-based framework (React preferred, but transferable experience counts)."

---

## 4. Jargon Padding

Filling space with buzzwords that say nothing specific.

**Bad:**
> "Join our fast-paced, dynamic, innovative team in a collaborative, results-driven environment where we leverage cutting-edge technology to disrupt the industry."

**Why it fails:** Every company says this. It's indistinguishable noise. Candidates actively distrust stacked buzzwords.

**Good:**
> "We ship weekly. The team is 6 engineers, 1 PM, 1 designer — small enough that your code hits production fast, large enough that you won't be on-call alone."

---

## 5. Company-Centric Framing

Leading with what the company needs instead of what the candidate gets.

**Bad:**
> "We need a Senior Engineer who can help us scale our platform to support our growing customer base and meet our ambitious revenue targets."

**Why it fails:** "We need" centers the company. Candidates care about what they'll do, learn, and build — not what you need from them.

**Good:**
> "You'll architect the systems behind a platform that 50K businesses rely on daily. Our scale challenges are real — handling 100K+ concurrent connections with sub-50ms latency — and you'll have the autonomy to solve them your way."

---

## 6. Wall-of-Text Responsibilities

15+ bullet points that blur together and signal scope creep.

**Bad:**
> - Develop new features across the full stack
> - Write unit and integration tests
> - Participate in code reviews
> - Collaborate with product managers
> - Work with designers to implement UI
> - Debug and fix production issues
> - Optimize application performance
> - Write technical documentation
> - Mentor junior developers
> - Participate in architecture discussions
> - Support DevOps in deployment
> - Manage technical debt
> - Stay current with technology trends
> - Present at engineering all-hands
> - Evaluate new tools and frameworks

**Why it fails:** 15 bullets means nothing is prioritized. The candidate can't tell what they'll actually spend 80% of their time doing. It reads like the company hasn't decided what this role is.

**Good:**
> - Own our checkout and payments flow end-to-end — from the React frontend through the Go API to Stripe integration (this is 60% of the role)
> - Drive down payment failure rates (currently 3.2%, target 1.5%) through better retry logic, fraud detection, and provider failover
> - Mentor 2 mid-level engineers on the payments team, with regular pairing and design reviews
> - Contribute to our engineering RFC process — you'll have a voice in technical direction

---

## 7. Hidden Requirements

Using "culture fit" or vague phrases to encode unstated expectations.

**Bad:**
> "Must be a culture fit. We value team players who go above and beyond."

**Why it fails:** "Culture fit" is a catch-all that masks bias. "Go above and beyond" signals unpaid overtime. Neither tells candidates what behavior is actually expected.

**Good:**
> "We work standard hours (no hero culture) and protect focus time. We value direct feedback — you'll give and receive it regularly in design reviews and retros. If you prefer to work through disagreements openly rather than avoid them, you'll thrive here."

---

## 8. Copy-Paste Boilerplate

"About Us" sections that could describe any company.

**Bad:**
> "We are a leading provider of innovative solutions in the technology space. Our mission is to empower businesses with cutting-edge tools. We are a team of passionate individuals committed to excellence."

**Why it fails:** This literally describes nothing. Swap in any company name and it still works — which means it does no work for any company.

**Good:**
> "Acme processes payroll for 12,000 small businesses across Europe. We started in Berlin in 2021, hit profitability in 2024, and now process over EUR 800M monthly. Our bet: payroll software shouldn't require an accountant to operate."

---

## Pattern Summary

| Anti-Pattern | Core Problem | Fix |
|-------------|-------------|-----|
| Vague requirements | Filters no one | Show what the skill looks like in practice |
| Task lists | No impact signal | Frame as outcomes with scope |
| Requirement inflation | Gates out qualified candidates | Capability over years, transferable over specific |
| Jargon padding | Zero information density | Replace with concrete specifics |
| Company-centric | Ignores candidate perspective | Lead with what they get, not what you need |
| Wall of text | No prioritization | 5-8 bullets, show time allocation |
| Hidden requirements | Masks bias, signals overtime | Name the behaviors explicitly |
| Boilerplate About Us | Indistinguishable | Specific traction, honest differentiator |
