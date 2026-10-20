# Glossary — Universal Intelligence Evolution and Relay Unit (UIERU)

**Project:** Universal Intelligence Evolution and Relay Unit  
**Version:** 1.0.0  
**Authors:** Sizhe Tan & GPT-Obot  
**Status:** Research terminology and proposed engineering conventions; not an established industry standard.

> **Engineering First · Theory Supported · Research Open**  
> No prerequisite DOI is required to read this glossary.

## 1. How to Read This Glossary

UIERU is a proposed **organizational intelligence unit**: a composable structure that coordinates existing human and machine capabilities through governed execution paths, forward guidance, evidence-preserving relay, and controlled structural improvement. It does **not** imply a new foundation model, a mandatory agent wrapper, autonomous personhood, or a universal solution for every task.

Terms labeled **[Proposed]** designate UIERU-specific concepts or conventions; **[Established]** indicates a widely used technical concept, though its precise interpretation may vary. **[Hypothesis]** identifies an unverified research proposition. Formal interfaces are specified in `specs/`, not by this glossary alone.

### Canonical shorthand

`U = (K, P, F, R, E)`

| Symbol | Name | Core responsibility |
|---|---|---|
| `U` | UIERU | Composable organizational intelligence unit |
| `K` | Contract | Task, principals, authority, constraints, goals, acceptance criteria |
| `P` | Calling Path | Governed decomposition and execution of work |
| `F` | Scoring Forest | Multi-perspective, forward-looking guidance and evaluation |
| `R` | Relay | Evidence-preserving exchange and handoff |
| `E` | Evolution | Validated, versioned structural improvement |

The five components describe **logical responsibilities**, not necessarily five separate software processes.

## 2. Core Unit and Execution Terms

**UIERU — Universal Intelligence Evolution and Relay Unit [Proposed].** A bounded, contract-governed organizational structure joining execution, guidance, relay, and evolution. A UIERU can be minimal, nested, temporary, persistent, human-operated, software-operated, or hybrid. Its usefulness is an empirical question relative to simpler alternatives.

**Canonical UIERU [Proposed].** The reference five-part decomposition `U = (K, P, F, R, E)`, used to compare implementations and describe conformance. Canonical does not mean every deployment must implement all advanced capabilities.

**Contract (`K`) [Proposed].** The explicit agreement governing a unit's objective, subject or principal, inputs, outputs, constraints, authorized actions, evidence requirements, and completion criteria. A contract is not merely a text prompt.

**Contract Boundary [Proposed].** The scope within which actions, data use, and decisions are permitted. Crossing this boundary requires an independently authorized change, not a high score.

**Principal [Established].** The person or organization on whose authority an action is requested or performed. A principal may differ from the actor that executes the action.

**Calling Graph [Proposed usage].** A graph of callable operations, dependencies, conditions, and transitions. It may include human steps, tools, services, agents, or model calls.

**Calling Path (`P`) [Proposed].** A selected, executable route through a Calling Graph, including its intermediate states, decisions, and evidence. A path may be revised during execution.

**Execution Trace [Established].** A record of actions, state transitions, inputs or references, outputs, timestamps, and errors. A trace alone does not establish correctness.

**Task Decomposition [Established].** Division of a task into smaller operations or subtasks with explicit dependencies and interfaces.

**Handoff [Established].** Transfer of responsibility or work state from one executor or unit to another. UIERU extends a handoff with structural context, evidence, and receiver validation.

**Minimal UIERU [Proposed].** A lightweight instantiation with a bounded contract, a small Calling Path, usable guidance, and a basic handoff/evidence record. Advanced multi-trail search and recursive improvement are optional.

**Selective Structural Containerization [Proposed].** Using UIERU-style packaging where portability, governance, or learning benefits justify its overhead; leaving simple tasks unwrapped where appropriate.

## 3. Scoring, Guidance, and Control

**Scoring Forest (`F`) [Proposed].** A collection of scoring trees or evaluators representing different objectives, constraints, perspectives, and evidence. It supports planning, resource allocation, monitoring, and settlement; it is not a single universal scalar score.

**Scoring Tree [Proposed].** A structured evaluator for one application, goal family, or comparative-advantage direction. Its outputs may include confidence, explanations, uncertainty, and abstention.

**Forward Guidance [Proposed].** Use of evidence and Scoring Forest outputs **before and during** execution to choose paths, allocate resources, challenge assumptions, and trigger replanning. This differs from post-hoc grading.

**Online Guidance [Proposed].** Re-evaluation of an active path when observations, constraints, or evidence change.

**Settlement [Proposed].** Post-execution assessment of outcomes against the contract, including evidence quality, deviations, costs, unresolved questions, and candidate improvements.

**Perspective-Aware Scoring [Proposed].** Evaluation that keeps stakeholder or domain perspectives identifiable instead of silently treating them as interchangeable.

**Scoring Folding [Proposed].** Reduction or reconciliation of multiple evaluation structures into a decision-support representation while preserving material conflicts, uncertainty, and counter-evidence. Folding does not require naive summation.

**Evaluator Governance [Proposed].** Controls over evaluator provenance, independence, versioning, calibration, conflicts of interest, and approval. An optimizer should not be allowed to unilaterally redefine the criteria that certify its own success.

**Anti-Goodhart Controls [Established principle / proposed application].** Measures to detect and mitigate situations in which optimizing a proxy score degrades the actual goal, including independent measures, challenge trails, and counter-evidence.

**Evaluation Sovereignty [Proposed].** The authority of the appropriate subject or principal to determine which goals and evaluation criteria apply within their legitimate scope, subject to applicable external constraints.

**Guidance–Authority Separation [Proposed].** The rule that a scoring recommendation does not itself confer permission to act, access data, spend resources, or deploy a change.

## 4. Multi-Trail Exploration and Sandboxes

**Multi-Trail Intelligence [Proposed].** Guided maintenance of multiple candidate routes rather than committing prematurely to one. Trails can be compared, challenged, folded, retained, or terminated.

**Trail [Proposed].** A bounded candidate path or hypothesis with its own objective, budget, evidence, and lifecycle state.

**Exploit Trail [Proposed].** A route using a currently credible method to accomplish the task efficiently.

**Explore Trail [Proposed].** A route testing alternative approaches or underexplored opportunities.

**Challenge Trail [Proposed].** A route explicitly seeking disconfirming evidence, failure modes, or hidden assumptions in a preferred solution.

**Trail Portfolio [Proposed].** A structured record of active, completed, rejected, or inconclusive trails, including reasons, evidence, costs, and reusable findings.

**Sandbox [Established].** An isolated or constrained environment for experimentation. Isolation strength must match the threat model; calling something a sandbox does not prove safety.

**Sandbox Threading [Proposed].** Coordinated branching and management of multiple bounded experiments or execution threads, potentially using separate sandboxes.

**Trail Lifecycle [Proposed].** Governed states such as proposed, authorized, running, paused, completed, rejected, and archived. Exact transitions are specified in `SPEC-002`.

**Counter-Evidence [Proposed usage].** Evidence that weakens, falsifies, or limits a claim, plan, score, or structural improvement. It must remain traceable and cannot be discarded merely because a preferred candidate wins.

**Evidence-Aware Folding [Proposed].** Synthesis of multiple trails while retaining decisive supporting and conflicting evidence and meaningful uncertainty.

**Budgeted Exploration [Proposed].** Allocation of time, compute, money, risk, and human attention across trails subject to contract limits.

**Abstention [Established].** An explicit refusal to select or certify a candidate when evidence or authority is insufficient.

## 5. Relay, Provenance, and Portability

**Structural Relay (`R`) [Proposed].** Transfer of actionable structures and their conditions of use—not only a final answer—between units, subjects, teams, or platforms.

**Relay Envelope [Proposed].** The outer exchange record describing sender, intended recipient, contract reference, version, integrity, permissions, and receipt/validation status.

**Relay Portfolio [Proposed].** The content package carried by a relay, potentially including Calling Paths, scoring summaries, trail results, provenance, counter-evidence, residuals, unresolved issues, and proposed Structural Deltas.

**Provenance [Established].** Traceable origin and transformation history of evidence, decisions, and artifacts. Provenance can support audit but does not guarantee truth.

**Evidence Lineage [Proposed usage].** Links from a conclusion or structural change to underlying observations, tests, transformations, and evaluators.

**Intelligence Portability [Proposed].** The ability to transfer useful task structures or learned principles across environments, subject to compatibility, authority, privacy, and revalidation.

**Localization [Proposed usage].** Adaptation of imported structures to the receiver's tools, context, constraints, goals, and evaluators before use.

**Receiver Sovereignty [Proposed].** The receiving subject's or organization's authority to inspect, reject, adapt, or independently validate imported structures rather than executing them automatically.

**Relay Fidelity [Proposed].** The extent to which meaning, constraints, evidence, and relevant uncertainty survive an exchange. Fidelity is not simply byte-for-byte equality.

**Portable Intelligence Unit [Related research].** A transferable bounded intelligence component. UIERU adds explicit forward guidance, governed relay, and evolution responsibilities to this broader family of ideas.

**Structural Precedent [Proposed].** A documented prior solution or failure pattern with applicability conditions, evidence, limits, and revision history.

**Structural Precedent Registry [Proposed].** A searchable collection of precedents available for validated reuse, comparison, and counter-evidence updates.

**Bidirectional Relay [Proposed].** Exchange in which receivers may return validation outcomes, failures, adaptations, and new evidence to the originator or shared registry.

**Portability ≠ Authority [Normative rule].** Possession of a transferable structure does not imply permission to execute it or access the originating subject's private data.

## 6. Structural Evolution and Recursive Improvement

**Evolution (`E`) [Proposed].** Governed modification of a UIERU's contracts, paths, evaluators, relay rules, or improvement process based on evidence and validation.

**Residual [Proposed usage].** A meaningful mismatch or unexplained remainder between expected and observed outcomes, including surprises, failures, uncertainty, and missed opportunities. Not every residual warrants a change.

**Structural Delta [Proposed].** A proposed, identifiable, versioned change to one or more UIERU structural components, with rationale, supporting and opposing evidence, applicability limits, and rollback plan.

**Residual-Driven Structural Evolution [Hypothesis].** The proposition that systematic analysis of residuals can identify improvements that outperform unstructured adaptation, subject to experimental validation.

**Structural RSI [Proposed].** Recursive self-improvement of the *organization and evaluation of intelligence*—for example, Calling Paths, Scoring Forests, sandbox policies, or relay mechanisms—without necessarily changing model weights.

**RSI-Based Intelligence Driving [Proposed].** Use of feedback and validated structural improvements to guide subsequent intelligent work, so improvements to the operating system of work can affect future tasks.

**Recursive Improvement [Established concept / proposed application].** Repeated improvement cycles in which later cycles can refine mechanisms used by earlier cycles. Recursion alone is not evidence of progress.

**Independent Validation [Established].** Assessment by a sufficiently separated test, evaluator, or approval mechanism to reduce self-certification and correlated failure.

**Candidate–Approval Separation [Proposed].** A structural improvement may be proposed by the system but cannot be treated as authorized for deployment without the designated approval path.

**Rollback [Established].** Reversion to a prior known state or version when an approved change causes unacceptable effects.

**Open-Ended Structural Growth [Hypothesis].** The possibility that new tasks, evidence, tools, and interfaces can continually create candidates for structural expansion. It is not a claim of unlimited performance improvement.

**Negative Transfer [Established].** Degradation caused by importing or generalizing a technique outside the conditions in which it works.

## 7. Composition, Contracts, and Conformance

**Composition [Established / proposed application].** Assembly of multiple units into a larger task structure with explicit interfaces, responsibilities, and boundaries.

**Nested UIERU [Proposed].** A UIERU that delegates bounded subproblems to other UIERUs while retaining appropriate parent-level coordination and oversight.

**Sequential Composition [Established].** Chaining units so a successor depends on a predecessor's output or completion.

**Parallel Composition [Established].** Running multiple units concurrently with a defined coordination and result-reconciliation mechanism.

**Hierarchical Composition [Established].** Parent–child organization of units with delegated goals and constrained authority.

**Federated Composition [Established / proposed application].** Coordination across independently governed units or organizations without assuming a single owner of all resources and decisions.

**Contract Reconciliation [Proposed].** Checking whether combined units have compatible goals, permissions, resources, evidence obligations, and failure-handling rules. Incompatibility must trigger rejection, renegotiation, or escalation.

**Compositional Closure [Hypothesis].** The proposition that suitably compatible UIERUs can be composed into a larger unit that still satisfies specified UIERU interfaces and invariants; it is not guaranteed for arbitrary units.

**Conformance [Established].** Demonstrated satisfaction of a stated set of requirements through inspection, tests, and evidence.

**Conformance Profile [Proposed].** A named subset of UIERU capabilities and obligations. The repository discusses core, guided, exploratory, composable, evolvable, and collective configurations; consult `SPEC-004` for the normative profile identifiers and tests.

**Reference Implementation [Established].** A concrete implementation intended to clarify or test a specification. This repository's research documents do not, by themselves, constitute one.

**Validation Baseline [Established].** A simpler or alternative method against which UIERU's added value, cost, and risks can be compared.

**Coordination Overhead [Established].** Additional latency, compute, engineering effort, or governance cost introduced by decomposition, monitoring, and handoffs.

## 8. Subject-Indexed Intelligence and World Models

*This section summarizes the natural research extension in `docs/extensions/UIERU-EXT-001-Subject-Indexed-World-Models-and-Structural-Memory.md`.*

**Subject [Proposed usage].** The entity whose goals, experiences, history, and evaluation perspective define a subject-relative interpretation of events. An engineering subject identifier does not imply consciousness.

**Subject Index Plane [Proposed].** Cross-cutting indexing and authorization structure connecting subjects, principals, executors, observers, evaluators, history, and memory to UIERU operations.

**Subject ID [Proposed].** Identifier used to associate records and permissions with a subject; its semantics and privacy rules must be explicit.

**Executor ID [Proposed].** Identifier of the actor or process that performed an action, which may differ from the subject or principal.

**Observer ID [Proposed].** Identifier of the sensor, person, agent, or process that supplied an observation.

**Evaluator ID [Proposed].** Identifier of the entity or evaluation mechanism responsible for a score or judgment.

**Perspective ID [Proposed].** Identifier of the context and criteria under which an event or candidate is interpreted or evaluated.

**World Model [Established research term].** A representation used to predict or reason about environment states, dynamics, and consequences. A world model may be learned, symbolic, hybrid, personal, or shared.

**Subject-Indexed World Model [Proposed].** A world representation that explicitly links shared events and relations to a subject's perceptual access, goals, history, and interpretation without equating those interpretations with objective facts.

**Self Model [Established research term].** A system's representation of its own state, capabilities, limits, or history. In AI, a functional self model does not establish phenomenal consciousness.

**Shared World Memory [Proposed].** Records of events, objects, and relations intended for reuse across authorized subjects, with provenance and access controls.

**Subjective Episode [Proposed].** An event record contextualized by a subject's perception, goals, state, actions, and temporal history. It is not synonymous with an unqualified event log.

**Autobiographical Memory [Established cognitive-science term].** Memory organized around a person's life history and self-relevant experiences. Its development has multiple interacting explanations; a self index alone does not explain childhood amnesia.

**Subject-Indexed Structural Memory [Proposed].** A layered design linking shared events, subject-specific episodes, world/self models, and validated structural precedents.

**Historical Identity [Proposed usage].** Continuity of a subject's recorded history and self-relevant state across interactions and changes. This is a functional notion, not proof of personal identity or consciousness.

**Experience-to-Intelligence Conversion [Hypothesis].** The proposition that subject-contextualized episodes can yield better reusable guidance or structural principles than unindexed logs, given appropriate validation.

## 9. Big-Animal Intelligence and Platform-Scale Organization

*This section summarizes `docs/extensions/UIERU-EXT-002-Big-Animal-Intelligence-Organization-and-Platform-Level-Structural-RSI.md`.*

**Big Animal [Informal project term].** A large AI developer, infrastructure provider, or platform organization that operates models, tools, agents, evaluations, and broad user or developer ecosystems. It is an organizational category, not a technical standard.

**Model Scaling [Established].** Increasing model-related resources or capabilities, such as parameters, training data, or inference compute.

**Intelligence Organization Scaling [Proposed].** Improving the discovery, coordination, governance, reuse, and evolution of many heterogeneous intelligent capabilities. This is distinct from improving an individual model.

**Platform-Level Structural RSI [Proposed].** Evidence-driven improvement of platform-wide task decomposition, evaluation, routing, sandboxing, relay, or learning infrastructure, with independent validation and controlled rollout.

**Global Governance Plane [Proposed].** Platform-level policies for security, identity, interface compatibility, audit, and evaluator oversight. It should not automatically override legitimate local evaluation authority.

**Distributed Scoring Forests [Proposed].** Multiple domain- or subject-specific evaluation structures operating under shared interoperability and governance constraints rather than a single universal scoring function.

**Domain UIERU Forest [Proposed].** A coordinated collection of units and evaluators specialized for a task domain, such as software engineering, research, or enterprise operations.

**Tenant Boundary [Established].** Isolation and policy boundary for a customer, organization, or deployment environment in a multi-tenant platform.

**Capability Registry [Established / proposed application].** A discoverable catalog of tools, agents, skills, interfaces, constraints, and version information.

**Cross-Domain Validation [Proposed].** Testing a structural precedent in materially different tasks or environments before claiming broad transferability.

**Platform Rollout [Established].** Controlled deployment of a validated change across a population of services or users, commonly with staged exposure, monitoring, and rollback.

## 10. Sovereign Collective Intelligence Ecosystems

*This section summarizes `docs/extensions/UIERU-EXT-003-Subject-Sovereignty-and-Collective-Intelligence-Ecosystems.md`.*

**Subject Sovereignty [Proposed].** Legitimate control over subject-bound goals, memories, evaluations, and permitted uses of associated intelligence artifacts, within applicable law and organizational obligations.

**Collective Structural Learning [Proposed].** Improvement of shared structural precedents through contributions, receiver-side validation, counter-evidence, localization, and feedback.

**Collective Intelligence Ecosystem [Proposed].** A network of subjects, organizations, platforms, and UIERUs that exchange validated structural knowledge under explicit governance and interoperability rules.

**Sovereign Structural Relay [Proposed].** Relay that enforces source-side permissions, receiver-side authority checks, privacy constraints, purpose limitations, and evidence provenance.

**Purpose Limitation [Established privacy principle].** Restriction of data or artifacts to specified authorized uses; technical possession does not cancel this restriction.

**Knowledge Sharing Right [Proposed usage].** Permission to disclose or reuse particular structural artifacts, distinct from authority to perform the original task.

**Privacy-Preserving Structural Exchange [Proposed].** Sharing appropriately minimized, authorized, or transformed structural information without exposing unnecessary subject-bound details. Privacy properties require concrete threat models and testing.

**Platform Governance Right [Proposed usage].** Legitimate authority over platform infrastructure, safety constraints, and operational policies, distinct from ownership of a user's memories or preferences.

**Local Evaluation Sovereignty [Proposed].** A receiving subject's ability to apply its own authorized goals and evaluators to imported structures rather than inheriting source-side scores as binding decisions.

**Sovereignty–Interoperability Tension [Open problem].** The engineering tradeoff between strong local control and efficient cross-system exchange; neither extreme is assumed optimal.

## 11. Evidence, Measurement, and Research Discipline

**Architecture Claim.** A statement about how components are intended to fit or operate. It is not, by itself, evidence of measured performance.

**Testable Hypothesis.** A proposition stated with measurable outcomes, comparison conditions, and potential disconfirming results. See `TESTABLE-HYPOTHESES.md`.

**Open Question.** An unresolved issue concerning feasibility, costs, correctness, scalability, governance, or scientific interpretation. See `OPEN-QUESTIONS.md`.

**Validation Roadmap.** A staged experimental plan with baselines, datasets or tasks, metrics, decision thresholds, and reporting rules. See `VALIDATION-ROADMAP.md`.

**Ablation Study [Established].** Comparison that removes a component—such as Forward Guidance, Challenge Trails, or provenance—to estimate its contribution.

**Counterfactual Baseline [Established usage].** An alternative workflow used to estimate whether a proposed component changed an outcome.

**Negative Result [Established].** A finding that does not support a hypothesis; it should be retained with its conditions and evidence.

**Uncertainty Preservation [Proposed usage].** Keeping relevant confidence limits, unresolved conflicts, and alternative explanations through folding, relay, and evolution.

**Conformance Test [Established].** A repeatable check that a system satisfies a defined protocol requirement, including expected rejection of invalid or unauthorized actions.

## 12. Critical Distinctions

| Do not conflate | Why it matters |
|---|---|
| UIERU and a foundation model | UIERU organizes existing capabilities; it does not replace their internals. |
| Calling Path and Scoring Forest | One structures action; the other guides and evaluates it. |
| Scoring recommendation and authorization | A high score does not grant permission. |
| Sandbox result and production approval | An isolated success does not establish deployment safety. |
| Event and subjective episode | Subject context changes interpretation and retrieval. |
| Subject ID and consciousness | An identifier is an engineering mechanism, not evidence of experience. |
| Execution trace and verified evidence | A trace may be incomplete or misleading. |
| Relay and uncritical copying | Receivers must validate and localize. |
| Portability and authority transfer | Reusable structures do not carry automatic rights. |
| Structural Delta and approved improvement | Proposals require independent checks and authorization. |
| Structural RSI and model-weight training | Recursive improvement may operate at the organizational layer. |
| Collective learning and unrestricted data collection | Sharing must respect provenance, privacy, and purpose. |
| Model scaling and organization scaling | Larger models do not automatically yield better coordination. |
| Architectural possibility and empirical benefit | Claimed advantages require comparative measurement. |

## 13. Document Map

### Core research

- [`UIERU-001`](docs/UIERU-001-From-Calling-Paths-to-Evolvable-Intelligence-Units.md): foundational organizational unit.
- [`UIERU-002`](docs/UIERU-002-Canonical-UIERU-Contracts-Execution-Guidance-and-Relay.md): canonical structure and contracts.
- [`UIERU-003`](docs/UIERU-003-Calling-Path-and-Scoring-Forest-Duality.md): execution–evaluation duality.
- [`UIERU-004`](docs/UIERU-004-Forward-Guidance-and-Multi-Trail-Intelligence.md): forward-guided search.
- [`UIERU-005`](docs/UIERU-005-Sandbox-Threading-and-Counter-Evidence.md): sandboxed challenge and evidence.
- [`UIERU-006`](docs/UIERU-006-Composition-Nesting-Folding-and-Contract-Reconciliation.md): composition and contract reconciliation.
- [`UIERU-007`](docs/UIERU-007-Structural-Relay-Provenance-and-Intelligence-Portability.md): provenance and portability.
- [`UIERU-008`](docs/UIERU-008-Bidirectional-Collective-Learning-and-Relay-Ecosystems.md): collective relay.
- [`UIERU-009`](docs/UIERU-009-Residual-Driven-Structural-Evolution-and-Recursive-Improvement.md): structural evolution and RSI.
- [`UIERU-010`](docs/UIERU-010-Universal-Architecture-Engineering-Boundaries-and-Validation.md): integration and validation.

### Engineering cases

- [`CASE-001`](cases/CASE-001-Neighborhood-Lawn-Service-as-a-Minimal-UIERU.md): accessible minimal unit.
- [`CASE-002`](cases/CASE-002-Multi-Agent-Software-Engineering-and-Multi-Trail-Sandboxes.md): multi-agent engineering and structural RSI.
- [`CASE-003`](cases/CASE-003-Large-Scale-Organizational-Relay-and-Collective-Learning.md): organizational-scale relay.

### Engineering specifications

- [`SPEC-001`](specs/SPEC-001-Canonical-UIERU-Contract-and-Schema.md): contract and schema.
- [`SPEC-002`](specs/SPEC-002-Forward-Guidance-and-Multi-Trail-Lifecycle.md): guidance and trail lifecycle.
- [`SPEC-003`](specs/SPEC-003-Structural-Relay-and-Portfolio-Exchange.md): relay exchange.
- [`SPEC-004`](specs/SPEC-004-Composition-Evolution-and-Conformance.md): composition, evolution, conformance.

### Research extensions

- [`UIERU-EXT-001`](docs/extensions/UIERU-EXT-001-Subject-Indexed-World-Models-and-Structural-Memory.md): subject-indexed world models and structural memory.
- [`UIERU-EXT-002`](docs/extensions/UIERU-EXT-002-Big-Animal-Intelligence-Organization-and-Platform-Level-Structural-RSI.md): platform-scale intelligence organization.
- [`UIERU-EXT-003`](docs/extensions/UIERU-EXT-003-Subject-Sovereignty-and-Collective-Intelligence-Ecosystems.md): subject sovereignty and collective learning.

### Navigation and validation

- [`README.md`](README.md) · [`START-HERE.md`](START-HERE.md) · [`CONTENTS.md`](CONTENTS.md)
- [`FIGURE-INDEX.md`](FIGURE-INDEX.md) · [`FUTURE-DIRECTIONS.md`](FUTURE-DIRECTIONS.md)
- [`OPEN-QUESTIONS.md`](OPEN-QUESTIONS.md) · [`TESTABLE-HYPOTHESES.md`](TESTABLE-HYPOTHESES.md) · [`VALIDATION-ROADMAP.md`](VALIDATION-ROADMAP.md)

## 14. Terminology Governance and Versioning

1. **Definitions are scoped.** A term's meaning in this repository does not automatically supersede meanings in other AI, cognitive-science, or software-engineering literature.
2. **Specifications take precedence for interface details.** Where an informal glossary entry and a normative specification differ, use the explicitly versioned specification for implementation and record the discrepancy for correction.
3. **Evidence is required for performance claims.** Do not treat proposed architectures or illustrative cases as experimentally validated.
4. **Authority remains explicit.** Neither composition, scoring, relay, nor recursion silently expands a principal's permissions.
5. **Extensions remain optional.** Subject indexing and Big-Animal platform designs enrich the research program but are not prerequisites for a minimal UIERU.
6. **Revisions should be traceable.** Update this glossary alongside `CHANGELOG.md` and affected `SPEC` files when normative meanings change.

---

**Citation:** See [`CITATION.cff`](CITATION.cff) for project attribution.  
**Authors:** Sizhe Tan & GPT-Obot.  
**Research status:** Proposed framework; engineering and scientific claims require validation.
