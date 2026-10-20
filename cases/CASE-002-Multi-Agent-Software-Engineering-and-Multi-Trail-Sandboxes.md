# CASE-002 — Multi-Agent Software Engineering and Multi-Trail Sandboxes

**Project:** Universal Intelligence Evolution and Relay Unit (UIERU)  
**Version:** 1.0.0  
**Authors:** Sizhe Tan & GPT-Obot  
**Status:** Research and engineering case study; illustrative design, not an empirical performance claim  
**Repository location:** `cases/CASE-002-Multi-Agent-Software-Engineering-and-Multi-Trail-Sandboxes.md`

## Abstract

This case examines a multi-agent software engineering workflow organized as a Universal Intelligence Evolution and Relay Unit (UIERU). A conventional development pipeline can delegate coding, testing, review, and deployment, yet still lose alternative designs, failed experiments, counter-evidence, and lessons about how the workflow itself should change. UIERU combines a governed Calling Path with a forward-guiding Scoring Forest, isolated Multi-Trail Sandboxes, evidence-preserving relay, and a controlled structural-evolution loop. The result is not merely an agent team that writes code: it is a candidate architecture for **recursive-self-improvement-based intelligence driving** (RSI-based intelligence driving), in which measured failures and counter-evidence can guide changes to future planning, tool selection, delegation, evaluation, and execution structure. This is *bounded structural RSI*, not a claim of unrestricted autonomous self-improvement. The case supplies an illustrative task, unit contracts, execution traces, scoring rules, sandbox controls, relay artifacts, an improvement proposal, and a falsifiable validation design.

**Keywords:** UIERU; multi-agent software engineering; Calling Graph; Scoring Forest; forward guidance; Multi-Trail Sandbox; counter-evidence; structural recursive self-improvement; relay; provenance.

---

## 1. Engineering Problem: From Code Production to Intelligence Driving

Consider a team maintaining a payment-service API. The task is to add **idempotency-key support** to the `POST /payments` endpoint without breaking existing clients. A successful implementation must avoid duplicate charges during retries, handle concurrent requests, maintain compatibility, and pass security and performance checks.

A conventional agent workflow might assign a planner, coder, tester, and reviewer in sequence. It may deliver a working patch but often leaves important questions unanswered:

- Why was this implementation chosen over other plausible designs?
- Were concurrency and failure modes challenged *before* merge?
- Which rejected experiments are reusable evidence rather than disposable logs?
- Did the task reveal a defect in the team's test-generation or review process?
- Can another team reuse the lesson without inheriting inappropriate assumptions or authority?

The proposed UIERU organization answers these questions by making **execution, guidance, evidence, relay, and structural improvement** explicit. Its objective is not to add ceremony to every change; it is to improve consequential or recurrent engineering work where the expected value of exploration and reuse exceeds orchestration cost.

## 2. Minimal Formal Model and Roles

Represent a UIERU as:

\[
U = (K, P, F, R, E)
\]

where:

| Component | Role in this case |
|---|---|
| **K — Contract** | Task goals, repository scope, security rules, acceptance tests, budgets, approval authority |
| **P — Calling Path** | Planner → design → implementation → tests → review → integration, with conditional branches |
| **F — Scoring Forest** | Prospective choice of paths, online allocation, risk checks, evidence-weighted evaluation |
| **R — Relay** | Portable evidence, decisions, alternatives, failure traces, provenance, unresolved issues |
| **E — Evolution** | Validated structural deltas to workflows, test suites, scoring criteria, and delegation policies |

**Actors.** A human maintainer owns the final merge/deployment decision. A coordinator agent proposes work plans and manages budget. Specialist agents can implement, test, challenge, and review. A sandbox controller enforces isolation. A policy/evaluation function checks evidence and recommends action. These roles may be performed by humans, tools, or models; UIERU does not require one agent per role.

**Authority boundary.** An agent may propose code or workflow changes but cannot independently broaden its repository permissions, change production credentials, redefine success criteria, or approve its own promotion into a higher-trust environment.

## 3. Task Contract and Acceptance Criteria

The illustrative contract `K-PAY-017` defines:

- **Object:** payment-service endpoint and associated data model.
- **Goal:** repeat requests with the same authorized idempotency key yield one charge and a consistent response.
- **Constraints:** no secret exfiltration, no unauthorized external calls, no destructive production operations, backward compatibility, bounded database overhead.
- **Required evidence:** unit tests, concurrent-request tests, failure-injection tests, migration review, security review, and performance measurements.
- **Budget:** fixed model/tool budget, maximum three active exploratory trails, deadline for decision.
- **Authority:** human approval required for schema migration, merge, and deployment.
- **Stop conditions:** unresolved duplicate-charge risk, missing provenance, budget exhaustion, or sandbox policy violation.

An operational contract must distinguish **claims** from **observations**. For example, “no duplicate charge” is a required property, not a proven property until suitable tests and production controls establish confidence within stated assumptions.

## 4. Calling Path: A Governed Execution Graph

The baseline Calling Path is:

```text
Task intake / authority check
          |
    Requirements + threat model
          |
    Candidate architecture design
          |
    Forward-guidance gate
          |
   +------+-------+----------------+
   |              |                |
Trail A         Trail B          Trail C
Known design    Alternative      Adversarial
   |              |                |
Isolated build / test / challenge environments
   +--------------+----------------+
                  |
         Evidence reconciliation
                  |
       Human-controlled decision
                  |
       Integration and monitoring
                  |
     Relay portfolio + residuals
                  |
      Structural delta proposal
```

This is a **Calling Graph**, not a rigid linear chain. A path may be revised when evidence changes. Each branch has an owner, contract, bounded tools, and an explicit termination condition.

## 5. Scoring Forest: Forward Guidance, Not Only Final Ranking

A Scoring Forest is a set of perspective-aware evaluation and control structures. In this case, perspectives include correctness, security, reliability, performance, maintainability, cost, and evidence quality. The forest guides decisions at three moments:

1. **Before execution:** decide which candidate trails merit investment and what counter-evidence must be sought.
2. **During execution:** reallocate effort, trigger additional tests, suspend risky trails, or request human review.
3. **After execution:** evaluate outcomes, preserve unresolved uncertainty, and determine what may be relayed or proposed as a structural improvement.

An illustrative utility model for a trail `t` is:

\[
V(t) = B_{quality}(t) + B_{information}(t) - C_{compute}(t) - C_{delay}(t) - R_{risk}(t)
\]

This expression is **not** a universal scalar objective. Hard safety and authority constraints are evaluated first; some perspectives are non-compensatory. A cheap but unsafe trail is ineligible even if its apparent score is high. Confidence intervals, evidence provenance, and uncertainty must accompany numerical estimates.

A forward-guidance decision can be written as:

\[
a^* = \operatorname*{argmax}_{a \in A_{permitted}}\; \mathbb{E}[\Delta V \mid s, a, e]
\]

where `s` is current state, `e` is available evidence, and `A_permitted` is the set of contract-compliant actions. Estimates must be calibrated experimentally; the formula defines a decision intent, not an already validated optimizer.

## 6. Multi-Trail Sandbox Design

Three trails deliberately have different purposes:

| Trail | Intent | Candidate approach | Evidence emphasis |
|---|---|---|---|
| **A — Exploit** | Apply a known, maintainable pattern | Database unique constraint + transaction-bound idempotency record | Regression, concurrency, operational fit |
| **B — Explore** | Investigate a potentially advantageous alternative | Request ledger with state transitions and recovery semantics | Recovery behavior, throughput, complexity |
| **C — Challenge** | Try to falsify A and B | Race injection, crash windows, key collision, replay, timeout | Counterexamples, invariant violations, missing tests |

Trails A and B produce implementations; Trail C may produce no production code at all. Its deliverable is *counter-evidence*. That distinction matters: an adversarial trail should not be penalized for finding defects that lower apparent progress.

Each trail runs in an isolated checkout/container with constrained network access, ephemeral credentials, explicit resource quotas, dependency pinning, and audit logs. Artifacts cross sandbox boundaries only after inspection. No trail can modify the authoritative branch directly.

### 6.1 Trail Lifecycle

```text
PROPOSED -> CONTRACTED -> SANDBOXED -> RUNNING
                                       |
                    +------------------+------------------+
                    |                  |                  |
                 PAUSED             COMPLETED            FAILED
                    |                  |                  |
                    +------------------+------------------+
                                       |
                                EVIDENCE_REVIEW
                                       |
                     ACCEPT / REJECT / RETAIN_UNCERTAIN
                                       |
                                  ARCHIVED_RELAY
```

“Failed” is an execution status, not permission to discard evidence. A failed experiment can expose a missing precondition or evaluator defect.

## 7. Worked Trace: An Illustrative Concurrency Failure

The following trace is hypothetical, designed to show the mechanism; it does not report a measured benchmark.

**T0 — Plan.** The coordinator identifies duplicate-charge prevention as a hard invariant. The Scoring Forest authorizes A and B plus a limited challenge budget for C.

**T1 — First implementations.** Trail A implements a unique-key reservation in a transaction. Trail B implements a stateful request ledger. Both pass basic unit tests.

**T2 — Counter-evidence.** Trail C introduces a simulated process crash between payment authorization and persistence of the final response. The test exposes a recovery ambiguity in A's first implementation. This is not proof that all A-style designs are unsafe; it is evidence against the *specific implementation and assumptions*.

**T3 — Online guidance.** The forest suspends promotion of A, requests a crash-recovery test for both trails, and reallocates part of the remaining budget from low-value performance tuning to recovery validation.

**T4 — Revision.** Trail A adds a durable state transition and reconciles the external payment-provider transaction identifier. Trail B passes the failure test but incurs higher measured database write overhead in this scenario.

**T5 — Decision.** The evaluation package recommends revised A subject to human review, records B as an alternative for other workload profiles, and retains C's test as a regression artifact. The human maintainer reviews migration safety and authorizes merge only after required checks.

**T6 — Residual.** The team discovers that the original test-generation template did not require crash-window testing for external side effects. This is a **structural residual**: the workflow, not just the code, needs improvement.

## 8. Why This Is RSI-Based Intelligence Driving

The key distinction is between **using intelligence to perform a task** and **using task evidence to improve the intelligence-driving structure itself**.

A conventional agent system may iteratively fix code. UIERU additionally asks whether its *own organization of intelligence* should change: the planner's branch policy, the Scoring Forest's risk criteria, the sandbox challenge catalog, the relay schema, or the validation gate.

This constitutes a bounded form of **RSI-based intelligence driving** when all of the following occur:

1. The system detects a persistent gap between intended and observed behavior.
2. It attributes at least part of the gap to a reusable structural mechanism, rather than treating it only as a local coding bug.
3. It proposes a change to the mechanism that guides future intelligence work.
4. It tests that change against independent criteria and counter-evidence.
5. Authorized governance accepts, rejects, or rolls back the change.
6. Subsequent tasks supply new evidence about whether the improved mechanism actually helps.

The recursive object is thus not necessarily the model's weights. It can be the **Calling Graph, scoring policy, evaluator, sandbox protocol, relay contract, or composition strategy**. An LLM may participate, but structural RSI can occur without retraining the LLM.

### 8.1 A Two-Level Improvement Loop

```text
LEVEL 1: TASK EXECUTION
Contract -> Guide -> Multi-Trail Execute -> Test -> Deliver
                   |                         |
                   +---- Evidence/Residual --+
                                 |
LEVEL 2: INTELLIGENCE-DRIVING IMPROVEMENT
Diagnose structural gap -> Propose Delta -> Adversarial A/B
                                 |
                    Independent verification
                                 |
                      Authorized promotion
                                 |
              Updated guidance for future tasks
```

A third level—modifying the improvement process itself—is conceivable, but requires stricter evaluator independence and approval. This case does not assume unrestricted self-modification or guaranteed recursive gains.

**Central proposition:** *UIERU can organize software engineering as a governed, evidence-driven structural RSI process: intelligence executes work, and verified work evidence selectively improves the structure that drives subsequent intelligence.* This is an architectural proposition requiring empirical validation.

## 9. Structural Delta: Improving the Test-Generation Contract

The residual at T6 motivates a candidate change:

```yaml
structural_delta:
  id: delta-payment-crash-test-v1
  target: software-engineering-uieru/test-planning-contract
  prior_version: "1.2"
  proposed_version: "1.3-candidate"
  trigger:
    type: missing_counter_evidence_coverage
    observation: "Crash-window test absent from original plan"
  proposed_change:
    rule: >
      For operations with external irreversible side effects,
      require crash-window and retry-interleaving tests before promotion.
  evidence:
    - challenge-trail-C/crash-window-reproduction
    - revised-trail-A/recovery-regression-test
  required_validation:
    - independent_test_review
    - retrospective_comparison_on_prior_tasks
    - false_positive_and_cost_assessment
    - policy_owner_approval
  promotion_status: proposed_not_approved
  rollback_condition: >
    Excessive test cost or demonstrable loss of coverage under agreed metrics.
```

The delta is not automatically adopted because one test found one defect. It is a hypothesis about a reusable improvement. Independent validation should determine whether the rule generalizes to other side-effecting operations, what it costs, and whether a narrower rule is preferable.

## 10. Evidence-Preserving Scoring and Folding

A naïve winner-take-all selection would keep Trail A's final patch and discard B and C. Evidence-preserving folding instead produces a decision with retained alternatives:

| Item | Folded decision | Retained evidence |
|---|---|---|
| Trail A | Recommended implementation after repair | Initial failure, repair diff, tests, assumptions |
| Trail B | Not selected for this workload | Throughput data, state-machine design, potential reuse conditions |
| Trail C | Challenge completed | Reproduction script, failure trace, counterexample catalog |
| Scoring Forest | Revised confidence | Scoring criteria, constraint checks, uncertainty |
| Evolution | Candidate improvement | Structural delta, validation status, rollback plan |

Folding reduces operational complexity without erasing the provenance needed to challenge or reuse the decision.

## 11. Relay Portfolio and Portability

The unit emits a **Relay Portfolio**, not merely a merged patch or summary. A compact illustrative envelope follows:

```yaml
uieru_relay:
  schema_version: "0.1-proposal"
  unit_id: payment-idempotency-uieru-017
  contract_id: K-PAY-017
  source_revision: commit-placeholder
  recipient_scope: authorized-software-teams
  status: reviewed_pending_merge
  selected_trail:
    id: A-revised
    rationale: "Meets required recovery tests within observed budget"
    limitations:
      - "Requires payment-provider reconciliation semantics"
      - "Production load behavior not established by sandbox tests"
  alternatives:
    - id: B
      disposition: retained_for_conditional_reuse
      evidence_ref: artifacts/trail-B-performance.json
  counter_evidence:
    - trail: C
      evidence_ref: artifacts/crash-window-repro.txt
      disposition: regression_test_added
  structural_deltas:
    - id: delta-payment-crash-test-v1
      status: proposed_not_approved
  provenance:
    manifest_ref: artifacts/manifest.sha256
    test_environment_ref: artifacts/test-environment.json
  authority:
    merge_approval: human_required
    deployment_approval: human_required
  privacy:
    secrets_included: false
    sharing_policy: internal_only
```

The receiving team must verify hashes and permissions, inspect dependency and environment assumptions, rerun relevant tests, and **localize** the imported pattern. The portfolio does not transfer deployment authority, guarantee correctness, or compel adoption of a particular scoring model.

## 12. Composition: Multiple UIERUs in a Software Organization

The payment feature unit can be composed with independently governed units:

- **Security UIERU:** threat modeling, vulnerability testing, approval evidence.
- **Reliability UIERU:** chaos tests, incident history, operational rollback design.
- **Migration UIERU:** schema compatibility, rollout sequencing, data integrity.
- **Release UIERU:** integration, canary criteria, human deployment authorization.

Composition requires contract reconciliation. For example, a feature unit's preference for a fast schema migration cannot override a release unit's hard constraint on zero-downtime compatibility. Parent-level scoring must preserve conflicts and escalation paths rather than average them away.

## 13. Algorithm Sketch

```text
function governed_multi_trail_uieru(contract K, prior_evidence H):
    assert authorize(K)
    state = inspect_repository_and_constraints(K)
    trails = propose_exploit_explore_challenge(state, H)
    trails = filter_by_hard_constraints(trails, K)
    budget = forward_allocate(trails, K, H)

    while budget.remains() and not terminal(state):
        observations = run_isolated_steps(trails, budget)
        evidence = verify_and_record(observations)
        if evidence.indicates_policy_violation:
            quarantine_affected_trail()
            escalate_if_required()
        guidance = update_scoring_forest(evidence, K)
        trails = revise_pause_or_branch(trails, guidance)
        budget = reallocate_within_contract(budget, guidance)

    portfolio = reconcile_without_erasing_counter_evidence(trails)
    decision = request_authorized_acceptance(portfolio, K)
    residuals = identify_structural_gaps(portfolio)
    deltas = propose_versioned_structural_changes(residuals)
    validate_deltas_independently(deltas)
    return relay(portfolio, decision, deltas)
```

This pseudocode is an architectural reference, not a claim that the optimization, evidence verification, or security isolation problems are solved.

## 14. Governance, Security, and Failure Modes

| Failure mode | Required control |
|---|---|
| Reward hacking or benchmark overfitting | Independent acceptance tests, challenge trails, holdout tasks |
| Self-approval of structural changes | Separate proposal, validation, and promotion authorities |
| Malicious code or prompt injection in repository | Treat code/comments/artifacts as untrusted input; tool sandboxing |
| Secret leakage through relay | Redaction, access controls, provenance checks, sharing policy |
| Sandbox escape or unauthorized side effects | Isolation, least privilege, network restrictions, auditable tool calls |
| Unbounded trail proliferation | Explicit branch budget, termination rules, marginal-value checks |
| False confidence from synthetic tests | Label evidence source, require production-like validation where warranted |
| Scoring conflict hidden by aggregation | Hard constraints, per-perspective results, unresolved-conflict records |
| Regression after structural delta promotion | Versioned rollout, monitoring, rollback trigger |
| Collective propagation of bad patterns | Local validation and receiver evaluation sovereignty |

A counter-evidence trail is valuable precisely because it is empowered to challenge assumptions—but that does **not** mean it should receive production privileges or unbounded autonomy.

## 15. Testable Hypotheses

The following are proposed experiments, not established outcomes.

**H1 — Defect discovery.** Under equal compute and review budgets, guided Multi-Trail execution detects more high-severity concurrency and recovery defects before merge than a single-path agent workflow.

**H2 — Evidence retention.** Relay Portfolios improve downstream teams' ability to reconstruct why a design was chosen, compared with patches plus ordinary summaries.

**H3 — Structural learning.** A validated structural-delta process improves defect prevention on future, related tasks beyond simply adding task-specific regression tests.

**H4 — Cost discipline.** Selective branching achieves a better defect-detection-per-dollar ratio than indiscriminate parallel agent execution for an identifiable class of tasks.

**H5 — Evaluator robustness.** Explicit challenge trails and independent promotion criteria reduce overfitting to self-generated tests.

**H6 — Local sovereignty.** Teams receiving relayed structures with explicit contracts and provenance exhibit fewer unsafe imports than teams receiving decontextualized prompts or code snippets.

## 16. Comparative Validation Protocol

### 16.1 Baselines

| Condition | Description |
|---|---|
| B0 | Human-directed conventional software workflow |
| B1 | Single-agent coding and test loop |
| B2 | Multi-agent pipeline without forward-guiding forest or preserved alternatives |
| B3 | Parallel agent branches with winner-take-all selection |
| B4 | UIERU with Multi-Trail guidance but no structural evolution |
| **U** | Full UIERU with independent structural-delta validation and relay |

### 16.2 Experimental Design

Use a preregistered task suite with payment-like idempotency, distributed retries, database migrations, authentication boundaries, and failure recovery. Stratify by difficulty and risk. Randomize task assignments across conditions, hold model/tool versions constant where possible, and report token, compute, wall-clock, and human-review costs. Use independent hidden tests and blinded expert review. Evaluate both initial task success and performance on **subsequent tasks**, since recursive structural improvement cannot be established by one successful patch.

### 16.3 Metrics

- Correctness: hidden-test pass rate, severe defect escape rate, concurrency invariant violations.
- Reliability: crash recovery, retry safety, rollback readiness.
- Efficiency: compute cost, elapsed time, human intervention, number of branches.
- Evidence quality: provenance completeness, reproducibility, counterexample retention.
- Structural evolution: proposed versus validated deltas, regression rate, measured transfer benefit.
- Relay: downstream adaptation success, localization effort, unsafe-import rate.
- Governance: unauthorized-action attempts, policy violations, time to detect and contain.

Report confidence intervals, negative results, and cases where UIERU overhead exceeds its benefits.

## 17. Boundary Conditions: When Not to Use Full UIERU

A one-line documentation correction or low-risk formatting task usually does not justify three sandboxes, elaborate scoring, or a structural-delta review. A simple checklist or single agent can be superior. Multi-Trail UIERU is most plausible when failures are costly, alternatives are materially different, counter-evidence is valuable, tasks recur, and relay or organizational reuse matters.

“Universal” describes the proposed **organizational abstraction**, not a proven universal optimum, a requirement to containerize all work, or an autonomous subject with independent authority.

## 18. Relationship to the UIERU Research Series

This case operationalizes concepts introduced in the core series:

- `UIERU-002`: Canonical contract, execution, guidance, relay, and evolution interfaces.
- `UIERU-003`: Calling Path / Scoring Forest duality.
- `UIERU-004`: Forward guidance and Multi-Trail allocation.
- `UIERU-005`: Sandbox threading and counter-evidence.
- `UIERU-006`: Composition and contract reconciliation.
- `UIERU-007`: Provenance-preserving structural relay.
- `UIERU-008`: Bidirectional collective learning.
- `UIERU-009`: Residual-driven structural RSI.
- `UIERU-010`: Engineering boundaries and validation.

These links are optional deeper reading; this case is intended to be understandable independently.

**Planned figure:** `figures/Fig-004-Sandbox-Threading-and-Counter-Evidence.png` may be cited near Sections 6–8. The figure is not required to understand the case.

## 19. Research Questions and Open Engineering Issues

1. How should a forward-guiding forest estimate information gain when tests are correlated or incomplete?
2. What evidence is sufficient to attribute a defect to the intelligence-driving workflow rather than a one-off implementation error?
3. How can evaluator independence be maintained when all agents share the same foundation model?
4. Which structural deltas transfer across repositories, languages, and deployment environments?
5. How should teams price the long-term value of retained failed trails?
6. What minimal relay schema balances portability, privacy, and reproducibility?
7. Under what conditions does structural RSI compound rather than merely accumulate workflow complexity?
8. How can nested UIERUs reconcile incompatible safety and performance constraints without silently weakening either?

## 20. Conclusion

The multi-agent software engineering case shows how a UIERU could transform a code-generation workflow into a governed system for **intelligence driving**. A Calling Path executes; a Scoring Forest guides and challenges; Multi-Trail Sandboxes explore and falsify; Relay Portfolios preserve evidence and alternatives; and a separately governed evolution process proposes changes to the structure that will guide future work.

The RSI connection is substantive but bounded: **recursive improvement is aimed at the organization, evaluation, and coordination of intelligence, and is accepted only when independently validated**. Whether this approach produces durable gains over simpler agent and workflow systems remains an empirical question. That question—and the controls needed to test it—is part of the architecture itself.

---

## Citation and Reuse Note

**Suggested citation:** Tan, Sizhe, and GPT-Obot. (2026). *CASE-002: Multi-Agent Software Engineering and Multi-Trail Sandboxes*. Universal Intelligence Evolution and Relay Unit, v1.0.0. GitHub repository: `https://github.com/sizhet/Universal-Intelligence-Evolution-and-Relay-Unit` (verify repository URL before publication).

**Evidence note:** All scenario outcomes and artifact identifiers above are illustrative, not measured results. The validation protocol describes how the hypotheses could be tested.
