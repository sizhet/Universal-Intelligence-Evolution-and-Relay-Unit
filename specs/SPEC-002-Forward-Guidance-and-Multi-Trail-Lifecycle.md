# SPEC-002 — Forward Guidance and Multi-Trail Lifecycle

**Project:** Universal Intelligence Evolution and Relay Unit (UIERU)  
**Version:** 1.0.0 (Research Specification)  
**Status:** Proposed; implementation and conformance testing required  
**Authors:** Sizhe Tan & GPT-Obot  
**Companion:** `SPEC-001-Canonical-UIERU-Contract-and-Schema.md`  
**License:** Refer to repository license

## Abstract

This specification defines an implementable lifecycle for forward-guided execution and multi-trail exploration within a Universal Intelligence Evolution and Relay Unit (UIERU). It separates *proposal* from *authorization*, *sandbox experimentation* from *real-world action*, and *candidate structural improvement* from *approved evolution*. A forward-guiding Scoring Forest evaluates candidate Calling Paths before execution, monitors evidence and constraints during execution, and supports settlement and learning afterward. Multi-trail execution permits controlled Exploit, Explore, and Challenge branches whose outcomes are preserved as a relayable evidence portfolio. The specification provides normative requirements, lifecycle states, event and decision contracts, scheduling rules, safety invariants, example records, and testable conformance criteria. It is a proposed interoperability contract, not a claim that universal applicability or intelligence improvement has already been demonstrated.

## 1. Scope and Normative Language

The key words **MUST**, **MUST NOT**, **REQUIRED**, **SHOULD**, **SHOULD NOT**, and **MAY** express normative requirements for implementations claiming conformance to this specification.

This document specifies the runtime relationship between:

- **K — Contract:** subject, goals, authority, constraints, budgets, acceptance criteria.
- **P — Calling Path:** ordered or partially ordered callable steps and dependencies.
- **F — Scoring Forest:** perspective-aware forward guidance, control, and settlement.
- **R — Relay:** provenance-bearing records and handoff portfolios.
- **E — Evolution:** proposed, evaluated, and governed structural deltas.

Formally, `U = (K, P, F, R, E)`. A conforming runtime MAY use humans, LLMs, deterministic software, services, tools, or mixed teams as execution nodes. This specification does **not** require autonomous AI or multi-trail execution for every task.

Out of scope: a mandatory scoring algorithm, a universal utility function, a specific distributed computing platform, a universal trust authority, or permission to modify model weights.

## 2. Architectural Principles

1. **Forward, online, and retrospective guidance are distinct.** Evaluation after execution cannot substitute for pre-execution control.
2. **Guidance does not grant authority.** Only the governing contract and its authorized approvers may permit an action.
3. **Exploration is optional and budgeted.** A single approved path remains valid when branching has no demonstrated value.
4. **Challenge is a first-class trail.** Counter-evidence may invalidate an apparently successful result.
5. **Sandbox effects are isolated.** Promotion into a live environment requires a separate authorization gate.
6. **Evidence survives selection.** Rejected, inconclusive, and failed trails remain available subject to retention and privacy policy.
7. **Evolution is a controlled proposal process.** Recursive improvement cannot bypass independent evaluation or rollback requirements.
8. **Recipient sovereignty is preserved.** Relay recipients independently validate compatibility, permissions, and evidence.

## 3. Actors and Responsibilities

| Actor | Responsibility | May authorize live side effects? |
| --- | --- | --- |
| Contract owner | Establishes objectives, permissions, and constraints | Within explicit scope |
| Guidance controller | Scores options and recommends allocation/replanning | No, unless separately delegated |
| Trail scheduler | Allocates bounded compute, time, and sandbox capacity | No |
| Trail executor | Runs an approved path in an assigned environment | Only within granted capability |
| Challenge evaluator | Searches for counter-evidence and assumption failures | No |
| Independent verifier | Evaluates results and candidate structural deltas | No automatic deployment right |
| Release approver | Authorizes promotion or structural updates | Within explicit scope |
| Relay recipient | Validates and localizes received portfolio | Under its own contract |

An implementation MAY combine operational roles in one service, but MUST preserve logically separate approval checks and auditable identity of decisions. A system that scores and automatically approves its own unrestricted structural changes is nonconforming.

## 4. Core Entities and Identifiers

Every unit run MUST have a `unit_id`, `run_id`, `contract_version`, and `guidance_policy_version`. Every trail MUST have a stable `trail_id`, `trail_type`, `parent_trail_id` (nullable), `sandbox_id` (nullable), `status`, `budget`, and `provenance_ref`.

All event records MUST carry an immutable `event_id`, a time value, an actor identity, a correlation reference, and the version of the contract under which the event occurred. Identifiers SHOULD be globally unique within the relay ecosystem. Timestamps SHOULD use RFC 3339 with explicit offsets.

### 4.1 Trail types

- `EXPLOIT`: execute a comparatively established candidate toward the immediate objective.
- `EXPLORE`: test a materially different hypothesis, strategy, implementation, or resource allocation.
- `CHALLENGE`: attempt to falsify claims, detect failure modes, or uncover hidden costs and counter-evidence.

A trail's type MUST describe its intended epistemic role, not guarantee its outcome. For example, a CHALLENGE trail may confirm the leading candidate.

### 4.2 Environment classes

- `SIMULATION`: modeled environment with no real external effects.
- `ISOLATED_SANDBOX`: bounded experimental environment with controlled resources and credentials.
- `STAGING`: production-like test environment with explicit safeguards.
- `LIVE`: authorized real-world or production environment.

The environment class MUST be recorded before execution. An environment change MUST trigger renewed capability and authorization checks.

## 5. Forward-Guidance Cycle

A guidance cycle MUST include the following logical stages, even if some stages are implemented as a single transaction:

1. **Observe:** collect the current state, constraints, prior evidence, and unresolved residuals.
2. **Generate:** identify feasible Calling Path candidates and, when warranted, potential trail branches.
3. **Filter:** remove candidates violating hard constraints or lacking required authorization.
4. **Score:** evaluate feasible candidates across declared perspectives and uncertainty estimates.
5. **Allocate:** propose budget and priority, including an explicit no-branch option.
6. **Authorize:** verify whether each proposed action is permitted in its target environment.
7. **Execute:** dispatch authorized trail steps with bounded resources.
8. **Monitor:** compare observations with predicted outcomes, safety invariants, and stopping criteria.
9. **Replan:** continue, pause, fork, redirect, or terminate based on evidence and available authority.
10. **Settle:** record outcomes, confidence, costs, counter-evidence, and relayable residuals.

The controller MUST preserve the distinction between a *score recommendation* and an *authorized action*. Hard constraints MUST NOT be traded away for a higher aggregate score.

## 6. Multi-Perspective Scoring Contract

A Scoring Forest MAY contain separate evaluators for task quality, safety, cost, latency, reliability, novelty, learning value, and subject-specific preferences. The scoring record MUST identify each perspective and its version, rather than presenting an unexplained scalar as sufficient evidence.

For a feasible candidate `p`, a proposed illustrative score is:

```text
GuidanceValue(p) = Fold({perspective_score_i(p), confidence_i(p)}, policy)
                   - ResourcePenalty(p)
                   - UncertaintyPenalty(p)
```

`Fold` is implementation-defined and MUST disclose its reconciliation policy. A candidate violating a hard safety, legal, privacy, or authority constraint is **ineligible** regardless of `GuidanceValue`. Implementations SHOULD retain conflicting perspectives, confidence intervals or calibrated uncertainty estimates, and reasons for ranking changes. The formula is an architectural example, not a validated universal scoring rule.

### 6.1 Guidance decision record

A guidance decision MUST capture:

- observed state reference and candidate set;
- hard-constraint checks and rejection reasons;
- per-perspective score references, uncertainties, and folding policy version;
- recommended action and expected benefit;
- required approvals and budget impact;
- alternatives considered, including `DO_NOT_BRANCH` where applicable;
- the evidence that would cause reconsideration.

## 7. Unit-Run Lifecycle

The canonical unit-run states are:

```text
CREATED -> CONTRACT_VALIDATED -> PLANNED -> AUTHORIZED -> ACTIVE
                                                      |-> PAUSED -> ACTIVE
                                                      |-> SETTLING -> SETTLED
                                                      |-> ABORTED
```

`CONTRACT_VALIDATED` requires schema and semantic checks. `AUTHORIZED` means an approved execution plan exists, **not** that all future branches have blanket authorization. `SETTLED` requires a durable outcome record. An aborted run MUST preserve evidence and the reason for aborting, subject to retention policy.

A transition from `ACTIVE` to `PAUSED` MUST stop new side-effecting dispatches. Existing actions that cannot be interrupted MUST be declared and managed explicitly.

## 8. Trail Lifecycle and State Machine

Canonical trail states:

```text
PROPOSED -> ADMISSIBILITY_CHECK -> APPROVAL_PENDING -> QUEUED
              |-> REJECTED             |-> REJECTED
QUEUED -> RUNNING -> {PAUSED, COMPLETED, FAILED, TERMINATED}
PAUSED -> {RUNNING, TERMINATED}
{COMPLETED, FAILED, TERMINATED, REJECTED} -> EVALUATED -> ARCHIVED
```

A trail MAY skip `APPROVAL_PENDING` only when the governing contract grants an explicit, auditable pre-authorization for the precise class of sandbox actions and resource limits. No trail may enter `RUNNING` before admissibility, environment, budget, and capability checks pass.

`COMPLETED` means the intended execution steps ended; it does **not** mean the hypothesis was verified. `FAILED` denotes an execution or acceptance failure. `TERMINATED` denotes a controlled stop (e.g., exhausted budget, superseded plan, safety trigger). `EVALUATED` MUST record the epistemic outcome separately: `SUPPORTED`, `REFUTED`, `INCONCLUSIVE`, or `NOT_EVALUABLE`.

### 8.1 Transition invariants

- A terminal trail MUST NOT resume under the same `trail_id`; a retry MUST create a new trail linked to the predecessor.
- A parent/child relationship MUST be acyclic.
- A trail MUST NOT exceed its authorized resource envelope.
- Any move to `LIVE` MUST have a recorded live-action approval.
- A CHALLENGE trail MUST NOT silently mutate the artifact it is independently evaluating.
- Trail termination MUST NOT erase adverse evidence.

## 9. Branching, Scheduling, and Budget Control

Branching is justified when the expected decision value of additional evidence exceeds its expected resource, risk, and coordination costs. The scheduler MUST support a no-branch decision.

Let `B_total` be the authorized run budget. At all times:

```text
sum(committed_trail_budget) + reserved_contingency <= B_total
```

For nonfungible resources (e.g., live credentials, human approvals, API quotas), the constraint MUST be enforced per resource class rather than through a single scalar budget. Resource allocations MUST be versioned and auditable.

A scheduler SHOULD consider:

- exploitation probability and immediate objective value;
- novelty and expected information gain;
- independence of evidence and correlated failure modes;
- counter-evidence coverage;
- time-to-result and critical path;
- safety and irreversibility of proposed actions;
- diminishing returns and contention between trails.

A higher-scoring candidate MUST NOT be automatically promoted to live execution without passing the relevant approval gate.

## 10. Sandbox Isolation and Side-Effect Boundaries

An isolated trail MUST declare allowed tools, network destinations, data classes, credentials, write targets, execution time, and cleanup policy. A sandbox MUST default to denying undeclared side effects. The runtime SHOULD use separate credentials and storage namespaces for competing trails.

Sandbox outputs are **untrusted evidence**, not executable authorization. Imported artifacts MUST be checked for provenance, malicious content, data leakage, and compatibility before reuse. A sandbox MAY use synthetic or de-identified data, but MUST label simulation limitations and any distribution shift relative to live conditions.

For irreversible operations, the system MUST require explicit authorization and a documented mitigation or compensation plan; it MUST NOT claim rollback where rollback is impossible.

## 11. Counter-Evidence and Challenge Protocol

Every high-impact or structural-change candidate SHOULD have a CHALLENGE plan. A CHALLENGE plan MUST identify:

1. the target claim or assumption;
2. plausible falsifiers and boundary cases;
3. independent evidence sources where practical;
4. stop conditions and expected cost;
5. an evaluation rubric that distinguishes failure to falsify from proof of correctness.

A refutation MUST trigger a documented reconsideration of affected rankings or decisions. If evidence is ambiguous, the system MUST record uncertainty rather than relabeling it as success. Evaluators SHOULD track correlated tests, adversarial contamination, and Goodhart effects when optimizing on repeatedly exposed benchmarks.

## 12. Monitoring, Replanning, and Emergency Stops

The runtime MUST monitor budget consumption, action authorization, hard constraints, execution health, and declared failure indicators. It SHOULD monitor score drift, evidence contradictions, and the gap between predicted and observed outcomes.

Replanning decisions include `CONTINUE`, `PAUSE`, `FORK`, `REALLOCATE`, `REPLAN`, `TERMINATE`, and `ESCALATE`. Each MUST be accompanied by a reason and evidence reference. `ESCALATE` MUST be used when the necessary action exceeds current delegated authority.

A safety violation or unauthorized capability request MUST prevent further affected side effects. A kill switch SHOULD exist for long-running or externally connected trails, with known limitations documented.

## 13. Settlement and Evidence-Preserving Folding

Settlement MUST produce a portfolio containing:

- the selected result, if any, and acceptance status;
- the final Calling Path and actual execution trace;
- all materially relevant trail outcomes, including rejected and failed branches;
- perspective-aware scores and evaluator versions;
- counter-evidence and unresolved contradictions;
- cost, time, resource use, and material side effects;
- provenance references, environmental assumptions, and confidence limits;
- residuals and candidate Structural Deltas;
- authorization and approval history.

A compact summary MAY be produced for efficiency, but it MUST link to retained evidence according to the retention contract. Folding MUST NOT convert an unresolved disagreement into an unsupported consensus.

## 14. RSI-Based Intelligence Driving and Evolution Gates

Multi-trail guidance can improve the *task result* and can also produce hypotheses about improving the *future intelligence process*. This latter mechanism is termed **RSI-based Intelligence Driving** when a unit proposes and tests modifications to its own or its ecosystem's Calling Paths, guidance policies, evaluator arrangements, sandbox protocols, or relay structures.

The proposed structural-evolution lifecycle is:

```text
RESIDUAL_DETECTED -> DELTA_PROPOSED -> SANDBOX_TESTED
    -> INDEPENDENTLY_VERIFIED -> APPROVAL_PENDING
    -> APPROVED -> STAGED -> DEPLOYED -> MONITORED
                               |-> ROLLED_BACK
```

A delta MUST NOT move from proposal or sandbox validation directly to production deployment. The verifier MUST compare against a declared baseline and evaluate regressions, safety, costs, and applicability. The approval record MUST identify a responsible authority independent of the candidate's self-generated score. Deployment MUST be versioned; rollback or compensating actions MUST be planned before promotion when technically feasible.

Recursive modification of evaluation policies or approval logic SHOULD face stricter review than ordinary task-level changes. This specification does not imply self-improvement is monotonic or that model-weight self-modification is required.

## 15. Event Model and Interoperability

Implementations MUST emit ordered, append-only logical events for material state transitions. A minimal event envelope is:

```yaml
schema_version: "1.0.0"
event_id: "evt-204"
unit_id: "uieru-payments-01"
run_id: "run-2026-10-20-01"
trail_id: "trail-challenge-03"
event_type: "TRAIL_EVALUATED"
timestamp: "2026-10-20T15:20:00Z"
actor:
  id: "independent-evaluator-1"
  role: "challenge_evaluator"
contract_version: "k-4"
guidance_policy_version: "f-2"
correlation_id: "decision-71"
previous_event_ref: "evt-203"
payload:
  execution_status: "COMPLETED"
  epistemic_outcome: "REFUTED"
  target_claim: "Candidate A preserves idempotency under concurrent retries"
  evidence_refs:
    - "evidence/concurrent-retry-failure-12"
  recommended_action: "REPLAN"
```

The envelope is illustrative YAML, not a complete machine-readable schema. `SPEC-001` supplies the canonical contract vocabulary; a future standalone JSON Schema or Protocol Buffers definition SHOULD formalize wire-level constraints. Implementations MUST NOT claim cross-vendor interoperability solely because they use these field names.

### 15.1 Guidance decision example

```yaml
decision_id: "decision-71"
run_id: "run-2026-10-20-01"
observed_state_ref: "state-17"
candidates:
  - trail_id: "trail-exploit-01"
    type: "EXPLOIT"
    eligible: true
    score_by_perspective:
      reliability: 0.76
      cost: 0.85
    confidence: 0.68
  - trail_id: "trail-explore-02"
    type: "EXPLORE"
    eligible: true
    score_by_perspective:
      reliability: 0.89
      cost: 0.48
    confidence: 0.43
  - trail_id: "trail-challenge-03"
    type: "CHALLENGE"
    eligible: true
    purpose: "test concurrent retry failure modes"
recommended_action: "ALLOCATE_SANDBOX_TRAILS"
allocation:
  trail-exploit-01: {compute_minutes: 25}
  trail-explore-02: {compute_minutes: 20}
  trail-challenge-03: {compute_minutes: 15}
requires_live_approval: true
rationale: "High-impact concurrency assumption remains unverified"
reconsider_if: "Challenge evidence refutes idempotency claim"
```

Numbers in this example are illustrative, not empirically calibrated.

## 16. Reference Runtime Algorithm

```text
function run_guided_unit(contract K, calling_path P, forest F):
    validate_schema_and_semantics(K, P, F)
    establish_run_budget_and_capabilities(K)
    state <- observe_current_state()
    candidates <- generate_paths_and_optional_trails(P, state)

    while not run_terminal():
        feasible <- reject_constraint_violations(candidates, K)
        guidance <- score_by_perspective(feasible, F, state)
        proposal <- allocate_or_choose_no_branch(guidance, remaining_budget)
        record_guidance_decision(proposal)

        authorized <- apply_capability_and_approval_gates(proposal, K)
        dispatch_only_authorized_trails(authorized)
        evidence <- collect_trail_events_and_counter_evidence()
        enforce_resource_limits_and_safety_stops(evidence)

        if evidence_changes_assumptions_or_scores():
            state <- update_observed_state(evidence)
            candidates <- replan_or_fork_within_authority(state)
        else:
            candidates <- pending_candidates()

    portfolio <- settle_preserving_positive_and_negative_evidence()
    deltas <- propose_structural_improvements(portfolio.residuals)
    send_deltas_to_independent_validation(deltas)
    return relay_portfolio(portfolio)
```

The algorithm is a control-flow reference, not a guarantee of convergence or optimality. Production systems require transactional event handling, retries, distributed consistency policies, and explicit handling of partially completed external actions.

## 17. Conformance Profiles

| Profile | Required capability |
| --- | --- |
| `FG-CORE` | Contract checks, forward guidance, auditable decisions, budget and approval gates, settlement |
| `FG-MULTITRAIL` | `FG-CORE` plus trail lifecycle, typed branches, sandbox isolation, bounded scheduling |
| `FG-CHALLENGE` | `FG-MULTITRAIL` plus counter-evidence plans and refutation-aware replanning |
| `FG-EVOLUTION` | `FG-CHALLENGE` plus independent structural-delta verification and governed deployment |
| `FG-RELAY` | Applicable profile plus evidence-preserving portfolio exchange and recipient validation |

An implementation MUST state which profile it claims and MUST NOT claim a higher profile without passing its additional tests. Profiles are proposed within this research repository, not external certifications.

## 18. Normative Conformance Tests

| ID | Test | Expected result |
| --- | --- | --- |
| T01 | Missing contract authority | Reject action before dispatch |
| T02 | Hard constraint violated but aggregate score high | Candidate remains ineligible |
| T03 | Trail starts without budget allocation | Reject transition to `RUNNING` |
| T04 | Sandbox trail requests undeclared network access | Deny access and record event |
| T05 | `EXPLORE` trail requests live promotion | Require new live approval |
| T06 | CHALLENGE refutes selected candidate | Reconsider ranking and record decision |
| T07 | Two trails jointly exceed total budget | Deny or reallocate before dispatch |
| T08 | Terminal trail is resumed with same ID | Reject; require linked retry trail |
| T09 | Trail completes but acceptance criteria fail | Record `COMPLETED` and `REFUTED` or appropriate outcome separately |
| T10 | Folding omits material negative evidence | Fail settlement validation |
| T11 | Proposed delta attempts direct deployment | Reject without independent verification and approval |
| T12 | Guidance policy changes during a run | Preserve policy versions and trigger required revalidation |
| T13 | Recipient imports foreign trail permissions | Deny inherited authority; require local authorization |
| T14 | Irreversible action advertised as rollback-safe | Reject unsupported rollback claim |
| T15 | No beneficial branch is identified | Permit documented `DO_NOT_BRANCH` decision |
| T16 | Evaluator uncertainty is unknown | Record unknown uncertainty; prohibit fabricated confidence |

A test report SHOULD include fixture, event trace, expected/actual result, runtime version, and evaluator identity. Passing these tests establishes only conformance to the specified behavior, not general intelligence superiority.

## 19. Evaluation Metrics and Experimental Baselines

Compare at least the following baselines on matched workloads:

- **B0:** ordinary deterministic workflow without forward guidance;
- **B1:** post-hoc scoring only;
- **B2:** single-path forward guidance;
- **B3:** multi-trail guidance without CHALLENGE;
- **B4:** multi-trail guidance with CHALLENGE and evidence-preserving settlement;
- **B5:** B4 with independently validated structural evolution.

Recommended metrics include task acceptance rate, severe regression rate, safety incidents, authorization violations, resource overhead, time to useful result, counter-evidence detection rate, calibration error, reproducibility, relay fidelity, and performance on *held-out future tasks* after approved structural changes. Report confidence intervals and negative results; stratify by task complexity. Measure whether exploration and coordination costs exceed the benefit for simple tasks.

## 20. Failure Modes and Limitations

| Risk | Mitigation |
| --- | --- |
| Scoring Goodhart or evaluator gaming | Independent challenge, held-out tests, policy versioning |
| Branch explosion | Explicit budgets, no-branch option, termination thresholds |
| Correlated multi-trail errors | Diversity constraints and independent evidence |
| Sandbox escape or data leakage | Capability isolation, least privilege, audit logs |
| False confidence from simulated success | Environment labeling and staged verification |
| Unresolved scoring conflicts hidden by folding | Preserve per-perspective evidence and disagreements |
| Relay-based authority escalation | Recipient-side reauthorization |
| Recursive regression | Baseline comparison, independent approval, rollback/compensation |
| Excessive coordination cost | Selective containerization and task-size thresholds |

No design here proves that multi-trail exploration improves every task. In particular, high-quality counter-evidence may be expensive, external effects may be irreversible, and structural changes can degrade future performance.

## 21. Worked Miniature: Concurrent Payment Retries

A software engineering UIERU must update a payment API to maintain idempotency under concurrent retries. Its contract permits isolated test runs but requires human approval for production deployment.

The Scoring Forest proposes: an EXPLOIT trail implementing the current known lock strategy; an EXPLORE trail testing a database uniqueness strategy; and a CHALLENGE trail generating adversarial concurrent requests. All run in isolated sandboxes. The CHALLENGE trail reveals that the EXPLOIT candidate can double-process a request under a rare interleaving. The guidance controller revises its ranking and requests additional tests for the EXPLORE candidate. After independent verification, the chosen code change is submitted for release approval. The failed EXPLOIT path, its reproducible counterexample, and a proposed improvement to future concurrency test generation are preserved in the relay portfolio.

The task result is a candidate code change. The **RSI-based intelligence-driving** opportunity is separate: a proposed, independently tested update to the team's future test-generation and path-selection structure. No self-approval or automatic production promotion follows from the proposal.

## 22. Relationship to the UIERU Research Series

- **UIERU-002:** canonical contract, execution, guidance, and relay structure.
- **UIERU-003:** Calling Path and Scoring Forest duality.
- **UIERU-004:** forward guidance and multi-trail intelligence.
- **UIERU-005:** sandbox threading and counter-evidence.
- **UIERU-006:** composition, nesting, and contract reconciliation.
- **UIERU-007/008:** structural relay and bidirectional collective learning.
- **UIERU-009:** residual-driven structural evolution and recursive improvement.
- **UIERU-010:** architecture boundaries and validation.
- **SPEC-001:** canonical contract and schema.
- **SPEC-003:** structural relay and portfolio exchange.
- **SPEC-004:** composition, evolution, and conformance.
- **CASE-002:** multi-agent software engineering and RSI-based intelligence driving.

These documents extend this specification but are not prerequisites for understanding its lifecycle rules.

## 23. Open Research Questions

1. Which scoring reconciliation policies best preserve minority but high-impact safety perspectives?
2. How can branch value-of-information be estimated without systematically rewarding novelty over utility?
3. What is the minimum counter-evidence budget that improves reliability on realistic workloads?
4. How can sandbox evidence be calibrated for production distribution shifts?
5. How can a relay portfolio remain compact without losing decision-critical negative evidence?
6. Which structural modifications yield persistent gains on held-out future tasks rather than benchmark overfitting?
7. What independent approval structures remain practical in large federated UIERU ecosystems?
8. Under which conditions should a task deliberately remain outside UIERU containerization?

## 24. Conclusion

Forward guidance turns a Calling Path from a fixed execution sequence into a continuously evaluated, constraint-aware action process. Multi-trail execution extends this process into bounded exploration and deliberate falsification. Evidence-preserving settlement makes both successes and failures available for relay. Governed structural evolution creates a pathway from local residuals to experimentally validated improvements in future intelligence organization. The essential engineering discipline is to keep scoring, authorization, experimentation, verification, and deployment distinct—even when they are orchestrated by one runtime.

**Engineering First · Theory Supported · Research Open.**

---

**Suggested repository path:** `specs/SPEC-002-Forward-Guidance-and-Multi-Trail-Lifecycle.md`  
**Suggested companion figure:** `figures/Fig-003-Forward-Guidance-and-Multi-Trail-Search.png` and `figures/Fig-004-Sandbox-Threading-and-Counter-Evidence.png`
