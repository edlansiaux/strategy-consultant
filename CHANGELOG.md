# Changelog

## 1.6.0 — 2026-11-23 (Strategic Advisor Operating Standard)

Additive upgrade. Moves the plugin from "evidence-faithful report writer" to "decision advisor": it now frames the decision, challenges the premise, quantifies, compares options, red-teams the conclusion, and ends in an execution plan with decision gates. No phase, checkpoint, gate, command, agent, artifact path, or workspace convention was removed or renamed. `engagement-state.json` gains three optional keys only.

### New shared references
- `references/strategic-advisor-standard.md` — canonical cross-phase quality bar (§1 posture · §2 decision frame · §3 epistemic labels · §4 evidence discipline · §5 problem solving & framework selection · §6 value case · §7 options · §8 red team & pre-mortem · §9 recommendation bar · §10 execution & gates · §11 stakes tiers · §12 communication · §13 domain modules), with a "Where this is enforced" table. Explicitly subordinate to the existing references for CS scoring, altitude, counter-arguments, expert anchors, and traceability — it adds context qualifiers to CS scores rather than creating a second scoring scale.
- `references/domains/startup-venture.md` and `references/domains/healthtech-medtech.md` — optional domain modules, each with a **Phase hooks** table (one row per phase/agent) and a Domain traps table. The startup verdict scale applies only when the decision is whether to pursue / fund / invest. The healthcare module lists what to investigate for EU/France regulation but asserts no current legal status; it requires primary official sources and a counsel-review flag.

### Orchestration — `engagement-manager`
- New "Strategic Advisor Operating Standard" section: the four orchestrator questions (decision, value at stake, constraints, evidence that would change the answer), stakes-tier classification, domain-module activation, simple-question off-ramp. Operating mode clarified: delivery mode is not deference.
- State schema: optional `stakes_tier`, `domain_modules`, `artifact_paths.hypothesis_tree`; backward-compatible defaults documented for older and reconstructed state files.
- Phase 1/2/3/3.5/4/5/5.5/6/6.5 descriptions and Checkpoints 1/3/4 updated to carry the new elements. Phase 6 decision contract now explicitly applies to .xlsx / .pptx deliveries too. Quality-check list extended to 5a–5n.

### Phase skills
- `problem-definition`: Step 2.5 Premise & Root-Cause Check (Holds / Reframed / Challenged); Decision Frame block in the Precision Anchor (decision owner, value at stake, baseline, target, horizon, constraints, decision success criteria, options in scope, evidence that would change the answer, stakes tier, domain modules); fourth stress test (decision test); missing fields become labeled assumptions instead of blockers.
- `hypothesis-tree`: references and workspace note; anti-theater limits; governing hypothesis framed against alternatives; mandatory disconfirming test and decision consequence per branch; test-cost ranking; explicit update/abandon rule; domain default branches grouped under ≤4 first-level branches.
- `research`: brief gains Decision Frame, disconfirmation quota, context qualifiers, quantitative triangulation, independence, and domain-module instructions; angles must be option-complete and domain-complete (two active modules merge into the two angles, overflow flagged for the deep dive); deep-dive assessment checks decision-critical uncertainty and is recommended by default for `high-stakes`.
- `expert-interview`: Challenge section in every guide; FACT/OPINION/HEARSAY mapped to epistemic labels.
- `sense-check`: claim labels and evidence-to-conclusion test; sensitivity, market-size discipline, number triangulation, base rates, what-must-be-true in Step 4; new Step 6.5 Red-Team & Pre-Mortem whose outputs feed the existing Evidence-Implied Risks table (so existing downstream checks carry them); new report sections Sensitivity Analysis, Red-Team & Pre-Mortem, Invalidation Conditions.
- `synthesis`: position and premise tests on the governing message; Step 1.5 option comparison; red-teaming the formed recommendation; Step 4.5 value case; Step 4.7 recommendation, execution plan, decision gates; full label pass; output template gains Options & Trade-offs, Value Case, Recommendation, Execution Plan, Decision Gates; evidence map gains a Label column.
- `client-report`: Executive Output Contract; executive summary leads with the recommendation; Options Considered and Execution Plan & Decision Gates sections; Executive Brief limits for those sections; new checks 5m (recommendation completeness) and 5n (epistemic labeling & precision). The inline banned-word list (a duplicate of `banned-language.md`) is replaced with a pointer.

### Agents
- `analyst-alpha`, `analyst-bravo`: Evidence Discipline block (independence, ≥25% disconfirming queries, evidence per option, context qualifiers, triangulation, labels, domain hooks); Evidence Table gains Label, Date/Geography/Definition, Direction, Option(s) columns; Quantitative Triangulation section; alpha gains a Disconfirming Evidence section.
- `analyst-deep`: "test, don't extend" rule against anchoring on validated findings; labels; contradiction direction column.
- `research-validator`: context-qualifier and label audit in Step 3; new Step 6.5 Evidence Balance & Option Coverage (ONE-SIDED branches, option evidence coverage, number triangulation, change-the-answer evidence); Consolidated Findings gains a Label column.
- `synthesis-critic`: Checks 9–13 (recommendation takes a position and is complete · options genuine · value-case integrity with recomputation · execution/gates/invalidation concrete · decision-critical analysis gaps incl. domain modules and framework theater); "Strongest Remaining Objection" paragraph.
- `deliverable-validator`: Check G honours domain-term exceptions; Check H extended to all epistemic labels; new Check K (recommendation and execution carry-forward, incl. domain-module requirements); legacy-storyline handling.

### Secondary references and docs
- `banned-language.md`: Domain-term exceptions table (pivot as a gate outcome, robustness as an evaluation term, optimization as a defined procedure) — resolves a conflict where the new standard's "go / pivot / stop" gates would have failed Check G.
- `analytical-traps.md`: TAM-as-revenue, vanity metrics, evidence-strength inflation, framework theater, false balance, status-quo omission.
- `storyline-patterns.md`: position and execution tests.
- `counter-argument-sources.md`: pre-mortem feeds tributary 3.
- `commands/engagement.md`, `README.md`: updated to the new behaviour. `plugin.json` version corrected from a stale 1.4.0 to 1.6.0.

### Migration notes
- Engagements started under 1.5.x resume normally. Missing `stakes_tier` → `strategic`; missing `domain_modules` → read the Precision Anchor, else `[]` and re-assess at the next checkpoint.
- A 1.5.x engagement resumed at Phase 5.5 will likely FAIL synthesis-critic Checks 9–13 because its storyline lacks the new sections; this routes back to synthesis, which regenerates them. This is intended. The user may also accept the open risks at Checkpoint 4 as before.
- deliverable-validator runs Check K in "legacy storyline" mode against pre-1.6 storylines.

## 1.5.1 — 2026-05-03 (cleanup)

Surgical consistency pass over the v1.5.0 release. No architectural changes; no shared references, agents, or phase gates were modified. The patch only fixes user-facing wording and one routing inconsistency that contradicted the v1.5.0 architecture.

- **Research sequencing wording.** `README.md`, `commands/engagement.md`, and `skills/engagement-manager/SKILL.md` previously described research as "three agents in parallel," lumping research-validator with the analysts. The validator runs sequentially after both analyst memos are complete. All three files now say "two analysts in parallel, then research-validator validates their memos."
- **`commands/engagement.md` brought up to v1.5 architecture.** The command file's Workflow section previously listed Phases 1–8 and missed the four phases added in v1.5.0 (Data Source Inquiry, Deliverable Format Confirmation, Storyline Critique, Deliverable Validation). The command file now mirrors the orchestrator's Phases 1, 2, 2.5, 2.7, 3, 3.5, 4, 5, 5.5, 6, 6.5 — concise summaries only; the orchestrator skill remains the source of truth for phase logic. The Output section now reflects user-selectable Word / Excel / PowerPoint formats with required source traceability in all three.
- **Workflow-plugin checklist in `README.md`.** The "Checklist when adding a new skill" item that referenced the legacy `./engagement/` workspace is now updated to the v1.5.0 convention: continuation commands check for `./engagements/<slug>-<date>/engagement-state.json`, with `./engagement/precision-anchor.md` retained as a backward-compatible fallback only. Migration language elsewhere in the file is unchanged.
- **`skills/problem-definition/SKILL.md` Routing Check.** Previously, `commands/define-problem.md` claimed the skill had a preflight gate, but the skill itself did not. A lightweight Routing Check section has been added near the top — explicitly NOT a hard upstream preflight (problem-definition is Phase 1; there is no upstream state to gate on for fresh runs). The check distinguishes (a) fresh `/engagement` Phase 1 invocation (proceed; engagement-manager owns workspace creation) from (b) `/define-problem` continuation (require active workspace). Subcommands must not create workspaces.
- **Subcommand frontmatter parallelism.** `commands/research.md` previously said "Continuation only — runs the research phase…" while `commands/define-problem.md` and `commands/interview-guide.md` said "resumes." All three now use "resumes" for consistency. No behavioral change.

## 1.5.0 — 2026-05-03

This release improves entry-point discipline, adds explicit engagement state and resume logic, hardens the phase gates, splits validation roles by phase, and consolidates duplicated doctrine into shared references. The architecture is preserved; the changes are reliability and maintainability passes.

### Prompt 1 — Command surface
- README: `/engagement` is the only fresh-start command. The Commands table now distinguishes "Fresh start (sole entry point)" from "Continuation only".
- Frontmatter `description:` for `/research`, `/define-problem`, and `/interview-guide` rewritten to read as continuation-only ("Continuation only — runs/resumes …").
- Sub-command workflow sections shortened. Step-by-step content lives in the SKILL.md, not duplicated in the command file.
- `engagement-manager`: collapsed nine repeated "Invoke the skill. Its internal gates are authoritative — do not bypass." preambles into a single rule near the top ("Skill invocation rule").

### Prompt 2 — State, resume logic, namespaced workspaces
- New convention: every engagement gets `./engagements/<slug>-<YYYY-MM-DD>/`.
- New file: `engagement-state.json` (engagement_id, topic, workspace_path, current_phase, completed_phases, artifact_paths, checkpoint_status, next_required_action, deliverable_format, scenario, created_at, last_updated). Schema documented in `skills/engagement-manager/SKILL.md`.
- Resume protocol: scan `./engagements/`, single-or-multiple workspace handling, state reconstruction from artifacts when state file is missing, legacy `./engagement/` migration that preserves the original folder.
- README updated with Workspace and state section pointing to the schema.

### Prompt 3 — Hard preflight gates
Each downstream skill received a "Preflight Gate" section that checks `engagement-state.json` + `completed_phases` + required artifact paths and STOPs (routing back to `engagement-manager`) when any item is missing or empty. Gates added to:
- `research/SKILL.md` — requires problem-definition + precision-anchor.md, client-question-checklist.md, source-material-extraction-log.md, step0-answers.md.
- `expert-interview/SKILL.md` — requires research + research-validated.md, precision-anchor.md.
- `sense-check/SKILL.md` — requires research + research-validated.md, precision-anchor.md, client-question-checklist.md.
- `synthesis/SKILL.md` — requires sense-check + sense-check.md, research-validated.md, precision-anchor.md. Also blocks DRIFTED upstream verdicts.
- `client-report/SKILL.md` — requires synthesis AND storyline-critique + storyline.md, research-validated.md, sense-check.md, precision-anchor.md, client-question-checklist.md.
- `agents/deliverable-validator.md` — requires client-report + final deliverable, storyline.md, research-validated.md, sense-check.md, precision-anchor.md, client-question-checklist.md.

Each gate also defines the state-file update on successful exit.

### Prompt 4 — Dedicated deliverable-validator
- New: `agents/deliverable-validator.md` — final-deliverable QA (counts, traceability, counter-argument coverage, client-question coverage, headline fidelity, altitude qualification, banned language, assumption labeling, expert-anchor / strategic-conflict, format-specific checks). Produces `deliverable-gap-report.md` with binary PASS/FAIL.
- Phase 6.5 in `engagement-manager` now dispatches `deliverable-validator` (not `research-validator`).
- `agents/research-validator.md` description tightened to scope it explicitly to ANALYST MEMOS. Added a "scope boundary" paragraph telling the agent to stop and reroute if dispatched against a final deliverable.
- README Agents table updated.

### Prompt 5 — Independent synthesis critique
- New: `agents/synthesis-critic.md` — Phase 5.5. Eight checks against the storyline (governing-message altitude, evidence backing, [ADJACENT] vs. [DIRECT] handling, client-objection carry-forward, headline-sequence-as-argument, gap qualification, Deliverable Blueprint coverage, value-add precedence). Produces `storyline-critique.md` with binary PASS/FAIL.
- New phase in `engagement-manager`: Phase 5.5 dispatches synthesis-critic. Client-report cannot begin until critique returns PASS OR the user explicitly accepts open risks at Checkpoint 4.
- New checkpoint: CHECKPOINT 5 — Validated Deliverable.
- Quick Reference skill sequence updated: `… → synthesis → storyline-critique → deliver → deliverable-validation`.
- Critic deliberately scoped to synthesis only (not added to every phase) to avoid process inflation.

### Prompt 6 — Audit and consolidate duplication
Audit (sources counted across SKILLs and agents):
- Altitude / precision references: 30+ mentions across 6+ files.
- Three-question Data Source Inquiry: duplicated nearly verbatim in `engagement-manager` Phase 2.5 and `research/SKILL.md` Step 0.
- Counter-argument three-source rule: present in 5 SKILLs + 2 agents.
- Expert-anchor and strategic conflict: present in 5+ files.
- Research Notes / source traceability: present in 5+ SKILLs + 5 agents.
- CS-1 to CS-4 scoring: already concentrated in `skills/research/references/research-source-guide.md`; do not duplicate.

Consolidation:
- New plugin-root `references/` directory with four shared specifications:
  - `references/data-source-inquiry.md`
  - `references/altitude-and-precision.md`
  - `references/counter-argument-sources.md`
  - `references/expert-anchor-and-conflicts.md`
  - `references/research-notes-and-traceability.md`
- `engagement-manager` gains a "Shared references" section listing all references and the existing skill-level references.
- `research/SKILL.md` Data Source Inquiry collapsed from ~40 lines to a pointer; Data Source Priority Hierarchy + Scenarios collapsed from ~40 lines to a pointer. Phase-specific actions retained.
- `engagement-manager` Phase 2.5 collapsed to a pointer + 5-step orchestration list. The three required questions now live only in `references/data-source-inquiry.md`.
- `sense-check`, `synthesis`, `client-report`: added a concise "References" section near the top pointing to the shared specs. Phase-specific gates and quality checks retained verbatim.
- Process not weakened: gates remain hard, sense-check still produces all eight required sections, client-report still runs all 12 quality checks (5a–5l), counter-argument three-source rule still enforced (now via reference + per-phase check).

## Migration notes for users

- v1.4.0 engagements with a `./engagement/` workspace will continue to work. On first `/engagement` invocation under v1.5.0, the orchestrator reconstructs `engagement-state.json` from artifacts and writes it into the legacy folder. New engagements use `./engagements/<slug>-<date>/`.
- No commands renamed. No skills removed.
- Agents added: `deliverable-validator`, `synthesis-critic`. Existing agents retained with tightened scope on `research-validator`.
