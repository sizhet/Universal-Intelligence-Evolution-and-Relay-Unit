# UIERU-EXT-002 — Big-Animal Intelligence Organization and Platform-Level Structural RSI

**Subtitle:** From Distributed Intelligence Units to Governed Platform-Scale Structural Evolution  
**Authors:** Sizhe Tan & GPT-Obot  
**Version:** 1.0.0  
**Status:** Research extension; proposed architecture and testable hypotheses  
**Project:** Universal Intelligence Evolution and Relay Unit (UIERU)  
**Location:** `docs/extensions/`  
**Companion:** `UIERU-EXT-001-Subject-Indexed-World-Models-and-Structural-Memory.md`  

---

## Abstract

Large AI platform organizations—here called **Big Animals**—operate across foundation models, inference infrastructure, agent runtimes, tools, applications, safety systems, and developer ecosystems. Their intelligence challenge is not merely to increase model capability. It is also to organize heterogeneous capabilities, distribute authority, preserve evidence, learn across tasks, and improve the structures that guide future intelligence work. This paper proposes the **Universal Intelligence Evolution and Relay Unit (UIERU)** as an optional organizational building block for that challenge. A UIERU combines a governed contract, a Calling Path, a forward-guiding Scoring Forest, structural relay, and evidence-driven evolution. At platform scale, these units may form federated forests of capabilities and evaluators rather than one monolithic controller. The paper develops a reference architecture, interface contracts, platform-level structural recursive self-improvement (RSI), multi-trail experimentation, governance boundaries, economics, failure modes, and falsifiable validation plans. The proposal does not assert that large organizations already implement UIERU, nor that structural RSI necessarily improves intelligence. Both are subjects for empirical evaluation.

**Keywords:** UIERU; Big Animal; intelligence organization; structural RSI; forward guidance; distributed scoring forest; multi-trail sandbox; structural relay; capability registry; evaluator governance; subject sovereignty; collective learning.

## 1. The Big-Animal Problem

A Big Animal is an AI-intensive organization or platform that develops or operates several layers of an intelligence ecosystem: models, compute, tool access, agent orchestration, evaluation, products, and external integrations. The term denotes an **organizational role and scale**, not a biological claim or a judgment about any particular company.

Consider a platform serving software engineering, research, enterprise operations, and customer assistance. A task may cross model selection, retrieval, code execution, policy checking, human approval, testing, and handoff. Each layer can be locally competent while the overall system remains inefficient, opaque, or difficult to improve.

The key problem is therefore:

> How can a large AI platform organize existing intelligence capabilities into governable, evidence-preserving, composable, and progressively improvable units—without replacing those capabilities or centralizing every decision?

This question differs from simply scaling parameters, tokens, agents, or compute. It concerns **intelligence organization scaling**.

## 2. Scope and Non-Claims

This paper focuses on architecture and engineering research. It does **not** claim that:

- Every workflow should be converted into a UIERU.
- Every UIERU is autonomous, conscious, or a subject.
- One universal scoring function can faithfully represent all objectives.
- Platform ownership of infrastructure implies ownership of users' experiences or evaluations.
- Sharing an improvement candidate implies permission to deploy it.
- Recursive structural modification guarantees recursive intelligence gain.

A UIERU is a selective coordination and learning structure. Straightforward stateless tool calls and low-risk workflows may remain simpler and cheaper outside it.

## 3. The Canonical Unit at Platform Scale

The base architecture remains:

\[
U=(K,P,F,R,E)
\]

where:

| Element | Local role | Platform-scale concern |
|---|---|---|
| **K — Contract** | Goals, actors, authority, constraints, acceptance | Tenant boundaries, delegation, policy compatibility |
| **P — Calling Path** | Executable sequence or graph of work | Routing across models, tools, teams, and regions |
| **F — Scoring Forest** | Forward guidance, monitoring, evaluation | Distributed evaluators, calibration, conflict management |
| **R — Relay** | Evidence-rich handoff and portability | Cross-domain interchange, provenance, retention |
| **E — Evolution** | Residuals, experiments, verified deltas | Platform-level structural RSI, staged rollout, rollback |

At scale, the unit remains small enough to own a bounded responsibility. Composition, not a giant universal unit, provides broader capabilities.

## 4. Three Planes and a Distributed Runtime

We propose four cooperating architectural components.

### 4.1 Global Governance and Interoperability Plane

This plane publishes policy constraints, identity and authorization services, contract schemas, provenance requirements, registry conventions, and conformance tests. It may enforce mandatory security restrictions, but **must not silently replace a subject's legitimate objectives with platform convenience metrics**.

### 4.2 Domain Intelligence Forests

Domain-scoped forests organize evaluators, capability precedents, routing strategies, and experimental practices for software, science, operations, or other specialties. A coding evaluator and a medical safety evaluator should not be forced into a single interchangeable scalar.

### 4.3 Subject and Tenant Planes

These hold locally authorized preferences, histories, evaluation policies, and task-specific context. A subject identifier, executing agent identifier, evaluator identifier, and provenance identifier are distinct. Cross-tenant use requires explicit data and authority boundaries.

### 4.4 Distributed UIERU Runtime and Relay Network

Runtime nodes execute Calling Paths, consult Scoring Forests, create isolated Multi-Trail experiments, emit signed or integrity-protected relay records, and submit structural improvement proposals. The runtime can span human teams and machine services.

A useful conceptual decomposition is:

```text
Global Governance / Interoperability
       | policies, schemas, registries, audit
       v
Domain Scoring Forests <----> Subject / Tenant Evaluation Planes
       | guidance requests           | local goals and consent
       v                             v
Distributed UIERU Runtime ----> Relay Portfolio Exchange
       |                               |
       v                               v
Sandbox Experiments ------> Validated Structural Precedents
                                      |
                                      v
                           Staged Structural Evolution
```

The diagram is conceptual, not a required physical deployment topology.

## 5. Why a Distributed Scoring Forest?

A monolithic score risks hiding incomparable objectives: quality, latency, cost, safety, privacy, user satisfaction, learning value, and regulatory constraints. A distributed Scoring Forest instead preserves multiple evaluators and their scope.

Each evaluator should declare:

- Its **perspective** and authorized domain.
- The evidence it consumes and produces.
- Calibration and uncertainty information.
- Hard constraints versus negotiable preferences.
- Its provenance, version, and known failure conditions.

For candidate path \(p\), an illustrative representation is:

\[
S(p) = \{s_{quality}(p), s_{cost}(p), s_{risk}(p), s_{latency}(p), s_{learning}(p)\}
\]

Selection is a **constrained multi-objective decision**, not necessarily a weighted sum. Non-negotiable authorization and safety conditions filter candidates before optimization. Remaining alternatives may be compared by Pareto dominance, lexicographic priorities, or an explicitly approved aggregation rule. Conflicts and uncertainty should survive folding into the relay record.

## 6. Forward Guidance as a Platform Service

A platform can expose forward guidance through a narrow interface without forcing every application to adopt the entire UIERU lifecycle.

```yaml
request_type: guidance.evaluate_candidates
contract_ref: contract:tenant-42/task-173
subject_ref: subject:tenant-42/user-8
candidate_paths:
  - path_ref: path:stable-implementation
  - path_ref: path:experimental-implementation
scoring_perspectives:
  - quality
  - security
  - latency
  - cost
hard_constraints:
  - no_production_writes_without_approval
budget:
  compute_units: 80
  sandbox_minutes: 30
response_requirements:
  - admissible_candidates
  - uncertainty
  - counter_evidence
  - recommended_next_step
  - provenance
```

The response is **advice within a contract**. It does not itself grant access to production systems, customer data, or budget beyond the existing authorization.

## 7. Multi-Trail Intelligence at Scale

Large platforms can benefit from portfolio-based exploration when failures are costly or alternatives are uncertain. A minimal portfolio distinguishes:

- **Exploit:** execute a validated or best-known approach.
- **Explore:** test a plausible alternative in an appropriate sandbox.
- **Challenge:** search for counterexamples, failure modes, or invalid assumptions.

A platform scheduler may allocate exploration budget based on expected decision value, risk, uncertainty, and cost. The scheduler must also prevent runaway branching, correlated experiments, and experiments that violate tenant or environment boundaries.

### 7.1 Multi-Trail Lifecycle

```text
PROPOSED -> ADMISSIBILITY_CHECKED -> BUDGETED -> SANDBOXED
         -> OBSERVED -> COMPARED -> SETTLED -> RELAYED

At any stage: REJECTED / PAUSED / EXPIRED / ABORTED
```

A real-world action is a separate, explicitly authorized transition; sandbox approval does not imply production approval.

### 7.2 Example: Cross-Product Software Reliability

A coding platform observes recurring deployment regressions in several products. It can run a known release process (Exploit), test an alternative dependency-checking workflow (Explore), and deliberately construct compatibility-breaking cases (Challenge). The outcome is not merely a chosen patch. It is a **portfolio of results**, including failures, confidence limits, and a candidate improvement to future release guidance.

## 8. Structural Precedent Registry

A Big Animal needs a way to distinguish reusable, validated intelligence structures from raw anecdotes. We propose a registry of **structural precedents**.

A precedent should contain:

| Field | Purpose |
|---|---|
| `precedent_id` and `version` | Stable reference and change history |
| `problem_signature` | Where the precedent may apply |
| `contract_constraints` | Required authority and operating conditions |
| `calling_path_pattern` | Reusable execution structure |
| `scoring_perspectives` | Evaluation logic and calibration scope |
| `supporting_evidence` | Trials, outcomes, and provenance |
| `counter_evidence` | Known failures and disconfirming cases |
| `transfer_limits` | Domains, tenants, environments not validated |
| `adoption_status` | Proposed, sandboxed, approved, deprecated |
| `rollback_reference` | Safe reversal mechanism where applicable |

Registry discovery is not execution authorization. A receiving unit must perform localization, compatibility checks, and its own evaluation.

## 9. Platform-Level Structural RSI

The central hypothesis is that a platform can improve **the structures that generate and govern future intelligent work**, not only the outputs of individual tasks.

A candidate loop is:

\[
\text{Task Residuals} \rightarrow \text{Candidate Structural Delta}
\rightarrow \text{Adversarial Validation} \rightarrow \text{Approved Rollout}
\rightarrow \text{Measured Outcomes}
\]

A structural delta might change:

1. Calling Path dispatch or task decomposition.
2. Scoring Forest evaluator composition or calibration.
3. Sandbox exploration and counter-evidence protocols.
4. Relay schemas, provenance checks, or localization rules.
5. The procedure used to propose and validate later deltas.

The fifth case is recursively self-referential: the platform attempts to improve its improvement process. This is **structural RSI**, distinct from retraining model weights. The two may complement one another, but neither is a prerequisite for the other.

### 9.1 Levels of Structural Improvement

| Level | Target | Example |
|---|---|---|
| L0 | Task outcome | Fix a specific bug |
| L1 | Execution structure | Improve bug-triage Calling Path |
| L2 | Evaluation structure | Add independent regression-risk evaluator |
| L3 | Learning structure | Improve precedent retrieval and evidence thresholds |
| L4 | Improvement governance | Revise the validation protocol itself under external approval |

Moving to a higher level is not automatically better. Changes to evaluators and approval procedures demand stronger independent oversight.

### 9.2 Separation of Proposal, Evaluation, and Deployment

No component should be able to propose a structural change, generate all its evidence, approve it, and deploy it without independent checks. The platform should require different roles or independently controlled processes for these steps, with auditable exceptions for narrowly scoped low-risk changes.

## 10. Candidate-to-Deployment Protocol

```text
1. Detect recurring residual or counter-evidence pattern.
2. Determine whether the pattern is local or cross-domain.
3. Draft a versioned structural delta and applicability claims.
4. Run static policy and contract compatibility checks.
5. Execute sandbox A/B and adversarial challenge trails.
6. Evaluate quality, cost, latency, safety, and transfer limits.
7. Seek approval from the authorized deployment owner.
8. Release to a bounded cohort with monitoring and kill switch.
9. Compare against a matched baseline; record regressions.
10. Promote, restrict, or roll back; publish evidence and limits.
```

Negative findings must remain discoverable; otherwise the platform can repeatedly rediscover and redeploy known failures.

## 11. Structural Relay and Portability

Relay should carry more than an answer. A minimal **Relay Portfolio** contains contract context, path and scoring versions, selected outcome, alternative trails, evidence, counter-evidence, unresolved residuals, candidate deltas, provenance, and explicit transfer restrictions.

```yaml
relay_portfolio:
  schema_version: "1.0"
  portfolio_id: rp:release-reliability-2026-014
  source_unit: uieru:engineering/release-42
  destination_scope: domain:software-delivery
  purpose: structural_learning
  authority:
    data_use_basis: approved_internal_learning
    production_execution_granted: false
  artifacts:
    selected_path: path:validated-release-check
    alternative_paths:
      - path:fast-check-rejected
    evidence_refs:
      - evidence:test-suite-781
    counter_evidence_refs:
      - evidence:compatibility-break-23
    residuals:
      - unresolved_dependency_edge_case
    structural_delta_ref: delta:release-check-v3
  provenance:
    issuer: service:relay-gateway
    created_at: "2026-10-20T16:00:00Z"
    integrity_digest: "sha256:<computed-by-implementation>"
  transfer_limits:
    - not_validated_for_safety_critical_systems
    - receiver_must_revalidate
```

This example is illustrative, not a finalized wire specification. Actual schemas and validation rules belong in `SPEC-001` through `SPEC-004`.

## 12. Subject Sovereignty, Tenancy, and Intellectual Boundaries

Big-Animal scale introduces asymmetric power. The platform may control compute, model routing, telemetry, and registries, while individuals or organizations supply objectives, sensitive context, and accumulated experience. These roles must not be collapsed.

A robust architecture separates:

- **Infrastructure control:** who operates the runtime and enforces system security.
- **Task authority:** who can authorize actions for a given objective.
- **Evaluation sovereignty:** whose legitimate criteria determine success.
- **Data rights and permissions:** which information may be retained, processed, or shared.
- **Structural contribution rights:** whether a learned pattern may be published, reused, or commercialized.

The technical ability to extract a reusable pattern does not itself establish permission to do so. Where possible, shared precedents should be minimized, de-identified, and independently checked for leakage; some data should remain entirely local. Formal legal requirements vary by jurisdiction and contract.

## 13. Economics of Intelligence Organization Scaling

UIERU adds coordination overhead: contracts, provenance, evaluator calls, sandbox compute, registry maintenance, and review. The architecture is justified only where these costs are offset by benefits such as reduced failures, improved reuse, safer delegation, or faster validated improvement.

For a workload family \(w\), an illustrative decision criterion is:

\[
\Delta V_w = V_{quality} + V_{reuse} + V_{risk\ reduction}
- C_{coordination} - C_{compute} - C_{governance}
\]

The terms must be measured in compatible units or evaluated as a constrained multi-objective decision; this equation is a bookkeeping abstraction, not a validated economic law. Low-risk, low-reuse tasks may rationally bypass UIERU.

## 14. Failure Modes and Controls

| Failure mode | Consequence | Proposed control |
|---|---|---|
| Global score monoculture | Suppresses legitimate local objectives | Perspective-aware forests; explicit conflict reporting |
| Goodhart effects | Optimizes proxy metrics instead of outcomes | Counter-evidence, independent evaluators, outcome audits |
| Runaway multi-trail branching | Excessive compute and latency | Budgets, branch caps, stopping rules |
| Contaminated structural precedents | Spreads invalid improvements | Provenance, applicability limits, receiver validation |
| Cross-tenant leakage | Privacy or contractual breach | Isolation, data minimization, permission checks |
| Self-approval of RSI | Unsafe or unaccountable changes | Independent authorization and staged deployment |
| Centralized single point of failure | Broad service disruption | Federation, local fallback, version pinning |
| Evaluator drift | Unreliable decisions over time | Calibration, holdouts, adversarial monitoring |
| Registry lock-in | Reduced interoperability | Exportable schemas and protocol adapters |
| Governance overload | Benefits erased by bureaucracy | Risk-tiered conformance and selective adoption |

## 15. Interoperability: Complement Existing Protocols

UIERU should sit **above or alongside** existing orchestration, tool, and agent communication mechanisms rather than replacing them. For example, a Calling Path can invoke conventional APIs and tool interfaces; relay adapters can map to existing agent communication channels. UIERU's distinctive proposed addition is the portable combination of **contract, forward guidance, evidence, counter-evidence, structural precedent, and governed evolution**.

Compatibility must be tested rather than presumed. An interoperable UIERU should expose stable identity, schema versions, idempotency keys, error semantics, capability negotiation, and explicit authorization boundaries.

## 16. Reference Interface Surface

The following endpoints are conceptual, not a published standard:

```text
POST /contracts/validate
POST /guidance/evaluate
POST /trails/propose
POST /trails/{id}/authorize
POST /trails/{id}/settle
POST /relay-portfolios
POST /relay-portfolios/{id}/accept
POST /precedents/query
POST /structural-deltas/submit
POST /structural-deltas/{id}/validate
POST /structural-deltas/{id}/approve
POST /structural-deltas/{id}/rollout
POST /structural-deltas/{id}/rollback
```

Every mutating endpoint should require authenticated principals, scoped authorization, version checks, auditable decisions, and replay-safe semantics. `approve` and `rollout` should be independently permissioned.

## 17. Deployment Profiles

A platform should support progressive adoption rather than requiring all capabilities at once:

| Profile | Minimum behavior | Suitable use |
|---|---|---|
| **P0 — Contracted** | Explicit scope, actors, constraints | Governed task execution |
| **P1 — Guided** | Forward scoring and traceable selection | Risk-aware orchestration |
| **P2 — Exploratory** | Budgeted Multi-Trail sandbox | Complex uncertain tasks |
| **P3 — Relay-Capable** | Provenance-rich exchange and receiver validation | Cross-team handoff |
| **P4 — Composable** | Nested contracts and scoring reconciliation | Multi-domain workflows |
| **P5 — Evolvable** | Independently verified structural deltas | Platform structural RSI |

These are **research profiles** for this paper, not claims of certification or replacements for the canonical repository specifications. Formal conformance must be reconciled with `SPEC-004` before implementation.

## 18. Testable Hypotheses

**H1 — Reuse efficiency.** Across matched recurring workflows, a structural precedent registry reduces time to validated reuse relative to a documentation-only baseline.

**H2 — Forward guidance.** A multi-perspective forward Scoring Forest reduces preventable task failures compared with post-hoc-only evaluation at comparable compute budgets.

**H3 — Counter-evidence.** Challenge trails improve detection of brittle solutions relative to exploit-only execution, at measurable additional cost.

**H4 — Structural relay.** Evidence-rich portfolios reduce recipient rework and provenance loss compared with result-only handoff.

**H5 — Platform structural RSI.** Independently validated changes to dispatch, evaluation, or relay protocols improve subsequent out-of-sample task performance compared with frozen protocols.

**H6 — Federation.** Distributed scoring with local sovereignty reduces cross-domain objective conflicts compared with a single global weighted score, without unacceptable latency.

**H7 — Selective adoption.** Risk-tiered UIERU deployment yields better net operational value than mandatory UIERU wrapping of every task.

**H8 — Governance integrity.** Separating proposal, evaluation, approval, and deployment reduces unauthorized structural changes relative to a self-approving pipeline.

All hypotheses can fail. An absence of benefit, excessive coordination cost, or unacceptable governance burden would be substantive findings.

## 19. Validation Program

### 19.1 Baselines

1. Ordinary workflow orchestration without structural relay.
2. Agent orchestration with post-hoc evaluation only.
3. Forward guidance without Multi-Trail challenge.
4. Multi-Trail without reusable precedent registry.
5. Centralized scalar scoring versus distributed perspective-aware scoring.
6. Frozen structural protocols versus independently validated evolution.

### 19.2 Experimental Design

Use matched task suites spanning software engineering, internal operations, and research workflows. Randomize or counterbalance workload assignment, keep model and compute budgets comparable where possible, and report confidence intervals. Separate **in-domain** from **out-of-domain** transfer. Include holdout tasks unknown to the improvement proposal process.

### 19.3 Metrics

- Task success and independently judged quality.
- Safety violations and unauthorized action attempts.
- End-to-end latency, compute consumption, and coordination overhead.
- Evaluator disagreement, calibration, and drift.
- Counterexample discovery rate and false-alarm rate.
- Relay completeness, provenance integrity, and recipient revalidation cost.
- Structural delta acceptance, regression, and rollback rates.
- Cross-domain transfer gain and negative transfer.
- User/tenant control violations and data-leakage incidents.

### 19.4 Go/No-Go Gates

A structural delta should not advance solely because an internal scoring metric improved. Promotion should require predefined thresholds on quality, risk, cost, and out-of-sample evidence, plus the relevant authority approval. Failed candidates remain documented with their applicability boundaries.

## 20. A Minimal Engineering Pilot

Start with a narrow platform function, such as CI regression triage across three internal software teams.

**Phase A — Instrumentation:** establish contracts, baseline traces, and independent outcome metrics.

**Phase B — Guidance:** add a domain Scoring Forest to rank candidate triage paths under fixed budgets.

**Phase C — Challenge:** add one bounded adversarial sandbox trail per eligible incident.

**Phase D — Relay:** publish evidence-preserving portfolios and require receiver-side validation.

**Phase E — Structural RSI:** propose a versioned change to the triage dispatch policy; test against held-out incidents; stage deployment; retain rollback.

The pilot succeeds only if its incremental value exceeds measurable operating costs and it respects authorization boundaries.

## 21. Open Research Questions

1. Which tasks benefit from UIERU organization, and which should remain simple tool calls?
2. How can a Scoring Forest maintain calibration across heterogeneous domains?
3. How should evaluators express non-comparable or conflicting values without premature scalar folding?
4. What is the minimum useful Relay Portfolio for cross-team learning?
5. How can a platform prevent sensitive subject memory from leaking into public structural precedents?
6. What independent evidence is sufficient to approve a change to the evaluation process itself?
7. How should registry search distinguish genuine structural analogies from superficial matches?
8. Can structural RSI produce persistent out-of-sample gains rather than benchmark-specific optimization?
9. What is the operational break-even point for selective UIERU adoption?
10. How can interoperable, portable units coexist with competing platform governance policies?

## 22. Relationship to the UIERU Research Program

This extension builds on, but does not require prior reading of:

- `UIERU-002-Canonical-UIERU-Contracts-Execution-Guidance-and-Relay.md`
- `UIERU-003-Calling-Path-and-Scoring-Forest-Duality.md`
- `UIERU-004-Forward-Guidance-and-Multi-Trail-Intelligence.md`
- `UIERU-007-Structural-Relay-Provenance-and-Intelligence-Portability.md`
- `UIERU-008-Bidirectional-Collective-Learning-and-Relay-Ecosystems.md`
- `UIERU-009-Residual-Driven-Structural-Evolution-and-Recursive-Improvement.md`
- `UIERU-010-Universal-Architecture-Engineering-Boundaries-and-Validation.md`
- `UIERU-EXT-001-Subject-Indexed-World-Models-and-Structural-Memory.md`

The companion extension `UIERU-EXT-003-Subject-Sovereignty-and-Collective-Intelligence-Ecosystems.md` will examine the tension between platform-level learning and subject-level memory, authority, and evaluation.

## 23. Conclusion

For a Big Animal, intelligence organization is a distinct scaling challenge. More capable models do not automatically yield coherent, portable, governable, and self-improving intelligence workflows. UIERU offers a **hypothesized organizational layer**: bounded contracts, executable Calling Paths, distributed forward Scoring Forests, evidence-rich structural relay, and governed structural evolution. Its platform-level promise is not unrestricted automation, but **reliable intelligence reuse and improvement under explicit authority and independent validation**.

The central proposition is therefore:

> **Model scaling expands available capability; intelligence organization scaling determines how capabilities are coordinated, evaluated, relayed, and improved.**

Whether UIERU provides a superior engineering solution must be decided by comparative experiments, including negative results and real operating costs.

---

## Research Notes and Terminology

- **Big Animal:** an informal name for an AI platform organization operating multiple layers of an intelligence ecosystem.
- **Structural RSI:** recursive improvement of execution, guidance, relay, or improvement procedures, not necessarily model-weight updates.
- **Scoring Forest:** a set of perspective-aware evaluators and guidance structures; not a claim of a universal objective function.
- **Structural precedent:** a reusable, evidence-bounded pattern with applicability conditions and counter-evidence.
- **Subject sovereignty:** bounded authority over a subject's objectives, history, evaluation, and permitted reuse; not unlimited exemption from platform security or law.

**Citation suggestion:** Tan, S., & GPT-Obot. (2026). *Big-Animal Intelligence Organization and Platform-Level Structural RSI*. UIERU Research Extension 002, v1.0.0. Repository: *Universal Intelligence Evolution and Relay Unit*.

**License:** Governed by the repository's declared license; this paper does not independently assign one.
