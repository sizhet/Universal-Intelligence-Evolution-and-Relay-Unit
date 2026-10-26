# Open Questions — Universal Intelligence Evolution and Relay Unit (UIERU)

**Version:** 1.0.0  
**Authors:** Sizhe Tan & GPT-Obot  
**Status:** Open research agenda; questions and proposed tests, not established results  
**Project principle:** Engineering First · Theory Supported · Research Open

## Purpose and Scope

The Universal Intelligence Evolution and Relay Unit (UIERU) proposes a composable organizational unit for coordinating existing human and machine capabilities through governed execution paths, forward guidance, structural relay, and validated evolution. Its compact reference model is:

$$
U=(K,P,F,R,E)
$$

where **K** is the contract, **P** the calling path, **F** the forward-guiding scoring forest, **R** the relay mechanism, and **E** the structural evolution mechanism. These components describe a research architecture, not a requirement that every task or every implementation use all mechanisms at full complexity.

This document identifies unanswered scientific and engineering questions, possible failure conditions, and practical investigation paths. A favorable demonstration is not sufficient evidence of universality. Negative results, unexpected costs, and failed transfer attempts should be preserved as research outputs.

**Question labels** are stable within this version. **Priority** reflects recommended investigation order, not importance in principle. **Evidence** names the kind of observation needed to advance the question.

## 1. Unit Definition, Scope, and Selection

### OQ-001 — What is the minimal useful UIERU?

Can a minimal contract, a simple calling path, a guidance policy, and a relay record provide measurable value without an elaborate scoring forest or evolution subsystem?

- **Test:** Compare checklist, ordinary workflow, minimal UIERU, and full UIERU on the same tasks.
- **Evidence:** Coordination overhead, handoff errors, completion quality, recovery time, and maintenance effort.
- **Failure condition:** Added structure increases cost without a corresponding operational benefit.
- **Priority:** High.

### OQ-002 — When should a task *not* be containerized as a UIERU?

What task characteristics predict that UIERU is counterproductive: short duration, stable requirements, low uncertainty, negligible handoff, or inexpensive errors?

- **Test:** Build a selection rule from task features and evaluate it on unseen tasks.
- **Evidence:** Net benefit relative to simpler baselines; false-positive containerization rate.
- **Priority:** High.

### OQ-003 — Is the five-part decomposition sufficient and composable?

Are there recurring requirements that cannot be represented cleanly by contracts, paths, scoring, relay, and evolution? Can nested units preserve essential semantics without introducing ad hoc exceptions?

- **Test:** Model heterogeneous workflows and document forced workarounds or semantic loss.
- **Evidence:** Representation coverage, interoperability defects, and nesting conformance.
- **Priority:** High.

## 2. Forward Guidance and Scoring Forests

### OQ-004 — Does forward guidance improve decisions beyond retrospective scoring?

When does guidance *before and during* execution outperform end-of-task evaluation alone?

- **Test:** Randomize comparable tasks among unguided, retrospective-only, and forward-guided conditions.
- **Evidence:** Task success, risk exposure, rework, latency, and total computation cost.
- **Priority:** High.

### OQ-005 — How should a scoring forest handle conflicting perspectives?

Can safety, quality, cost, time, subject preferences, and exploration value be reconciled without hiding irreducible disagreement?

- **Test:** Compare weighted sums, constrained optimization, lexicographic rules, Pareto-front methods, and explicit escalation.
- **Evidence:** Constraint violations, preference reversals, interpretability, and stakeholder acceptance.
- **Priority:** High.

### OQ-006 — How can the scoring mechanism resist Goodhart effects?

Can the system detect when optimizing its visible score degrades the actual objective?

- **Test:** Introduce proxy-target mismatches, adversarial candidate generation, and evaluator drift.
- **Evidence:** Proxy exploitation rate, counter-evidence detection, and independent outcome quality.
- **Priority:** High.

### OQ-007 — How should uncertainty and calibration affect guidance?

Which uncertainty representations are useful for deciding whether to proceed, branch, gather evidence, defer, or stop?

- **Test:** Compare calibrated and uncalibrated policies under distribution shift.
- **Evidence:** Calibration error, abstention quality, failure severity, and exploration cost.
- **Priority:** Medium.

## 3. Multi-Trail Intelligence and Sandbox Threading

### OQ-008 — When is branching worth its cost?

Under what uncertainty, consequence, and resource conditions should UIERU launch Exploit, Explore, or Challenge trails?

- **Test:** Compare fixed branching, uncertainty-triggered branching, and adaptive portfolio allocation.
- **Evidence:** Quality gain per unit cost, time-to-decision, and unnecessary branching rate.
- **Priority:** High.

### OQ-009 — How should exploration budgets be allocated and terminated?

What policy best balances exploitation, alternative discovery, and adversarial challenge when compute and wall-clock budgets are limited?

- **Test:** Benchmark budgeted bandit, heuristic, and scoring-forest policies across task families.
- **Evidence:** Regret, marginal value of exploration, missed failure modes, and budget overruns.
- **Priority:** High.

### OQ-010 — Can sandboxes isolate consequential side effects reliably?

How do we distinguish simulation, test environment, staging, and authorized production action, especially when external services are involved?

- **Test:** Fault injection, permission-boundary tests, simulated exfiltration, and unauthorized-action probes.
- **Evidence:** Isolation breaches, audit completeness, and reproducibility.
- **Priority:** High.

### OQ-011 — What information from failed trails should survive folding?

Can UIERU compress a multi-trail search into a usable portfolio without discarding decisive counter-evidence or uncertainty?

- **Test:** Have independent receivers make decisions from full traces versus compressed relay portfolios.
- **Evidence:** Decision fidelity, missed caveats, record size, and retrieval cost.
- **Priority:** High.

## 4. Contracts, Composition, and Scoring Folding

### OQ-012 — What constitutes contract compatibility?

How should nested UIERUs reconcile delegated authority, conflicting goals, privacy restrictions, deadlines, resource limits, and acceptance criteria?

- **Test:** Generate compatible, ambiguous, and contradictory contracts; evaluate resolution and refusal behavior.
- **Evidence:** Unauthorized actions, unresolved conflicts, and false acceptance rates.
- **Priority:** High.

### OQ-013 — Can composition preserve safety and provenance?

If each child unit satisfies its local contract, under what assumptions does the parent satisfy its global contract?

- **Test:** Compose individually conformant units with deliberately conflicting dependencies and emergent side effects.
- **Evidence:** Global invariant violations, provenance breaks, and escalation correctness.
- **Priority:** High.

### OQ-014 — What information is lost during scoring folding?

Can multi-perspective scores be summarized without concealing veto conditions, dissent, or rare catastrophic risks?

- **Test:** Compare full evidence with folded summaries in safety-sensitive decisions.
- **Evidence:** Preference fidelity, tail-risk detection, and reversible unpacking.
- **Priority:** High.

### OQ-015 — What is the operational scaling limit of nested UIERUs?

Does coordination overhead grow linearly, superlinearly, or remain bounded with hierarchy depth and number of units?

- **Test:** Scale synthetic and real workflows across nesting depth, fan-out, and concurrency.
- **Evidence:** Latency, token/compute consumption, deadlocks, and operator burden.
- **Priority:** Medium.

## 5. Structural Relay, Portability, and Provenance

### OQ-016 — What must a relay envelope preserve?

What is the minimum transferable package needed for safe continuation: goals, state, authorization, evidence, uncertainties, failures, alternatives, or all of these?

- **Test:** Systematically ablate relay fields and measure receiver performance.
- **Evidence:** Handoff success, rework, hallucinated assumptions, and authority errors.
- **Priority:** High.

### OQ-017 — How portable is structural intelligence across environments?

Can a calling path or scoring principle learned in one toolchain, organization, or domain transfer to another without excessive localization cost?

- **Test:** Cross-environment transfer with explicit adaptation and independent validation.
- **Evidence:** Transfer gain, negative transfer, adaptation effort, and constraint failures.
- **Priority:** High.

### OQ-018 — How can provenance remain trustworthy across transformations?

Can summaries, translations, redactions, and derived structural precedents retain verifiable links to their supporting evidence?

- **Test:** Track provenance through multiple relay hops, transformations, and partial disclosure.
- **Evidence:** Attribution accuracy, tamper detection, and unverifiable-claim rate.
- **Priority:** High.

### OQ-019 — What does bidirectional relay add beyond one-way knowledge sharing?

Does feedback from receiving units materially improve the originating structure and the collective registry?

- **Test:** Compare no sharing, one-way sharing, and feedback-enabled relay networks.
- **Evidence:** Repeated-error reduction, transfer accuracy, and cumulative improvement.
- **Priority:** Medium.

## 6. Residual-Driven Evolution and Structural RSI

### OQ-020 — Which residuals indicate structural defects rather than task noise?

How can UIERU distinguish flawed procedures, misaligned scoring, incomplete contracts, environmental shifts, and random variation?

- **Test:** Inject known fault classes and assess residual diagnosis.
- **Evidence:** Diagnostic precision, recall, and false structural-update rate.
- **Priority:** High.

### OQ-021 — How should structural deltas be validated before adoption?

What combination of counterfactual tests, sandbox trials, independent evaluators, staged deployment, and rollback criteria is sufficient for different risk levels?

- **Test:** Compare approval protocols on known beneficial, neutral, and harmful proposed changes.
- **Evidence:** False acceptance, false rejection, regression frequency, and validation cost.
- **Priority:** High.

### OQ-022 — When does recursive structural improvement genuinely improve intelligence?

Can repeated modifications to calling paths, scoring forests, evaluator rules, and relay contracts yield sustained gains on held-out tasks rather than merely fitting a local benchmark?

- **Test:** Longitudinal evaluations with frozen independent test sets and periodic distribution shifts.
- **Evidence:** Out-of-sample gains, diminishing returns, regressions, and improvement stability.
- **Priority:** High.

### OQ-023 — Who evaluates and authorizes changes to the evaluator?

Can evaluator governance avoid circular self-approval while allowing legitimate improvements to scoring policy?

- **Test:** Separate proposal, evaluation, authorization, and deployment roles; simulate evaluator capture.
- **Evidence:** Governance bypass rate, independence, and audit quality.
- **Priority:** High.

## 7. Subject-Indexed World Models and Structural Memory

*Related extension:* [UIERU-EXT-001](docs/extensions/UIERU-EXT-001-Subject-Indexed-World-Models-and-Structural-Memory.md).

### OQ-024 — What should a subject index represent?

How should the system distinguish the subject of an experience from the principal who authorizes action, the executor who acts, the observer who records, and the evaluator who judges?

- **Test:** Multi-actor scenarios with overlapping and conflicting roles.
- **Evidence:** Identity-binding accuracy, unauthorized attribution, and role-confusion rate.
- **Priority:** High.

### OQ-025 — Does subject-indexed memory improve longitudinal guidance?

Does binding events to subject history, goals, perspective, and outcomes improve future decisions compared with flat event logs or generic vector memory?

- **Test:** Long-horizon tasks with recurrent goals and changing circumstances.
- **Evidence:** Recall relevance, personalization fidelity, task success, and privacy cost.
- **Priority:** High.

### OQ-026 — How should shared world facts and subjective episodes interact?

Can the system preserve a common event record while maintaining distinct, possibly incompatible, subject-specific interpretations?

- **Test:** Multi-perspective event reconstruction and disagreement preservation.
- **Evidence:** Fact/interpretation separation, provenance fidelity, and false consensus.
- **Priority:** Medium.

### OQ-027 — What constitutes continuity of a functional self-model?

Which identity and memory invariants should persist across model upgrades, delegation, tool replacement, and migration? Does a persistent identifier alone suffice?

- **Test:** Migrate long-lived agents across implementations and compare decision continuity and explicit preference preservation.
- **Evidence:** Continuity failures, drift, and user-correctable identity errors.
- **Priority:** Medium.

**Scientific caution:** Childhood amnesia and autobiographical self-development motivate inquiry, but do not establish that absence of a self-index is the sole cause of early memory limitations. A functional AI self-model is not evidence of consciousness.

## 8. Big-Animal Intelligence Organization and Platform-Level RSI

*Related extension:* [UIERU-EXT-002](docs/extensions/UIERU-EXT-002-Big-Animal-Intelligence-Organization-and-Platform-Level-Structural-RSI.md).

### OQ-028 — Does organizational intelligence scale independently of model capability?

Holding underlying model capabilities approximately fixed, can better unit composition, routing, guidance, and relay yield measurable system-level gains?

- **Test:** Compare orchestration architectures using the same models and task suites.
- **Evidence:** Quality, reliability, resource efficiency, and cross-task transfer.
- **Priority:** High.

### OQ-029 — What should be global versus local in a large scoring ecosystem?

Which rules require platform-wide enforcement, and which evaluations must remain domain-, tenant-, or subject-specific?

- **Test:** Compare centralized, federated, and hybrid governance under conflicting goals.
- **Evidence:** Local preference fidelity, safety violations, governance latency, and concentration risk.
- **Priority:** High.

### OQ-030 — How should a structural precedent registry prevent harmful propagation?

Can a registry express applicability limits, version compatibility, uncertainty, counter-evidence, and revocation strongly enough to prevent negative transfer?

- **Test:** Seed both useful and misleading precedents; measure retrieval, adoption, and rollback.
- **Evidence:** Misapplication rate, detection latency, and propagation radius.
- **Priority:** High.

### OQ-031 — What are the economics of platform-level structural RSI?

When do gains from shared validated improvements exceed the costs of collection, review, localization, governance, and distribution?

- **Test:** Cost-benefit analysis at increasing workload and tenant diversity.
- **Evidence:** Marginal gain per unit compute, human review load, and time to break even.
- **Priority:** Medium.

## 9. Subject Sovereignty and Collective Intelligence Ecosystems

*Related extension:* [UIERU-EXT-003](docs/extensions/UIERU-EXT-003-Subject-Sovereignty-and-Collective-Intelligence-Ecosystems.md).

### OQ-032 — What can be shared without transferring authority?

Can a reusable structural pattern be exported while preserving subject control over private experience, goals, permissions, and evaluation?

- **Test:** Consent-scoped relay and adversarial attempts to infer or reuse restricted information.
- **Evidence:** Unauthorized disclosure, unauthorized action, and useful transfer rate.
- **Priority:** High.

### OQ-033 — Can collective learning preserve minority and dissenting perspectives?

Will common scoring and precedent registries systematically erase rare but valid perspectives or unusual failure modes?

- **Test:** Inject minority-context cases and assess retention across repeated folding and aggregation.
- **Evidence:** Dissent preservation, subgroup error, and counter-evidence visibility.
- **Priority:** High.

### OQ-034 — How should consent, revocation, and derived artifacts be governed?

What obligations persist when shared data have been summarized into a structural principle or used in a validated precedent?

- **Test:** Simulate changing consent, revoked access, and downstream derived artifacts.
- **Evidence:** Policy compliance, traceability, deletion feasibility, and residual leakage.
- **Priority:** High.

### OQ-035 — How can ecosystem participants challenge collective scoring rules?

What appeal, audit, contestation, and versioning mechanisms prevent shared intelligence infrastructure from becoming an unaccountable scoring authority?

- **Test:** Governance stress tests with contested evaluations and conflicting participant objectives.
- **Evidence:** Appeal outcomes, time to correction, audit completeness, and abuse resistance.
- **Priority:** Medium.

## 10. Validation Methodology and Falsification

### OQ-036 — Which baselines are necessary for a credible UIERU evaluation?

At minimum, comparisons should include manual/checklist execution, conventional workflows, standard agent orchestration, and selective UIERU configurations. All conditions should receive comparable model access, tool access, budgets, and task information.

- **Test:** Pre-register a shared evaluation protocol with matched resources.
- **Evidence:** Reproducible effect sizes, confidence intervals, and negative findings.
- **Priority:** High.

### OQ-037 — What should count as net intelligence gain?

Task success alone can conceal added latency, energy cost, unsafe autonomy, evaluator overfitting, or maintenance burden.

- **Test:** Report multidimensional outcomes and explicit trade-offs, rather than one composite score alone.
- **Evidence:** Quality, reliability, safety, cost, transfer, interpretability, and governance burden.
- **Priority:** High.

### OQ-038 — How can independent teams reproduce UIERU claims?

Which specifications, traces, fixtures, synthetic data, and conformance tests must be public to permit independent implementation and challenge?

- **Test:** Blind replication by teams unfamiliar with the originating implementation.
- **Evidence:** Replication rate, specification ambiguities, and divergence between implementations.
- **Priority:** Medium.

## 11. Recommended First Experiments

| Experiment | Questions | Minimal comparison | Primary outcome |
|---|---|---|---|
| E1: Minimal lawn-service workflow | OQ-001, 002, 004 | Checklist vs minimal UIERU | Net coordination value |
| E2: Guided software engineering | OQ-004, 005, 006 | Retrospective vs forward guidance | Quality under matched budget |
| E3: Multi-trail sandbox challenge | OQ-008–011 | Single path vs adaptive trails | Failure detection per cost |
| E4: Contract composition stress test | OQ-012–015 | Flat workflow vs nested units | Global invariant preservation |
| E5: Cross-team relay | OQ-016–019 | Summary-only vs relay portfolio | Receiver decision fidelity |
| E6: Structural RSI longitudinal trial | OQ-020–023 | Fixed architecture vs governed deltas | Held-out improvement without regressions |
| E7: Subject-indexed memory | OQ-024–027 | Flat memory vs subject-indexed memory | Long-horizon guidance fidelity |
| E8: Platform-scale registry | OQ-028–031 | Centralized vs federated precedent sharing | Transfer gain and negative-transfer rate |
| E9: Sovereign collective relay | OQ-032–035 | Unscoped vs consent-scoped sharing | Useful transfer without authority leakage |

For each experiment, define a pre-registered task distribution, a held-out evaluation set, a budget envelope, a stopping rule, and an independent evaluator. Record counter-evidence and failures even when they weaken the architectural thesis.

## 12. Research Priorities and Decision Gates

**Gate A — Minimal utility:** Demonstrate at least one repeatable task family where minimal UIERU beats a simpler baseline on a pre-specified net-value criterion. Otherwise narrow the applicability claim.

**Gate B — Forward guidance:** Demonstrate that early guidance changes consequential decisions for the better, not merely the explanation after execution.

**Gate C — Safe exploration:** Show that multi-trail branching can improve decision quality under matched budgets while maintaining isolation and authority boundaries.

**Gate D — Relay fidelity:** Show that a receiver can safely reconstruct actionable context and retain important uncertainty from a portable portfolio.

**Gate E — Structural evolution:** Show held-out, independently validated improvement over multiple iterations, with detectable regressions and rollback.

**Gate F — Ecosystem scaling:** Demonstrate that subject-indexed memory, platform registries, and collective learning improve utility without unacceptable governance or privacy costs.

Passing a gate is evidence for a bounded claim, not proof of universal superiority.

## 13. Boundary Conditions and Non-Claims

UIERU does **not** assume that:

1. Every task should become a UIERU.
2. A scoring forest always improves on a conventional workflow.
3. More trails always produce better decisions.
4. A transferable structure grants permission to execute it.
5. Structural change is automatically an intelligence improvement.
6. A persistent subject index implies AI consciousness.
7. Platform-scale aggregation is necessarily beneficial or legitimate.
8. A successful case study proves universality or recursive self-improvement.

The project should document cases where UIERU is unnecessary, harmful, or not yet implementable.

## 14. Navigation and Related Documents

### Core architecture

- [UIERU-001 — From Calling Paths to Evolvable Intelligence Units](docs/UIERU-001-From-Calling-Paths-to-Evolvable-Intelligence-Units.md)
- [UIERU-003 — Calling Path and Scoring Forest Duality](docs/UIERU-003-Calling-Path-and-Scoring-Forest-Duality.md)
- [UIERU-004 — Forward Guidance and Multi-Trail Intelligence](docs/UIERU-004-Forward-Guidance-and-Multi-Trail-Intelligence.md)
- [UIERU-009 — Residual-Driven Structural Evolution and Recursive Improvement](docs/UIERU-009-Residual-Driven-Structural-Evolution-and-Recursive-Improvement.md)
- [UIERU-010 — Universal Architecture, Engineering Boundaries, and Validation](docs/UIERU-010-Universal-Architecture-Engineering-Boundaries-and-Validation.md)

### Engineering cases and specifications

- [CASE-001 — Neighborhood Lawn Service](cases/CASE-001-Neighborhood-Lawn-Service-as-a-Minimal-UIERU.md)
- [CASE-002 — Multi-Agent Software Engineering](cases/CASE-002-Multi-Agent-Software-Engineering-and-Multi-Trail-Sandboxes.md)
- [CASE-003 — Organizational Relay](cases/CASE-003-Large-Scale-Organizational-Relay-and-Collective-Learning.md)
- [SPEC-001 — Canonical Contract and Schema](specs/SPEC-001-Canonical-UIERU-Contract-and-Schema.md)
- [SPEC-002 — Forward Guidance and Multi-Trail Lifecycle](specs/SPEC-002-Forward-Guidance-and-Multi-Trail-Lifecycle.md)
- [SPEC-003 — Structural Relay and Portfolio Exchange](specs/SPEC-003-Structural-Relay-and-Portfolio-Exchange.md)
- [SPEC-004 — Composition, Evolution, and Conformance](specs/SPEC-004-Composition-Evolution-and-Conformance.md)

### Research planning

- [TESTABLE-HYPOTHESES.md](TESTABLE-HYPOTHESES.md)
- [VALIDATION-ROADMAP.md](VALIDATION-ROADMAP.md)
- [FUTURE-DIRECTIONS.md](FUTURE-DIRECTIONS.md)
- [GLOSSARY.md](GLOSSARY.md)

## 15. Closing Research Position

UIERU's most important open question is not whether a sophisticated architecture can be described, but **under what measurable conditions a governed, composable intelligence unit creates more reliable, transferable, and improvable intelligence than simpler alternatives**.

The research program should seek positive results, negative results, boundary conditions, and counter-evidence with equal seriousness. The desired outcome is an implementable body of knowledge about intelligence organization—not an architecture that must be adopted everywhere.

---

**Citation and authorship:** Sizhe Tan & GPT-Obot. See [`CITATION.cff`](CITATION.cff) for repository citation metadata when available.
