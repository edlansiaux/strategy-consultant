# Domain module — Healthcare, MedTech, digital health, and clinical AI

Module id: `healthtech-medtech`. Activated by engagement-manager (see `../strategic-advisor-standard.md` §13) when the engagement concerns healthcare delivery, hospitals, clinical products, medical devices, digital health, health AI, health data, clinical research, or health-sector commercialization.

This module adds domain content. General doctrine (decision frame, labels, evidence, value case, options, pre-mortem, recommendation bar) lives in `../strategic-advisor-standard.md` and is not repeated here. When the engagement is also a venture/investment question, activate `startup-venture.md` as well; this module then governs value, evidence, regulatory, and adoption questions, and the startup module governs venture economics and capital.

**Regulatory caution.** This module lists what to investigate; it does not state the current law. Regulatory status, classification, dates, and transitional provisions must be established from current primary official sources found during research (CS-1), qualified by jurisdiction and by the product's intended purpose and claims, and flagged for review by qualified regulatory/legal counsel. Never give a definitive regulatory conclusion from memory.

---

## Phase hooks (what each phase does differently when this module is active)

| Phase | Additional actions |
|---|---|
| problem-definition | Add to the Precision Anchor: **Intended purpose & claims** (what the product is claimed to do, for whom, in what setting), **Jurisdiction(s)**, **Current evidence rung** (§3), **Stakeholder map** (user / patient / clinician / purchaser / payer / IT-security / DPO / sponsor). Decision success criteria must include at least one safety or clinical-quality criterion where patients are affected. |
| hypothesis-tree | Default branches (prune those that cannot change the decision): clinical/operational value · evidence sufficiency for the claims · regulatory pathway & cost · adoption & workflow · purchaser economics & budget route · deployment/data/hosting feasibility. |
| research (brief + analysts) | Brief must list jurisdiction(s) and intended purpose. One angle should cover clinical/operational value and the evidence base; the other regulatory pathway, procurement/reimbursement, and adoption. Regulatory findings must come from official primary sources (regulators, official journals, competent-authority guidance) with as-of dates. Clinical claims must record study design and evidence rung. |
| research-validator | Downgrade any outcome claim whose evidence is retrospective-only or simulated when stated as clinical impact. Flag regulatory statements without an official primary source or as-of date as `[UNVERIFIED — regulatory, primary source required]`. |
| expert-interview | Prioritize profiles across the stakeholder map (clinical champion, operational sponsor, purchaser/procurement, IT-security/DPO, regulatory affairs). Record each expert's stakeholder role and incentive. |
| sense-check | Run the domain traps (end of file). Pre-mortem must include a patient-safety failure scenario and a non-adoption scenario. |
| synthesis | Recommend a focused initial **use case × segment × workflow × validation milestone × commercial route × evidence plan** (§8). Value case separates clinical benefit, operational benefit, and purchaser economics, and states who captures the savings. Decision gates include safety / evidence / regulatory / adoption thresholds. |
| synthesis-critic | Check 13 includes: claims match evidence rung; regulatory statements qualified; benefit-vs-payer gap addressed; safety stop criterion present. |
| client-report | Include: stakeholder value map; evidence ladder with current rung and next proof point; regulatory pathway with explicit qualification and counsel-review flag; adoption & procurement path; health-AI economics; pilot design (§6) if a pilot is recommended. |
| deliverable-validator | Check K includes: regulatory qualification present; no clinical-outcome claim above its evidence rung; safety stop criterion in the decision gates. |

---

## §1 Whose value — stakeholder map

User, patient, clinician, purchaser, payer, regulator, IT/security, DPO, and executive sponsor may all be different. For each: current pain and workflow · desired outcome and measurable benefit · adoption friction and incentives · budget ownership and procurement route · evidence threshold and trust concerns.

A clinical benefit is not automatically an economic benefit for the purchaser. Map who experiences the benefit, who pays, who bears implementation cost, and who may resist.

## §2 Clinical and operational value

Assess: patient safety and clinical outcomes · workflow impact, time, capacity, throughput, burden · reliability, usability, accessibility, adoption · quality, equity, unintended consequences · training, change management, operational ownership · total cost of ownership and economic value.

## §3 Evidence ladder

1. Technical verification and data quality
2. Retrospective external validation, including subgroups
3. Prospective silent / shadow-mode evaluation
4. Usability and workflow validation
5. Controlled prospective impact evaluation, where appropriate
6. Routine-use evidence with post-deployment monitoring (drift detection, incident handling, periodic reassessment)

Claims must not exceed the rung reached: retrospective performance or simulation is not evidence of improved outcomes. The evidence roadmap is proportionate to risk and to the claims made.

For clinical AI, examine as relevant: calibration and discrimination, subgroup performance, missingness, data leakage, temporal and site shift, robustness, human factors and automation bias, limits of explainability, operational failure modes. State the reference standard and its limitations.

## §4 Regulatory, privacy, and governance — what to investigate

Establish jurisdiction and intended purpose/claims first; classification follows from them.

For EU / France, investigate as relevant (confirm current text, applicability, dates, and transitional provisions from primary sources):
- Medical-device qualification and classification under the EU Medical Device Regulation (MDR) and the MDCG guidance on software qualification/classification; clinical evaluation; quality management system; risk management; post-market surveillance; cybersecurity.
- EU AI Act obligations for AI systems, including interaction with MDR for AI that is a medical device or a safety component.
- GDPR (controller/processor roles, lawful basis, minimization, retention, access, security) and national health-data rules, including French health-data hosting requirements (HDS) and CNIL frameworks for health research data.
- National evaluation, coverage, and reimbursement pathways (in France, e.g. HAS evaluation and the relevant early/conditional access or digital-medical-device reimbursement routes).
- European Health Data Space provisions where secondary use or interoperability is in scope.

Map: intended purpose and claims · users and use environment · risk-classification rationale · clinical evidence requirements · QMS and lifecycle responsibilities · data roles and hosting architecture · procurement and institutional governance · monitoring, incident response, and change control.

A research prototype, a CE-marked product, a hospital pilot, and a non-device software tool have different regulatory and purchasing requirements. Never assume one from another.

## §5 Market sizing and commercial access

Segment by clinically and commercially meaningful units: facility type, specialty, workflow, case volume, geography, purchasing group, installed base, ability to deploy. Never multiply "all hospitals" by a speculative price.

Bottom-up chain: eligible sites / users / workflows → share reachable via the initial channel → budget and purchasing constraints → deployment capacity and sales cycle → realistic penetration over time → price basis (site, seat, case, subscription, service, license). Cross-check top-down and show every filter.

## §6 Adoption and go-to-market

Map decision rights and blockers across clinical champion, operational sponsor, IT, security, DPO, procurement, finance, legal, medical leadership, and users. Account for sales cycle, evidence required, integration, training, change management, contracting, support, reimbursement.

**Pilot design standard**: explicit hypothesis · measurable endpoints · comparator · duration · data access and governance · pre-agreed purchasing or scale-up decision at the end. A pilot that can only produce testimonials is not recommended.

## §7 Health-AI economics

Cost lines: implementation, integrations, hosting, compute, monitoring, support, validation, regulatory, quality, cybersecurity, customer success. Test whether gross margin survives real deployment and service burden.

Identify who captures savings and whether value converts into budget or willingness to pay. Freed clinician time is capacity, not cash, unless a credible mechanism (avoided hires, avoided overtime/locum spend, additional billable activity) is shown.

## §8 Strategic recommendation shape

Recommend a focused initial clinical use case, customer segment, workflow, validation milestone, commercial route, and evidence plan. Name the next proof point that most reduces risk. Include stop/pivot thresholds — mandatory when safety, evidence, regulatory, or adoption uncertainty is material.

---

## Domain traps (used by sense-check Step 6 when this module is active)

| Trap | Check |
|---|---|
| Accuracy-to-outcome leap | Is improved patient outcome claimed from retrospective AUC/accuracy or simulation only? |
| Benefit–payer mismatch | Does the party that pays capture the benefit? If not, what is the budget mechanism? |
| Freed time as cash | Is time saved converted to money without a mechanism? |
| Site transferability | Was performance shown on the target population, sites, and data pipeline — or elsewhere? |
| Reference-standard weakness | Is the ground truth itself noisy or biased (e.g. inter-rater variability)? |
| Regulatory assumption | Is device status or class assumed rather than derived from intended purpose and sourced guidance? |
| Pilot without decision | Does the proposed pilot end in a pre-agreed purchase/scale decision? |
| Automation bias / deskilling | Are human-factors risks and override behavior assessed? |
| Equity blind spot | Are subgroup performance and access effects examined? |
