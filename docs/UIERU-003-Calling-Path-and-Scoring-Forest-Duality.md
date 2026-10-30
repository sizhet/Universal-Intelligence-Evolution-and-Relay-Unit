# UIERU-003 — Calling Path and Scoring Forest Duality

**Universal Intelligence Evolution and Relay Unit (UIERU)**  
**Subtitle:** From Recorded Behavior to Forward-Guided, Evidence-Coupled, and Relayable Intelligence  
**Authors:** Sizhe Tan & GPT-Obot  
**Version:** 1.0.0  
**Date:** 2026-10-20  
**Status:** Research architecture and testable design hypotheses; not an established universal standard  
**Repository:** [Universal-Intelligence-Evolution-and-Relay-Unit](https://github.com/sizhet/Universal-Intelligence-Evolution-and-Relay-Unit)  
**Companions:** [UIERU-001](UIERU-001-From-Calling-Paths-to-Evolvable-Intelligence-Units.md) · [UIERU-002](UIERU-002-Canonical-UIERU-Contracts-Execution-Guidance-and-Relay.md)

---

## Abstract

A calling path records or organizes **what is done and in what dependency structure**. A scoring tree or forest represents **what matters, how alternatives are evaluated, and how decisions are constrained**. Both are useful separately; neither alone guarantees a transferable, governable intelligence unit. This paper proposes **Calling Path–Scoring Forest Duality** as the operational core of the Universal Intelligence Evolution and Relay Unit (UIERU): a contract-governed coupling in which evaluation guides path construction and execution *before and during* action, while execution returns evidence that updates evaluation, settlement, relay, and candidate structural improvements.

The duality is not a claim that execution and scoring are mathematically identical, nor that a scoring forest always produces a globally optimal path. It is a design relationship with explicit mappings, state, authority, feedback, and conformance conditions. We develop the coupling model, a forward-guidance lifecycle, score folding across nested units, multi-trail search, evidence-based settlement, and relay of both selected and rejected alternatives. We identify failure modes, including reward misspecification, incomparable perspectives, feedback delay, exploration cost, and unsafe authority transfer, and propose falsifiable evaluation criteria. The architecture is **selective and non-replacement-oriented**: human judgment, existing workflows, planners, LLMs, tools, and specialized control systems remain valid components.

**Keywords:** calling graph; calling path; scoring forest; forward guidance; behavior–valuation duality; evidence provenance; multi-trail; sandbox; relay; compositional intelligence; structural evolution.

---

## 1. A Concrete Task: Guidance Changes the Path

A lawn-care provider is asked to mow a yard before an afternoon event. A simple recorded calling path might be:

```text
Accept request -> Prepare tools -> Mow -> Clean -> Inspect -> Handoff
```

A record of this path does not explain *why* the provider selected a mower, postponed a step, or avoided a wet slope. A post-hoc quality score does not help select a safer plan in advance.

A forward-guiding scoring structure can consider completion quality, weather, safety, time, cost, and customer constraints **before** execution. It can reject an unsafe route, rank alternatives, monitor changing conditions, and specify evidence needed for acceptance. The executed path then returns measurements, observations, exceptions, and unfinished obligations. Those records can change future guidance and can accompany the handoff to another provider.

This is the basic UIERU insight: **an execution structure and a valuation structure become more useful when their interaction is explicit, continuous, and relayable**.

The same organizational pattern may apply to software agents, manufacturing, logistics, and human teams. The claim concerns reusable *interfaces and responsibilities*, not identical implementations or guaranteed gains at every scale.

## 2. Two Distinct Structures

### 2.1 Calling graph and calling path

Let a calling graph be a directed, attributed structure:

$$
G_C=(N_C,E_C,\tau,\sigma),
$$

where nodes represent actions, services, observations, decisions, or nested units; edges represent admissible calls, dependencies, transitions, or handoffs; $\tau$ assigns types; and $\sigma$ holds execution-relevant state or metadata.

A **calling path** $P$ is an execution trace, plan, or structured subgraph of $G_C$. The term *path* is deliberately broad here: it may include conditional branches, bounded loops, parallel threads, and a nested calling graph. A trace records what occurred; a plan records what is intended; neither should be silently confused with the other.

Calling structures can preserve order, dependencies, inputs and outputs, provenance, and reusable precedents. They do **not**, merely by existing, provide a complete theory of goal selection, preference, authority, or settlement.

### 2.2 Scoring tree, forest, and folding

Let a scoring forest be a collection of perspective-aware evaluation structures:

$$
F=\{T_1,T_2,\ldots,T_m\},
$$

where each $T_j$ may represent a task objective, stakeholder perspective, safety criterion, resource constraint, or specialized valuation model. The forest may combine numeric scores, ordinal judgments, logical gates, hard constraints, and human decisions. It need not be differentiable or reducible to one scalar.

**Scoring folding** summarizes or reconciles lower-level evidence and scores into a decision at a higher level, subject to explicitly declared aggregation and veto rules. Folding must not erase provenance, unresolved disagreement, or non-compensable constraints merely to produce a convenient single number.

### 2.3 Why coupling matters

A calling path without forward valuation can become an efficiently recorded mistake. A scoring forest without a callable execution interface can become a disconnected policy document. Their **duality** is a controlled exchange:

- **Guidance → path:** constraints, candidate generation, ranking, branching, scheduling, and stopping decisions.
- **Path → guidance:** observations, costs, outcomes, exceptions, counter-evidence, and confidence updates.
- **Jointly → relay:** accepted result, supporting evidence, alternatives, residuals, and responsibility boundaries.

## 3. The UIERU Boundary and the Dual Core

Following UIERU-002, define the canonical unit:

$$
U=(K,P,F,R,E),
$$

where $K$ is the governing contract, $P$ the calling path, $F$ the scoring forest, $R$ the relay interface, and $E$ the structural evolution mechanism.

This paper concentrates on the **$P\leftrightarrow F$** interaction. Its operation remains bounded by $K$: the scorer cannot grant itself permissions, and the executor cannot silently redefine acceptance criteria. The relay $R$ preserves decisions and evidence; evolution $E$ may propose modifications but must pass validation before deployment.

```text
                    Contract K
         goals | authority | constraints
                         |
                         v
    +--------------------+--------------------+
    |                                         |
    v                                         v
Calling Path P  <------ guidance ------  Scoring Forest F
(actions, state) ------ evidence ------> (criteria, control)
    |                                         |
    +--------------------+--------------------+
                         |
                         v
              Evaluation / Settlement
                         |
                         v
             Relay R + Evolution E
```

---

![Fig-002-Calling-Path-and-Scoring-Forest-Duality.png](../figures/Fig-002-Calling-Path-and-Scoring-Forest-Duality.png)

---

## 4. The Duality as an Operational Contract

A useful coupling is more than a score attached to an event. We propose five minimum interface obligations:

1. **Shared referents:** path steps and scoring criteria refer to the same task, objects, states, and versions.
2. **Prospective influence:** at least one decision about execution can be affected by scoring *before* its irreversible commitment.
3. **Evidence return:** relevant execution observations can be attributed to steps, criteria, and time.
4. **Authority preservation:** scoring recommendations cannot override contract permissions, human approval gates, or hard safety constraints.
5. **Relay completeness:** downstream recipients can distinguish planned, executed, evaluated, rejected, and unresolved items.

A system that only appends a score to a completed log satisfies **retrospective evaluation**, not the full forward-guided duality proposed here.

### 4.1 Typed interface sketch

```text
GuidanceRequest:
  unit_id, contract_version, current_state,
  candidate_paths, evidence_snapshot, resource_budget

GuidanceResponse:
  admissible_paths, rejected_paths, reasons,
  priorities, confidence_or_uncertainty,
  required_observations, approval_gates

ExecutionEvidence:
  unit_id, path_version, step_id, event_time,
  observation, provenance, exceptions, cost

SettlementRecord:
  contract_version, executed_path_version,
  criteria_results, unresolved_items,
  signoff_authority, relay_readiness
```

These are conceptual fields, not a ratified wire protocol. Their precise types belong in `SPEC-001` and `SPEC-002`.

## 5. Forward Guidance Is the Primary Differentiator

The scoring forest should participate in **three phases**, not only the last one.

| Phase | Question | Scoring-forest contribution | Calling-path consequence |
|---|---|---|---|
| **Before** | What should we attempt? | Goal decomposition, feasibility, risk and candidate comparison | Select, generate, branch, or reject plans |
| **During** | Should we continue or change? | Monitor deviations, evidence, resources, and changing constraints | Replan, pause, request approval, fork, or terminate |
| **After** | What was achieved and learned? | Evaluate acceptance, uncertainty, residuals, and counter-evidence | Settle, relay, archive, and propose deltas |

A generic single-score model may be written:

$$
P^* \in \underset{P\in\mathcal A(K,s)}{\mathrm{argmax}}\; \widehat V_F(P\mid K,s,e),
$$

where $\mathcal A(K,s)$ is the set of **contract-admissible** candidate paths at state $s$, and $e$ is the current evidence. This is a simplified case. In general, $\widehat V_F$ may be a vector, partial ordering, set of rules, or a deliberative decision procedure; no scalar optimum need exist.

### 5.1 Separate hard gates from trade-offs

A practical forward-guidance process should first enforce non-negotiable constraints (authorization, safety, privacy, resource ceilings) and only then compare feasible alternatives. A high estimated task value must not compensate for an unauthorized or unsafe action.

### 5.2 Preserve uncertainty

Predicted scores should carry assumptions and uncertainty. When two paths are indistinguishable under available evidence, the scorer may request more information or initiate a bounded sandbox trial rather than present unjustified certainty.

### 5.3 Guide observations, not only actions

The scorer can specify *which evidence to collect* before and during execution. This turns measurement design into part of forward guidance: the path may include an inspection or test because it will distinguish competing hypotheses, not merely because it is a conventional workflow step.

## 6. Closed-Loop Coupling and Temporal State

Let $s_t$ be the observed execution state, $e_t$ the accumulated evidence, and $K_t$ the active contract version. An abstract cycle is:

$$
\begin{aligned}
q_t &= \mathrm{Guide}(F_t,K_t,s_t,e_t),\\
a_t &= \mathrm{AuthorizeAndSelect}(q_t,K_t),\\
(s_{t+1},o_{t+1}) &= \mathrm{Execute}(P_t,a_t,s_t),\\
e_{t+1} &= \mathrm{AppendEvidence}(e_t,o_{t+1}),\\
F_{t+1} &= \mathrm{UpdateIfValidated}(F_t,e_{t+1}).
\end{aligned}
$$

This describes **logical responsibilities**, not a mandatory software architecture. The scorer may remain unchanged during many steps; humans may approve decisions; and some actions are non-reversible. Updating a scoring forest is not equivalent to silently changing a contractual target mid-execution.

The unit should preserve separate records for:

- **Plan version:** what was intended.
- **Execution trace:** what actually happened.
- **Evaluation version:** which criteria and evidence were used.
- **Contract version:** which commitments and permissions applied.

These distinctions prevent retrospective score changes from rewriting history.

## 7. Multi-Trail Forward Guidance

Advanced guidance may decide not only **which path to select** but also **which alternatives are worth exploring**. This creates a portfolio of bounded *trails* (candidate execution or learning trajectories), potentially running in separate sandboxes or threads.

```text
                     Forward Scoring Forest
                     /         |          \
                    v          v           v
             Trail A       Trail B       Trail C
             Exploit       Explore       Challenge
                \             |             /
                 \            |            /
                  Evidence + Counter-Evidence
                              |
                  Compare / Fold / Preserve
                              |
                 Selected Path + Relay Portfolio
```

A useful exploratory criterion may include predicted task value, information gain, risk, and resource cost:

$$
J(P_i)=\mathbb E[V(P_i)]+\lambda I(P_i)-\mu R(P_i)-\nu C(P_i),
$$

**only after** contract admissibility and hard constraints are enforced. The coefficients are context-dependent, and this expression is a research heuristic rather than a universal optimization law.

A trail may be:

- **Exploitative:** reuse a well-supported path.
- **Exploratory:** test a novel decomposition, tool, or sequence.
- **Adversarial:** seek counterexamples, hidden failure conditions, or scorer blind spots.

The scorer may create, prioritize, throttle, pause, merge, or terminate trails. Parallel execution is optional: *multi-trail* can mean sequential experiments, simulations, or retained candidate designs. Sandbox evidence must be labeled as simulated or experimental and must not be reported as production execution.

**Further treatment:** UIERU-004 specifies forward search and allocation; UIERU-005 specifies sandbox threading, adversarial testing, and lifecycle controls.

## 8. Scoring Trees, Forests, and Perspective Conflict

Different stakeholders may score the same path differently. For example, a customer values timely completion and quality; a worker values safety and reasonable cost; a regulator imposes non-negotiable rules. A forest makes these perspectives visible without pretending they always collapse into one preference function.

For a path $P$, consider:

$$
\mathbf v(P)=(v_{\mathrm{quality}},v_{\mathrm{time}},v_{\mathrm{cost}},v_{\mathrm{safety}}).
$$

A **contractual aggregation operator** may be used when the parties agree on one. Otherwise, the outcome can remain a Pareto set, an unresolved conflict, or a decision requiring an authorized human or governance process.

**Scoring sovereignty:** a receiving UIERU may inspect and reuse an upstream score, but it must not be forced to adopt that score as its own judgment. Preserve scorer identity, criterion version, assumptions, and evidence references during relay.

## 9. Folding Without Losing What Matters

A higher-level unit may compose child units $U_1,\ldots,U_n$ into a macro-unit. The execution structure composes through dependencies, sequencing, parallelism, and handoffs. Its scoring structure must also reconcile child results and system-level constraints.

In general:

$$
V_{\mathrm{macro}}\ne\sum_{i=1}^{n}V_i.
$$

Interactions matter: a locally efficient path may delay a downstream dependency, exhaust a shared resource, or violate a system-level safety gate. The parent forest therefore requires explicit composition rules, including:

1. **Comparable units and provenance:** normalize only where semantics permit.
2. **Cross-unit dependencies:** include sequencing, resource contention, and externalities.
3. **Veto and exception preservation:** never fold away hard failures.
4. **Residual retention:** retain disputed, uncertain, or non-aggregable evidence.
5. **Reversible summaries:** preserve links to detailed child evidence for later unfolding.

The goal of folding is efficient higher-level decision-making, **not** deletion of uncertainty or disagreement. UIERU-006 develops this composition problem in detail.

## 10. Evidence-Based Settlement

A completed path is not automatically an accepted result. Settlement asks whether the delivered state satisfies the contract under the applicable evidence and authority rules.

We propose distinguishing:

- **Executed:** actions were performed or attempted.
- **Observed:** results were measured or reported.
- **Evaluated:** criteria were applied to evidence.
- **Accepted:** the authorized party approved the result.
- **Relayed:** a downstream party received a defined handoff package.

These states may occur at different times. A failed acceptance test may require rework or a new path; an accepted result may still carry residual uncertainty. The forest should record both positive evidence and counter-evidence, rather than optimizing only for an attractive final score.

## 11. Relay the Decision Context, Not Just the Winner

A traditional handoff may transmit the selected result. A stronger UIERU relay can transmit a **portfolio**:

```yaml
relay_portfolio:
  unit_id: example-unit
  contract_version: v1
  selected_path:
    id: path-A
    status: executed-and-evaluated
  alternatives:
    - id: path-B
      status: sandbox-tested
      reason_not_selected: higher-cost-under-current-constraints
    - id: path-C
      status: unresolved
      reason_not_selected: insufficient-evidence
  scoring:
    criteria_version: scoring-v2
    evidence_refs: [inspection-17, test-21]
    known_limitations: [weather-assumption]
  residuals:
    - uncertain-long-term-maintenance-effect
  recipient_actions:
    - independently-validate-applicability
    - accept-or-reject-handoff
```

This is an illustrative payload, not a finalized schema. In practice, a relay should also carry access controls, provenance signatures or attestations where appropriate, confidentiality constraints, and explicit obligations.

**Key distinction:** a rejected trail may still be valuable to another subject or under another contract. Relay should preserve why a trail was rejected rather than reduce it to a universal failure label.

## 12. Structural Evolution from Dual-Core Residuals

The coupling itself produces potential improvement signals:

- **Path residual:** a missing step, brittle dependency, or repeated exception.
- **Scoring residual:** a criterion that failed to predict outcomes or missed an important concern.
- **Coupling residual:** correct evidence arrived too late to influence the decision.
- **Relay residual:** a recipient lacked the assumptions or provenance needed to reuse the result.
- **Composition residual:** locally successful units produced a globally poor outcome.

A disciplined evolution process is:

```text
Observe residual
   -> formulate candidate structural delta
   -> test in bounded sandbox / replay / A-B comparison
   -> inspect counter-evidence and regressions
   -> approve, reject, or revise
   -> version and relay the outcome
```

A delta can modify $P$, $F$, their interface, or the governing contract, but changes to permissions and commitments require proper authorization. **Learning is not synonymous with automatic deployment.**

## 13. Minimal and Advanced Operating Profiles

UIERU does not require an elaborate scoring infrastructure for every task.

| Profile | Calling path | Guidance | Evidence / relay | Exploration |
|---|---|---|---|---|
| **Minimal** | Checklist or short workflow | Pre-execution rules and acceptance criteria | Basic signed or attributed record | None required |
| **Operational** | Stateful graph with conditional branches | Dynamic scoring and intervention | Versioned evidence and handoff | Optional |
| **Exploratory** | Multiple candidate paths | Search allocation and uncertainty-aware ranking | Portfolio with alternatives and counter-evidence | Bounded multi-trail |
| **Collective** | Nested cross-subject units | Perspective-aware scoring and reconciliation | Provenance-rich bidirectional exchange | Shared, localized, validated learning |

The minimal profile must still support meaningful *prospective* guidance; otherwise it is merely an after-the-fact evaluation wrapper. Tasks with low coordination or handoff needs may be better left outside UIERU entirely.

## 14. Failure Modes and Protective Boundaries

| Failure mode | Why it matters | Proposed safeguard |
|---|---|---|
| Reward misspecification / Goodhart effects | A high score can mask poor real outcomes | Counter-evidence, multiple criteria, independent audits |
| Unaligned stakeholder objectives | No legitimate common scalar may exist | Perspective separation, negotiated contracts, explicit vetoes |
| Stale or delayed feedback | Guidance acts on outdated state | Timestamps, freshness checks, safe fallback or pause |
| Excessive multi-trail cost | Exploration can exceed task value | Budgets, early stopping, value-of-information thresholds |
| Sandbox-to-production confusion | Simulated success may be mistaken for deployment evidence | Provenance and environment labels, approval gates |
| Authority leakage | A scorer or upstream unit may overreach | Contract-bound permissions and recipient sovereignty |
| Lossy folding | Summary hides exceptions and uncertainty | Unfoldable evidence references, residual registers |
| Relay contamination | Invalid or misleading precedents spread | Validation, provenance, local acceptance and revocation |

These safeguards are proposed requirements for robust implementations, not proof that the risks have been eliminated.

## 15. Testable Hypotheses and Baselines

The architecture makes claims that should be tested against simpler alternatives.

**H1 — Forward guidance benefit.** Compared with the same calling path plus post-hoc evaluation, prospective scoring improves task quality, safety, or constraint compliance under defined workloads.

**H2 — Coupling benefit.** Explicit step-to-criterion and evidence-to-decision mappings reduce unexplained deviations and improve auditability relative to disconnected planning and logging.

**H3 — Multi-trail value.** Under meaningful uncertainty and controlled budgets, guided multi-trail exploration yields better feasible solutions or more useful counter-evidence than a single-path baseline.

**H4 — Relay richness.** Evidence-bearing trail portfolios improve downstream adaptation or error detection compared with result-only handoffs.

**H5 — Compositional integrity.** Explicit scoring reconciliation reduces cross-unit contract conflicts relative to naive aggregation.

### 15.1 Suggested experiment design

Use the same task set, models, tools, resource ceilings, and authorized decision makers across arms:

- **A:** calling path / workflow only;
- **B:** calling path plus post-hoc scoring;
- **C:** calling path plus forward scoring and closed-loop evidence;
- **D:** C plus budgeted multi-trail sandboxing and portfolio relay.

Measure completion quality, safety violations, latency, total compute or labor cost, calibration, traceability, handoff success, and valid structural improvements. Include trivial tasks where overhead is expected to outweigh gains. Report uncertainty intervals, failed trials, and sensitivity to scoring errors. Do not treat an attractive architecture diagram as evidence of empirical superiority.

## 16. Relationship to Existing Engineering Methods

This paper does not claim to invent workflow orchestration, control feedback, planning under uncertainty, multi-objective optimization, or provenance tracking. Existing methods such as business process management, hierarchical task planning, decision processes, control systems, and agent orchestration already address substantial parts of this problem.

The proposed UIERU contribution is the **joint, relayable organizational boundary**: a governed calling structure, prospective and retrospective valuation, typed evidence coupling, optional multi-trail exploration, and versioned structural evolution. Whether this combination offers practical advantages over well-engineered existing systems is an empirical question.

Related internal research includes Calling Graph intelligence, Universal Control Planes and Scoring Forest/Folding, Portable Intelligence Units, Structural Intelligence Framework, and Subject–Predicate–Object Structural Intelligence. **None is a prerequisite for reading or implementing the ideas in this paper.** They are optional background and intellectual provenance, not mandatory dependencies.

## 17. Implementation and Specification Roadmap

The next research artifacts should make the duality executable and falsifiable:

1. **`SPEC-001` — Canonical UIERU Contract and Schema:** stable identities, versions, permissions, states, and evidence types.
2. **`SPEC-002` — Forward Guidance and Multi-Trail Lifecycle:** scoring calls, trail allocation, intervention, stopping, and sandbox provenance.
3. **`SPEC-003` — Structural Relay and Portfolio Exchange:** result, alternatives, residuals, recipient acceptance, and source attribution.
4. **`SPEC-004` — Composition, Evolution, and Conformance:** cross-unit scoring reconciliation, change approval, and regression tests.

The companion papers `UIERU-004` and `UIERU-005` will deepen the forward-guidance and multi-trail mechanisms; `UIERU-006` through `UIERU-009` address composition, relay, collective learning, and structural evolution. The final synthesis, `UIERU-010`, will examine engineering limits and validation.

## 18. Conclusion

The proposed **Calling Path–Scoring Forest Duality** is a disciplined interface between *doing* and *judging*. The calling path provides executable structure and evidence; the scoring forest provides prospective direction, ongoing control, and retrospective evaluation. Their coupling is bounded by contracts, made transferable through relay, and made evolvable through validated structural deltas.

The decisive step is **forward guidance**: a scorer should help shape actions and experiments before outcomes are known, not merely calculate a score afterward. Advanced implementations may generate multiple trails, test them in bounded sandboxes, preserve counter-evidence, and relay a portfolio of possibilities rather than only a single winning trace. Yet the architecture remains selective, non-exclusive, and compatible with existing human and machine intelligence.

The research opportunity is to determine when this dual-core organization makes intelligence **more governable, more composable, more relayable, and more capable of evidence-based structural growth**—and when its added complexity is not justified.

---

## Suggested Citation

Tan, Sizhe, and GPT-Obot. (2026). *UIERU-003 — Calling Path and Scoring Forest Duality: From Recorded Behavior to Forward-Guided, Evidence-Coupled, and Relayable Intelligence*. Universal Intelligence Evolution and Relay Unit, version 1.0.0. GitHub repository: https://github.com/sizhet/Universal-Intelligence-Evolution-and-Relay-Unit

## License and Reuse

Refer to the repository's published license and citation metadata for applicable terms. This paper is a proposed research architecture, not a certification of interoperability or an empirical guarantee of performance.
