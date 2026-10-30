# UIERU-006 — Composition, Nesting, Folding, and Contract Reconciliation

**Project:** Universal Intelligence Evolution and Relay Unit (UIERU)  
**Authors:** Sizhe Tan & GPT-Obot  
**Version:** 1.0.0  
**Status:** Research architecture and engineering proposal; not an empirically validated universal standard  
**Series:** UIERU Research Papers · 006

## Abstract

An intelligence unit becomes an engineering primitive only if it can participate in larger workflows without losing authority boundaries, evidence provenance, or the ability to adapt. This paper develops a compositional model for the Universal Intelligence Evolution and Relay Unit (UIERU). A unit couples a contract, an executable Calling Path, a forward-guiding Scoring Forest, a relay interface, and an evolution mechanism. We examine sequential, parallel, hierarchical, and federated composition; distinguish nesting from mere task decomposition; specify contract reconciliation and score folding; and propose an evidence-preserving composition lifecycle. The central claim is deliberately conditional: UIERUs may support scalable organization of heterogeneous human and machine intelligence when interfaces, authority, resources, evidence, and failure semantics can be reconciled. Composition is not automatically valid, and scoring functions cannot generally be summed. We conclude with schemas, failure cases, conformance tests, and falsifiable evaluation hypotheses.

**Keywords:** structural intelligence; compositional intelligence; nested agents; Calling Graph; Scoring Forest; contract reconciliation; score folding; provenance; structural relay; collective learning

---

## 1. Engineering Motivation: From One Unit to an Organization

A single UIERU can coordinate a bounded task. A neighborhood lawn-service unit, for example, receives a customer request, evaluates schedules and constraints, performs or delegates work, verifies completion, and relays a record. A landscaping company, however, must coordinate many such units alongside routing, equipment, billing, safety, and customer-service functions. A software engineering organization faces the same structural question with requirements, design, coding, testing, release, and maintenance.

The engineering challenge is not simply to add more agents. It is to make **units interoperable without erasing their boundaries**:

- Who may authorize each action, expenditure, or external effect?
- Which outputs are valid inputs to the next unit?
- How are conflicting objectives and constraints resolved?
- How can a parent judge overall outcomes without double-counting subordinate scores?
- What evidence, failures, uncertainties, and learning opportunities survive handoff?

UIERU composition addresses these questions as a candidate organizational layer above heterogeneous workers, models, tools, services, and people. It does not require every operation to be wrapped as a UIERU.

## 2. The Canonical Unit and Its Compositional Boundary

We use the canonical representation introduced in UIERU-002:

$$
U=(K,P,F,R,E)
$$

where:

| Component | Function | Composition concern |
|---|---|---|
| **K — Contract** | Subject, authority, task, goals, constraints, acceptance and accountability | Compatibility, delegation, obligation inheritance |
| **P — Calling Path** | Planned and observed actions, transitions, dependencies, evidence | Dependency correctness, execution and recovery |
| **F — Scoring Forest** | Forward guidance, candidate valuation, online control and settlement | Cross-perspective aggregation and conflict |
| **R — Relay** | Transferable results, provenance, alternatives and unresolved residuals | Interoperability and recipient verification |
| **E — Evolution** | Validated structural deltas and versioned adaptation | Change propagation, rollback and compatibility |

A UIERU boundary is meaningful when it exposes an explicit contract and relay surface, even if its internal execution is opaque. A component may be implemented by a human team, LLM-based agent, deterministic service, physical system, or a combination. The unit abstraction governs coordination; it does not prescribe the intelligence substrate.

### 2.1 Minimum compositional interface

A composable unit should expose, at minimum:

1. **Contract descriptor:** purpose, inputs, outputs, constraints, authority, and acceptance criteria.
2. **Invocation interface:** start, pause, resume where feasible, cancel, and report state.
3. **Guidance interface:** goals, budgets, risk limits, priorities, and permissible adjustments.
4. **Evidence interface:** outcome, confidence qualifications, provenance, failures, and unresolved questions.
5. **Relay interface:** versioned export and import with recipient-side validation.
6. **Evolution interface:** proposed changes, validation status, scope, and rollback information.

These are proposed logical interfaces, not a claim that all systems must expose identical APIs.

## 3. Composition Is Not the Same as Nesting

Let $\mathcal{U}=\{U_1,\ldots,U_n\}$ be participating units and $G_C=(\mathcal{U},D)$ a directed dependency graph, where $D$ represents data, authority, or workflow dependencies. A **composition** combines units to satisfy a larger contract. A **nesting relation** assigns a child unit to the internal organization of a parent, with explicit scope of delegation.

A composed workflow need not have a single parent. For example, two independently governed organizations may exchange verified relay packets without surrendering their local scoring sovereignty. Conversely, a nested child may be invoked repeatedly in several branches of a parent's Calling Graph.

Four useful patterns are:

| Pattern | Example | Primary coordination problem |
|---|---|---|
| Sequential | Inspection → repair → acceptance | Interface and evidence continuity |
| Parallel | Multiple candidate designs | Budget allocation, comparison, integration |
| Hierarchical | Organization → department → task | Delegation, escalation, accountability |
| Federated | Independent partners exchange units | Trust, sovereignty, version compatibility |

Hybrid structures are normal. Composition should therefore be modeled as a graph with optional containment edges, not only as a rigid tree.

---

![Fig-005 — Composable and Nested UIERU](../figures/Fig-005-Composable-and-Nested-UIERU.png)

*Figure 5. Sequential, parallel, hierarchical, and federated UIERU composition, with explicit contract reconciliation and evidence-preserving relay boundaries.*

---

## 4. Calling Graph Composition: Paths, Dependencies, and Recovery

Each unit has an internal Calling Path or Calling Graph fragment $P_i$. Composition creates inter-unit edges that connect exit conditions of one fragment to entry conditions of another. An edge should specify more than “next step”:

$$
e_{ij}=(\text{trigger},\text{input mapping},\text{preconditions},\text{authority},\text{failure policy})
$$

The composed path is not necessarily a single linear trace. It may contain forks, joins, retries, optional tasks, and multi-trail sandboxes. Correctness requires that an edge's preconditions be established by validated upstream evidence rather than inferred from a nominal success flag.

### 4.1 Three path-level invariants

**Dependency validity.** A downstream action must not consume an unverified or semantically incompatible upstream artifact.

**Authority preservation.** Delegation may narrow a permission but must not silently broaden it. Escalation is required when a child reaches a forbidden or unassigned decision.

**Failure containment.** A child failure should have a defined effect on its parent: retry, alternate trail, compensation, human review, partial completion, or abort.

Not all real-world actions are reversible. Compensation is a best-effort engineering strategy, not a guarantee of restoring the prior state.

## 5. Contract Reconciliation as a First-Class Operation

Naive composition assumes that if units can exchange data, they can be safely combined. This is false. Two units may agree on data types but disagree on authority, timing, safety, privacy, objectives, or responsibility.

Let $K_i$ denote the contract of unit $U_i$. A parent or coordinating unit proposes an effective composite contract:

$$
K_C=\mathrm{Reconcile}(K_1,\ldots,K_n;K_{\mathrm{parent}},\Pi)
$$

where $\Pi$ represents applicable governance policies and reconciliation rules. The operator may return a valid contract, a conditional contract requiring approval, or a conflict report. **It must not be assumed to always succeed.**

### 5.1 Reconciliation dimensions

| Dimension | Required check | Example conflict |
|---|---|---|
| Subject and authority | Delegator, delegatee, scope, revocation | A contractor cannot authorize a purchase |
| Goals | Shared outcomes and acceptable tradeoffs | Speed target conflicts with inspection rigor |
| Constraints | Safety, privacy, legal, physical and resource limits | Cloud transfer prohibited by data policy |
| Inputs/outputs | Schema, units, semantics, quality thresholds | “Completion” means different things |
| Time and budget | Deadlines, resource reservations, overruns | Two units spend the same budget allocation |
| Accountability | Approval, audit and dispute ownership | No actor owns final acceptance |
| Evidence | Required provenance and verification | Upstream confidence has no supporting trace |
| Evolution | Allowed updates and version boundaries | Child changes contract during execution |

### 5.2 Hard constraints versus negotiable preferences

A practical reconciliation process distinguishes **hard constraints**, which cannot be traded away, from **soft objectives**, which may be optimized within the feasible set. For example, cost and delivery speed may be negotiable, while a safety interlock is not.

A feasible composite plan $x$ must satisfy:

$$
x\in\bigcap_i \mathcal{C}_i \cap \mathcal{C}_{\mathrm{parent}}
$$

where $\mathcal{C}_i$ is the applicable constraint set of each participating unit. Empty intersection means the proposed composition is infeasible under current contracts. The correct output is a conflict or redesign request, not an invented compromise.

## 6. Delegation, Sovereignty, and Accountability

The contract hierarchy must distinguish three roles:

- **Originating subject:** owns or initiates the larger objective and its applicable authority.
- **Executing subject:** performs or controls a bounded delegated action.
- **Receiving subject:** imports a relay packet and decides what to accept, re-evaluate, or reject.

These roles may coincide but need not. A parent can delegate execution without delegating policy-setting authority. A receiving organization can reuse a method without accepting the sender's evaluation weights. Evidence travels; authority does not automatically travel with it.

A defensible delegation record includes the grantor, grantee, authorized action set, resource limits, expiry or revocation condition, audit expectations, and escalation route. This supports accountable collaboration without presuming one universal governing subject.

## 7. Scoring Forest Composition: Why Scores Cannot Simply Be Added

Each unit may use a Scoring Forest $F_i$ to guide its own decisions. Forests can represent multiple perspectives: cost, quality, reliability, safety, fairness, customer value, learning potential, or other domain-specific objectives.

A tempting but generally invalid rule is:

$$
S_C=\sum_i S_i
$$

Local scores may differ in scale, reference population, uncertainty, incentives, and measurement coverage. They may double-count shared benefits or hide catastrophic failures behind high averages. Moreover, a parent may value cross-unit interactions that no child measures.

We therefore propose a **perspective-aware folding operator**:

$$
F_C=\mathrm{Fold}(F_1,\ldots,F_n;K_C,\Gamma,\Omega)
$$

where $\Gamma$ contains cross-unit dependencies and $\Omega$ specifies normalization, uncertainty, evidence provenance, and aggregation policy. This is an architectural signature, not a uniquely defined mathematical solution.

### 7.1 A defensible folding sequence

1. **Preserve local evaluations:** keep original scores, scales, versions, and evaluators.
2. **Align semantics:** determine whether two metrics actually measure comparable constructs.
3. **Enforce constraints:** reject infeasible alternatives before compensatory optimization.
4. **Model interactions:** account for shared resources, coupled risks, and dependency effects.
5. **Normalize conditionally:** calibrate only where evidence supports comparability.
6. **Aggregate by perspective:** preserve Pareto tradeoffs or explicit policy weights where justified.
7. **Expose residuals:** retain unmeasured dimensions, uncertainty, dissent, and counter-evidence.
8. **Audit and re-evaluate:** let the receiving subject apply its own valuation framework.

When reliable normalization is unavailable, a vector of partially ordered outcomes may be preferable to a single scalar score.

## 8. Forward Guidance Across Levels

Scoring Forests must guide the *future*, not merely summarize the past. In a composed UIERU, forward guidance operates at two coupled levels:

**Local guidance:** each child selects candidate actions and controls execution under its own contract.

**Composite guidance:** the parent or coordinator allocates budgets, chooses which child to invoke, manages dependencies, initiates alternative trails, and adjusts global priorities when evidence changes.

A useful decision formulation is:

$$
\pi_C^*=\arg\max_{\pi\in\mathcal{P}_{\mathrm{feasible}}}
\mathrm{Value}_{F_C}(\pi\mid E_t,K_C,B_t)
$$

Here $E_t$ is current evidence and $B_t$ the remaining resource budget. The expression identifies the optimization target but does not imply that an exact optimizer is always available. Heuristics, human review, constraint solvers, and learned policies are all possible implementations.

### 8.1 Replanning triggers

Examples include failed acceptance tests, changed demand, resource exhaustion, contradictory evidence, unavailable services, emerging safety risks, and newly discovered opportunities. Replanning may affect one child or require renegotiating the parent contract. A local improvement must not be accepted if it violates global constraints.

## 9. Multi-Trail Composition and Sandbox Isolation

The Multi-Trail model developed in UIERU-004 and UIERU-005 introduces three broad roles: **Exploit** known viable approaches, **Explore** alternatives, and **Challenge** assumptions through counter-evidence. In composition, these trails can occur within a child, across several children, or at the parent level.

Examples:

- Two software implementation units independently develop candidate patches under the same interface contract.
- A verification unit attempts to falsify the preferred solution before release.
- A scheduling unit simulates alternate assignments while a production unit executes the approved plan.

Sandbox outputs are **candidate evidence**, not automatically authorized real-world actions. A trial may be computational, simulated, human-reviewed, or physically executed only within approved limits. Isolation must cover credentials, side effects, data access, resource quotas, and the promotion boundary.

### 9.1 Multi-trail selection

A coordinator may score each trail by expected task value, uncertainty reduction, novelty, risk, and resource cost. These quantities should be estimated and labeled rather than presented as known facts. Trails can be paused, terminated, merged, or retained as alternatives. Rejected trails may still be valuable when they reveal failure conditions.

## 10. Evidence-Preserving Structural Folding

**Folding** compresses many actions, trails, and subordinate results into a usable higher-level representation. **Unfolding** expands that representation when a decision, audit, or exception requires additional detail.

A safe folding policy distinguishes:

- **Summary:** concise decision-relevant outcome.
- **Trace pointers:** immutable or versioned references to supporting evidence.
- **Alternatives:** material nonselected candidates and why they were rejected.
- **Counter-evidence:** failed tests, dissent, contradictory observations.
- **Residuals:** unresolved problems and unmeasured dimensions.
- **Responsibility:** who evaluated, approved, and accepted the result.

Folding is lossy by design, but the losses must be explicit and governed. For high-stakes decisions, a summary without retrievable provenance is not sufficient. Privacy or confidentiality may restrict trace access; a relay should disclose that limitation rather than silently implying complete auditability.

## 11. Relay Across Nested and Federated Units

A child-to-parent relay and a peer-to-peer relay share the same basic requirement: **the receiver must know what was done, under which contract, with what evidence, and what remains unresolved.**

A candidate relay portfolio includes:

```yaml
relay_portfolio:
  schema_version: "0.1-proposal"
  unit_id: "inspection-unit-17"
  unit_version: "1.2"
  originating_contract: "contract-42"
  sender_subject: "inspection-team"
  recipient_subject: "maintenance-coordinator"
  authority_scope: "inspection-only"
  outcome:
    status: "completed-with-exceptions"
    deliverables: ["inspection-report-v3"]
    acceptance_evidence: ["checklist-hash-abc"]
  scoring:
    evaluator_version: "safety-forest-2"
    dimensions:
      coverage: "measured; see report"
      risk: "unresolved in zone B"
    aggregation_warning: "not comparable to cost score"
  trails:
    selected: "inspection-route-A"
    alternatives: ["inspection-route-B"]
    counter_evidence: ["sensor-disagreement-9"]
  provenance:
    trace_refs: ["trace-117", "trace-118"]
    restrictions: ["personnel-data-redacted"]
  residuals:
    - "zone B requires specialist inspection"
  evolution_candidates:
    - id: "delta-8"
      status: "unvalidated"
      proposal: "add redundant sensor check"
  receiver_actions_required:
    - "verify evidence and contract compatibility"
    - "decide whether to authorize follow-up"
```

The example is illustrative. A production schema would require typed identifiers, authentication, integrity protection, retention rules, and well-defined error handling.

### 11.1 Import is not endorsement

The receiving unit should validate schema compatibility, provenance, authority scope, acceptance evidence, and policy fit. It may then **accept**, **conditionally accept**, **request more evidence**, **re-evaluate**, or **reject** the portfolio. This preserves recipient-side scoring sovereignty and prevents blind propagation of errors through collective learning networks.

## 12. Evolution Under Composition

A UIERU may evolve its local Calling Path, Scoring Forest, contract templates, or relay strategy. But changing a child can break the assumptions of its parent or peers. Evolution therefore needs a compatibility discipline.

A candidate structural delta $\Delta_i$ should carry:

$$
\Delta_i=(\text{target},\text{change},\text{evidence},\text{tests},\text{compatibility},\text{rollback})
$$

Suggested lifecycle:

1. Detect a residual, repeated failure, inefficiency, or missed opportunity.
2. Propose a bounded structural delta with expected benefits and risks.
3. Validate in an appropriately isolated environment.
4. Check local and composite contract compatibility.
5. Evaluate against baselines and counter-evidence.
6. Approve, version, and deploy under authorized governance.
7. Observe outcomes and roll back when necessary.
8. Relay validated learning to eligible peers or registries.

A delta proven locally useful is not necessarily transferable. Context, dependencies, and evaluator assumptions must accompany it.

## 13. A Worked Example: Composing a Neighborhood Service

Consider a small lawn-care service with four UIERUs:

- **U1 — Customer Intake:** confirms property, service scope, access, and customer consent.
- **U2 — Scheduling:** selects an available time and allocates personnel and equipment.
- **U3 — Service Execution:** performs the approved work with safety constraints.
- **U4 — Verification and Billing:** checks acceptance evidence and generates the invoice.

The composite contract sets the customer scope, budget ceiling, safety requirements, deadline, and approval conditions. U1 relays an authorized work order to U2; U2 reserves resources; U3 records execution and exceptions; U4 verifies acceptance before settlement.

Suppose rain is forecast. U2's local scoring may favor rescheduling to minimize operational risk, while U1 records a customer's strict deadline. A composite forest must weigh feasibility, contractual obligations, safety, and customer preferences **without treating local scores as commensurate by default**. It may propose a revised appointment, a reduced scope with explicit consent, or escalation to the customer. It must not silently relax a safety condition.

A Challenge trail might test whether the planned route creates equipment conflicts; an Explore trail might evaluate a different scheduling arrangement. A failed alternative is retained with its evidence so future scheduling units can avoid the same conflict.

This example illustrates the architecture; it does not establish performance superiority over a conventional workflow engine.

## 14. A Second Example: Multi-Agent Software Engineering

A software-delivery composition might contain requirements, implementation, testing, security review, and release units. The parent contract specifies feature behavior, interfaces, access permissions, quality thresholds, and release authority.

The implementation unit may spawn competing coding trails, while a security Challenge unit attempts to find vulnerabilities. A passing test suite is useful evidence but not sufficient proof of correctness. Release authority remains with the designated approver. The parent folds code changes, test artifacts, security findings, unresolved issues, and deployment conditions into a release relay portfolio.

If an implementation unit updates its code-generation strategy, the change must not automatically alter release criteria or security permissions. This separation illustrates why **evolution boundaries** matter as much as execution boundaries.

## 15. A Candidate Composition Lifecycle

```text
RECEIVE parent objective and governance policy
DISCOVER candidate child units and their contracts
RECONCILE authority, goals, constraints, interfaces, and budgets
IF conflicts remain: request redesign, approval, or terminate
BUILD dependency graph and define relay checkpoints
ALIGN scoring perspectives; preserve incomparable dimensions
ALLOCATE resources and authorize bounded execution
WHILE parent acceptance criteria are not resolved:
    GUIDE children and evaluate emerging evidence
    SPAWN sandboxed alternatives only when justified
    VALIDATE child outputs before downstream consumption
    HANDLE failures by retry, escalation, compensation, or abort
    REPLAN when evidence or constraints change
FOLD results without erasing provenance or counter-evidence
VERIFY parent acceptance and approval conditions
RELAY outcome, alternatives, residuals, and accountability
PROPOSE structural deltas for separate validation
```

This is a reference workflow, not executable code. Domain-specific implementations must supply concurrency control, security, transaction semantics, monitoring, and recovery behavior.

## 16. Composition Conformance: Proposed Checks

A minimal conformance suite should exercise both successful and adversarial cases:

| Test | Expected property |
|---|---|
| Valid sequential handoff | Output satisfies downstream preconditions |
| Incompatible contracts | Composition refuses or escalates the conflict |
| Delegation overreach | Unauthorized action is blocked and logged |
| Score-scale mismatch | Aggregation is withheld or qualified |
| Shared-resource contention | Allocation prevents silent double spending |
| Child failure | Defined recovery or escalation is invoked |
| Sandbox escape attempt | Unapproved side effects are contained |
| Evidence gap | Receiver sees an explicit uncertainty or rejection |
| Version incompatibility | Upgrade is negotiated or safely rejected |
| Unvalidated structural delta | Promotion is blocked pending approval |
| Counter-evidence present | Folding retains the material contradiction |
| Federated import | Receiver can independently re-score or decline |

These checks describe desired properties. They are not evidence that any implementation already satisfies them.

## 17. Testable Hypotheses and Evaluation Design

**H1 — Composition reliability.** Contract-reconciled UIERU workflows produce fewer unauthorized or semantically invalid handoffs than functionally equivalent ad hoc agent chains.

**H2 — Guidance efficiency.** Cross-level forward guidance improves task completion per unit cost under dynamic constraints relative to fixed workflow orchestration.

**H3 — Evidence retention.** Evidence-preserving folding increases downstream error detection and audit reconstruction compared with outcome-only summaries.

**H4 — Transfer quality.** Relay portfolios containing alternatives, counter-evidence, and residuals improve recipient adaptation compared with transferring only successful trajectories.

**H5 — Evolution safety.** Compatibility-checked structural deltas cause fewer regressions in composed workflows than unconstrained local updates.

### 17.1 Baselines

Compare against: (a) a conventional workflow engine with explicit task interfaces; (b) a multi-agent orchestration system without canonical relay portfolios; (c) a flat centralized planner; and (d) the same UIERU architecture with contract reconciliation, evidence retention, or forward guidance ablated individually.

### 17.2 Metrics

Measure completion quality, latency, compute and human effort, policy violations, recovery success, calibration, provenance completeness, audit reconstruction time, transfer performance, structural-update regressions, and operator burden. Report confidence intervals and workload characteristics. Include cases where UIERU overhead outweighs its benefits.

## 18. Limits and Counterexamples

The composition model has important boundaries:

1. **Trivial tasks:** wrapping a simple deterministic function as a UIERU may add cost without benefit.
2. **Unreconcilable contracts:** some collaborations should not proceed.
3. **Incommensurable values:** a single aggregate score may be inappropriate or ethically unacceptable.
4. **Opaque external actors:** provenance and authority guarantees may be unverifiable.
5. **Non-reversible actions:** sandbox and rollback techniques cannot eliminate real-world harm.
6. **Dynamic organizational politics:** formal contracts cannot capture all tacit incentives and relationships.
7. **Overhead and latency:** fine-grained nesting can generate excessive coordination and evidence traffic.
8. **Security and privacy:** portability can conflict with confidentiality or data-locality obligations.
9. **Evaluator capture:** shared scoring frameworks can amplify common blind spots or Goodhart effects.
10. **Emergent interactions:** correct child behavior does not guarantee correct global behavior.

A strong engineering result would identify the workloads and conditions where UIERU composition is useful, rather than asserting universal superiority.

## 19. Research Directions

Several questions remain open:

- Can contract reconciliation be partially automated with machine-checkable proofs and meaningful human escalation?
- What algebraic properties, if any, can safe scoring-fold operators satisfy across domains?
- How should a parent allocate exploration budgets when child uncertainties are correlated?
- What is the smallest relay portfolio that preserves decision-critical counter-evidence?
- Can compatibility tests predict downstream regressions before a structural delta is promoted?
- How should federated units reconcile provenance without disclosing protected information?
- At what scale does hierarchical coordination outperform flat or market-like organization?

The accompanying `SPEC-004-Composition-Evolution-and-Conformance.md` is intended to refine these questions into concrete interfaces and tests.

## 20. Conclusion

The proposed UIERU is more than an executable path and more than a score-bearing task wrapper. Its engineering significance depends on whether units can be **composed, nested, folded, relayed, and evolved** while retaining enforceable contracts, forward guidance, evidence provenance, and subject-level evaluation sovereignty.

The decisive shift is from merely connecting capabilities to **reconciling their authority, objectives, evidence, and change processes**. A Calling Graph provides the operational substrate; a Scoring Forest guides and evaluates choices; contracts establish legitimate boundaries; relay preserves transferable knowledge; and governed evolution allows the organization to learn without silently invalidating its own commitments.

This is a research architecture and a testable engineering proposal. Its usefulness must be demonstrated against simpler alternatives, with explicit attention to coordination overhead, failure cases, and contexts where no UIERU wrapping is warranted.

---

## Series Context and Related Research

This article is self-contained. Within the UIERU series, it extends the canonical unit of **UIERU-002**, the Calling Path / Scoring Forest duality of **UIERU-003**, and the multi-trail and counter-evidence mechanisms of **UIERU-004** and **UIERU-005**. Related structural-intelligence projects may offer additional perspectives on Calling Graphs, scoring forests, portable intelligence, and collective learning, but they are not prerequisites for this paper.

**Suggested citation:** Tan, Sizhe, and GPT-Obot. (2026). *UIERU-006: Composition, Nesting, Folding, and Contract Reconciliation*. Universal Intelligence Evolution and Relay Unit, v1.0.0. DOI pending.

**License:** See repository-level license and citation metadata.
