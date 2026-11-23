# Domain module — Startup, venture, business plan, and investment decisions

Module id: `startup-venture`. Activated by engagement-manager (see `../strategic-advisor-standard.md` §13) for startup evaluation, venture creation, business plans, fundraising strategy, new-business market entry, and investment decisions.

This module adds domain content. The general doctrine — decision frame, labels, evidence, value case, options, pre-mortem, recommendation bar — lives in `../strategic-advisor-standard.md` and is not repeated here. This module is a strategic judgment aid; it is not regulated investment advice, and deliverables must say so when they issue an investment verdict.

---

## Phase hooks (what each phase does differently when this module is active)

| Phase | Additional actions |
|---|---|
| problem-definition | Add to the Precision Anchor: **Venture thesis** (§1 sentence), **Stage** (idea / pre-seed / seed / Series A+ / corporate venture), **Next value-inflecting milestone**, **Capital ask or budget** if any. When the decision is whether to pursue, fund, or invest in the venture, the options are the §9 verdict scale; for other venture decisions (raise timing, GTM, pricing, wedge choice), options are those decisions and the §9 verdict is given only as context if the user asks for it. |
| hypothesis-tree | Default branches (prune those that cannot change the verdict): customer pain & demand evidence · reachable market · differentiation & defensibility · go-to-market & unit economics · capital path to next milestone · team / execution. |
| research (brief + analysts) | One angle should cover demand evidence, customers and alternatives (§2, §4); the other the economics, GTM, and capital path (§3, §5–§7). Analysts rank demand evidence on the ladder in §2 and capture comparable-company outcomes (including failures). |
| research-validator | Flag any demand claim rated above its evidence rung; flag observed vs. projected metrics that are not labeled. |
| expert-interview | Prioritize target buyers/payers and operators of comparable ventures over founders, advisors, or investors with a stake. Probe willingness to pay with past behavior ("what did you buy / budget last year for this?"), not hypothetical intent. Record each expert's stake in the venture. |
| sense-check | Run the domain traps (end of file) in addition to `../../skills/sense-check/references/analytical-traps.md`. Base rate for the stage/category is mandatory in the pre-mortem. |
| synthesis | When the decision is pursue / fund / invest, the governing message carries the §9 verdict. Value case = unit economics + capital plan to next milestone, with base / downside / upside. Execution plan is milestone-based. |
| synthesis-critic | Check 13 includes: verdict stated (when the decision is pursue / fund / invest); demand evidence not overstated; LTV/CAC assumptions defensible; capital plan tied to a milestone. |
| client-report | Include: venture thesis up front, and the verdict when the decision is pursue / fund / invest; demand-evidence ladder; market sizing (TAM/SAM/SOM separated); unit economics table (observed vs. projected); capital & runway plan; kill criteria. If the deliverable is a business plan, follow §10 structure. Add a one-line "not investment advice" notice when a verdict is issued. |
| deliverable-validator | Check K includes the presence of the verdict (when the decision is pursue / fund / invest), kill criteria, and observed-vs-projected labeling of every unit-economics metric. |

---

## §1 Venture thesis

> For **[customer / segment]** experiencing **[pain]**, **[product]** delivers **[outcome]**, unlike **[current alternative]**, because **[credible advantage]**.

Test each bracket against evidence. Separate customer pain from founder enthusiasm and from technology novelty.

## §2 Customer problem and demand

Map customer, user, buyer, payer, and decision-maker separately — they often differ. Assess frequency, severity, urgency, and cost of the problem; the current workaround; competing priorities; switching friction; willingness to pay and budget owner.

**Demand evidence ladder** (weakest → strongest): stated interest → problem interviews with quantified pain → letters of intent / waitlists → unpaid pilot with usage data → paid pilot → paid deployment → renewal / expansion → unprompted referral. A pilot is not product-market fit. Report the highest rung actually reached.

## §3 Market sizing

- **Bottom-up**: reachable customers × realistic annual spend (or value captured) per customer.
- **Top-down cross-check**: credible dataset filtered for geography, segment, channel, eligibility, adoption.
- State what is excluded. Give range, base case, sensitivity. Translate the result into implications for growth path and financing need — a market that cannot support the next round's expectations is a finding.

## §4 Competition and defensibility

Include direct competitors, indirect alternatives, status quo, internal build, and adjacent entrants. Compare on customer outcome, workflow fit, price, distribution, switching cost, implementation burden, trust, data, regulatory position, service model.

Differentiation must be **valuable, demonstrable, durable, and hard to replicate**. A feature, a model, a patent, or a first-mover claim is not a moat on its own. Credit distribution, workflow integration, data rights/quality, network effects, brand/trust, switching costs, regulatory know-how, or scale only where evidence supports them.

## §5 Business model and go-to-market

Specify who pays, for what, pricing metric, packaging, contract length, renewal logic; sales motion (self-serve, product-led, inside, enterprise, channel, partner, hybrid); buying process, stakeholders, procurement, cycle length; acquisition channels and funnel; implementation and customer-success cost; the critical channel dependency.

Identify the **wedge segment**: narrow enough to win now, with a credible expansion path.

## §6 Unit economics

ARPA/ARR per customer · gross and contribution margin · CAC by channel · payback · retention, churn, expansion, cohorts · LTV with defensible (finite) retention · cost to serve (implementation, support, infrastructure) · break-even volume and cash need.

Label each metric **observed** or **projected**. Run base / downside / upside; name the two or three assumptions that most affect survival.

## §7 Capital and runway

Capital to reach the next value-inflecting milestone; burn and runway; hiring sequence; capital efficiency; financing timing and risk; dilution; non-dilutive alternatives (revenue, grants, debt, strategic capital) where relevant.

Recommend the **smallest credible capital plan that de-risks the venture** — never fundraising merely because it is possible.

## §8 Product and technology

Separate must-have MVP capability · nice-to-have · differentiating capability · critical technical uncertainty · regulatory/security/data dependency · evidence needed for product-market fit.

For AI ventures, scrutinize data access and rights, evaluation quality, performance under real conditions, workflow integration, inference cost and latency, human oversight, reliability, model commoditization, switching costs. "AI-powered" is not a customer benefit.

## §9 Investor-grade verdict

Assess team / founder-market fit · problem severity and evidence · market size and growth · timing · product and validation · defensibility · GTM · unit economics trajectory · capital requirements and milestones · execution risks · exit paths only where plausible and supported.

Verdict scale (one must be chosen when the decision is whether to pursue, fund, or invest): **Pursue aggressively** · **Pursue with conditions** · **Test before committing** · **Reposition** · **Do not pursue**. State the evidence that would change the verdict. ("Reposition" replaces the word "pivot" in client-facing text to stay consistent with banned-language.md; "pivot" remains acceptable as a defined decision-gate outcome — see that file's exceptions.)

## §10 Business plan structure (when the deliverable is a business plan)

1. Executive summary and thesis · 2. Problem, customer, demand evidence · 3. Product and customer outcome · 4. Market sizing and segmentation · 5. Competition and positioning · 6. Business model and pricing · 7. Go-to-market and sales plan · 8. Operations, organization, partnerships · 9. Technology / IP / data strategy · 10. Regulatory and compliance (if relevant) · 11. Financial assumptions and scenarios · 12. Funding requirement, use of funds, milestones · 13. Risks, mitigations, kill criteria · 14. 12–24-month roadmap.

Sections that remain hypothesis-driven are labeled as such. A polished plan must not conceal weak evidence.

---

## Domain traps (used by sense-check Step 6 when this module is active)

| Trap | Check |
|---|---|
| Interest mistaken for demand | Which rung of the §2 ladder does the evidence actually reach? |
| Pilot mistaken for PMF | Is there paid, retained, expanding usage — or only a pilot? |
| Perpetual-retention LTV | Is churn finite and evidence-based? What is LTV at 2× the assumed churn? |
| Blended CAC hiding channel reality | Is CAC split by channel, including founder-led sales that will not scale? |
| TAM-to-revenue leap | Is there an explicit SAM/SOM filter chain, or a "1% of a big market" assumption? |
| Raise-driven plan | Is the capital ask tied to a milestone, or to what investors might fund? |
| Technology as moat | Would a well-funded entrant with the same model/data access replicate it in 12 months? |
| Survivorship in comparables | Are failed comparables in the set? What is the base rate for this stage/category? |
