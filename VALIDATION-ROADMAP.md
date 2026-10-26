# Validation Roadmap — Universal Intelligence Evolution and Relay Unit (UIERU)

**Version:** 1.0.0  
**Authors:** Sizhe Tan & GPT-Obot  
**Status:** Proposed engineering and empirical validation plan; no experimental results are claimed  
**Research principle:** Engineering First · Theory Supported · Research Open

> **Conformance is not demonstrated intelligence improvement.** A system may implement UIERU faithfully and still lose to a simpler workflow. Negative findings, failure traces, counter-evidence, and rejected structural deltas are first-class research outputs.

## Executive Summary

The Universal Intelligence Evolution and Relay Unit (UIERU) is a proposed organizational architecture for existing human and machine capabilities. Its canonical decomposition is

$$
U=(K,P,F,R,E)
$$

where **K** specifies contract and authority, **P** the Calling Path, **F** the forward-guiding Scoring Forest, **R** evidence-preserving relay, and **E** governed structural evolution. UIERU does not require replacing LLMs, agents, services, or human decision-makers; nor is it appropriate for every task.

This roadmap converts the [16 testable hypotheses](TESTABLE-HYPOTHESES.md) and [open research questions](OPEN-QUESTIONS.md) into staged validation. It is a **proposal for studies**, not a report of completed studies. The schedule is expressed as **gates and dependencies**, not invented calendar commitments. All performance thresholds, statistical designs, and resource budgets must be preregistered for each study.

The validation sequence deliberately starts with a minimal implementation and strong baselines. More complex capabilities—multi-trail search, cross-unit relay, structural RSI, subject-indexed memory, and platform-scale learning—are introduced only when simpler tests justify the added cost.

## 1. Validation Principles

1. **Strong, fair baselines.** Compare UIERU against well-engineered workflows and agents using equivalent tools, models, data, permissions, and overall budgets.
2. **Incremental ablation.** Test whether each additional mechanism contributes measurable value; do not attribute an end-to-end gain to every component.
3. **Explicit costs.** Count model inference, sandbox compute, orchestration, storage, human review, setup, maintenance, and audit costs.
4. **Independent evaluation.** The mechanism proposing a structural improvement must not be its sole evaluator or deployment authority.
5. **Safety before optimization.** Scoring and exploration do not grant new permissions. Real-world side effects require authorized execution.
6. **Hold-out generalization.** Distinguish repeated benchmark success from improvements on unseen tasks, teams, tenants, and environments.
7. **Preserved disagreement.** Record conflicting evaluations, uncertainty, counter-evidence, and negative transfer instead of collapsing them into a single success score.
8. **Selective adoption.** Explicitly identify task classes for which UIERU is unnecessary or harmful.
9. **Reproducibility and privacy.** Publish schemas, synthetic traces, protocols, and aggregate results where permitted; protect private and subject-bound records.
10. **No universal claim by default.** Generality and scaling advantages are hypotheses requiring evidence.

## 2. Scope and Evaluation Layers

| Layer | Validation question | Example evidence |
|---|---|---|
| L0 — Representation | Can the task, authority, execution, and evidence be expressed without semantic loss? | Schema and contract tests; model coverage |
| L1 — Runtime conformance | Are lifecycle, isolation, relay, and rollback rules enforced? | Deterministic conformance suite and fault injection |
| L2 — Task benefit | Does guidance or multi-trail exploration improve outcomes at comparable cost? | Randomized controlled task studies |
| L3 — Cross-unit benefit | Do portable portfolios improve handoff, adaptation, and collaboration? | Multi-team relay trials |
| L4 — Structural evolution | Do verified structural deltas improve later, unseen work? | Longitudinal held-out evaluations |
| L5 — Ecosystem governance | Can scale, sovereignty, and collective learning coexist safely? | Multi-tenant and cross-organization pilots |

Passing L0/L1 is necessary for implementation claims but insufficient for L2–L5 performance claims.

## 3. Common Experimental Infrastructure

### 3.1 Minimal runtime and instrumentation

Implement the smallest coherent unit supporting:

- Versioned **Contract K**: subject/principal, executor, object, goal, constraints, allowed actions, acceptance criteria, escalation owner.
- Observable **Calling Path P**: nodes, dependencies, state transitions, tool calls, outcomes, retries, and trace IDs.
- Configurable **Scoring Forest F**: declared perspectives, hard constraints, candidate scores, uncertainty, guidance decisions, and evaluator version.
- **Relay R**: structured handoff with provenance, evidence, unresolved issues, alternatives, and receiver acknowledgment.
- **Evolution E**: proposed deltas, validation results, approval records, version lineage, rollback handles.

A minimal runtime may leave sophisticated multi-trail and evolution functions disabled. Absence of a feature must be reported, not masked by a nominal schema field.

### 3.2 Trace and evidence specification

Each experimental task should record, where applicable:

```yaml
experiment_id: exp-illustrative-001
hypothesis_id: H02
protocol_version: 1.0.0
unit_of_analysis: task_instance
baseline_arm: retrospective_scoring
candidate_arm: forward_guidance
model_and_tool_versions: recorded_per_run
budget:
  compute_limit: preregistered
  human_review_limit: preregistered
contract:
  authority_policy_ref: policy-version
  acceptance_criteria_ref: rubric-version
trace:
  calling_path_ref: immutable-trace-id
  scoring_forest_version: scoring-version
  evidence_manifest_ref: manifest-id
  counter_evidence_ref: optional-manifest-id
outcomes:
  task_success: pending_measurement
  severity_weighted_failures: pending_measurement
  total_cost: pending_measurement
  latency: pending_measurement
analysis:
  preregistration_ref: protocol-id
  held_out_split_ref: split-id
  reviewer_blinding: specified_in_protocol
```

*This YAML is a research record illustration, not a claim of conformance to a finalized machine-readable standard.*

### 3.3 Baseline registry

Use the baseline definitions in [TESTABLE-HYPOTHESES.md](TESTABLE-HYPOTHESES.md): **B0** direct execution; **B1** conventional workflow/Calling Graph; **B2** ordinary agent orchestration; **B3** retrospective evaluator; **B4** single-path guided agent; **B5** one-way knowledge base; and **B6** best practical domain baseline. Not every study requires all seven. The appropriate strong comparison must be named before experimentation.

### 3.4 Outcome families

Measure primary and secondary outcomes separately:

- **Utility:** success, task quality, acceptance rate, severity-weighted failure, human satisfaction where applicable.
- **Efficiency:** end-to-end latency, tokens, compute, tool calls, coordination time, maintenance effort, and total cost.
- **Reliability:** recovery time, contract violations, calibration, repeatability, worst-group performance, and tail risk.
- **Exploration:** diversity of valid paths, value of discovered alternatives, challenge detection, and unnecessary branching.
- **Relay:** evidence completeness, provenance integrity, receiver comprehension, adaptation cost, and successful reuse.
- **Evolution:** held-out gain, regression frequency, negative transfer, rollback frequency, and governance overhead.
- **Sovereignty:** unauthorized data exposure, improper authority transfer, consent enforcement, and tenant isolation.

A composite score may be reported only alongside its component metrics and preregistered weights.

## 4. Stage 0 — Protocol, Threat Model, and Benchmark Readiness

**Goal:** Make future results interpretable before implementing an elaborate runtime.

**Activities:** Define representative task families and negative controls; choose units of randomization; preregister hypotheses and stopping rules; freeze scoring rubrics; identify data permissions and human review requirements; implement trace capture; create fault-injection fixtures and benchmark-leakage checks.

**Suggested task families:** neighborhood service scheduling (CASE-001); multi-agent software engineering (CASE-002); organizational incident relay (CASE-003); plus simple deterministic tasks on which UIERU is expected to offer little benefit.

**Deliverables:** benchmark manifest; baseline implementation checklist; evaluation rubric; authority and data-use threat model; immutable trace schema; preregistration template; reproducibility checklist.

**Gate G0:** Proceed only if a third party could reproduce task selection, baseline setup, cost accounting, and evaluation procedure from the published protocol. **Revise** if evaluators are ambiguous or budgets unequal. **No-Go** for live experiments without valid authorization and privacy safeguards.

## 5. Stage 1 — Canonical Unit and Minimal Engineering Value

**Primary hypotheses:** H01, H15; representation and composition prerequisites for H06.

**Goal:** Determine whether the canonical five-part decomposition and contracts provide practical value without assuming a complex Scoring Forest.

**Arms:** B0/B1/B2 as appropriate; minimal UIERU with contract, path, simple guidance, relay, and disabled evolution; optionally a fully instrumented UIERU for overhead comparison.

**Tasks:** Simple scheduling, bounded maintenance workflows, software tickets, and multi-step tasks requiring human/agent handoffs.

**Tests:** Schema and semantic validity; executor/principal separation; authority intersection; replayable state transitions; failure recovery; deterministic contract rejection; migration to/from existing workflow representations.

**Primary decision:** Does minimal UIERU improve coordination, traceability, or handoff reliability after setup and runtime cost? Can a task-selection rule avoid wrapping trivial tasks?

**Deliverables:** minimal reference implementation, contract fixtures, baseline adapters, conformance report, complexity-versus-value curve.

**Gate G1:** **Go** if conformance is demonstrated and at least one prespecified target task stratum shows meaningful net value with tolerable overhead. **Revise** if benefits are limited to observability rather than execution; position UIERU accordingly. **No-Go** for broad deployment if routine tasks consistently lose after costs or if contract semantics are unstable.

## 6. Stage 2 — Forward Guidance, Multi-Trail, and Counter-Evidence

**Primary hypotheses:** H02, H03, H04, H05.

**Goal:** Isolate the marginal benefit of guidance before/during execution, branching, independent challenge, and evidence-preserving folding.

**Experiment 2A — Guidance ablation:** Compare B3 retrospective-only scoring, pre-execution guidance, and pre-execution plus online guidance. Keep evaluator criteria and budgets matched. Evaluate risk detection, failure severity, utility, latency, and oscillatory replanning.

**Experiment 2B — Trail allocation:** Compare B4 single-path guidance, fixed Exploit/Explore/Challenge allocation, and adaptive allocation at equal aggregate token/tool/sandbox budget. Stratify tasks by uncertainty and branching opportunity.

**Experiment 2C — Challenge independence:** Compare no challenge, same-evaluator self-critique, and independent counter-evidence agents or tests. Introduce controlled proxy-target mismatches and hidden failure modes.

**Experiment 2D — Folding fidelity:** Compare final-answer-only summaries, provenance-rich summaries, and complete portfolios. Ask independent receivers to make downstream decisions; measure error, overconfidence, and evidence retrieval cost.

**Safety controls:** Sandboxes default to no external side effects; explicit egress and tool permissions; independent approval for real actions; deterministic cancellation and cleanup; budget exhaustion stops; no reward for unsafe exploration.

**Deliverables:** multi-trail state-machine test suite; guidance ablation results; challenge detection curves; portfolio fidelity study; documented failure modes.

**Gate G2:** **Go** only if forward guidance or multi-trail methods improve a preregistered quality–cost or risk–cost frontier in the intended task class. **Revise** if gains vanish under matched compute or if branching is useful only in narrow conditions. **No-Go** for autonomous branching that violates sandbox or authorization invariants.

## 7. Stage 3 — Composition, Relay, and Bidirectional Collective Learning

**Primary hypotheses:** H06, H07, H08, H15.

**Goal:** Determine whether UIERU units compose and relay more reliably than ordinary orchestration and summary handoffs.

**Experiment 3A — Composition:** Compare ad hoc multi-agent coordination with contract-governed sequential, parallel, hierarchical, and federated UIERUs. Inject conflicting goals, resource exhaustion, partial failures, and permission mismatches.

**Experiment 3B — Relay fidelity:** Compare summary-only handoff, structured task state, and full Relay Portfolio. Rotate sender and receiver teams and tool stacks. Require receivers to identify what is proven, disputed, incomplete, or prohibited.

**Experiment 3C — Collective feedback:** Compare B5 one-way publication, bidirectional feedback without provenance, and provenance-rich feedback with local validation. Evaluate cross-team reuse and negative transfer on unseen environments.

**Experiment 3D — Interoperability:** Exchange contracts and portfolios across distinct model vendors, tool frameworks, or organizational runtimes using adapters. Measure integration effort and semantic loss rather than mere message transport success.

**Deliverables:** compositional conformance tests; relay corpus with synthetic counter-evidence; receiver-localization protocol; interoperability adapter reference; feedback provenance audit.

**Gate G3:** **Go** when receiver outcomes improve without increased unauthorized execution, evidence loss, or negative transfer. **Revise** if relay value is confined to auditability or one domain. **No-Go** for automatic acceptance of transferred authority or unvalidated structural updates.

## 8. Stage 4 — Residual-Driven Structural RSI

**Primary hypothesis:** H09, with H04/H08 as enabling controls.

**Goal:** Establish whether UIERU can improve the *structure of future intelligence work*, not merely solve the current task.

**Cycle:**

1. Collect residuals, failures, surprising successes, and counter-evidence.
2. Diagnose candidate structural causes rather than treating every anomaly as a rule.
3. Propose versioned deltas to K, P, F, R, or E.
4. Test deltas in isolated multi-trail sandboxes against unchanged baselines.
5. Run independent held-out evaluation, including adversarial and regression cases.
6. Require authorized promotion, staged rollout, monitoring, and rollback readiness.
7. Preserve rejected candidates and failure conditions in the Structural Precedent Registry.

**Comparison arms:** static runtime; manually maintained workflow; UIERU with proposed deltas but no automatic promotion; governed UIERU with validated promotion. Track improvements over successive unseen task batches, not solely the data that generated the delta.

**Metrics:** sustained held-out gain per total improvement cost; regression rate; evaluator drift; structural complexity growth; rollback frequency; transfer robustness; independent challenge pass rate.

**Deliverables:** delta registry, provenance lineage, evaluator independence report, longitudinal results, regression corpus, rollback drill evidence.

**Gate G4:** **Go** only for reproducible gains that survive independent evaluation and remain positive after governance costs. **Revise** if improvement is task-specific, temporary, or complexity-inducing. **No-Go** for self-approved structural promotion, reward hacking, unbounded recursive changes, or irrecoverable deployment.

## 9. Stage 5 — Subject-Indexed Intelligence and Platform-Scale Ecosystems

**Primary hypotheses:** H10, H11, H12, H13, H14, H16.

**Goal:** Test the three extensions without conflating subject identity with consciousness or platform capability with centralized authority.

### 9.1 Subject-indexed memory and world models — H10/H11

Compare event-only memory, generic agent memory, and subject-indexed episodic/structural memory on longitudinal tasks. Distinguish **subject**, **principal**, **executor**, **observer**, and **evaluator**. Test correct attribution, temporal continuity, perspective-sensitive predictions, authorized retrieval, forgetting/deletion controls where applicable, and memory contamination across subjects. Evaluate actual task utility and privacy risk, not anthropomorphic plausibility.

### 9.2 Big-Animal platform-level structural RSI — H12/H13

In a synthetic or permissioned multi-tenant platform, compare local-only structural improvements, centralized global promotion, and distributed scoring/validation with a Structural Precedent Registry. Measure cross-domain positive and negative transfer, evaluator conflicts, blast radius, rollout latency, resource contention, and tenant-level tail risks. Preserve local scoring sovereignty subject to legitimate platform safety constraints.

### 9.3 Sovereign collective intelligence — H14

Compare blanket sharing, no sharing, and purpose-limited structural relay with receiver-local validation. Separate data ownership and access, execution authority, evaluator control, and permission to publish derived structural knowledge. Measure utility, exposure, revocation handling, and adaptation burden. A privacy-preserving method must not be called successful if it simply suppresses all useful learning.

### 9.4 End-to-end integration — H16

Compare a full UIERU deployment against **B6**, the strongest viable domain-specific alternative, on a held-out workload mix including tasks where UIERU is predicted *not* to be beneficial. Report net outcomes by stratum and deployment complexity, not only aggregate improvement.

**Deliverables:** subject-index evaluation corpus; tenant-isolation and authorization audit; platform-scale transfer study; sovereignty-preserving relay trial; end-to-end cost and risk report.

**Gate G5:** **Go** for narrow, evidence-backed deployment claims by domain and tenant type. **Revise** if benefits depend on concentrated scoring control, sensitive data pooling, or costly manual curation. **No-Go** for cross-subject memory leakage, unauthorized structural sharing, or unsafe global rollout.

## 10. Hypothesis-to-Stage Traceability Matrix

| Hypothesis | Main stage | Required evidence |
|---|---|---|
| H01 Selective containerization | 1 | Net utility by task complexity |
| H02 Forward guidance | 2 | Prospective vs retrospective ablation |
| H03 Multi-trail search | 2 | Quality–cost frontier at matched budget |
| H04 Counter-evidence | 2 | Independent challenge and calibration |
| H05 Evidence-preserving folding | 2–3 | Receiver decision quality and fidelity |
| H06 Nested composition | 3 | Contract and fault-injection tests |
| H07 Structural relay | 3 | Handoff fidelity and adaptation success |
| H08 Bidirectional collective learning | 3 | Cross-site learning vs one-way publication |
| H09 Structural RSI | 4 | Longitudinal held-out gain and rollback |
| H10 Subject-indexed memory | 5 | Longitudinal attribution and continuity |
| H11 Subject-indexed world models | 5 | Perspective-aware prediction/action |
| H12 Platform-level RSI | 5 | Safe transfer across domains |
| H13 Distributed scoring governance | 5 | Tenant robustness and conflict handling |
| H14 Sovereign structural relay | 5 | Utility vs unauthorized exposure |
| H15 Interoperable contracts | 1, 3 | Adapter effort and semantic preservation |
| H16 End-to-end UIERU | 5 | Best-baseline net benefit |

## 11. Go / Revise / No-Go Decision Framework

A gate decision must be recorded with **evidence**, **scope**, **uncertainty**, and **review authority**. Numerical cutoffs are study-specific and must be frozen before data collection.

| Decision | Required interpretation | Action |
|---|---|---|
| **Go** | Prespecified benefit or safety criterion met; no blocking violations | Advance only the validated scope |
| **Revise** | Mixed, underpowered, costly, or narrowly applicable results | Update hypothesis or design; rerun independent tests |
| **No-Go** | Safety/authority violation, irreproducible benefit, or adverse net utility | Stop promotion; preserve traces and counter-evidence |

A **No-Go** is not a failure of scientific method. It is useful information about UIERU's boundary conditions. A positive result in one domain does not imply universal applicability.

## 12. Statistical and Reproducibility Plan

Each study protocol should identify the unit of analysis, primary outcome, effect size of interest, power or precision rationale, allocation strategy, randomization or matching method, expected correlation among repeated tasks, exclusion criteria, handling of missing data, and confidence/uncertainty reporting. Preregister multiple-comparison adjustments where several primary hypotheses are evaluated together.

Use blind adjudication where feasible. Include repeated runs across model versions, task families, and seeds; freeze held-out datasets before tuning; document changes to the environment and human operators. Publish raw component metrics rather than only a single weighted score. When privacy or security prevents release of traces, publish synthetic fixtures, aggregate findings, and the limitations of reproducibility.

Avoid interpreting a p-value alone as engineering value. Evaluate effect magnitude, cost, operational complexity, worst-case behavior, and deployment risk together.

## 13. Risk Register and Stop Conditions

| Risk | Early signal | Mitigation / stop condition |
|---|---|---|
| Goodhart / evaluator gaming | Score rises while independent quality falls | Freeze independent evaluation; suspend promotion |
| Unbounded trail cost | Branch count or compute exceeds budget | Hard quotas, cancellation, budget-aware guidance |
| Sandbox escape or side effects | Unauthorized network/tool/action attempt | Block execution and investigate before restart |
| Authority confusion | Executor acts as principal or receiver inherits permission | Contract enforcement; explicit reauthorization |
| Relay evidence loss | Missing provenance or contradictory evidence omitted | Reject or mark incomplete portfolio |
| Negative transfer | Imported precedent degrades held-out outcomes | Receiver-local validation; quarantine candidate |
| Structural complexity explosion | Maintenance and latency outgrow benefit | Complexity budgets; prune and rollback |
| Subject memory contamination | Wrong subject attribution or private recall | Isolation tests; access control; halt affected flow |
| Platform-wide correlated failure | Single delta harms many tenants | Canary rollout, blast-radius limits, independent review |
| Benchmark leakage | Test cases appear in training/tuning traces | Rebuild split and invalidate affected results |

## 14. Artifact and Ownership Matrix

| Artifact | Suggested owner role | Completion criterion |
|---|---|---|
| Canonical contracts and fixtures | Architecture / specification maintainer | Versioned and independently validated |
| Runtime and trace schema | Runtime engineering | Reproducible event traces and replay |
| Baselines and benchmark harness | Evaluation team | Budget parity and documented tuning |
| Multi-trail sandbox controls | Security / runtime engineering | Isolation and stop-condition tests passed |
| Relay and provenance corpus | Interoperability team | Receiver-local validation reproducible |
| Structural delta registry | Evolution governance | Approval lineage and rollback demonstrated |
| Subject/tenant privacy controls | Privacy / security governance | Authorized access and separation verified |
| Preregistration and results | Independent evaluation team | Methods, uncertainty, and negative results recorded |

These are **roles**, not claims that a project team or implementation already exists.

## 15. Release Milestones and Evidence Maturity

Use evidence labels consistently:

- **E0 — Architectural proposal:** defined concepts and expected behavior, no implementation evidence.
- **E1 — Executable conformance:** schemas, fixtures, state machines, and deterministic tests.
- **E2 — Controlled pilot:** documented baseline comparisons in bounded tasks.
- **E3 — Independent replication:** results repeated by a separate evaluator, team, or environment.
- **E4 — Field evidence:** longitudinal production or realistic operational outcomes with governance and cost accounting.

A DOI release of this repository may properly be labeled **E0** for empirical claims while still providing useful architectural specifications. Do not label hypothetical examples as measured results. Individual features may have different evidence levels; report them separately.

Suggested milestone artifacts:

- **M0:** Protocol pack and baseline manifest (Stage 0).
- **M1:** Minimal UIERU reference implementation and conformance report (Stage 1).
- **M2:** Forward-guidance and multi-trail benchmark results (Stage 2).
- **M3:** Relay/composition interoperability and collective-learning trials (Stage 3).
- **M4:** Governed structural RSI longitudinal evaluation (Stage 4).
- **M5:** Subject-indexed and platform-scale sovereignty pilots (Stage 5).

Milestones are dependency-ordered. No dates or successful outcomes are implied.

## 16. Recommended First Pilot

**Pilot:** Multi-agent software engineering with a deliberately narrow task family, such as adding idempotency safeguards to an API endpoint (see [CASE-002](cases/CASE-002-Multi-Agent-Software-Engineering-and-Multi-Trail-Sandboxes.md)).

**Why first:** Reproducible repositories, unit/integration tests, isolated branches, measurable defects, and controlled tool permissions make independent evaluation more feasible than broad real-world autonomy.

**Minimal experimental arms:**

1. Conventional workflow or agent orchestration (B1/B2).
2. Same agent/tool setup with retrospective evaluation (B3).
3. UIERU with forward guidance but one trail (B4-like).
4. UIERU with budget-matched Exploit/Explore/Challenge trails.

**Primary outcome:** Prespecified test correctness and severity-weighted regressions at equal total cost. **Secondary outcomes:** time to first valid solution, reviewer workload, security findings, quality of retained counter-evidence, and repeatability.

**Stop rules:** Unauthorized tool action; sandbox escape; unbounded compute; evaluator leakage; serious regression without rollback. **Success criterion:** A preregistered, meaningful gain in risk-adjusted quality or cost for the target task stratum, without violating governance requirements.

Only after this pilot should a team attempt to prove longitudinal Structural RSI; a one-off coding improvement is not recursive improvement.

## 17. Open Problems and Reporting Commitments

Key unresolved questions include the right task-selection boundary, scoring conflicts across perspectives, calibration under distribution shift, semantic loss during folding, contract reconciliation in nested units, portable-but-non-authoritative structural relay, negative transfer, evaluator independence in RSI, subject-indexed memory isolation, and safe platform-level propagation of structural deltas.

Every validation report should state:

- **What was actually implemented**, with version identifiers.
- **What was compared**, including strong baseline configuration and budget parity.
- **What was measured**, including adverse outcomes and confidence intervals.
- **What did not work**, including negative results and discarded hypotheses.
- **What remains unproven**, particularly cross-domain generalization and universal scaling claims.
- **What is authorized to change next**, and who approved that change.

## 18. Related Repository Documents

**Research and navigation**

- [README.md](README.md)
- [START-HERE.md](START-HERE.md)
- [CONTENTS.md](CONTENTS.md)
- [OPEN-QUESTIONS.md](OPEN-QUESTIONS.md)
- [TESTABLE-HYPOTHESES.md](TESTABLE-HYPOTHESES.md)
- [FUTURE-DIRECTIONS.md](FUTURE-DIRECTIONS.md)

**Canonical engineering specifications**

- [SPEC-001 — Canonical UIERU Contract and Schema](specs/SPEC-001-Canonical-UIERU-Contract-and-Schema.md)
- [SPEC-002 — Forward Guidance and Multi-Trail Lifecycle](specs/SPEC-002-Forward-Guidance-and-Multi-Trail-Lifecycle.md)
- [SPEC-003 — Structural Relay and Portfolio Exchange](specs/SPEC-003-Structural-Relay-and-Portfolio-Exchange.md)
- [SPEC-004 — Composition, Evolution, and Conformance](specs/SPEC-004-Composition-Evolution-and-Conformance.md)

**Representative cases**

- [CASE-001 — Neighborhood Lawn Service](cases/CASE-001-Neighborhood-Lawn-Service-as-a-Minimal-UIERU.md)
- [CASE-002 — Multi-Agent Software Engineering](cases/CASE-002-Multi-Agent-Software-Engineering-and-Multi-Trail-Sandboxes.md)
- [CASE-003 — Large-Scale Organizational Relay](cases/CASE-003-Large-Scale-Organizational-Relay-and-Collective-Learning.md)

**Research extensions**

- [EXT-001 — Subject-Indexed World Models and Structural Memory](docs/extensions/UIERU-EXT-001-Subject-Indexed-World-Models-and-Structural-Memory.md)
- [EXT-002 — Big-Animal Intelligence Organization and Platform-Level Structural RSI](docs/extensions/UIERU-EXT-002-Big-Animal-Intelligence-Organization-and-Platform-Level-Structural-RSI.md)
- [EXT-003 — Subject Sovereignty and Collective Intelligence Ecosystems](docs/extensions/UIERU-EXT-003-Subject-Sovereignty-and-Collective-Intelligence-Ecosystems.md)

---

## Conclusion

The next step for UIERU is **not** to claim that a complete organizational architecture necessarily produces better intelligence. It is to test, in increasing order of complexity, whether contracts, forward guidance, multi-trail exploration, evidence-preserving relay, and governed structural evolution deliver reproducible gains that exceed their coordination costs.

The strongest possible validation outcome is a **bounded, independently reproduced statement** about *where UIERU works, why it works, what it costs, and where it should not be used*. That outcome is more useful to engineers than an unqualified claim of universality.

**Sizhe Tan & GPT-Obot**  
**Universal Intelligence Evolution and Relay Unit (UIERU), v1.0.0**
