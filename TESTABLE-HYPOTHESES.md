# Testable Hypotheses — Universal Intelligence Evolution and Relay Unit (UIERU)

**Version:** 1.0.0  
**Authors:** Sizhe Tan & GPT-Obot  
**Status:** Research hypotheses and proposed validation protocol; not empirical findings  
**Repository:** Universal-Intelligence-Evolution-and-Relay-Unit  
**Companion documents:** [OPEN-QUESTIONS.md](OPEN-QUESTIONS.md) · [VALIDATION-ROADMAP.md](VALIDATION-ROADMAP.md) · [FUTURE-DIRECTIONS.md](FUTURE-DIRECTIONS.md)

> **Engineering First · Theory Supported · Research Open.** UIERU is an architectural research proposal. The hypotheses below are intentionally falsifiable. Passing a schema or conformance test does not establish a performance advantage.

## 1. Purpose and Research Discipline

UIERU organizes existing intelligence capabilities into a governed, composable unit:

$$
U=(K,P,F,R,E)
$$

where **K** is the contract and authority boundary, **P** the Calling Path, **F** the forward-guiding Scoring Forest, **R** evidence-preserving relay, and **E** governed structural evolution. A UIERU may include human operators, LLMs, agents, conventional software, external services, and sandboxed exploration. It is not a requirement that every task use a UIERU, nor that a UIERU be an autonomous conscious subject.

The objective of this document is to distinguish: (a) what a UIERU implementation **must** do to claim conformance; (b) what the architecture **might** improve; and (c) which observations would disconfirm those improvements.

All numerical margins below are **illustrative preregistration templates**, not observed outcomes or universal acceptance thresholds. Study teams must choose and freeze context-appropriate thresholds, sample sizes, budgets, and analysis plans **before** evaluating the held-out test set.

## 2. Hypothesis Registry

| ID | Research axis | Primary comparison | Intended outcome |
|---|---|---|---|
| H01 | Selective structural containerization | Ordinary workflow | Net value after overhead |
| H02 | Forward guidance | Retrospective-only scoring | Risk-adjusted task utility |
| H03 | Multi-trail search | Single-path execution | Quality under equal budget |
| H04 | Counter-evidence | No independent challenge | Defect and overconfidence reduction |
| H05 | Evidence-preserving folding | Result-only aggregation | Better downstream decisions |
| H06 | Nested composition | Ad hoc orchestration | Reliable complex-task coordination |
| H07 | Structural relay | Summary-only handoff | Relay fidelity and reuse |
| H08 | Bidirectional collective learning | One-way knowledge distribution | Cross-site adaptation |
| H09 | Residual-driven structural RSI | Static runtime | Sustained held-out improvement |
| H10 | Subject-indexed memory | Event-only memory | Subject-specific continuity |
| H11 | Subject-indexed world models | Shared-only world model | Perspective-aware prediction/action |
| H12 | Platform-level structural RSI | Local-only improvements | Safe cross-domain transfer |
| H13 | Distributed scoring governance | Single centralized scoring policy | Multi-tenant robustness |
| H14 | Sovereign structural relay | Unrestricted or blanket sharing | Useful sharing with lower exposure |
| H15 | Interoperable contracts | Proprietary point integrations | Integration and migration efficiency |
| H16 | End-to-end UIERU | Best-matched non-UIERU baseline | Net system-level benefit |

## 3. Common Experimental Protocol

### 3.1 Units of analysis

Use a **task instance** for execution studies, a **handoff** for relay studies, a **subject-session sequence** for memory studies, and a **team/tenant/domain over time** for collective or platform studies. Account for correlated observations from the same operator, model, tenant, task family, or organization; do not treat every agent message as an independent sample.

### 3.2 Fair baselines

Compare against strong, tuned alternatives rather than deliberately weak controls:

- **B0 — Direct execution:** a human or agent uses existing tools without UIERU wrapping.
- **B1 — Conventional workflow/Calling Graph:** explicit steps, dependencies, retries, and logging.
- **B2 — Agent orchestration:** delegated specialist agents, tool calling, and ordinary memory.
- **B3 — Retrospective evaluator:** scoring and review after execution, without forward guidance.
- **B4 — Single-path guided agent:** same model and tools, but no multi-trail exploration.
- **B5 — One-way knowledge base:** published solutions without receiver feedback or provenance-rich relay.
- **B6 — Best practical domain baseline:** an established, appropriately tuned production workflow.

Baselines are selected per hypothesis; they need not all be run for every experiment. Equalize access to underlying models, data, tools, permissions, and compute wherever the scientific question permits. Report unavoidable differences.

### 3.3 Outcomes and costs

Record **task quality**, **success rate**, **severity-weighted failures**, **latency**, **token/compute/tool cost**, **human review time**, **authorization violations**, **calibration**, **reproducibility**, **relay fidelity**, **negative transfer**, and **rollback frequency** as relevant. A weighted utility score may be used only if weights are declared before testing and raw component metrics are also published. Report tail risks and worst-group outcomes, not merely means.

### 3.4 Design and statistical safeguards

Use randomized or counterbalanced assignments where feasible; hold out unseen tasks and domains; blind human graders to experimental arm; audit for benchmark leakage; run repeated trials across seeds; disclose model versions and environmental drift; predeclare stopping rules and multiple-comparison adjustments. Publish uncertainty intervals and effect sizes. Where randomization is impractical, document confounding and use matched or stepped-wedge designs.

### 3.5 Safety and authority

Real-world actions require the same independent authorization in all arms. Exploration runs in isolated sandboxes by default. Red-team tests use synthetic or permissioned environments. A scoring advantage never overrides a contract, legal requirement, subject consent, or organizational policy.

## 4. Core Architecture and Forward Guidance

### H01 — Selective structural containerization has positive net value in sufficiently complex tasks

**Claim.** For tasks above a prespecified coordination/uncertainty threshold, UIERU organization improves risk-adjusted outcomes relative to an equivalent ordinary workflow after accounting for setup and runtime overhead.

**Design.** Stratify tasks by dependency count, uncertainty, number of actors, and handoff frequency; randomize within strata to B1/B2 versus UIERU. Include trivial tasks as a negative-control stratum.

**Primary metric.** Risk-adjusted completed-task utility per total cost; secondary: setup time, latency, operator burden, failure severity.

**Falsifier.** No meaningful net benefit in target strata, or benefits disappear once contract, scoring, and logging overhead is counted. UIERU being worse on simple tasks is an anticipated boundary, not a reason to hide those results.

### H02 — Forward guidance improves decisions beyond retrospective scoring

**Claim.** A Scoring Forest that guides planning and online replanning produces better risk-adjusted outcomes than the same evaluator applied only after execution.

**Design.** Three arms: B3 retrospective-only; guidance at plan selection; guidance at plan selection plus online control. Hold evaluator criteria, tools, model, and budget constant.

**Primary metric.** Severity-weighted task failure rate; secondary: time to risk detection, quality, compute, intervention count.

**Falsifier.** Forward guidance does not improve held-out outcomes, causes frequent oscillation, or adds cost exceeding its benefit.

### H03 — Multi-trail search improves the quality–cost frontier

**Claim.** Under equal total resource budgets, guided Exploit/Explore/Challenge portfolios outperform single-path guided execution on tasks with meaningful alternative strategies.

**Design.** B4 versus multi-trail; match wall-clock limits and aggregate token, tool, and sandbox budgets. Include low-uncertainty tasks as controls. Compare fixed versus adaptive trail allocation.

**Primary metric.** Quality at a fixed cost and cost to reach a prespecified quality threshold; secondary: diversity of valid alternatives, tail failures.

**Falsifier.** No frontier improvement, or gains require hidden additional compute/human review. Multi-trail is not presumed useful on deterministic, low-risk tasks.

### H04 — Independent counter-evidence reduces false confidence

**Claim.** An independently tasked Challenge trail catches consequential errors that exploit-only self-review misses.

**Design.** Seed permissioned test cases with known edge conditions and genuine unknowns; compare exploit-only, same-agent self-critique, and independent challenge with blinded adjudication.

**Primary metric.** Detection recall for high-severity defects at a fixed false-alarm rate; secondary: calibration error, cost of unnecessary challenges.

**Falsifier.** Challenge trails fail to find additional material defects, or generate so many unsupported objections that downstream decisions degrade.

### H05 — Evidence-preserving folding yields better downstream decisions

**Claim.** Folding multiple trails while retaining uncertainty, failed alternatives, provenance, and counter-evidence leads to better subsequent decisions than a single winning-result summary.

**Design.** Provide downstream teams with either result-only, full raw logs, or a structured folded portfolio under equal reading-time budgets.

**Primary metric.** Accuracy of downstream acceptance/rejection and error recovery; secondary: comprehension time, omitted caveats, provenance traceability.

**Falsifier.** Structured portfolios offer no advantage over concise summaries or raw logs, or systematically conceal minority evidence.

## 5. Composition, Relay, and Collective Learning

### H06 — Contract-reconciled composition improves coordination reliability

**Claim.** Nested UIERUs with explicit authority intersections, responsibility boundaries, and perspective-aware scoring reduce coordination failures versus ad hoc orchestration.

**Design.** Compare B2 with contract-reconciled sequential, parallel, hierarchical, and federated compositions on matched complex tasks.

**Primary metric.** Cross-unit coordination failure rate; secondary: deadlocks, escalation time, unauthorized actions, completion cost.

**Falsifier.** Reconciliation overhead dominates or composition increases deadlocks, duplicated work, or authority confusion.

### H07 — Structural relay increases fidelity and transfer utility

**Claim.** Relay Portfolios containing contracts, evidence, provenance, alternatives, and unresolved residuals improve receiving-unit continuation and safe reuse over narrative-only handoffs.

**Design.** Randomize handoff format while keeping the underlying task history constant. Rotate sender and receiver teams, tools, and contexts.

**Primary metric.** Correct continuation rate without unauthorized assumptions; secondary: rework, evidence retrieval, time to localization.

**Falsifier.** No improvement after accounting for payload size, preparation effort, and receiver interpretation burden.

### H08 — Bidirectional collective learning improves cross-site adaptation

**Claim.** Receiver validation and feedback loops improve future transfer quality compared with one-way publication of structural precedents.

**Design.** Multi-team longitudinal trial: isolated teams, one-way registry, and bidirectional registry with receiver feedback. Use held-out local variations.

**Primary metric.** Validated transfer success across sites; secondary: negative transfer, time to correct precedent, local autonomy, coordination cost.

**Falsifier.** Feedback fails to improve transfer, creates correlated errors, or imposes unacceptable information-sharing overhead.

## 6. Structural Evolution and Recursive Improvement

### H09 — Residual-driven structural RSI yields sustained held-out gains

**Claim.** A governed cycle of residual discovery, candidate Structural Delta, sandbox challenge, independent validation, authorized rollout, and rollback improves future task performance beyond a frozen runtime.

**Design.** Compare a frozen baseline, ordinary prompt/workflow tuning, and governed structural RSI over sequential task waves. Reserve a final unseen evaluation set and an adversarial regression suite.

**Primary metric.** Improvement on held-out future tasks net of experimentation and governance costs; secondary: regressions, calibration, rollback success, evaluator drift.

**Falsifier.** Gains do not generalize, vanish after cost accounting, or are explained by benchmark leakage, evaluator gaming, or relaxed permissions.

**Critical boundary.** Structural RSI here means improvement of calling structures, guidance, evaluators, relay, or governance—not necessarily self-modification of foundation-model weights. Candidate improvements are not automatically authorized deployments.

## 7. Subject-Based Extensions

### H10 — Subject-indexed structural memory improves longitudinal continuity

**Claim.** Linking events to subject identity, goals, historical context, and provenance improves authorized, subject-specific recall and decision continuity compared with event-only memory.

**Design.** Synthetic and consented longitudinal tasks with multiple subjects sharing overlapping events; compare event store, ordinary retrieval memory, and subject-indexed episodic/structural memory.

**Primary metric.** Correct subject attribution and context-appropriate recall; secondary: temporal consistency, false attribution, privacy leakage, memory storage/retrieval cost.

**Falsifier.** No improvement in attribution or continuity, or greater cross-subject leakage. Functional self-indexing is not evidence of consciousness.

### H11 — Subject-indexed world models improve perspective-aware guidance

**Claim.** Explicit separation of shared world facts from subject-specific observation, embodiment, goals, and valuation improves prediction and action selection in multi-perspective tasks.

**Design.** Give agents identical shared observations but different legitimate capabilities, histories, and objectives; compare shared-only world models with subject-indexed models.

**Primary metric.** Perspective-conditioned decision correctness under hard constraints; secondary: calibration, transfer, inappropriate goal substitution.

**Falsifier.** Subject indexing does not improve decisions or introduces systematic bias and identity confusion.

**Scientific caveat.** Childhood amnesia and self-development motivate questions but do not establish a single causal explanation or prove an AI architectural analogue.

## 8. Big-Animal and Sovereign Ecosystem Extensions

### H12 — Platform-level structural RSI transfers safely across domains

**Claim.** Validated cross-task structural precedents improve multiple domain UIERUs beyond isolated local optimization, without unacceptable negative transfer.

**Design.** Platform simulation or permissioned multi-tenant pilot: local-only improvement versus global candidate registry with domain-specific validation gates.

**Primary metric.** Weighted held-out gain across domains with a prespecified cap on worst-domain regression; secondary: rollout time, compute, incident frequency, rollback effectiveness.

**Falsifier.** Apparent aggregate gain masks significant domain regressions, or registry and governance costs exceed improvements.

### H13 — Distributed scoring governance protects heterogeneous objectives

**Claim.** A global policy plane combined with local subject/tenant scoring improves legitimate objective satisfaction and conflict handling compared with a single global utility score.

**Design.** Simulate heterogeneous tenants and policy constraints; compare centralized scalar scoring, unconstrained local scoring, and governed distributed scoring.

**Primary metric.** Hard-constraint compliance and worst-tenant utility; secondary: aggregate utility, conflict resolution latency, auditability.

**Falsifier.** Distributed scoring increases policy violations, unresolved conflicts, or severe inequity without offsetting benefits.

### H14 — Sovereign relay preserves utility with less unnecessary exposure

**Claim.** Purpose-limited, provenance-aware, receiver-validated structural exchange retains useful collective learning while reducing unauthorized disclosure and authority confusion.

**Design.** Compare blanket data sharing, no sharing, and selective structural relay in synthetic or explicitly consented multi-tenant settings. Use adversarial attempts to elicit restricted information.

**Primary metric.** Transfer utility at a fixed privacy/authorization-violation threshold; secondary: data minimization, revocation handling, receiver-localization success.

**Falsifier.** Selective relay leaks sensitive content, cannot honor restrictions, or produces negligible utility compared with simpler controls.

## 9. Interoperability and System-Level Hypotheses

### H15 — Standardized contracts reduce integration and migration effort

**Claim.** A canonical UIERU contract and relay envelope reduce integration effort across heterogeneous agents, tools, and organizational boundaries relative to custom point-to-point adapters.

**Design.** Independent teams implement the same tasks across a matrix of runtimes using either bespoke integrations or published contract profiles. Include schema evolution and version mismatches.

**Primary metric.** Engineer-hours to achieve validated interoperability; secondary: conformance defects, compatibility breaks, runtime overhead.

**Falsifier.** Contract complexity offsets integration savings or requires excessive vendor-specific exceptions.

### H16 — End-to-end UIERU offers net value in its target operating region

**Claim.** For a preregistered region of high-uncertainty, multi-actor, evidence-sensitive tasks, the integrated architecture outperforms the best-matched non-UIERU baseline on a multi-objective quality/cost/risk frontier.

**Design.** Multi-site trial with staged ablations: contract only; +forward guidance; +multi-trail; +relay; +governed evolution. Include B6, equal budgets, and independent auditors.

**Primary metric.** Pareto improvement across quality, total cost, and severity-weighted risk, with no unacceptable hard-constraint regression.

**Falsifier.** No robust advantage on held-out tasks, or a simpler subset matches the full architecture. If so, prefer the simpler architecture and revise UIERU's recommended deployment boundary.

## 10. Ablation and Causal Attribution Matrix

| Experimental removal | What it isolates | Key confound to control |
|---|---|---|
| Remove forward guidance, retain post-hoc evaluator | Planning/control value of F | Evaluator quality |
| Remove Explore/Challenge trails | Incremental search value | Total compute budget |
| Remove counter-evidence retention | Value of negative evidence | Portfolio length |
| Replace relay portfolio with narrative | Value of structural handoff | Receiver reading time |
| Disable receiver feedback | Bidirectional learning value | Knowledge-base freshness |
| Freeze Structural Delta deployment | Evolution value | Additional training data |
| Remove Subject Index Plane | Identity/history attribution value | Retrieval capacity |
| Replace local scoring with global scalar | Sovereignty/governance value | Policy constraint set |

The full UIERU must not receive credit for improvements that are attributable solely to more compute, more human reviewers, larger context windows, better base models, or relaxed permissions.

## 11. Preregistration Template

Each study should publish a record before held-out evaluation:

```yaml
study_id: UIERU-H03-PILOT-001
hypothesis_id: H03
status: proposed
research_question: "Does multi-trail guidance improve quality at equal cost?"
unit_of_analysis: task_instance
population: "Permissioned software-engineering tasks with alternative solutions"
assignment: randomized_within_task_stratum
arms:
  - single_path_guided
  - multi_trail_guided
controls:
  base_model: identical
  tools_and_permissions: identical
  aggregate_compute_budget: matched
  human_review_budget: matched
primary_outcome: quality_at_fixed_total_cost
secondary_outcomes:
  - severity_weighted_failure_rate
  - time_to_valid_solution
  - counter_evidence_yield
minimum_effect_of_interest: "Set before test; context-specific"
sample_size_and_power: "Specify before test"
analysis_plan: "Specify estimator, clustering, uncertainty, multiplicity"
stopping_rule: "Predeclared; no opportunistic stopping"
held_out_set: "Frozen and access-controlled"
independent_evaluator: required
safety_boundary: "Sandbox-only until authorized"
report_negative_results: true
```

## 12. Reporting Standard and Evidence Grades

For every study, report: dataset/task construction, assignment, model and tool versions, prompts and scoring policies where shareable, resource accounting, sample sizes, confidence/credible intervals, adverse outcomes, subgroup effects, failed trials, and protocol deviations. Distinguish **engineering feasibility**, **controlled performance improvement**, **external replication**, and **operational reliability**.

Suggested evidence grades:

- **E0 — Proposed:** coherent hypothesis; no relevant experiment.
- **E1 — Feasibility:** demonstrator and conformance tests; no comparative performance claim.
- **E2 — Controlled comparison:** preregistered, held-out baseline comparison.
- **E3 — Independent replication:** reproduced across independent implementations or sites.
- **E4 — Operational validation:** sustained deployment with cost, risk, and drift monitoring.

An E1-compliant implementation must not be described as empirically superior. Claims should specify the measured task distribution and evidence grade.

## 13. Decision Gates

1. **G1 — Minimal value:** Is there a task class where UIERU's net benefit exceeds overhead?
2. **G2 — Guidance causality:** Does forward guidance outperform retrospective evaluation at matched resources?
3. **G3 — Exploration safety:** Do multi-trail and counter-evidence improve outcomes without unacceptable cost or risk?
4. **G4 — Relay integrity:** Can independent receivers reuse structures without silently inheriting unauthorized assumptions?
5. **G5 — Evolution validity:** Do governed Structural Deltas improve unseen future tasks and remain reversible?
6. **G6 — Ecosystem governance:** Can subject sovereignty, platform coordination, and collective learning coexist under enforceable boundaries?

A failed gate should narrow or revise the architecture rather than trigger an unqualified claim of universal applicability.

## 14. Recommended Validation Sequence

**Phase A — Minimal task and contract:** [CASE-001](cases/CASE-001-Neighborhood-Lawn-Service-as-a-Minimal-UIERU.md), [SPEC-001](specs/SPEC-001-Canonical-UIERU-Contract-and-Schema.md); H01, H15.

**Phase B — Guidance and adversarial search:** [CASE-002](cases/CASE-002-Multi-Agent-Software-Engineering-and-Multi-Trail-Sandboxes.md), [SPEC-002](specs/SPEC-002-Forward-Guidance-and-Multi-Trail-Lifecycle.md); H02–H05.

**Phase C — Composition and relay:** [SPEC-003](specs/SPEC-003-Structural-Relay-and-Portfolio-Exchange.md), [SPEC-004](specs/SPEC-004-Composition-Evolution-and-Conformance.md); H06–H08, H15.

**Phase D — Governed structural RSI:** [UIERU-009](docs/UIERU-009-Residual-Driven-Structural-Evolution-and-Recursive-Improvement.md); H09, H16.

**Phase E — Subject and platform extensions:** [EXT-001](docs/extensions/UIERU-EXT-001-Subject-Indexed-World-Models-and-Structural-Memory.md), [EXT-002](docs/extensions/UIERU-EXT-002-Big-Animal-Intelligence-Organization-and-Platform-Level-Structural-RSI.md), [EXT-003](docs/extensions/UIERU-EXT-003-Subject-Sovereignty-and-Collective-Intelligence-Ecosystems.md); H10–H14.

## 15. Open Failure Conditions

The UIERU research program should explicitly seek and report cases in which:

- A conventional workflow is simpler, cheaper, safer, or more reliable.
- Forward scoring amplifies metric gaming, evaluator capture, or Goodhart effects.
- Multi-trail exploration increases noise, latency, or dangerous coordination complexity.
- Folding suppresses minority evidence or hides uncertainty.
- Relay loses provenance, context, consent, or local applicability.
- Structural RSI overfits benchmarks or causes cascading regressions.
- Subject indexing misattributes memories or leaks one subject's information to another.
- Platform-wide precedents propagate common-mode failures.
- Central governance suppresses legitimate local perspectives, or local autonomy undermines hard global constraints.

These are not peripheral exceptions; they define the operating boundary of a credible UIERU architecture.

## 16. Conclusion

The principal UIERU proposition is not that every intelligence task needs another wrapper. It is that **governed Calling Paths, forward-guiding Scoring Forests, multi-trail evidence, structural relay, and validated evolution** may form a reusable organizational intelligence unit in task environments where coordination, uncertainty, provenance, and learning matter.

Its value must be earned experimentally. The strongest result may be a **selective deployment rule**: where UIERU is useful, which components are necessary, and where conventional approaches should remain preferred.

**Research maxim:** *A structural change is a candidate improvement; only independent evidence can establish an intelligence improvement.*

---

**Authors:** Sizhe Tan & GPT-Obot  
**Version:** v1.0.0  
**Related:** [README.md](README.md) · [CONTENTS.md](CONTENTS.md) · [OPEN-QUESTIONS.md](OPEN-QUESTIONS.md) · [VALIDATION-ROADMAP.md](VALIDATION-ROADMAP.md)
