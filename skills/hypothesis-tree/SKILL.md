---
name: hypothesis-tree
description: >
  Build a structured hypothesis tree with testable branches to guide analysis. Use when someone asks to "build a hypothesis tree", "structure this problem into hypotheses", "create an issue tree", "break this down MECE", or when a defined problem would benefit from structured decomposition before research begins. This skill is optional — not every problem requires a formal hypothesis tree. Skip it when the question is narrow enough that direct research is more efficient.
---

# Hypothesis Tree

Build a hypothesis tree that decomposes the client question into testable branches. This skill is a tool, not a requirement — invoke it only when structuring hypotheses genuinely helps focus the research effort.

## When to Use vs. Skip

**Use a hypothesis tree when:**
- The client question has multiple plausible answers and research needs prioritization
- The problem has 3+ distinct dimensions (e.g., market entry involves market attractiveness, competitive dynamics, and client capabilities)
- The team risks boiling the ocean without a structured view of what to investigate

**Skip the hypothesis tree when:**
- The question is narrow and specific enough that direct research answers it
- The user explicitly wants to go straight to research
- The situation is better served by a simple decision framework or pros/cons analysis

## References and workspace

- `../../references/strategic-advisor-standard.md` §5 — decomposition discipline and framework selection. §2 — the Decision Frame (options in scope, evidence that would change the answer) that the tree must serve.
- `../../references/domains/*.md` — when a domain module is active (Precision Anchor `Domain modules:` line), start from the default branches in its hypothesis-tree row and prune those that cannot change the decision.

Inside an engagement, read `precision-anchor.md` from the active workspace and write the output to `hypothesis-tree.md` in that workspace; engagement-manager records it in `artifact_paths.hypothesis_tree`. This skill does not create workspaces.

**Anti-theater limits.** A tree is useful only if every leaf ends in a test and every test can move the decision.
- Maximum 4 first-level branches and 2 levels of depth unless a branch is both high-impact and untestable at level 2.
- Delete any branch whose outcome would not change which option is chosen ("interesting but not decision-relevant").
- MECE is a means to completeness, not a goal: accept small overlaps if separating them adds no testable content.
- Domain-module default branches are a candidate list, not a structure: keep the decision-relevant ones and group them under ≤4 first-level branches (e.g. "regulatory pathway & cost" and "deployment/data/hosting feasibility" under one "Can it be deployed legally and practically?" branch).

## Process

### Step 1: Start with the Governing Hypothesis
Write a single, falsifiable statement that represents the best initial answer to the client question. This is not a guess — it is a reasoned starting position that research will confirm, modify, or disprove.

Format: "We believe [specific answer to the client question] because [initial reasoning]."

The governing hypothesis must be:
- Specific enough to be wrong (if it cannot be disproven, it is not a hypothesis)
- Actionable — if proven true, the client knows what to do
- Grounded in at least preliminary logic, not pulled from thin air
- Framed against the alternatives: name which option in the Decision Frame it favors and which it rejects, so research tests the choice, not just the favored option in isolation

### Step 2: Decompose into Branches
Break the governing hypothesis into 2-4 supporting conditions — the things that must be true for the hypothesis to hold.

Each branch must be:
- **Mutually exclusive**: no overlap between branches
- **Collectively exhaustive**: together they fully support (or disprove) the governing hypothesis
- **Testable**: each branch ends in a question that research can answer with evidence

Do not fetishize perfect MECE structure at the expense of speed. A pragmatic decomposition that the team can test in days beats an elegant one that takes a week to build.

### Step 3: Define What Proves or Disproves Each Branch
For every branch, specify:
- What evidence would **support** this branch (and where to find it)
- What evidence would **undermine** it (and where to find it)
- What **threshold** or benchmark distinguishes "this is true" from "this is false"
- **Decision consequence**: which option wins or loses if this branch turns out false

The disconfirming test is mandatory: a branch with no "undermines if" cannot be tested and must be rewritten or removed.

### Step 4: Prioritize
Not all branches are equally important or equally uncertain. Mark each branch:
- **Priority**: High / Medium / Low (based on impact on the overall answer)
- **Certainty**: High / Medium / Low (based on how much we already know)
- **Test cost**: Low / Medium / High (time and effort to get decisive evidence)
- **Research approach**: What data or analysis is needed to test this branch

The research phase should start with high-priority, low-certainty, low-test-cost branches — that is where investigation adds the most value per unit of effort. A high-priority branch with high test cost is flagged as a candidate for client data, expert interview, or a reversible experiment.

### Step 5: Update rule
The tree is a working hypothesis, not a commitment. State in the output: "Branches will be updated or abandoned as evidence arrives; research must report disconfirming evidence with the same weight as confirming evidence." Sense-check and synthesis may revise or retire the governing hypothesis; they record why.

## Output Format

```
## Governing Hypothesis
[The falsifiable initial answer]

## Hypothesis Tree

### Branch 1: [Name]
- Statement: [What must be true]
- Supports if: [Evidence that would confirm]
- Undermines if: [Evidence that would disprove]
- Decision consequence: [Which option wins/loses if false]
- Priority: [High/Medium/Low] | Certainty: [High/Medium/Low] | Test cost: [Low/Medium/High]
- Research needed: [Specific data or analysis]

### Branch 2: [Name]
[Same structure]

### Branch 3: [Name]
[Same structure]

## Research Prioritization
[Ordered list of what to investigate first and why]
```

Present the tree to the user for review. Adjust branches based on their feedback — they often know which branches are already settled (no research needed) and which are genuinely uncertain.
