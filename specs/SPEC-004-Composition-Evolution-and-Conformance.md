# SPEC-004 — Composition, Evolution, and Conformance

**Project:** Universal Intelligence Evolution and Relay Unit (UIERU)  
**Version:** 1.0.0  
**Status:** Proposed research specification  
**Authors:** Sizhe Tan & GPT-Obot  
**License:** Apache-2.0 (subject to repository licensing)  
**Companion specifications:** SPEC-001, SPEC-002, SPEC-003

> **Engineering First · Theory Supported · Research Open**  
> This specification is self-contained at the architectural level. Its normative rules are proposals for implementation and testing, not claims of an established external standard.

## Abstract

A Universal Intelligence Evolution and Relay Unit (UIERU) coordinates an execution path, a forward-guiding scoring structure, relayable evidence, and governed structural evolution under an explicit contract. This specification defines how units may be composed and nested without silently expanding authority; how multi-perspective evaluations may be folded while preserving conflicts and counter-evidence; how structural modifications are proposed, tested, approved, deployed, and rolled back; and how implementations can demonstrate conformance. The central requirement is **governed compositional growth**: larger systems may be assembled from smaller intelligence units, but composition must preserve contract boundaries, traceability, independent validation, and the right to reject incompatible components.

## 1. Scope and terminology

This specification covers: (1) composition and nesting; (2) contract reconciliation; (3) scoring and evidence folding; (4) cross-unit relay; (5) structural evolution, including structural recursive self-improvement (RSI); and (6) conformance assessment.

It does **not** prescribe a particular LLM, programming language, runtime, distributed consensus mechanism, or organizational governance model. UIERU is an optional organization layer, not a requirement that every workflow become an autonomous agent.

The keywords **MUST**, **MUST NOT**, **SHOULD**, **SHOULD NOT**, and **MAY** indicate normative requirements within this *proposed* specification. A deployment's governing contract and applicable law take precedence over this document.

**Unit:** `U = (K, P, F, R, E)`, where `K` is contract, `P` calling path, `F` scoring forest, `R` relay, and `E` evolution.  
**Composition:** connecting two or more units under an explicit parent or federation contract.  
**Nesting:** a unit delegates a bounded subtask to another unit.  
**Folding:** reducing a complex portfolio into a decision-ready representation while retaining material evidence and dissent.  
**Structural delta:** a versioned proposed change to one or more of `K, P, F, R, E`.  
**Conformance:** evidence that an implementation satisfies the requirements of a declared profile.

## 2. Architectural invariants

An implementation claiming conformance to this specification MUST maintain the following invariants:

1. **Authority non-amplification.** A child cannot obtain more effective authority merely by being nested, copied, or relayed.
2. **Contract explicitness.** Every unit-to-unit execution edge identifies the governing contract, responsible principal, and permitted operations.
3. **Traceable execution.** Material decisions, tool calls, approvals, and side effects are attributable to an actor, time, contract, and version.
4. **Scoring non-sovereignty.** A high score cannot override a hard constraint or grant authorization.
5. **Evidence preservation.** Folding cannot silently erase decision-relevant counter-evidence, unresolved disagreement, or provenance.
6. **Versioned evolution.** Structural changes have immutable proposal identifiers and auditable transitions.
7. **Independent acceptance.** A proposed delta is not equivalent to an approved deployment.
8. **Safe failure.** Unknown compatibility, missing approvals, or invalid relay integrity results in rejection, quarantine, or escalation rather than automatic execution.
9. **Receiver sovereignty.** Imported structures require local validation and authorization.
10. **Optionality.** Implementations MAY use simpler non-UIERU workflows where orchestration overhead exceeds expected benefit.

## 3. Composition patterns

### 3.1 Sequential composition

`U_A -> U_B` passes a typed output and a relay envelope from `U_A` to `U_B`. `U_B` MUST verify the artifact's schema, provenance, validity period, and receiving permissions before acting.

### 3.2 Parallel composition

`U_parent -> {U_1, U_2, ... U_n}` allocates bounded work to concurrent units. The parent MUST define concurrency limits, resource budgets, cancellation policy, and conflict-resolution authority. Concurrent completion does not imply automatic merge.

### 3.3 Hierarchical nesting

A parent unit MAY delegate a subproblem to a child. The child MUST receive an explicit scope, budget, expiration or revocation rule, evidence obligations, and return contract. A parent remains accountable for decisions within its retained authority.

### 3.4 Federated composition

Independent organizations MAY exchange relay portfolios without creating a common controlling parent. Each party retains its own policies, evaluation perspectives, and acceptance authority. Federation requires an explicit interoperability agreement, not shared trust by default.

### 3.5 Dynamic reconfiguration

A composition MAY change at runtime, but new edges MUST undergo compatibility and authorization checks. An unvalidated reconfiguration MUST NOT inherit previous approvals by implication.

## 4. Canonical composition descriptor

A composition record SHOULD contain at least:

```yaml
composition_id: comp-payment-042
schema_version: "1.0"
mode: hierarchical
parent_unit_id: u-parent-01
contract_ref: contract-parent-v3
members:
  - unit_id: u-implementer
    role: implementation
    contract_ref: contract-impl-v2
  - unit_id: u-challenger
    role: counter_evidence
    contract_ref: contract-challenge-v1
edges:
  - from: u-parent-01
    to: u-implementer
    interface: task_request/v1
    approval_ref: approval-123
  - from: u-implementer
    to: u-parent-01
    interface: relay_portfolio/v1
budgets:
  max_cost_units: 500
  max_wall_time_seconds: 7200
policy:
  side_effects: approval_required
  on_contract_conflict: reject_and_escalate
  on_missing_provenance: quarantine
reconciliation:
  state: validated
  validator: policy-engine-v2
  evidence_ref: validation-report-045
```

This is an illustrative interchange record, not a complete machine-validatable schema. SPEC-001 governs the canonical contract and schema definitions; implementations MUST document any local extensions.

## 5. Contract reconciliation

Before activating a composition edge, the receiving controller MUST perform the following checks in order:

1. **Identity and integrity:** authenticate participating units and verify signed or otherwise integrity-protected artifacts as required by local policy.
2. **Schema and type compatibility:** validate input/output types, version ranges, and declared semantics.
3. **Purpose and scope:** confirm the delegated objective falls within the parent's authorized purpose.
4. **Permission intersection:** compute effective permissions as the intersection of parent authorization, child permissions, and local environment policy.
5. **Hard constraints:** check safety, privacy, residency, confidentiality, and non-negotiable operational constraints.
6. **Budget compatibility:** confirm time, compute, financial, and external-effect limits.
7. **Evidence obligations:** ensure required logging, counter-evidence, and return artifacts can be produced.
8. **Conflict resolution:** accept, conditionally accept with explicit amendments, reject, or escalate.

A suggested formal condition is:

`EffectiveAuthority(child) ⊆ ParentDelegatedAuthority ∩ ChildLocalPolicy`.

This relation is a design invariant; a real implementation MUST define the authority lattice or policy evaluation semantics it uses. Missing or incomparable permissions MUST NOT be treated as allowed.

### 5.1 Conflict classes

| Conflict | Example | Required disposition |
|---|---|---|
| Authorization | Child requests production write access without delegation | Reject or obtain explicit approval |
| Objective | Parent optimizes speed; child contract requires complete verification | Reconcile constraints or escalate |
| Scoring | Reliability and cost perspectives rank trails differently | Preserve both; apply authorized decision rule |
| Evidence | Required audit trail absent | Quarantine or reject |
| Resource | Combined subunits exceed budget | Reallocate or cancel before execution |
| Version | Incompatible relay or schema versions | Negotiate supported version or reject |

## 6. Calling-path composition

A composite calling path is a directed execution graph whose nodes may be actions, checks, human approvals, or nested UIERUs. Every edge MUST identify its data and control semantics. Cycles MUST have bounded termination, budget, or human-escalation rules. Parallel branches MUST define joining behavior and partial-failure policy.

A composite runtime SHOULD distinguish **plan approval**, **tool execution approval**, and **structural change approval**. Authorization for one is not authorization for the others.

## 7. Cross-level forward guidance

The parent scoring forest MAY rank candidate subunits, allocate exploration budgets, request additional evidence, or pause a path. A child scoring forest MAY optimize within its delegated scope. Neither can override the other's hard constraints through score aggregation.

A reference guidance cycle is:

```text
Observe parent state and child reports
  -> Verify contracts and budgets
  -> Generate candidate continuations / delegations
  -> Filter by hard constraints
  -> Score across declared perspectives
  -> Identify disagreement and uncertainty
  -> Select authorized actions or request approval
  -> Execute and collect evidence
  -> Replan, fold, or terminate
```

An implementation SHOULD log the scoring-model version, inputs, candidate set, constraints, and decision rationale. It SHOULD explicitly distinguish predicted utility from observed outcomes.

## 8. Perspective-aware scoring folding

Let `S_i(t)` be the score of trail `t` under perspective `i`, and `C(t)` be hard constraints. A candidate is eligible only if `C(t) = true`. Among eligible candidates, a policy-approved aggregator `A(S_1(t), ..., S_m(t); W, Q)` MAY assist selection, where `W` denotes declared weights and `Q` uncertainty or evidence quality.

No universal aggregator is prescribed. The implementation MUST record its selected aggregation rule and SHOULD preserve per-perspective scores, confidence qualifications, conflicts, and vetoes. A scalar summary MUST NOT be represented as a complete substitute for the underlying evidence.

**Folding output SHOULD include:** selected candidate; alternatives considered; perspectives and weights; hard constraints; unresolved disagreements; counter-evidence; provenance; uncertainty; residuals; and the decision authority.

## 9. Multi-trail composition and sandbox boundaries

A composite unit MAY maintain an **Exploit** trail (best-known execution), **Explore** trails (alternatives), and **Challenge** trails (adversarial checks). Each trail MUST carry its own budget, state, contract scope, and evidence record. Sandbox execution MUST remain isolated from production side effects unless a separately authorized transition is recorded.

The parent MUST NOT infer that a successful sandbox result is safe for production without environment-specific validation. Failed and abandoned trails SHOULD be retained as compact evidence when permitted by data retention policy.

## 10. Structural relay across compositions

Relay records MUST distinguish:

- **Facts and observations** from inferred judgments.
- **Execution results** from hypothetical or simulated outcomes.
- **Proposed structural deltas** from accepted deltas.
- **Transferred artifacts** from transferred authority (the latter does not occur implicitly).

A relay portfolio SHOULD preserve the relevant contract and calling-path versions, scoring perspectives, counter-evidence, unresolved residuals, source lineage, and receiver acceptance decision. SPEC-003 defines exchange semantics.

## 11. Evolution lifecycle

Structural evolution follows a controlled state machine:

```text
OBSERVED_RESIDUAL
  -> DELTA_PROPOSED
  -> STATIC_CHECKED
  -> SANDBOX_TESTED
  -> INDEPENDENTLY_REVIEWED
  -> APPROVED
  -> CANARY_DEPLOYED
  -> MONITORED
  -> ACCEPTED
```

At any validation stage, a delta MAY transition to `REJECTED` or `NEEDS_REVISION`. A deployed delta MAY transition to `ROLLED_BACK` after monitoring failure. The implementation MUST document which transitions require human or external policy approval.

### 11.1 Delta record

```yaml
delta_id: delta-2026-017
base_unit_version: u-parent@1.2.0
target_components: [P, F]
trigger:
  residual_ref: residual-071
  counter_evidence_refs: [ce-014]
proposal:
  summary: Add a challenger trail before production release
  patch_ref: patch-017
hypothesis:
  metric: escaped_defect_rate
  expected_direction: decrease
  cost_tradeoff: additional_test_compute
validation:
  static_checks: passed
  sandbox_report_ref: sandbox-017
  independent_evaluator_ref: evaluator-3
approval:
  status: pending
  authority_ref: release-board
rollout:
  status: not_deployed
rollback:
  artifact_ref: u-parent@1.2.0
```

A change to the scoring forest or evaluator itself SHOULD receive stricter independent validation than an ordinary task-level update, because it may affect the mechanism used to judge future changes.

## 12. RSI-based intelligence driving

UIERU supports a research direction termed **RSI-based Intelligence Driving**: evidence from completed or attempted tasks may improve not only the next task outcome, but the structures that guide future tasks. Eligible targets include calling paths, scoring forests, sandbox policies, relay contracts, and evolution procedures.

This is **structural RSI**, not necessarily model-weight self-training. Recursive change does not establish recursive *improvement* unless independent measurements demonstrate sustained benefit under controlled conditions. Implementations MUST distinguish proposal generation, evaluation, approval, and deployment roles. Self-evaluation alone MUST NOT suffice to approve changes that modify the evaluator or approval mechanism.

## 13. Composition closure and limits

The expression `Compose(U_1, ..., U_n) -> U_parent` is an architectural aspiration, not a proven closure theorem. A composition qualifies as a valid UIERU only when it supplies all mandatory canonical fields and satisfies contract, provenance, and conformance invariants. Composition can fail because of incompatible goals, irreconcilable policy, excessive overhead, nonportable state, or inadequate evidence.

Implementations SHOULD provide a **non-composition fallback** (ordinary workflow, human handoff, or rejection) when benefits are insufficient or requirements cannot be satisfied.

## 14. Conformance profiles

Conformance is modular. An implementation MUST state exactly which profiles it claims and provide corresponding test evidence.

| Profile | Required capabilities | Primary evidence |
|---|---|---|
| **C0 — Canonical Core** | `K,P,F,R,E` descriptors; identity and versioning | Schema and invariant checks |
| **C1 — Guided Execution** | Forward guidance with policy-filtered decisions | Decision logs and authorization tests |
| **C2 — Multi-Trail Exploration** | Trail lifecycle, sandbox separation, counter-evidence | Isolation and lifecycle tests |
| **C3 — Composable Units** | Nesting, contract reconciliation, budget propagation | Composition compatibility tests |
| **C4 — Governed Evolution** | Delta lifecycle, independent evaluation, rollback | Evolution audit and rollback tests |
| **C5 — Collective Relay** | Portfolio exchange, provenance, local acceptance, feedback | Interoperability and receiver-sovereignty tests |

Profiles C1–C5 are capability declarations, not a simple maturity ranking. A C4 claim requires C0 and relevant supporting C1/C2 capabilities; a C5 claim requires C0 and the relay requirements of SPEC-003. A project MAY implement C3 without C2. Dependencies MUST be declared explicitly.

## 15. Conformance test suite

The following tests are minimum reference scenarios. `PASS` requires recorded evidence of the expected outcome; a verbal assertion is insufficient.

| ID | Scenario | Expected result |
|---|---|---|
| CT-001 | Missing mandatory contract field | Reject invalid unit |
| CT-002 | Child requests undelegated permission | Deny; log reason |
| CT-003 | Parent/child objectives conflict | Reconcile explicitly or escalate |
| CT-004 | Combined child budgets exceed parent budget | Block launch or reallocate |
| CT-005 | Scoring favors prohibited action | Constraint veto wins |
| CT-006 | Child reports untraceable evidence | Quarantine or reject |
| CT-007 | Fold hides material counter-evidence | Reject incomplete fold |
| CT-008 | Concurrent child outputs disagree | Preserve conflict; apply authorized resolver |
| CT-009 | Nested calling graph contains unbounded cycle | Reject or require termination control |
| CT-010 | Sandbox attempts unauthorized production write | Block and audit |
| CT-011 | Multi-trail run exhausts budget | Stop or request fresh authorization |
| CT-012 | Proposed delta lacks independent evaluation | Prevent approval/deployment |
| CT-013 | Evaluator-modifying delta self-approves | Reject |
| CT-014 | Canary regression crosses rollback threshold | Roll back; preserve evidence |
| CT-015 | Receiver imports structurally valid but locally forbidden portfolio | Reject local execution |
| CT-016 | Relay loses source provenance | Fail integrity/acceptance checks |
| CT-017 | Child schema version is incompatible | Negotiate or reject |
| CT-018 | Parent revokes delegation mid-execution | Halt further privileged actions |
| CT-019 | Failed challenge trail contains valuable counter-evidence | Preserve per retention policy |
| CT-020 | Recomposition changes effective permissions | Revalidate; no inherited approval |
| CT-021 | Non-UIERU path is cheaper and sufficient | Permit simpler fallback |
| CT-022 | Repeated delta causes performance regression | Detect, reject or roll back |

An implementation SHOULD publish machine-readable test fixtures and execution traces for these cases. Test fixtures MUST use synthetic or appropriately de-identified data.

## 16. Reference conformance report

```yaml
report_id: conf-2026-004
implementation: example-uieru-runtime
implementation_version: "0.3.0"
specification: SPEC-004@1.0.0
claimed_profiles: [C0, C1, C2, C3, C4]
test_run:
  started_at: "2026-10-20T09:00:00Z"
  fixture_set: uieru-conformance-fixtures-v1
  results:
    passed: 21
    failed: 1
    skipped: 0
  failed_test_ids: [CT-014]
conformance_status: not_conformant
remediation:
  issue_ref: issue-rollback-threshold
  retest_required: true
```

The record is illustrative. **A failed mandatory test prevents an unqualified conformance claim** for the affected profile. Conformance reports SHOULD identify deviations, waivers, test environment, and the independent reviewer where applicable.

## 17. Reference orchestration algorithm

```python
# Reference pseudocode; not a production security implementation.
def compose_and_evolve(parent, children, policy, evidence_store):
    validate_canonical(parent)
    for child in children:
        validate_canonical(child)
        decision = reconcile_contracts(parent.contract, child.contract, policy)
        if decision.status != "approved":
            record_rejection_or_escalation(child, decision)
            continue
        allocate_bounded_budget(parent, child, decision)

    while parent.has_authorized_work():
        state = observe_composite_state(parent, children)
        candidates = propose_paths_and_trails(state)
        eligible = [c for c in candidates if hard_constraints_pass(c, policy)]
        ranked = perspective_aware_score(eligible, state)
        decision = authorized_select(ranked, policy)
        if decision is None:
            escalate_or_stop(parent)
            break
        outcomes = execute_with_isolation_and_audit(decision)
        evidence_store.append(outcomes)
        preserve_counter_evidence_and_residuals(outcomes)
        if should_replan(outcomes):
            continue
        if parent.objective_satisfied(outcomes):
            break

    portfolio = fold_with_provenance(parent, children, evidence_store)
    validate_relay_portfolio(portfolio)
    for delta in derive_structural_delta_candidates(portfolio):
        register_proposal(delta)  # Never auto-deploy.
    return portfolio
```

The reference algorithm intentionally leaves policy, authentication, isolation, and approval implementation-specific. A production implementation MUST supply those mechanisms before executing privileged actions.

## 18. Failure modes and governance controls

| Failure mode | Consequence | Control |
|---|---|---|
| Authority leakage through nesting | Unauthorized side effects | Effective-permission intersection and revocation |
| Goodharted scoring | Metric gains without real improvement | Independent metrics and challenge trails |
| Lossy folding | Hidden dissent and uncertainty | Evidence retention and traceable summaries |
| Recursive evaluator capture | Self-serving approvals | Separate evaluator governance |
| Relay contamination | Propagation of invalid structures | Provenance and receiver-local validation |
| Combinatorial trail explosion | Excessive cost or latency | Budget caps, pruning, and stop rules |
| Contract drift | Unintended behavior after updates | Version pinning and reconciliation |
| Irreversible production change | Unrecoverable damage | Approval gates, canaries, backups, rollback plans |
| Privacy leakage | Cross-boundary data exposure | Data minimization and purpose limitation |
| False universality | Excessive overhead | Compare against simpler baselines |

## 19. Validation program

A useful evaluation program compares UIERU composition against at least four baselines: (a) manual workflow, (b) conventional orchestrated workflow, (c) multi-agent execution without forward scoring or governed relay, and (d) UIERU variants with individual mechanisms ablated.

Measure: task quality; latency; total cost; side-effect incidents; contract violations; recovery time; provenance completeness; relay fidelity; acceptance/rejection precision; diversity and utility of counter-evidence; structural-delta adoption rate; regression rate; and long-horizon performance after repeated evolution cycles.

Suggested experiments:

1. **Nested delegation:** test authority and budget propagation at increasing nesting depths.
2. **Scoring conflict:** vary stakeholder priorities and compare scalar-only folding against evidence-preserving folding.
3. **Sandbox exploration:** compare exploit-only, exploit/explore, and exploit/explore/challenge configurations under equal budgets.
4. **Cross-team relay:** compare ordinary summaries with portfolios containing provenance, alternatives, and residuals.
5. **Structural RSI:** evaluate whether independently validated changes improve held-out future tasks without unacceptable regression.
6. **Overhead boundary:** identify task complexity thresholds below which simpler workflows outperform UIERU.

These are **proposed experiments**, not empirical results.

## 20. Testable hypotheses

- **H1 — Contract preservation:** Explicit reconciliation reduces unauthorized cross-unit actions relative to implicit delegation.
- **H2 — Guided composition:** Forward-guided composition improves quality or cost-adjusted task performance under selected complex workloads.
- **H3 — Evidence-preserving folding:** Retaining counter-evidence reduces downstream decision error relative to scalar-only aggregation.
- **H4 — Multi-trail value:** Budgeted challenge trails improve robustness on adversarial or ambiguous tasks.
- **H5 — Relay fidelity:** Provenance-rich portfolios improve safe reuse across heterogeneous receiving environments.
- **H6 — Governed structural RSI:** Independently validated structural deltas yield more reliable long-horizon improvement than unreviewed self-modification.
- **H7 — Optionality:** For sufficiently simple tasks, ordinary workflows outperform UIERU on cost and latency.

All hypotheses require workload-specific operational definitions, preregistered or transparently reported evaluation procedures, and comparison baselines.

## 21. Interoperability and versioning

Implementations MUST declare the specification version and supported conformance profiles. Backward-incompatible changes to required fields or normative semantics SHOULD increment the major version of the relevant schema or protocol. Relay envelopes SHOULD include schema version, producer version, and any compatibility transformations applied by the receiver.

A receiving unit MUST NOT assume that a syntactically compatible artifact is semantically or operationally compatible. Local conformance and authorization remain mandatory.

## 22. Relationship to companion documents

- **UIERU-001–010:** conceptual architecture, research arguments, and validation framing.
- **CASE-001:** minimal neighborhood lawn-service workflow.
- **CASE-002:** multi-agent software engineering, challenge trails, and RSI-based intelligence driving.
- **CASE-003:** cross-organizational relay and collective learning.
- **SPEC-001:** canonical contract and schema.
- **SPEC-002:** forward guidance and multi-trail lifecycle.
- **SPEC-003:** structural relay and portfolio exchange.
- **SPEC-004 (this document):** composition, governed evolution, and conformance.

The broader Structural Intelligence research lineage provides optional context, but no external DOI repository is a prerequisite for implementing or evaluating this specification.

## 23. Open engineering questions

1. What is the smallest policy model that supports reliable authority intersection across heterogeneous organizations?
2. Which evidence summaries preserve enough information for safe scoring folding without unbounded storage?
3. How can scoring perspectives be reconciled when there is no legitimate common utility function?
4. When should a parent delegate scoring authority, and when should it require local or human review?
5. How should reversible structural changes be distinguished from irreversible real-world side effects?
6. Can independent evaluators remain independent as structural RSI improves their surrounding infrastructure?
7. What interoperability subset yields useful portability without imposing a heavyweight universal runtime?
8. What workload characteristics predict positive return on UIERU orchestration overhead?

## 24. Conclusion

UIERU composition is meaningful only when its assembled parts remain **governable, inspectable, and evolvable**. Nesting increases reach, not automatic authority. Scoring increases guidance, not sovereignty. Folding improves decision usability, not permission to erase disagreement. Relay transfers structured evidence, not trust by fiat. Structural RSI creates improvement candidates, not an entitlement to deploy them.

This specification provides a proposed engineering foundation for composing and evolving intelligence units while retaining contracts, evidence, independent evaluation, and explicit conformance. Its universal ambition remains a research hypothesis to be tested against practical alternatives.

---

**Suggested repository location:** `specs/SPEC-004-Composition-Evolution-and-Conformance.md`  
**Citation:** Sizhe Tan & GPT-Obot (2026). *SPEC-004: Composition, Evolution, and Conformance*. Universal Intelligence Evolution and Relay Unit, v1.0.0.  
**Project principle:** *Engineering First · Theory Supported · Research Open.*
