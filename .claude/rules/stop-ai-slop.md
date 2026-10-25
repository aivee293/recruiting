---
paths:
  - roles/**
  - reports/**
---

# Anti-Slop: Remove AI Writing Patterns

All prose in deliverables must pass these checks before saving.

The phrase lists, structural patterns, jargon replacements, and before/after examples live in the `stop-slop` skill (`.claude/skills/stop-slop/`), which every agent loads via its `skills:` frontmatter. Use the `professional` register for recruiting deliverables and the `casual` register for candidate outreach. This rule adds only the recruiting-specific checks below.

## Generic Analogies

Analogies that are plausible but vague — they gesture toward meaning without achieving it. If the analogy could apply to anything, cut it.

| Kill | Why |
| ---- | --- |
| "Your career is a journey" | Could describe anyone's career |
| "Think of it like building a house" | Generic construction metaphor |
| "It's like putting puzzle pieces together" | Applies to everything |
| "They're the quarterback of the team" | Lazy sports analogy |
| "It's a marathon, not a sprint" | Cliche dressed as wisdom |

**Rule:** An analogy must reference something specific to the role, candidate, or company. If you could swap the subject and the analogy still works, delete it.

## Substance Check

Surface polish concealing empty content is the hardest AI pattern to catch. A paragraph can pass every phrase and structure check above and still say nothing.

Before saving any deliverable, ask:

- **Delete test:** Remove this paragraph. Does the document lose a specific fact, number, or recommendation? If not, the paragraph is filler.
- **So-what test:** After each claim, ask "so what?" If there's no concrete implication for the hiring decision, cut or rewrite.
- **Swap test:** Could this sentence appear in a deliverable for a completely different role? If yes, it's generic. Add specifics.
- **Number test:** Does the deliverable contain at least one concrete data point per section (pool size, comp range, response rate, timeline)? If not, it's opinion without evidence.

## Quick Check Before Saving

- Three consecutive sentences same length? Break one.
- Paragraph ends with punchy one-liner? Vary it.
- Explaining a metaphor? Trust it to land.
- Sounds like a pull-quote? Rewrite it.
- Analogy could apply to any role? Delete it.
- Paragraph removable without losing a fact? It's filler.
