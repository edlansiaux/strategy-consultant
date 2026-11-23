---
name: sense-check
description: >
  Pressure-test research findings and analytical conclusions for robustness. Use when someone asks to "sense-check this", "pressure-test these findings", "challenge this analysis", "stress-test the argument", "play devil's advocate", "poke holes in this", or when the analytical workflow needs a quality gate between research and synthesis. Also trigger when someone presents a conclusion and wants it challenged before taking it to a client.
---

# Sense-Check — Pressure-Test Everything

Take the research findings and emerging conclusions and systematically try to break them. This is the quality gate between having evidence and having a defensible argument. Most weak consulting work fails here — the analyst found data that supports the hypothesis and stopped looking.

## Preflight Gate (run BEFORE any other step)

This phase requires upstream state and artifacts. Before doing anything else, verify ALL of the following:

1. `engagement-state.json` exists in the active workspace.
2. `"research"` is in `completed_phases`.
3. The following artifacts exist on disk and are non-empty:
   - `research-validated.md`
   - `precision-anchor.md`
   - `client-question-checklist.md`

If ANY required item is missing or empty, STOP. Do not inventory claims, do not run triangulation, do not write the sense-check report. Report the specific missing state field or artifact path and route control back to `engagement-manager`. Do not reconstruct upstream artifacts locally — pressure-testing fabricated context produces fabricated confidence.

When the gate passes:
- Read `engagement-state.json` and treat its `workspace_path` as the active workspace.
- Use `research-validated.md` (consolidated findings, source registry, contradictions) as the claim inventory source.
- Use `precision-anchor.md` for the Question-Answer Precision Check and altitude evaluation.
- Use `client-question-checklist.md` for the Client-Raised Objections Inventory.

At the end of this phase, append `"sense-check"` to `completed_phases`, update `artifact_paths.sense_check`, set `current_phase` to `synthesis` (or back to `research` if the verdict was DRIFTED), refresh `next_required_action` and `last_updated`, and write `engagement-state.json`.

## References (read once, before pressure-testing)

- `../../references/altitude-and-precision.md` — altitude rules and the Question-Answer Precision Verdict (PRECISE / PARTIAL / DRIFTED) used in Step 5.
- `../../references/counter-argument-sources.md` — the three tributaries (steel-man, client-raised objections, evidence-implied risks) you must produce in Step 3.
- `../../references/expert-anchor-and-conflicts.md` — how expert claims and strategic conflicts must be preserved (relevant in Step 1 / Step 2 when assessing claims that originated from expert interviews).
- `references/analytical-traps.md` — the trap checklist used in Step 6.
- `../../references/strategic-advisor-standard.md` — §3 (labels used in the claim inventory), §6 (quantification and sensitivity rules used in Step 4), §8 (red-team and pre-mortem items used in Step 6.5), §11 (depth by stakes tier).
- `../../references/domains/*.md` — if the Precision Anchor lists domain modules, apply the sense-check row of each module's Phase hooks and its Domain traps table in Step 6.

These references are the source of truth. The steps below are the phase-specific actions; they do not re-explain the underlying doctrine.

## Process

### Step 1: Inventory the Claims
List every substantive claim that the eventual storyline will rest on. For each claim, note:
- What evidence supports it
- How many independent sources corroborate it
- What confidence level the research assigned
- Its epistemic label (FACT / CALC / ESTIMATE / ASSUMPTION / HYPOTHESIS / JUDGMENT / UNKNOWN — Standard §3). A load-bearing claim labeled HYPOTHESIS, ASSUMPTION, or UNKNOWN is a vulnerability by definition and goes into Key Vulnerabilities.
- Whether the evidence actually supports the conclusion drawn from it, or only something weaker (e.g. evidence of interest used to conclude demand; correlation used to conclude causation)

### Step 2: Triangulate
For each major claim, check whether the same conclusion holds when approached from different angles:
- Does the top-down view (market data) align with the bottom-up view (unit economics)?
- Does the quantitative evidence (numbers) align with the qualitative evidence (expert opinions, case studies)?
- Does the historical trend support the forward-looking projection?

If three independent angles point the same way, the claim is on solid ground. If only one does, flag it as fragile.

### Step 3: Steel-Man the Opposite AND Surface Client-Raised Objections
This step has two parts. Both are mandatory.

**Part A: Steel-man the analytical counter-argument.**
For each key conclusion, construct the strongest possible counter-argument:
- What would someone who disagrees point to?
- What data would you need to see to change your mind?
- What assumptions does the conclusion depend on, and how sensitive is it to those assumptions being wrong?

Write the steel-man argument out in full. If you cannot articulate a strong opposing case, the conclusion may be trivially true (and therefore not very useful) — or you have not thought hard enough.

**Part B: Systematically extract client-raised objections.**
Re-read the client call transcript, brief, and all source materials. Extract every concern, hesitation, objection, or risk the client raised — even offhand comments. For each one:
- Note the exact concern and where it appeared
- Assess whether the current evidence base addresses it
- If unaddressed, flag it as a gap that must be covered in the counter-argument section of the synthesis and report

Client-raised concerns that go unaddressed in the deliverable are a credibility risk. The client will notice their own question was not answered. Even if the concern seems minor, it is safer to address it briefly than to ignore it.

**Part C: Evidence-implied risks.**
Review the research findings for risks, threats, or caveats that the client did not raise but that the evidence itself surfaces. For each:
- Note the risk and the evidence that implies it
- Assess whether the current storyline addresses it
- If unaddressed, flag it for inclusion in the Considerations section of the report

### Step 4: Sanity-Check the Math
For every quantitative claim:
- Does the back-of-envelope math check out? (A 15% margin improvement on a $2B revenue base is $300M — does that magnitude make sense in context?)
- Are the units consistent? (Market share percentages vs. absolute revenue vs. volume)
- Are comparisons apples-to-apples? (Same geography, same time period, same definition)
- Is the precision warranted? (Do not say "$4.237B" when the assumptions could swing by $500M — use ranges)
- **Sensitivity**: Identify the drivers that move the decision-critical numbers most (1 for `tactical`, 2–3 for `strategic`, 3 plus an explicit downside case for `high-stakes`). Show how the result moves across a plausible range of each, and whether any plausible value flips the decision.
- **Market-size discipline**: Are TAM, SAM, SOM, and obtainable revenue kept separate? Is any revenue figure derived from an unsupported share-capture percentage?
- **Triangulation of numbers**: Where both bottom-up and top-down bases exist, do they agree within a reasonable band? If not, which is preferred and why?
- **Base rates**: What is the base rate of success for this type of move (entry, launch, acquisition, transformation, venture stage)? Does the emerging conclusion assume an outcome far above it, and on what evidence?
- **What must be true**: State the breakeven conditions under which the emerging recommendation creates value. These feed the decision gates in synthesis.

### Step 5: Question-Answer Precision Check
This is the most important check in the sense-check process. Re-read the **Precision Anchor** from the problem-definition phase, then ask:

**Has the analysis drifted?** Compare the emerging conclusion to the exact question in the Precision Anchor. Common drift patterns:
- The question asks "should we enter market X?" but the analysis answers "market X is growing" (describes the market instead of recommending an action)
- The question asks about a specific geography but the data is global
- The question asks about profitability but the analysis focuses on revenue
- The question asks "which option?" but the analysis only evaluates one option favorably
- The question asks for a timeline but the analysis gives a static snapshot

**Is the answer at the right altitude?** This is the most common and most dangerous form of analytical drift. The analysis may address the right topic but at the wrong level of specificity:
- Client asks for per-store breakdown → analysis provides network totals
- Client asks for country-specific data → analysis provides global averages
- Client asks for margin impact → analysis provides revenue impact
- Client asks for by-SKU economics → analysis provides category-level economics

An altitude mismatch is NOT a precise answer. It is a PARTIAL answer at best. When the sense-check identifies an altitude mismatch, the verdict must be PARTIAL and the gap must be explicitly stated: "The evidence answers [what it actually answers] but the client asked for [what they actually asked]. The gap is [specific missing data]. To close it, [specific recommended action]."

Do NOT let altitude mismatches pass as precise answers. A consultant who presents network totals when the client asked for per-store breakdowns has not answered the question — they have provided useful context that happens to be on the same topic.

**If the data doesn't match the question**: This is NOT a reason to answer a different question. Instead, the sense-check must flag: (a) what the available data can answer, (b) the gap between that and what the client asked, and (c) a clear recommendation for how to close the gap (additional research, client data, expert interviews). If the gap cannot be closed, the conclusion must include an explicit qualification.

**Coverage completeness check:** If the Precision Anchor includes a Deliverable Blueprint with Coverage Dimensions, produce a Coverage Matrix that maps every dimension the client asked for against the evidence base. The matrix should make gaps immediately visible. Any dimension classified as GAP downgrades the overall verdict to PARTIAL at best — you cannot call an answer PRECISE if entire dimensions the client asked for are missing.

**Verdict**: [The emerging conclusion PRECISELY answers the Precision Anchor question / The conclusion PARTIALLY answers it — specify the gap / The analysis has DRIFTED — specify to what question]

If the verdict is DRIFTED, recommend looping back to targeted research before proceeding to synthesis. Do not let a drifted analysis pass this gate.

### Step 5.5: Value-Add Completeness Check

The preceding steps ensure the analysis precisely answers the question. This step checks whether the deliverable stops at precision when it should go further.

Review the full research base and ask: **"Is there anything the research uncovered that a knowledgeable practitioner would expect to see in a deliverable on this topic — even though the client didn't ask for it?"**

This is not about padding the report. Clients often don't know what to ask for, and part of a consultant's value is surfacing what they need to know beyond what they asked.

Scan the validated findings, expert extractions, and any [ADJACENT] findings. For each, ask: would omitting this leave the client materially less equipped to act? If yes, flag it for inclusion as a value-add section in synthesis.

### Step 6: Check for Analytical Traps
Run through this checklist:

**Confirmation bias**: Did the research primarily seek evidence that supports the hypothesis? Is there a systematic gap in disconfirming evidence?

**Survivorship bias**: Are we only looking at successful examples? What about companies/markets/strategies that tried the same thing and failed?

**Cherry-picking**: Are there data points that were found but excluded because they did not fit the narrative?

**False precision**: Are we presenting uncertain estimates as if they were exact?

**Missing "compared to what?"**: Every number needs context. 8% growth sounds good — unless the market grew 12%. $50M in savings sounds large — unless the cost base is $20B.

**Recency bias**: Are we over-weighting recent events and under-weighting structural factors?

**Anchoring**: Are we anchored on the first number we found rather than the best number?

Then run the remaining traps in `references/analytical-traps.md` and, if a domain module is active, its Domain traps table.

### Step 6.5: Red-Team and Pre-Mortem (MANDATORY — depth by stakes tier)
Apply `../../references/strategic-advisor-standard.md` §8 to the emerging conclusion. Item 1 (strongest counter-argument) is the steel-man already written in Step 3 Part A — reference it, do not rewrite it. Produce items 2–9; for `tactical` engagements items 2, 8, and 9 are sufficient.

Key outputs:
- **Most fragile assumption** and what happens to the conclusion if it is wrong.
- **Actor objections** (customer, competitor, regulator, investor, operator, skeptical board member — those relevant).
- **Second-order effects and opportunity cost**, including what the status-quo option preserves.
- **Cheaper / faster / reversible test** that could answer the question before full commitment.
- **Pre-mortem**: three most likely causes of failure 18–24 months out.
- **Invalidation conditions**: measurable signals that would trigger pivot, pause, or stop.

Integration rule: every pre-mortem failure cause and actor objection that is not already in the Evidence-Implied Risks table is added to it (or to the Client-Raised Objections Inventory if the client raised it). This carries them through the existing counter-argument doctrine to synthesis, synthesis-critic Check 4, and deliverable-validator Check C without a parallel tracking mechanism.

If the red team shows that the emerging conclusion does not survive, say so in the Overall Assessment and state the revised emerging conclusion. Do not bury it.

### Step 7: Produce the Sense-Check Report

```
## Overall Assessment
[1-2 sentences: How robust is the evidence base? Can we proceed to synthesis or does more work need to happen?]

## Question-Answer Precision Verdict: [PRECISE / PARTIAL / DRIFTED]
[If PARTIAL: what does the data answer vs. what was asked? What is the gap?]
[If DRIFTED: what question is the analysis actually answering? What would bring it back on track?]

## Claim-by-Claim Assessment
| Claim | Label | Evidence Strength | Triangulated? | Counter-Argument | Verdict |
|-------|-------|------------------|--------------|-----------------|---------|

## Coverage Matrix (if Deliverable Blueprint has Coverage Dimensions)
| Dimension Unit | Status (COVERED / THIN / GAP) | Notes |
|----------------|-------------------------------|-------|

## Key Vulnerabilities
[The 2-3 weakest points in the argument — where a skeptical partner or client would push back]

## Steel-Man Counter-Narrative
[The best case against the emerging conclusion, written as a coherent argument]

## Client-Raised Objections Inventory
| # | Client Concern | Source (where raised) | Addressed in Evidence? | Action Needed |
|---|---------------|----------------------|----------------------|---------------|
[Every concern, hesitation, or objection the client raised in the call, brief, or messages. For each: note whether the current evidence addresses it, and if not, what action is needed to address it in the synthesis/report.]

## Evidence-Implied Risks
| # | Risk | Evidence Source | Addressed in Storyline? | Action Needed |
|---|------|----------------|------------------------|---------------|
[Risks, threats, or caveats that the client did not raise but that the research findings themselves surface. For each: the risk, the evidence that implies it, whether the current storyline addresses it, and if not, what action is needed.]

## Value-Add Opportunities
[High-value findings from the research base that go beyond the Precision Anchor but would materially elevate the deliverable. For each: the finding, why it matters to the client, and whether the current storyline would include or filter it out.]

## Math Checks
[Results of back-of-envelope sanity checks on key numbers; market-size discipline; bottom-up vs. top-down triangulation; base rates]

## Sensitivity Analysis
| Driver | Base value (label) | Plausible range | Effect on result | Flips the decision? |
|--------|-------------------|-----------------|------------------|---------------------|
[What must be true: the breakeven conditions for the emerging recommendation]

## Analytical Traps Identified
[Any biases or logical errors found, with specific examples — including domain traps when a module is active]

## Red-Team & Pre-Mortem
[Most fragile assumption · actor objections · second-order effects and opportunity cost · cheaper/reversible test · three pre-mortem failure causes. Note which items were added to the Evidence-Implied Risks table.]

## Invalidation Conditions
| Signal | Threshold | Response (pivot / pause / stop / escalate) |
|--------|-----------|--------------------------------------------|

## Recommendation
[Proceed to synthesis / Revisit specific research areas / Downgrade confidence on specific claims / REDIRECT — analysis has drifted, needs targeted research on the actual question]
```

Present the sense-check report to the user. If vulnerabilities are serious or the precision verdict is DRIFTED, recommend specific follow-up research before proceeding to synthesis. A DRIFTED verdict is a hard stop — do not proceed to synthesis until the analysis is redirected to answer the actual question.
