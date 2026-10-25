# Universal Intelligence Evolution and Relay Unit (UIERU)

**From Governed Calling Paths and Scoring Forests to Multi-Trail Exploration, Collective Relay, and Open-Ended Structural Evolution**

**Authors:** Sizhe Tan & GPT-Obot  
**Release:** v1.0.0  
**Status:** Research architecture, engineering specifications, and testable hypotheses  
**Guiding approach:** **Engineering First · Theory Supported · Research Open**

> **UIERU = Execution Path + Forward Guidance + Relay + Evolution.**
>
> A UIERU is a composable organizational intelligence unit that coordinates existing human and machine capabilities. It does **not** replace LLMs, agents, tools, workflows, or human decision-makers.

## 1. The Idea in One Minute

Most systems can *perform* a task. Fewer can preserve a reusable account of **how the task was guided, what alternatives were considered, what evidence challenged the result, what should be handed to the next participant, and what structural change is justified**.

UIERU proposes a common unit for that complete cycle:

```text
Task / Goal
    |
    v
Contract and authority (K)
    |
    v
Calling Path (P) <----> Forward Scoring Forest (F)
    |                       |
    +---- Multi-Trail exploration and counter-evidence
    |
    v
Execution evidence and settlement
    |
    v
Structural Relay (R) ----> Next UIERU / Team / Ecosystem
    |
    v
Governed Evolution (E) ----> validated structural improvements
```

A **Calling Path** organizes executable actions and dependencies. A **Scoring Forest** guides candidate selection, resource allocation, replanning, and evaluation—not merely retrospective scoring. A **Relay Portfolio** carries evidence, alternatives, failures, open questions, and candidate improvements. **Evolution** uses these records to propose, test, authorize, and, where appropriate, roll back structural changes.

![UIERU in Motion — From Task to Relay and Evolution](figures/Fig-001-UIERU-in-Motion-From-Task-to-Relay-and-Evolution.png)

## 2. A Minimal Example: Neighborhood Lawn Service

A homeowner requests lawn mowing before the weekend.

- **Contract:** scope, address, schedule, budget, access permissions, and acceptance criteria.
- **Calling Path:** confirm request → inspect weather → prepare equipment → travel → mow → inspect → hand off.
- **Forward Scoring:** compare scheduling alternatives, forecast rain risk, check safety constraints, and replan when the gate is locked.
- **Multi-Trail (when warranted):** compare rescheduling, obtaining authorized access, and assigning another team; challenge assumptions rather than blindly choosing the cheapest option.
- **Relay:** send the next crew the job status, verified access constraints, photos where authorized, unresolved questions, and a proposed checklist improvement.
- **Evolution:** validate whether a pre-visit access check reduces future failures before adopting it as a new standard.

This can be implemented with people, ordinary software, agents, or combinations of them. A simple one-off job may not justify the extra coordination: **UIERU is selective structural containerization, not mandatory ceremony.**

**Start with:** [CASE-001 — Neighborhood Lawn Service](cases/CASE-001-Neighborhood-Lawn-Service-as-a-Minimal-UIERU.md).

## 3. Canonical Structure

The research model is:

$$
U = (K, P, F, R, E)
$$

| Element | Name | Engineering responsibility |
|---|---|---|
| **K** | Contract | Subject/principal, task, goals, constraints, authority, inputs, outputs, acceptance conditions |
| **P** | Calling Path | Executable graph/path, dependencies, actors, tools, states, and evidence capture |
| **F** | Scoring Forest | Forward guidance, multi-perspective valuation, candidate selection, control, and settlement |
| **R** | Relay | Portable envelopes/portfolios, provenance, localization, receiving-side validation, feedback |
| **E** | Evolution | Residuals, counter-evidence, structural deltas, experiments, approval, versioning, rollback |

These elements are **roles**, not necessarily five separately deployed services. Implementations may be lightweight, hierarchical, federated, or embedded in existing systems.

**Read:** [UIERU-002 — Canonical UIERU](docs/UIERU-002-Canonical-UIERU-Contracts-Execution-Guidance-and-Relay.md) and [SPEC-001 — Canonical Contract and Schema](specs/SPEC-001-Canonical-UIERU-Contract-and-Schema.md).

## 4. Five Research Contributions

### 4.1 Calling Path–Scoring Forest Duality

The Calling Path provides possible actions, observed states, and execution evidence. The Scoring Forest provides prospective valuation, constraint-aware guidance, dynamic control, and evaluation. Their interaction is bidirectional: evidence updates guidance; guidance changes the path.

**Read:** [UIERU-003](docs/UIERU-003-Calling-Path-and-Scoring-Forest-Duality.md).

### 4.2 Forward Guidance and Multi-Trail Intelligence

A scoring system should not be confined to choosing a winner after execution. It can allocate bounded effort across **Exploit** (known path), **Explore** (alternatives), and **Challenge** (counter-evidence) trails. Sandboxes isolate speculative activity; real-world actions remain subject to authorization.

**Read:** [UIERU-004](docs/UIERU-004-Forward-Guidance-and-Multi-Trail-Intelligence.md), [UIERU-005](docs/UIERU-005-Sandbox-Threading-and-Counter-Evidence.md), and [SPEC-002](specs/SPEC-002-Forward-Guidance-and-Multi-Trail-Lifecycle.md).

### 4.3 Composition, Nesting, and Folding

Units can be composed sequentially, in parallel, hierarchically, or across federated organizations. Composition requires contract reconciliation; scoring folding must preserve important disagreements, uncertainties, and provenance rather than erase them in a single score.

**Read:** [UIERU-006](docs/UIERU-006-Composition-Nesting-Folding-and-Contract-Reconciliation.md) and [SPEC-004](specs/SPEC-004-Composition-Evolution-and-Conformance.md).

### 4.4 Structural Relay and Bidirectional Collective Learning

Relay means more than passing a final answer. It can carry a **portfolio** of paths, evidence, alternatives, failure modes, counter-evidence, residuals, and proposed structural changes. Receiving subjects validate and localize what they import, then may return improvements to the collective ecosystem.

**Read:** [UIERU-007](docs/UIERU-007-Structural-Relay-Provenance-and-Intelligence-Portability.md), [UIERU-008](docs/UIERU-008-Bidirectional-Collective-Learning-and-Relay-Ecosystems.md), and [SPEC-003](specs/SPEC-003-Structural-Relay-and-Portfolio-Exchange.md).

### 4.5 Residual-Driven Structural RSI

Failures, unexpected successes, and evaluator conflicts may reveal opportunities to improve future task decomposition, guidance, sandbox policy, relay, or evaluation. This is **structural recursive self-improvement (RSI)**—not necessarily model-weight updates. Proposed changes require independent testing and appropriate authorization before deployment.

**Read:** [UIERU-009](docs/UIERU-009-Residual-Driven-Structural-Evolution-and-Recursive-Improvement.md), [UIERU-010](docs/UIERU-010-Universal-Architecture-Engineering-Boundaries-and-Validation.md), and [CASE-002](cases/CASE-002-Multi-Agent-Software-Engineering-and-Multi-Trail-Sandboxes.md).

## 5. What UIERU Is—and Is Not

**UIERU is:**

- A **composable organizational unit** for execution, guidance, evidence, relay, and governed evolution.
- A possible interoperability layer over existing models, tools, agent frameworks, and human workflows.
- A research architecture with proposed specifications, cases, and falsifiable hypotheses.

**UIERU is not:**

- A claim that every task needs an intelligent container or that every unit is an autonomous subject.
- A replacement for foundation models, orchestration frameworks, existing agent protocols, or conventional software.
- A proof of universal applicability, superior performance, machine consciousness, or unconstrained self-improvement.
- A grant of authority: **portability does not transfer permission; scoring does not create authorization; a proposed improvement is not an approved deployment.**

The term *universal* describes a **research aspiration for broadly reusable organizational structure**, not an experimentally established result.

## 6. Three Engineering Cases

| Case | Question |
|---|---|
| [CASE-001 — Neighborhood Lawn Service](cases/CASE-001-Neighborhood-Lawn-Service-as-a-Minimal-UIERU.md) | Can an everyday service illustrate the minimal structure without excessive complexity? |
| [CASE-002 — Multi-Agent Software Engineering](cases/CASE-002-Multi-Agent-Software-Engineering-and-Multi-Trail-Sandboxes.md) | Can guided sandboxes and counter-evidence improve delivery and enable structural RSI? |
| [CASE-003 — Organizational Relay](cases/CASE-003-Large-Scale-Organizational-Relay-and-Collective-Learning.md) | Can teams exchange validated intelligence structures without surrendering local control? |

## 7. Engineering Specifications

| Specification | Scope |
|---|---|
| [SPEC-001 — Contract and Schema](specs/SPEC-001-Canonical-UIERU-Contract-and-Schema.md) | Canonical unit fields, contract semantics, schema and validation |
| [SPEC-002 — Guidance and Multi-Trail Lifecycle](specs/SPEC-002-Forward-Guidance-and-Multi-Trail-Lifecycle.md) | Guidance loop, sandbox states, budgets, authorization, counter-evidence |
| [SPEC-003 — Structural Relay](specs/SPEC-003-Structural-Relay-and-Portfolio-Exchange.md) | Relay envelope, portfolio exchange, provenance, localization, feedback |
| [SPEC-004 — Composition and Conformance](specs/SPEC-004-Composition-Evolution-and-Conformance.md) | Nested units, contract reconciliation, structural changes, conformance |

These are **research specifications**, not yet a ratified industry standard or a claim of interoperable production implementations.

## 8. Research Extensions: Subjects, Platforms, and Sovereignty

The extensions develop natural consequences of the core architecture without changing its central ten-document sequence. No additional figures are required.

| Extension | Research focus |
|---|---|
| [EXT-001 — Subject-Indexed World Models and Structural Memory](docs/extensions/UIERU-EXT-001-Subject-Indexed-World-Models-and-Structural-Memory.md) | Subject identity, episodic memory, world/self models, structural precedents |
| [EXT-002 — Big-Animal Intelligence Organization and Platform-Level Structural RSI](docs/extensions/UIERU-EXT-002-Big-Animal-Intelligence-Organization-and-Platform-Level-Structural-RSI.md) | Distributed scoring forests, large-scale coordination, platform-level improvement |
| [EXT-003 — Subject Sovereignty and Collective Intelligence Ecosystems](docs/extensions/UIERU-EXT-003-Subject-Sovereignty-and-Collective-Intelligence-Ecosystems.md) | Authority, memory boundaries, privacy, portable knowledge, collective learning |

A **subject index** is a functional organization mechanism, not evidence of AI consciousness. Platform-scale learning must preserve local authorization, evaluator independence, and appropriate data-use restrictions.

## 9. Figures

The repository's eight architectural figures are:

1. [Fig-001 — UIERU in Motion](figures/Fig-001-UIERU-in-Motion-From-Task-to-Relay-and-Evolution.png)
2. [Fig-002 — Calling Path and Scoring Forest Duality](figures/Fig-002-Calling-Path-and-Scoring-Forest-Duality.png)
3. [Fig-003 — Forward Guidance and Multi-Trail Search](figures/Fig-003-Forward-Guidance-and-Multi-Trail-Search.png)
4. [Fig-004 — Sandbox Threading and Counter-Evidence](figures/Fig-004-Sandbox-Threading-and-Counter-Evidence.png)
5. [Fig-005 — Composable and Nested UIERU](figures/Fig-005-Composable-and-Nested-UIERU.png)
6. [Fig-006 — Structural Relay and Portfolio Exchange](figures/Fig-006-Structural-Relay-and-Portfolio-Exchange.png)
7. [Fig-007 — Bidirectional Collective Learning Ecosystem](figures/Fig-007-Bidirectional-Collective-Learning-Ecosystem.png)
8. [Fig-008 — UIERU Grand Architecture and Structural Evolution](figures/Fig-008-UIERU-Grand-Architecture-and-Structural-Evolution.png)

See [FIGURE-INDEX.md](FIGURE-INDEX.md) for intended placement and interpretation. **Figure links will render when the eight corresponding PNG files are committed under these exact names.**

## 10. Reading Paths

**New to UIERU (15–30 minutes):** [START-HERE](START-HERE.md) → [CASE-001](cases/CASE-001-Neighborhood-Lawn-Service-as-a-Minimal-UIERU.md) → [UIERU-001](docs/UIERU-001-From-Calling-Paths-to-Evolvable-Intelligence-Units.md).

**Engineer or architect:** [UIERU-002](docs/UIERU-002-Canonical-UIERU-Contracts-Execution-Guidance-and-Relay.md) → [SPEC-001](specs/SPEC-001-Canonical-UIERU-Contract-and-Schema.md) → [SPEC-002](specs/SPEC-002-Forward-Guidance-and-Multi-Trail-Lifecycle.md) → [SPEC-003](specs/SPEC-003-Structural-Relay-and-Portfolio-Exchange.md) → [SPEC-004](specs/SPEC-004-Composition-Evolution-and-Conformance.md).

**Researcher:** [CONTENTS](CONTENTS.md) → [UIERU-003](docs/UIERU-003-Calling-Path-and-Scoring-Forest-Duality.md) → [UIERU-004](docs/UIERU-004-Forward-Guidance-and-Multi-Trail-Intelligence.md) → [UIERU-009](docs/UIERU-009-Residual-Driven-Structural-Evolution-and-Recursive-Improvement.md) → [TESTABLE-HYPOTHESES](TESTABLE-HYPOTHESES.md) → [VALIDATION-ROADMAP](VALIDATION-ROADMAP.md).

**Ecosystem and governance:** [UIERU-007](docs/UIERU-007-Structural-Relay-Provenance-and-Intelligence-Portability.md) → [UIERU-008](docs/UIERU-008-Bidirectional-Collective-Learning-and-Relay-Ecosystems.md) → [EXT-001](docs/extensions/UIERU-EXT-001-Subject-Indexed-World-Models-and-Structural-Memory.md) → [EXT-002](docs/extensions/UIERU-EXT-002-Big-Animal-Intelligence-Organization-and-Platform-Level-Structural-RSI.md) → [EXT-003](docs/extensions/UIERU-EXT-003-Subject-Sovereignty-and-Collective-Intelligence-Ecosystems.md).

## 11. Research Questions and Validation

Important unresolved questions include:

- When does the coordination overhead of a UIERU outweigh its benefits?
- Does forward guidance outperform retrospective-only scoring under matched resource budgets?
- Do Multi-Trail and counter-evidence improve robustness without unacceptable latency or cost?
- Can nested contracts be reconciled without silently expanding authority?
- What information must survive scoring folding and relay to preserve decision quality?
- Does validated structural transfer outperform result-only handoff or unvalidated copying?
- Can structural RSI yield sustained improvements without evaluator drift, negative transfer, or uncontrolled updates?
- How can subject-indexed memory and platform-scale collective learning coexist with privacy and local sovereignty?

**Required comparisons:** conventional workflow; single-path agent; retrospective-scoring agent; forward-guided single trail; forward-guided Multi-Trail; and relay/structural-learning variants under matched budgets. Evaluate task quality, safety, latency, compute cost, evidence completeness, relay fidelity, generalization, and rollback effectiveness.

See [OPEN-QUESTIONS.md](OPEN-QUESTIONS.md), [TESTABLE-HYPOTHESES.md](TESTABLE-HYPOTHESES.md), and [VALIDATION-ROADMAP.md](VALIDATION-ROADMAP.md). These documents articulate research plans, **not completed experimental findings**.

## 12. Repository Map

```text
Universal-Intelligence-Evolution-and-Relay-Unit/
├── README.md
├── START-HERE.md
├── CONTENTS.md
├── GLOSSARY.md
├── FIGURE-INDEX.md
├── FUTURE-DIRECTIONS.md
├── OPEN-QUESTIONS.md
├── TESTABLE-HYPOTHESES.md
├── VALIDATION-ROADMAP.md
├── CHANGELOG.md
├── CITATION.cff
├── .zenodo.json
├── docs/
│   ├── UIERU-001-...md through UIERU-010-...md
│   └── extensions/
│       ├── UIERU-EXT-001-...md
│       ├── UIERU-EXT-002-...md
│       └── UIERU-EXT-003-...md
├── cases/
│   ├── CASE-001-...md
│   ├── CASE-002-...md
│   └── CASE-003-...md
├── specs/
│   ├── SPEC-001-...md through SPEC-004-...md
├── figures/
│   └── Fig-001-...png through Fig-008-...png
└── release/
    ├── GitHub-Release-Notes-v1.0.0.md
    ├── ResearchGate-Description.txt
    └── UIERU-v1.0.0-ResearchGate-Overview.pdf
```

For the complete exact filenames, see [CONTENTS.md](CONTENTS.md).

## 13. Relationship to Earlier Research

UIERU is **self-contained**. Readers do **not** need to read any predecessor DOI repository to understand the concept, cases, or specifications.

Optional intellectual context includes research on Calling Graphs, Universal Control Planes and Scoring Forests, portable intelligence units, structural recursive self-improvement, and Subjective Structural Intelligence. These provide useful background, but are not implementation prerequisites or evidence that the UIERU hypotheses are already validated.

## 14. How to Evaluate or Contribute

Constructive evaluation is especially welcome on:

1. **Counterexamples:** tasks where UIERU adds cost but no benefit.
2. **Interoperability:** mappings to existing agent, workflow, tool, and event protocols.
3. **Conformance:** independently reproducible contract, lifecycle, relay, and evolution tests.
4. **Governance:** authority preservation, evaluator independence, data minimization, and rollback.
5. **Measurement:** matched-budget comparisons and evidence of both positive and negative transfer.

Please distinguish **architecture proposals**, **illustrative examples**, and **empirical findings**. The repository currently presents the first two and proposes methods to obtain the third.

## 15. Citation, Release, and License

**Authors:** Sizhe Tan & GPT-Obot  
**Project:** *Universal Intelligence Evolution and Relay Unit (UIERU)*  
**Version:** v1.0.0  
**Repository:** https://github.com/sizhet/Universal-Intelligence-Evolution-and-Relay-Unit

For machine-readable citation and release metadata, see [CITATION.cff](CITATION.cff), [.zenodo.json](.zenodo.json), and [CHANGELOG.md](CHANGELOG.md). Add the assigned Zenodo DOI after publication; **no DOI is asserted here before issuance**.

Check the repository's actual LICENSE file and metadata for applicable terms. This README does not independently declare a license.

---

**The central proposition:** Intelligence can improve not only by increasing the capability of its components, but by improving how existing capabilities are **organized, guided, challenged, relayed, and structurally evolved**.

*Engineering First · Theory Supported · Research Open.*

---

## 📚 DBM-SI Series Navigation

See:\
[./docs/DBM-SI-Series-of-gitHub-Repositories/DBM-SI-Series-of-gitHub-Repositories.md](./docs/DBM-SI-Series-of-gitHub-Repositories/DBM-SI-Series-of-gitHub-Repositories.md)

---

