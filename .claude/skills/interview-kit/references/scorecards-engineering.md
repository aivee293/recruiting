# Engineering Scorecards

Technical deep-dive, system design, and live coding. See `scorecard-templates.md` for the rating scale, usage steps, and the Traits Section template that must be added to every stage.

---

## 2. Technical Deep-Dive Scorecard (Engineering)

**Format:** Video call with screen share | **Duration:** 60 min
**Interviewer:** Senior Engineer / Tech Lead

### Competencies Assessed

#### 1. Domain Expertise

**Definition:** Depth of knowledge in the technical domain relevant to the role — languages, frameworks, infrastructure, or specific technical areas.

| Rating | Behavioral Indicators |
|--------|----------------------|
| 5 -- Strong Yes | Expert-level knowledge demonstrated through nuanced explanations. Understands not just "how" but "why." Can discuss trade-offs, edge cases, and failure modes. References real production experience with depth. |
| 4 -- Yes | Strong working knowledge with practical depth. Explains concepts accurately with real-world examples. Understands common trade-offs and can articulate them. Production experience is solid and relevant. |
| 3 -- Mixed | Solid working knowledge. Can explain concepts clearly with practical examples. Understands common trade-offs. Experience is relevant and substantive. |
| 2 -- No | Surface-level knowledge. Can describe what things are but not why or when to use them. Limited practical depth. Relies on textbook answers without production context. |
| 1 -- Strong No | Fundamental gaps in required domain knowledge. Cannot explain basic concepts. Claims experience that doesn't hold up under questioning. |

**Questions:**

1. Tell me about the most challenging technical problem you've solved in [relevant domain]. Walk me through your approach. → Probe: What alternatives did you consider? Why did you choose this approach?
2. How would you explain [key technical concept for role] to a junior engineer? What are the common pitfalls? → Probe: When would you NOT use this approach?

**Evidence to capture:** Specific technologies discussed, depth of understanding demonstrated, real vs theoretical knowledge signals.

#### 2. Problem-Solving Approach

**Definition:** How the candidate approaches unfamiliar problems — their ability to break down complexity, form hypotheses, and reason through unknowns.

| Rating | Behavioral Indicators |
|--------|----------------------|
| 5 -- Strong Yes | Systematically decomposes problems. Asks clarifying questions before jumping to solutions. Considers edge cases proactively. Evaluates multiple approaches. Comfortable with ambiguity. |
| 4 -- Yes | Structured approach to problem decomposition. Asks relevant clarifying questions. Considers important edge cases. Works through the problem methodically. Identifies a sound approach and can justify it. |
| 3 -- Mixed | Reasonable approach to problem decomposition. Asks some clarifying questions. Can work through a problem methodically when guided. Identifies the main edge cases. |
| 2 -- No | Jumps to solutions without understanding the problem. Narrow thinking — only considers one approach. Misses important edge cases. Needs significant guidance to make progress. |
| 1 -- Strong No | Cannot break down problems. Gets stuck and doesn't try alternative approaches. Defensive when assumptions are questioned. No systematic methodology. |

**Questions:**

1. [Present a technical problem relevant to the role — open-ended, not a trivia question] → Probe: What would change if [add a constraint or twist]?
2. Walk me through how you'd investigate [relevant production scenario]. → Probe: What would you check first and why?

**Evidence to capture:** How they structured their approach, questions they asked, alternatives they considered, how they handled getting stuck.

#### 3. Technical Communication

**Definition:** Ability to explain technical concepts, decisions, and trade-offs clearly — to both technical and non-technical audiences.

| Rating | Behavioral Indicators |
|--------|----------------------|
| 5 -- Strong Yes | Explains complex concepts simply without losing accuracy. Uses diagrams, analogies, and progressive disclosure naturally. Adjusts explanation depth based on questions. Clear about what they know and don't know. |
| 4 -- Yes | Explains concepts clearly and accurately. Structures explanations logically. Communicates trade-offs well. Acknowledges knowledge gaps honestly. |
| 3 -- Mixed | Explains concepts clearly when asked. Communicates trade-offs. Answers are structured and follow-able. Honest about knowledge gaps. |
| 2 -- No | Explanations are confusing or overly jargon-heavy. Difficulty structuring thoughts. Assumes shared context that doesn't exist. Struggles to simplify. |
| 1 -- Strong No | Cannot explain their own work clearly. Hides behind jargon. Becomes defensive when asked to clarify. Contradicts themselves. |

**Questions:** Evaluated throughout the conversation — no specific questions needed. Pay attention to how they explain technical concepts during the deep-dive.

**Evidence to capture:** Clarity of explanations, use of examples/analogies, how they handled questions they couldn't answer.

#### 4. Technical Judgment

**Definition:** Quality of technical decisions — ability to evaluate trade-offs, choose appropriate solutions for the context, and reason about long-term implications.

| Rating | Behavioral Indicators |
|--------|----------------------|
| 5 -- Strong Yes | Makes decisions based on clear criteria. Weighs short-term vs long-term trade-offs explicitly. Considers operational implications (monitoring, debugging, maintenance). Adapts approach to context (startup vs scale). |
| 4 -- Yes | Makes sound decisions with articulated reasoning. Weighs relevant trade-offs. Aware of operational implications. Decisions reflect appropriate judgment for the context. |
| 3 -- Mixed | Makes reasonable decisions with articulated trade-offs. Considers the most important factors. Experience-appropriate judgment. Learns from past decisions. |
| 2 -- No | Decisions are dogmatic ("always use X") or arbitrary (no clear criteria). Doesn't consider operational implications. Over-engineers or under-engineers consistently. |
| 1 -- Strong No | Poor judgment on basic technical decisions. Resume-driven development (chooses tech for career benefit, not project needs). Cannot explain why they made past decisions. |

**Questions:**

1. Tell me about a technical decision you made that you'd make differently today. → Probe: What would you change and why? How would you evaluate it now?
2. How do you decide between building something custom vs using an off-the-shelf solution? → Probe: Give me a recent example of each.

**Evidence to capture:** Decision criteria mentioned, trade-offs articulated, quality of reasoning about past decisions, awareness of operational implications.

### Stage Recommendation

- [ ] 5 -- Strong Yes: Advance immediately and prioritize scheduling
- [ ] 4 -- Yes: Advance to next stage
- [ ] 3 -- Mixed: Flag areas of uncertainty, may still advance
- [ ] 2 -- No: Do not advance (document specific gaps)
- [ ] 1 -- Strong No: Do not advance

**Key evidence for recommendation:**
**Strongest technical areas:**
**Technical gaps or concerns:**
**What the next interviewer should probe:**

---

---

## 3. System Design Scorecard (Engineering)

**Format:** Whiteboard / virtual whiteboard | **Duration:** 60 min
**Interviewer:** Staff+ Engineer / Architect

### Competencies Assessed

#### 1. Requirements Gathering & Scoping

**Definition:** Ability to take an ambiguous problem and define the scope, constraints, and requirements before designing a solution.

| Rating | Behavioral Indicators |
|--------|----------------------|
| 5 -- Strong Yes | Asks clarifying questions proactively. Identifies functional and non-functional requirements. Quantifies scale (users, data volume, latency). Makes and states assumptions explicitly. Prioritizes requirements. |
| 4 -- Yes | Asks relevant clarifying questions without prompting. Identifies the key functional and non-functional requirements. Makes reasonable assumptions and states them. Quantifies scale at a useful level. |
| 3 -- Mixed | Asks reasonable clarifying questions. Identifies the main requirements. Makes sensible assumptions. May need prompting on non-functional requirements. |
| 2 -- No | Jumps to design without gathering requirements. Misses key constraints. Assumptions are implicit or unreasonable. Doesn't quantify scale. |
| 1 -- Strong No | Cannot articulate requirements. Starts drawing boxes without understanding the problem. Ignores constraints when pointed out. |

**Questions:**

1. [Present system design problem] — Let's start: what questions would you want answered before designing this? → Probe: What scale are we designing for? What are the most important quality attributes?

**Evidence to capture:** Questions asked, requirements identified, assumptions made, how they prioritized scope.

#### 2. High-Level Architecture

**Definition:** Ability to design a coherent system architecture — appropriate components, clear data flow, sensible technology choices for the given constraints.

| Rating | Behavioral Indicators |
|--------|----------------------|
| 5 -- Strong Yes | Clean, well-structured architecture. Components have clear responsibilities. Data flow is logical. Technology choices are justified by requirements. Identifies the hard problems early. Architecture evolves as requirements are discussed. |
| 4 -- Yes | Coherent architecture that addresses the requirements. Components have defined responsibilities. Data flow is sound. Technology choices are reasonable and justified. Handles the key use cases. |
| 3 -- Mixed | Reasonable architecture that addresses the core requirements. Mostly clear component boundaries. Technology choices are sensible if not deeply justified. Handles the main use cases. |
| 2 -- No | Architecture has unclear component boundaries. Data flow is confused. Technology choices are based on familiarity rather than requirements. Misses important components. |
| 1 -- Strong No | Cannot produce a coherent architecture. Components don't make sense together. Fundamental misunderstanding of how distributed systems work. |

**Questions:**

1. Walk me through your high-level design. → Probe: Why did you separate these into different services? What's the data flow for [key use case]?
2. What are the hardest parts of this system to get right? → Probe: How does your design address [identified hard problem]?

**Evidence to capture:** Architecture diagram clarity, component choices and reasoning, data flow, identified hard problems.

#### 3. Scalability & Performance

**Definition:** Understanding of how the system behaves under load — bottlenecks, scaling strategies, performance trade-offs.

| Rating | Behavioral Indicators |
|--------|----------------------|
| 5 -- Strong Yes | Identifies bottlenecks proactively. Proposes scaling strategies appropriate to the requirements. Understands caching, sharding, replication trade-offs. Back-of-the-envelope calculations to validate design. Considers failure scenarios at scale. |
| 4 -- Yes | Identifies the main bottlenecks. Proposes sound scaling strategies. Understands key trade-offs (caching, replication). Can do basic capacity estimation. Considers how the system behaves under increased load. |
| 3 -- Mixed | Understands basic scaling concepts. Can identify the main bottleneck. Proposes reasonable scaling approaches. May need prompting on some trade-offs. |
| 2 -- No | Generic scaling answers ("just add more servers"). Doesn't identify bottlenecks. Misapplies scaling patterns. No quantitative reasoning. |
| 1 -- Strong No | No understanding of scalability concepts. Design cannot work at stated scale. Fundamental misconceptions about distributed systems. |

**Questions:**

1. Where are the bottlenecks in this design? How would you address them? → Probe: What happens when we 10x the load?
2. Let's do some back-of-the-envelope math on [key dimension — storage, throughput, latency]. → Probe: Does that change your design?

**Evidence to capture:** Bottlenecks identified, scaling strategies proposed, quality of quantitative reasoning, trade-offs articulated.

#### 4. Reliability & Operations

**Definition:** Consideration of failure modes, monitoring, and operational concerns — not just the happy path.

| Rating | Behavioral Indicators |
|--------|----------------------|
| 5 -- Strong Yes | Proactively discusses failure modes. Designs for graceful degradation. Includes monitoring and alerting in the design. Considers data consistency guarantees. Discusses deployment and rollback strategies. |
| 4 -- Yes | Considers failure modes for key components. Includes redundancy and monitoring in the design. Addresses consistency trade-offs. Thinks about deployment concerns. |
| 3 -- Mixed | Acknowledges failure scenarios when prompted. Adds basic redundancy and error handling. Understands monitoring is important. Considers the main consistency concerns. |
| 2 -- No | Only designs for the happy path. Doesn't consider failure modes until asked. No mention of monitoring. Handwaves consistency ("we'll handle that later"). |
| 1 -- Strong No | Ignores failure modes even when prompted. Doesn't understand CAP theorem basics. No operational awareness. Design would be undeployable. |

**Questions:**

1. What happens when [component X] goes down? → Probe: How would you detect it? How would the user experience degrade?
2. How would you monitor this system in production? What alerts would you set up? → Probe: Walk me through an on-call scenario.

**Evidence to capture:** Failure modes discussed, redundancy/fallback strategies, monitoring approach, consistency model chosen and why.

### Stage Recommendation

- [ ] 5 -- Strong Yes: Advance immediately and prioritize scheduling
- [ ] 4 -- Yes: Advance to next stage
- [ ] 3 -- Mixed: Flag areas of uncertainty, may still advance
- [ ] 2 -- No: Do not advance (document specific gaps)
- [ ] 1 -- Strong No: Do not advance

**Key evidence for recommendation:**
**Strongest design areas:**
**Design gaps or concerns:**
**What the next interviewer should probe:**

---

---

## 5. Live Coding Scorecard (Engineering)

**Format:** Collaborative coding (shared IDE) | **Duration:** 45-60 min
**Interviewer:** Engineer at or above role level

### Competencies Assessed

#### 1. Code Quality & Craft

**Definition:** Writing clean, readable, maintainable code — not just code that works.

| Rating | Behavioral Indicators |
|--------|----------------------|
| 5 -- Strong Yes | Clean, idiomatic code from the start. Meaningful variable/function names. Appropriate abstractions. Handles edge cases proactively. Code is production-quality without prompting. Refactors as they go. |
| 4 -- Yes | Code is clean and readable. Good naming conventions and structure. Handles edge cases when they arise. Code quality is solid and would pass review with minor comments at most. |
| 3 -- Mixed | Code is readable and functional. Reasonable naming and structure. Handles main edge cases when prompted. Minor cleanup needed but overall solid. |
| 2 -- No | Code works but is hard to follow. Poor naming or structure. Misses edge cases. Doesn't consider readability. Brute-force solutions without thought for elegance. |
| 1 -- Strong No | Code doesn't compile/run. Fundamental language syntax issues. Cannot write basic data structures or algorithms appropriate for level. Copy-paste without understanding. |

**Questions:**

1. [Present coding problem appropriate for level] → Probe: Before you start coding, walk me through your approach.
2. [After initial solution] How would you improve this code if it were going into production? → Probe: What edge cases should we handle?

**Evidence to capture:** Code quality observations, language proficiency, edge cases handled, refactoring decisions.

#### 2. Problem Decomposition

**Definition:** Breaking a coding problem into manageable steps and tackling them in a logical order.

| Rating | Behavioral Indicators |
|--------|----------------------|
| 5 -- Strong Yes | Breaks the problem into clear steps before coding. Identifies the core algorithm/approach first. Builds incrementally — gets a simple version working, then extends. Anticipates complexity. |
| 4 -- Yes | Plans the approach before writing code. Identifies the main steps and tackles them in order. Builds incrementally. Recognizes where complexity will arise and plans for it. |
| 3 -- Mixed | Plans before coding (even briefly). Takes a reasonable approach. Makes progress incrementally. Can adjust when initial approach has issues. |
| 2 -- No | Starts coding immediately without a plan. Gets lost in implementation details. Doesn't break the problem down. Builds everything at once and then debugs. |
| 1 -- Strong No | Cannot identify the core problem to solve. Scattered approach with no direction. Cannot make progress without extensive guidance. |

**Questions:** Evaluated through observation of their coding process. Prompt: "Before you start coding, can you walk me through your approach?"

**Evidence to capture:** How they planned their approach, order of implementation, whether they built incrementally, how they handled complexity.

#### 3. Debugging & Testing Mindset

**Definition:** How the candidate validates their code, handles bugs, and thinks about correctness.

| Rating | Behavioral Indicators |
|--------|----------------------|
| 5 -- Strong Yes | Tests their code with examples before declaring "done." Traces through edge cases mentally or with test cases. When a bug appears, debugs systematically (not randomly). Considers what could go wrong proactively. Writes tests or test cases naturally. |
| 4 -- Yes | Tests with multiple examples including edge cases. Debugs methodically when issues arise. Thinks about correctness throughout, not just at the end. Identifies likely failure points. |
| 3 -- Mixed | Tests with at least one example. Can debug methodically when something goes wrong. Considers basic edge cases. Responds well to hints about bugs. |
| 2 -- No | Declares "done" without testing. Debugs by random changes. Misses obvious edge cases. Needs hints to find bugs. Limited testing instinct. |
| 1 -- Strong No | Cannot debug their own code. Does not test at all. Cannot trace through code execution. Gets stuck on simple bugs indefinitely. |

**Questions:**

1. [After they write code] How would you verify this works correctly? → Probe: What inputs would break this?
2. [If there's a bug] I think there might be an issue with [input]. Can you walk me through what happens? → Probe: How would you find this in production?

**Evidence to capture:** Testing approach, edge cases identified, debugging methodology, time to identify and fix bugs.

#### 4. Collaboration & Communication During Coding

**Definition:** How well the candidate communicates their thinking while coding — important for pair programming and code reviews.

| Rating | Behavioral Indicators |
|--------|----------------------|
| 5 -- Strong Yes | Thinks out loud naturally. Explains their reasoning before and during coding. Asks clarifying questions. Responds to hints constructively. Treats it as collaboration, not performance. Open about what they're unsure about. |
| 4 -- Yes | Communicates their approach and reasoning clearly. Engages with feedback and suggestions. Explains key decisions as they code. Comfortable asking questions and acknowledging uncertainty. |
| 3 -- Mixed | Communicates their approach when asked. Responds to feedback. Explains major decisions. Engages in discussion about trade-offs. |
| 2 -- No | Codes in silence. Doesn't explain decisions. Defensive when given feedback. Treats hints as criticism rather than collaboration. |
| 1 -- Strong No | Cannot explain their code. Ignores feedback. Becomes confrontational. Refuses to adjust approach when guidance is offered. |

**Questions:** Evaluated through observation. If the candidate goes silent: "Can you walk me through what you're thinking right now?"

**Evidence to capture:** Quality of verbal communication during coding, response to hints and feedback, collaboration style.

### Stage Recommendation

- [ ] 5 -- Strong Yes: Advance immediately and prioritize scheduling
- [ ] 4 -- Yes: Advance to next stage
- [ ] 3 -- Mixed: Flag areas of uncertainty, may still advance
- [ ] 2 -- No: Do not advance (document specific gaps)
- [ ] 1 -- Strong No: Do not advance

**Key evidence for recommendation:**
**Coding strengths:**
**Coding concerns:**
**Comparison to level expectations:**
**What the next interviewer should probe:**

---
