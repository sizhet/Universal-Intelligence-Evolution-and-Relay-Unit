# UIERU-001 — From Calling Paths to Evolvable Intelligence Units

**Universal Intelligence Evolution and Relay Unit (UIERU)**  
**Subtitle:** From Governed Execution and Forward Scoring to Multi-Trail Exploration, Structural Relay, and Collective Learning  
**Authors:** Sizhe Tan & GPT-Obot  
**Version:** 1.0.0  
**Date:** 2026-10-20  
**Status:** Conceptual architecture and testable research proposal  
**Repository:** [Universal-Intelligence-Evolution-and-Relay-Unit](https://github.com/sizhet/Universal-Intelligence-Evolution-and-Relay-Unit)

---

## Abstract

Modern intelligent systems can generate plans, invoke tools, execute workflows, score outcomes, and exchange artifacts. Yet these capabilities often remain fragmented across agents, services, organizations, and learning systems. A calling path may describe what happened without carrying the criteria that guided it; a scoring system may evaluate results without controlling the choices that produced them; a successful workflow may be transferred without its evidence, unresolved risks, or conditions of applicability. These gaps limit composability, reliable handoff, and structural learning.

This paper proposes the **Universal Intelligence Evolution and Relay Unit (UIERU)**: a selectively adopted, composable organizational unit that couples a governed execution path with a **forward-guiding Scoring Forest**, explicit relay contracts, and mechanisms for evidence-based structural improvement. Its distinguishing objective is not to replace existing models, agents, software, human expertise, or non-containerized workflows. Rather, it supplies a common operational boundary within which heterogeneous capabilities can be guided, executed, evaluated, transferred, and improved.

We introduce a compact canonical model, distinguish execution from exploratory trails, and describe how multi-trail sandboxes can produce not only a selected result but also a **Relay Portfolio** of alternatives, counter-evidence, residual problems, and reusable structural deltas. We further outline bidirectional collective learning, composition rules, safety and authority boundaries, comparison baselines, and falsifiable hypotheses. The proposal is an architectural research framework, not a claim that universal applicability or performance gains have already been demonstrated.

**Keywords:** structural intelligence; calling graph; calling path; forward guidance; scoring forest; multi-trail exploration; sandbox; relay contract; provenance; collective learning; structural evolution; composable intelligence.

---

## 1. The Engineering Problem: Intelligence That Works but Does Not Travel Well

Consider a routine lawn-care service. A customer specifies a lawn, quality expectations, a budget, and a deadline. A worker selects tools, checks the weather, performs the work, and receives payment after inspection. If the lawn is wet, the worker may defer mowing or choose another method. If a new technique reduces cost without degrading quality, that technique may be worth testing and reusing.

A conventional workflow can record:

```text
Request -> Prepare -> Mow -> Clean -> Inspect -> Pay
```

But the workflow alone does not necessarily preserve:

- **Why** this path was selected over alternatives;
- **Who** authorized the work and which constraints were binding;
- **How** quality, cost, timing, and safety were assessed before and during execution;
- **What** evidence supports the final settlement;
- **Which** alternatives were tried or rejected, and why;
- **What** another worker or service could safely reuse;
- **Which** unresolved issues should trigger future exploration.

These are not merely documentation problems. They concern the boundary of a reusable, governable, and evolvable functional unit.

The same coordination problem appears in software engineering, multi-agent systems, supply chains, organizational operations, and human–AI delegation. A task may be executed successfully while its rationale, evidence, and learning value remain difficult to transfer.

**Research question:** Can we define a practical organizational unit that connects guided action, evidence, relay, and structural improvement without requiring a common internal implementation for every participant?

UIERU is a candidate answer.

## 2. The Core Proposal

A **Universal Intelligence Evolution and Relay Unit (UIERU)** is a bounded organizational structure for a task or functional capability that integrates:

1. A **contract** identifying the task, responsible parties, goals, objects, permissions, and constraints;
2. An **execution path** describing actions, dependencies, state transitions, and observable evidence;
3. A **Scoring Forest** that guides choices before and during execution and evaluates outcomes afterward;
4. A **relay interface** for transferring results, state, provenance, obligations, and reusable knowledge;
5. An **evolution mechanism** for proposing and validating structural improvements.

An intuitive shorthand is:

```text
UIERU = Execution Path + Forward Guidance + Relay + Evolution
             governed by an explicit task contract
```

A compact architectural representation is:

\[
U=(K,P,F,R,E)
\]

where:

- \(K\): **Contract** — scope, actors, goals, object states, authority, and constraints;
- \(P\): **Path** — executable or observable calling graph/path, including state and evidence;
- \(F\): **Forest** — perspective-aware guidance, evaluation, and settlement structure;
- \(R\): **Relay** — handoff contracts, provenance, evidence, and portable outputs;
- \(E\): **Evolution** — candidate trails, residuals, structural deltas, validation, and versioning.

This is a **design decomposition**, not a mathematical proof of universality. The components may be lightweight, delegated, or implemented by existing tools. A UIERU need not be an autonomous agent or an independent conscious subject.

### 2.1 Why “universal”?

“Universal” names a proposed **cross-domain organizational interface**, not a universal algorithm, an assertion of universal optimality, or an obligation to containerize all activity. A one-step computation may remain a simple function call. Some tasks are better served by direct human action, ordinary workflows, or domain-specific systems.

The architecture is valuable only where its coordination, governance, transfer, and learning benefits justify its overhead.

### 2.2 What UIERU does not replace

UIERU does not replace language models, neural networks, symbolic reasoning, planning algorithms, APIs, calling graphs, workflow engines, databases, human organizations, or existing agent frameworks. It may **organize** them within a contract-governed functional boundary.

The container-shipping analogy is useful: standard containers can transform logistics while bulk and specialized transport remain necessary. Likewise, selective structural containerization can coexist with non-UIERU execution.

---

![Fig-001-UIERU-in-Motion-From-Task-to-Relay-and-Evolution.png](../figures/Fig-001-UIERU-in-Motion-From-Task-to-Relay-and-Evolution.png)

---

## 3. From a Recorded Calling Path to a Governed Operational Unit

A **calling graph** describes actions and their invocation, dependency, or causal relationships. A **calling path** is a trajectory or connected portion of that graph; it need not be a single edge or a strictly linear sequence. Paths may contain branches, retries, nested calls, concurrent threads, and human decisions.

A recorded calling path is useful for traceability and reuse. However, the record itself does not necessarily define the goals, evaluation authority, or rules that select its next action.

UIERU couples the path to a governed scoring structure:

```text
                         Task Contract
                    goals | authority | limits
                              |
                +-------------+-------------+
                |                           |
          Calling Path                 Scoring Forest
       actions | state | evidence     guidance | control | value
                |             <----->        |
                +-------------+-------------+
                              |
                   Relay + Structural Delta
```

The coupling is **bidirectional**:

- **Forest -> Path:** prospective guidance, candidate ranking, resource allocation, constraint checks, replanning, and stop/go decisions;
- **Path -> Forest:** observations, execution evidence, deviations, costs, failures, and outcomes used for reassessment and settlement.

A scoring forest is not merely an accounting layer appended after execution. Its **front-end guidance** is a defining research concern.

## 4. Forward Guidance: Before, During, and After Execution

A useful scoring architecture has at least three operating horizons.

| Horizon | Primary question | Typical operation |
|---|---|---|
| **Before** | Which feasible action or path should we try? | Generate candidates, compare perspectives, check constraints, allocate budgets |
| **During** | Should we continue, branch, pause, or replan? | Monitor evidence, detect deviations, adjust guidance |
| **After** | What was achieved and what can be reused? | Evaluate outcomes, settle obligations, record counter-evidence and residuals |

For a feasible candidate set \(\mathcal{P}_{K}\) under contract \(K\), a conceptual decision rule is:

\[
P^* \in \operatorname*{arg\,max}_{P\in\mathcal{P}_{K}}
V_F(P\mid K,X,E_{\mathrm{obs}})
\]

Here \(X\) denotes relevant context, \(E_{\mathrm{obs}}\) available evidence, and \(V_F\) a context- and perspective-dependent evaluation produced by the Scoring Forest. This notation does **not** imply that the system can enumerate all possible paths, calculate exact values, or solve global optimization. In practice, candidate generation and scoring can be heuristic, approximate, hierarchical, learned, or human-assisted.

**Hard constraints must be enforced independently of compensatory utility scores.** A high expected benefit cannot justify violating a non-negotiable authorization, safety, or privacy constraint.

### 4.1 Scoring Tree, Forest, and Folding

A **Scoring Tree** decomposes an evaluation perspective into criteria and subcriteria. A **Scoring Forest** coordinates multiple trees or perspectives, such as cost, quality, safety, reliability, and stakeholder objectives. **Folding** compresses or aggregates structure for decision-making while respecting specified constraints and retaining essential counter-evidence.

Scoring trees can disagree. A low-cost path may have higher operational risk; one actor's preferred result may impose unacceptable costs on another. Consequently, a UIERU needs explicit reconciliation or escalation rules, not a presumed universally shared score.

## 5. Multi-Trail Exploration: Guidance That Searches, Not Only Selects

Advanced guidance may do more than choose among already known paths. It may **create and manage multiple exploratory trails**—some executed, some simulated, some adversarial, and some preserved as untested candidates.

```text
                 Forward Scoring Forest
                          |
             Candidate generation / branching
                          |
             +------------+------------+
             |            |            |
          Trail A       Trail B       Trail C
          Exploit       Explore       Challenge
             |            |            |
          Evidence     Evidence     Counter-evidence
             +------------+------------+
                          |
              Comparison + Constrained Folding
                          |
             Selected Path + Relay Portfolio
```

These labels denote **roles**, not mandatory fixed threads:

- **Exploit:** test or execute a known, relatively mature path;
- **Explore:** investigate a new method, tool, combination, or capability;
- **Challenge:** seek counterexamples, hidden dependencies, failure modes, and unsafe assumptions.

The Scoring Forest can allocate exploration budgets, pause or terminate trails, and decide when further information is worth its cost. A conceptual trail-priority model is:

\[
J(T_i)=\mathbb{E}[V(T_i)]
+\lambda I(T_i)-\mu C(T_i)-\nu R(T_i)
\]

where \(I\) represents expected information or structural-learning value, \(C\) exploration cost, and \(R\) modeled risk. The coefficients are context-dependent; this expression is a **research heuristic**, not a validated universal formula. Feasibility and hard safety constraints remain separate.

### 5.1 Sandboxes versus live execution

Sandbox trials should have explicit isolation, permissions, resource budgets, observation protocols, and promotion criteria. A simulated result is not equivalent to a real-world result. The evidence record must distinguish simulation, offline replay, shadow evaluation, limited rollout, and production execution.

### 5.2 Threading tracks are also learning tracks

A losing trail may contain a useful partial method; a failed trail may reveal a new constraint; a challenge trail may produce counter-evidence that improves future decisions. The goal is therefore not simply winner-take-all selection. It is **decision plus structured knowledge preservation**.

## 6. Structural Relay: Beyond Passing a Final Answer

A conventional handoff may pass a result or artifact. A **structural relay** should pass enough information for the recipient to interpret, verify, continue, or adapt the work responsibly.

A candidate **Relay Portfolio** contains:

| Field | Purpose |
|---|---|
| Contract identity and version | Clarify scope, authority, and applicable rules |
| Selected output and state | Support immediate continuation |
| Path and decision provenance | Explain what happened and why |
| Scoring criteria and assumptions | Make the decision interpretable and contestable |
| Evidence and confidence limits | Distinguish verified claims from estimates |
| Alternative trails | Preserve useful paths not selected |
| Counter-evidence and failures | Prevent repeated mistakes and misleading transfer |
| Residuals and open obligations | Identify unfinished work and unknowns |
| Structural deltas | Supply candidates for local improvement |
| Recipient acceptance conditions | Support authorization, compatibility checks, and refusal |

The recipient is not required to adopt the sender's scoring preferences. **Relay is transfer, not surrender of evaluation sovereignty.** Local context, authority, and validation remain decisive.

Relay quality can be investigated through measurable properties such as state fidelity, provenance completeness, contract compatibility, successful continuation, and rate of unsafe or misleading transfers.

## 7. Composition: Units Within Units

UIERUs may be nested and composed to form larger functions. A software-development UIERU, for example, might contain planning, implementation, testing, review, and release units. A logistics unit might contain scheduling, routing, warehousing, and delivery units.

Conceptually:

\[
U_{\mathrm{macro}}=\operatorname{Compose}(U_1,\ldots,U_n;K_{\mathrm{macro}})
\]

Composition is **not automatically valid**. It requires checking:

1. Contract and interface compatibility;
2. Authority and responsibility boundaries;
3. State, resource, and temporal dependencies;
4. Evidence and provenance continuity;
5. Scoring conflicts across actors and levels;
6. Failure propagation, rollback, and escalation conditions.

A macro-unit's evaluation is generally **not** the simple sum of local scores. Interactions, shared constraints, nonlinear risks, and different stakeholder perspectives require explicit reconciliation.

**Research challenge:** Identify conditions under which composing conformant units yields a conformant larger unit, and identify counterexamples where local validity fails to imply global validity.

## 8. Residual-Driven Structural Evolution

A **residual** is an unresolved discrepancy, limitation, missing capability, unexplained outcome, or opportunity not adequately represented by the current structure. Residuals can initiate improvement, but they do not guarantee that a proposed change is useful.

A candidate evolution cycle is:

```text
Current Unit
   -> Detect residual / counter-evidence
   -> Propose structural delta
   -> Generate one or more candidate trails
   -> Sandbox / compare / validate
   -> Accept, reject, defer, or escalate
   -> Version the approved change
   -> Relay evidence and remaining residuals
```

A **structural delta** may change a calling path, scoring criterion, contract, interface, tool selection, composition boundary, or relay policy. Approved deltas should have provenance, test results, compatibility notes, and rollback options.

Evolution is **conditional**, not compulsory. A successful routine execution may need only a lightweight record; exploration is justified when expected learning or improvement value exceeds its costs and risks.

This enables two kinds of improvement:

- **Local evolution:** one unit improves its own path, guidance, or contract;
- **Compositional evolution:** multiple units are replaced, reorganized, or connected differently to create new macro-capabilities.

## 9. Bidirectional Collective Learning

A UIERU can be both a **provider** and a **recipient** in a wider learning ecosystem.

**Outbound contribution** may include validated paths, reusable contracts, scoring methods, evidence, counterexamples, candidate deltas, and known applicability limits.

**Inbound learning** may include new paths, improved scoring approaches, specialized services, external evidence, or proposed structural modifications. Adoption should proceed through localization, compatibility assessment, authorization, and appropriate validation.

```text
UIERU A -- evidence / methods / deltas --> Collective Registry
UIERU B <-- candidates / precedents ------ Collective Registry
UIERU B -- local validation / adaptation --> Updated UIERU B
UIERU B -- new evidence / counterexamples -> Collective Registry
```

A registry need not be centralized. The critical properties are discoverability, identity, provenance, versioning, permission-aware exchange, and verifiable claims.

A structure that works under one subject's objectives may fail under another's. Collective learning therefore requires **perspective-aware localization** rather than blind copying.

## 10. The Canonical Lifecycle

For engineering clarity, we propose the following **candidate** lifecycle:

1. **Declare:** identify the task contract, responsible parties, goals, object state, and constraints.
2. **Locate:** discover applicable capabilities, precedents, paths, and candidate units.
3. **Guide:** use a Scoring Forest to assess feasible paths and exploration opportunities.
4. **Branch selectively:** launch sandbox or live trails within authorized limits.
5. **Execute:** perform the selected path while collecting state and evidence.
6. **Reassess:** compare observations with expectations; pause, replan, or escalate as needed.
7. **Settle:** evaluate outcomes, obligations, deviations, and evidence quality.
8. **Relay:** transfer the selected result and a suitably scoped Relay Portfolio.
9. **Evolve selectively:** validate and version useful structural deltas.
10. **Contribute and learn:** exchange validated knowledge with other units or registries.

This is a logical lifecycle, not a mandatory sequential implementation. Some stages may overlap, be delegated, or be omitted in lightweight configurations.

## 11. Three Scales of Application

### 11.1 Neighborhood lawn service

A minimal UIERU can combine an agreement, a short task path, simple weather/quality/cost guidance, inspection evidence, and a handoff note. This case tests whether the benefits of structured guidance and relay outweigh the overhead for a small task.

### 11.2 Multi-agent software engineering

A development task can branch into multiple implementation trails, evaluate them in isolated test sandboxes, retain failing test cases as counter-evidence, and relay the selected code with its test provenance and alternative designs. This case tests multi-trail value and reliability of technical handoff.

### 11.3 Cross-organizational logistics

Multiple teams and services may use nested units with distinct objectives, authority boundaries, and scoring perspectives. This case tests contract reconciliation, state continuity, multi-party handoff, and collective improvement under scale.

These cases are proposed **validation settings**, not demonstrations of already measured success.

## 12. Engineering Boundaries and Failure Modes

UIERU should not be treated as a default requirement for every action. Its overhead can exceed its benefit in simple, low-risk, short-lived tasks.

Important failure modes include:

- **Over-containerization:** excessive contracts, records, or scoring layers for trivial operations;
- **False scoring precision:** treating uncertain estimates as reliable measurements;
- **Goodhart effects:** optimizing a proxy at the expense of the actual goal;
- **Unsafe branching:** exploratory trails exceeding authorization or sandbox isolation;
- **Evidence loss:** folding or handoff discarding material uncertainty and counter-evidence;
- **Scoring sovereignty violations:** imposing one participant's preferences on another;
- **Composition mismatch:** locally acceptable units creating globally unacceptable behavior;
- **Uncontrolled evolution:** promoting unvalidated deltas or losing rollback capability;
- **Registry contamination:** circulating stale, unverified, or malicious precedents.

Controls should include hard constraints, provenance, uncertainty labels, independent counter-evidence, recipient acceptance, versioning, rollback, and escalation to responsible human or institutional authorities when appropriate.

## 13. Research Hypotheses and Baselines

The following claims require controlled comparison, not assertion:

| Hypothesis | Comparison baseline | Candidate metrics |
|---|---|---|
| H1: Forward scoring improves guided execution | Workflow or agent without explicit forward Scoring Forest | Quality, constraint violations, replans, resource cost |
| H2: Multi-trail exploration improves complex decisions | Single-path planning under matched budgets | Best feasible quality, information gain, total cost |
| H3: Relay Portfolio improves handoff | Result-only handoff | Continuation success, state fidelity, provenance loss |
| H4: Structured composition improves reuse | Ad hoc integration | Integration time, interface defects, reuse rate |
| H5: Bidirectional learning improves transfer | No sharing or unvalidated copying | Transfer success, adaptation cost, negative transfer |
| H6: Residual-driven deltas improve long-run outcomes | Static workflow or ungoverned updates | Validated improvement, regression rate, rollback frequency |

Evaluation must control for task difficulty, computational budget, expertise, and instrumentation overhead. Negative results should be retained and reported, especially where a simpler architecture performs better.

## 14. Relationship to Existing Systems and Research

UIERU overlaps with important existing traditions: workflow orchestration, business process management, hierarchical planning, multi-agent coordination, service-oriented architecture, event sourcing, provenance tracking, experimentation platforms, and continual learning.

The **proposed contribution** is the *integrated organizational boundary* connecting governed paths, **prospective scoring**, exploratory trails, rich relay, and validated structural evolution. Whether that integration yields genuinely new capabilities or superior performance must be assessed against strong existing baselines.

Related structural-intelligence research includes calling-graph and trajectory models, Universal Control Planes and Scoring Forests, portable intelligence units, structural contracts, and subject-centered evaluation. These are conceptual antecedents and optional deeper reading; **none is a prerequisite for understanding or implementing the UIERU model introduced here**.

In particular, [Subject–Predicate–Object Structural Intelligence (SPO-SI)](https://github.com/sizhet/Subject-Predicate-Object-Structural-Intelligence) offers a related semantic perspective. UIERU does not require readers to adopt its terminology: actor, action, object, and authority are introduced directly through the task contract.

## 15. A Focused Research and Specification Roadmap

The remaining papers in this series expand the architecture in a progressive engineering order:

| Paper | Focus |
|---|---|
| **UIERU-002** | Canonical UIERU contracts, execution, guidance, and relay |
| **UIERU-003** | Calling Path and Scoring Forest duality |
| **UIERU-004** | Forward guidance and multi-trail intelligence |
| **UIERU-005** | Sandbox threading and counter-evidence |
| **UIERU-006** | Composition, nesting, folding, and contract reconciliation |
| **UIERU-007** | Structural relay, provenance, and portability |
| **UIERU-008** | Bidirectional collective learning and relay ecosystems |
| **UIERU-009** | Residual-driven evolution and recursive improvement |
| **UIERU-010** | Universal architecture, engineering boundaries, and validation |

Four proposed specifications will address the canonical contract, multi-trail lifecycle, relay portfolio exchange, and composition/evolution conformance. Three case studies will test small-scale service, multi-agent software engineering, and large-scale organizational relay.

## 16. Conclusion

A calling path records or organizes behavior. A forward-guiding Scoring Forest helps determine **which behavior to attempt, how to adapt it, and how to evaluate it**. A relay contract preserves the conditions, evidence, and obligations needed for another participant to continue responsibly. Multi-trail exploration can enrich that relay with alternatives, counter-evidence, and reusable discoveries. Validated structural deltas allow the unit to improve without requiring wholesale replacement of its constituent models or services.

UIERU proposes to bring these capabilities into one **selectively adopted, composable organizational unit**. Its promise is not a single universal intelligence algorithm, but a practical way to make heterogeneous intelligence **work together, hand off more faithfully, and learn structurally over time**.

The architecture remains a research proposal. Its value will be established by precise contracts, interoperable implementations, honest comparisons, and evidence about where it helps—and where simpler approaches remain preferable.

> **Core proposition:** Organize intelligent work so that a task can be guided before execution, evaluated during and after execution, relayed with its evidence and alternatives, and improved through validated structural change.

---

## Suggested Citation

Tan, S., & GPT-Obot. (2026). *UIERU-001: From Calling Paths to Evolvable Intelligence Units*. Universal Intelligence Evolution and Relay Unit, version 1.0.0. GitHub repository: https://github.com/sizhet/Universal-Intelligence-Evolution-and-Relay-Unit

**DOI:** To be assigned after the repository's archived release. Do not cite a DOI until it has been issued.

## License and Reuse

See the repository's root license and citation metadata for the authoritative reuse terms. This paper does not independently assign a license.
