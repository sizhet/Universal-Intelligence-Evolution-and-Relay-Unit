# UIERU-EXT-001 — Subject-Indexed World Models and Structural Memory

**Project:** Universal Intelligence Evolution and Relay Unit (UIERU)  
**Series:** Research Extensions  
**Version:** 1.0.0 — Research proposal  
**Authors:** Sizhe Tan & GPT-Obot  
**Status:** Conceptual architecture and testable engineering hypotheses; not an implemented standard

## Abstract

World models represent objects, events, relations, and anticipated changes. Yet a single event can have distinct significance for different subjects: what a person observes, can do, remembers, values, and authorizes depends on the subject's history, embodiment, goals, and institutional role. This paper proposes **Subject-Indexed World Models (SIWM)** and **Subject-Indexed Structural Memory (SISM)** as optional, cross-cutting capabilities within the Universal Intelligence Evolution and Relay Unit (UIERU). It distinguishes shared event records from subject-specific interpretations, autobiographical episodes, operational memory, and validated structural precedents. It defines identity and provenance semantics, sketches schemas and interfaces, and specifies how forward guidance, relay, and structural evolution should respect subject boundaries. The proposal does **not** claim that indexing produces consciousness, that all AI agents are persons, or that early childhood amnesia has a single cause. Its engineering claims are hypotheses to be tested against ordinary event stores, retrieval-augmented memory, and conventional agent workflows.

**Keywords:** subject index; world model; episodic memory; autobiographical memory; self-model; structural memory; UIERU; provenance; relay; evaluation sovereignty; structural RSI.

---

## 1. Motivation: The Same Event Is Not the Same Experience

Consider a sudden storm during a neighborhood lawn-service job. A weather service records rainfall; a customer worries about damage; a crew leader decides whether equipment can be used safely; an insurer considers liability. These participants can reference the **same event ID** while holding different observations, stakes, authority, and next actions. Treating every view as one undifferentiated world-model entry loses important distinctions. Treating every view as a wholly separate reality loses opportunities for factual reconciliation.

The engineering question is therefore:

> How can a system preserve shared facts while retaining the subject-dependent context required for reliable memory, guidance, and relay?

The proposed answer is to index **perspective-bearing records** to explicitly identified subjects, without making the underlying facts private or subjective by default.

## 2. Scope and Terminology

A **subject** is an entity for which the system maintains an identifiable locus of goals, constraints, experience history, or evaluation authority. Depending on the application, this may be a human, team, organization, or functionally modeled AI agent. This is an *engineering role*, not a claim of sentience or legal personhood.

An **executor** performs an action; a **principal** authorizes it; an **observer** provides evidence; an **evaluator** judges results; a **memory owner/controller** sets applicable access and retention rules. These roles can differ.

A **world model** is a task-relevant representation of states, entities, relationships, dynamics, and possible interventions. A **self-model** represents a subject's own capabilities, limits, commitments, and continuity. An **episode** binds events to a subject-specific context and temporal sequence. A **structural precedent** is a validated, scoped reusable procedure, scoring rule, constraint, or lesson.

## 3. Developmental Memory as an Inspiration, Not a Proof

Childhood amnesia—the relative scarcity of accessible autobiographical memories from the earliest years—is relevant because it highlights that **recording an event** and **later retrieving it as part of a continuous personal history** are different functions. Developmental research implicates interacting factors such as hippocampal maturation, language, social narration, temporal organization, and developing self-concepts. Children younger than three can form and use memories; a missing self-index is **not** an established single-cause explanation of childhood amnesia.

The transferable *engineering hypothesis* is narrower: stable subject references, temporal continuity, and narrative/causal organization may improve an artificial system's ability to retrieve past episodes in the context of future decisions. This analogy motivates tests; it does not establish equivalence between AI memory and human autobiographical memory.

## 4. Architecture: Shared Facts, Indexed Perspectives

We propose four separable layers:

1. **Shared event and object layer:** versioned claims about the world, with sources, timestamps, confidence, and access restrictions.
2. **Subject-indexed episode layer:** observations, perceived consequences, objectives, available actions, and local interpretations for a particular subject.
3. **Subject-indexed world/self-model layer:** beliefs, predictive models, preferences where authorized, abilities, commitments, and time-varying identity context.
4. **Structural memory layer:** reusable Calling Paths, Scoring Principles, counter-evidence, residuals, and tested structural deltas, each with an applicability envelope.

A useful conceptual representation is:

```text
Shared events / objects / evidence
             |
             +--> Subject A: episodes --> world/self model --> guidance
             |
             +--> Subject B: episodes --> world/self model --> guidance
             |
             +--> Subject C: episodes --> world/self model --> guidance
                              |
                     validated structural precedents
                              |
                   governed relay and localization
```

No layer is assumed to be globally visible. Shared does not mean unrestricted.

## 5. Formal Model

Let `s` be a subject, `t` a time, `e` an event, and `c` an authorized task context. Define:

$$
W_{s,t,c}= \mathrm{Update}(W_{s,t-1,c},\mathrm{Observe}_{s,c}(e),H_{s,t},B_{s,t},G_{s,t},V_{s,t})
$$

where `H` is accessible history, `B` capability/embodiment context, `G` goals, and `V` evaluative perspective. This is a **design notation**, not a claim that every world model has these explicit fields or that they can be measured without error.

A subject-indexed episode can be represented as:

$$
\epsilon=(event\_ref,subject\_ref,observation,context,action,consequence,time,provenance,access)
$$

A reusable structural precedent is not merely an episode:

$$
\pi=(pattern,conditions,evidence,counterevidence,validation,version,authority)
$$

The distinction is essential: **experience is not automatically a generalizable principle**.

## 6. Integrating with Canonical UIERU

Canonical UIERU is represented by `U = (K, P, F, R, E)`:

| UIERU element | Subject-indexed requirement |
|---|---|
| `K` — Contract | Identify principal, subject(s), executor, consent/authorization, purpose, scope, and retention policy |
| `P` — Calling Path | Record which subject initiated, experienced, executed, or observed each node |
| `F` — Scoring Forest | Distinguish evaluator identity, scoring perspective, constraints, and conflict resolution |
| `R` — Relay | Transfer only authorized views; preserve subject references and evidence provenance |
| `E` — Evolution | Require validation and approval before a subject-specific observation becomes a reusable structural delta |

Subject indexing is a **cross-cutting plane**, not a mandatory sixth element, and it does not convert an ordinary UIERU into an autonomous subject.

## 7. Identity, Continuity, and Role Separation

A robust implementation distinguishes:

- `subject_id`: stable scoped identifier for whose history or perspective is represented.
- `principal_id`: authority under which work occurs.
- `executor_id`: actual actor/tool/agent performing an operation.
- `observer_id`: evidence source.
- `evaluator_id` and `perspective_id`: who evaluates and by which criteria.
- `event_id`, `episode_id`, and `provenance_id`: distinguish occurrences, interpretations, and evidence lineage.

These identifiers must not be casually equated. A platform agent acting on behalf of a customer does not thereby acquire ownership of the customer's memories or preferences. Identity continuity must be handled explicitly across account changes, delegation, agent replacement, and organizational restructuring. Where stable identity is not needed, use ephemeral or pseudonymous identifiers.

## 8. Canonical Data Example (Illustrative YAML)

The following is an **illustrative exchange profile**, not a normative schema. Field names are candidates for later specification and validation.

```yaml
schema_version: "siwm-draft-0.1"
event:
  event_id: "evt-storm-0042"
  type: "heavy_rain"
  observed_at: "2026-10-20T15:20:00Z"
  evidence_refs: ["weather-report-17"]
  confidence: "source-reported"
subject_episode:
  episode_id: "ep-crew-0042"
  subject_id: "crew-alpha"
  principal_id: "service-company"
  executor_id: "crew-lead-7"
  event_ref: "evt-storm-0042"
  perspective_id: "operational-safety"
  observed_effect: "wet ground; unsafe mower traction"
  goals_at_time: ["finish safely", "avoid property damage"]
  available_actions: ["delay", "reschedule", "inspect manually"]
  selected_action: "reschedule"
  rationale: "safety constraint dominated schedule score"
  provenance_refs: ["crew-observation-11", "weather-report-17"]
  access_policy: "service-operations-only"
  retention_policy: "per-contract"
structural_candidate:
  candidate_id: "delta-wet-ground-gate-01"
  proposal: "add traction check before dispatch"
  applicability: ["powered mower", "wet terrain"]
  validation_state: "unverified"
  counterevidence_refs: []
  deployment_authorized: false
```

**Security note:** Real deployments should use machine-enforced authorization, encryption, deletion/retention rules, and structured provenance; a string such as `access_policy` is not an access-control system.

## 9. Retrieval: From Event Lookup to Subject-Aware Recall

Conventional retrieval often ranks semantic similarity. Subject-aware recall may additionally consider:

- subject relevance and delegated access;
- temporal sequence and identity continuity;
- goals and constraints active at the time;
- causal links between action and outcome;
- provenance quality and conflicting evidence;
- whether a precedent is valid for the current environment.

An illustrative ranking objective is:

$$
Score(r\mid s,q,c)=w_1 Rel(r,q)+w_2 Context(r,s,c)+w_3 Causal(r,q)+w_4 Evidence(r)-w_5 Risk(r)
$$

This ranking applies **after mandatory access-control filtering**. No score may override a denied permission. Weights should be calibrated and evaluated; the expression is not a proven universal retrieval formula.

## 10. Forward Guidance with Subject-Specific World Models

Before executing a Calling Path, the Scoring Forest may consult a subject-indexed model to estimate feasible actions and their consequences. During execution, it updates predictions from new observations. Afterward, it compares expected and actual results, preserving both objective evidence and perspective-specific judgments.

A minimal control loop:

```text
1. Authenticate principal and resolve subject context.
2. Fetch only authorized shared facts and subject episodes.
3. Generate candidate Calling Paths and optional sandbox trails.
4. Reject candidates violating hard constraints or authority.
5. Evaluate surviving paths under named perspectives.
6. Execute approved path; collect observations and provenance.
7. Update subject episodes and world-model beliefs separately.
8. Propose structural precedents from residuals and counter-evidence.
9. Validate candidates independently before relay or deployment.
```

The world model can be wrong; observed facts and inferred beliefs must remain distinguishable.

## 11. Multi-Subject Conflicts and Scoring Sovereignty

Multiple subjects may legitimately disagree about a proposed action. A customer values timeliness, a crew leader prioritizes physical safety, and the company values cost. The system should not silently collapse these perspectives into a single opaque number.

A practical reconciliation procedure is:

1. Enforce non-negotiable safety, legal, and authorization constraints.
2. Preserve each perspective's evaluator identity and criteria.
3. Expose tradeoffs and evidence conflicts.
4. Apply contractually designated decision rights or escalate.
5. Record the decision and dissenting evidence in the Relay Portfolio.

This is **perspective-aware scoring**, not a claim that every preference deserves identical authority.

## 12. Relay: Portable Structure, Not Portable Ownership

Subject-indexed records complicate relay because a useful structural lesson may contain private episodes. A relay should therefore distinguish:

- **raw private episode:** normally local, access-restricted;
- **redacted evidence:** shared only when permitted and adequate;
- **abstract structural precedent:** a generalizable procedure with documented validation;
- **receiver-localized adaptation:** accepted only under the receiver's own contract and scoring criteria.

A receiver may import a validated rule without importing the originating person's private history. Conversely, provenance may require retaining a protected reference to source evidence without exposing the underlying record.

## 13. Structural Memory and Governed RSI

The proposed evolution loop is:

```text
Subject episode
  -> residual or surprising outcome
  -> candidate causal explanation
  -> candidate Calling Path / Scoring Forest delta
  -> sandbox exploit / explore / challenge
  -> independent evaluation and counter-evidence
  -> authorized versioned structural precedent
  -> localized relay to future UIERUs
```

This constitutes a candidate form of **structural RSI-based intelligence driving** when a system improves its future planning, evaluation, or learning procedures—not merely the answer to one task. It does not imply unrestricted self-modification, model-weight updates, or guaranteed recursive gains.

## 14. API Sketch

```text
POST /events                       # write a sourced event, subject to policy
POST /subjects/{id}/episodes       # append authorized subject episode
GET  /subjects/{id}/memory         # query filtered episode/structural memory
POST /world-models/{id}/predict    # produce versioned predictions
POST /precedents/candidates        # propose a structural lesson
POST /precedents/{id}/validate     # attach independent validation results
POST /relay/portfolios             # export an authorized relay package
POST /relay/portfolios/{id}/accept # localize and explicitly accept/reject
```

All endpoints require authentication, purpose-scoped authorization, auditability, and idempotency semantics. Endpoint names are illustrative; they do not establish an existing service.

## 15. Worked Example: Lawn Service, Two Subjects

**Shared event:** Rain starts before the scheduled lawn service.

**Customer episode:** The appointment is missed; the customer prefers advance notification and offers a different time slot.

**Crew episode:** The soil is saturated; traction and property-damage risk make mowing unsafe.

**Company evaluation:** Safety constraints rule out mowing. The service sends a rescheduling proposal and documents why.

**Structural candidate:** Introduce a pre-dispatch wet-ground decision gate and customer-notification branch. The proposal is tested across multiple weather scenarios before promotion.

A conventional event log can record the cancellation. A subject-indexed UIERU aims to preserve **why it mattered to each party**, who could authorize alternatives, and what generalizable structure—if any—was learned.

## 16. Engineering Boundaries and Failure Modes

| Failure mode | Consequence | Mitigation |
|---|---|---|
| Subject/executor conflation | Incorrect authority or attribution | Separate identifiers and delegation chains |
| Incorrect identity stitching | Mixed personal histories | Confidence-aware linking; reversible merges |
| Privacy leakage in relay | Unauthorized cross-subject exposure | Redaction, access checks, minimization, retention controls |
| Model belief treated as fact | Compounding errors | Separate assertions, predictions, and evidence |
| Premature generalization | Bad structural precedent | Counter-evidence, scoped validation, rollback |
| Excessive personalization | Narrowed exploration or bias | Alternative perspectives, user controls, challenge trails |
| Memory overaccumulation | Cost and stale decisions | Retention, summarization, decay, versioned provenance |
| Centralized scoring override | Loss of subject sovereignty | Contract reconciliation and independent approvals |
| Anthropomorphic inference | Unjustified claims about AI experience | Operational definitions and explicit limitations |

## 17. Testable Hypotheses

**H1 — Episodic continuity:** Under equivalent storage and retrieval budgets, subject-indexed episodes improve multi-session causal recall compared with a flat event store.

**H2 — Role fidelity:** Explicit principal/executor/evaluator separation reduces authorization and attribution errors in delegated workflows.

**H3 — Forward guidance:** Subject-aware world-model retrieval improves constraint satisfaction or task completion compared with non-indexed retrieval on multi-party tasks.

**H4 — Relay fidelity:** Provenance-preserving, subject-scoped relay reduces erroneous cross-context transfer relative to unrestricted memory copying.

**H5 — Structural growth:** Validated structural precedents derived from episodes outperform raw episode reuse on held-out task families, after accounting for validation cost.

**H6 — Tradeoff:** Subject indexing increases governance and retrieval overhead; benefits should exceed costs only above measurable task-complexity thresholds.

All six are open hypotheses; none is established by this paper.

## 18. Validation Program

**Baselines:** (A) stateless workflow, (B) shared event store, (C) conventional RAG/agent memory, (D) subject-indexed memory without structural evolution, and (E) full subject-indexed UIERU.

**Benchmarks:** longitudinal customer service, multi-party software review, incident response, and simulated household or team planning. Include conflicting observations, changing identities, revoked delegation, stale evidence, and adversarial memory injection.

**Metrics:** task success; correct attribution; temporal/causal recall; unauthorized disclosure rate; constraint violations; retrieval latency; token/compute/storage cost; relay fidelity; structural-delta acceptance rate; and improvement on held-out tasks. Include human review where evaluation sovereignty or sensitive memory is involved.

**Ablations:** remove subject IDs, remove self-model, remove provenance, remove counter-evidence, remove structural precedent validation, and remove relay localization. Report negative results and distribution shift.

**Acceptance condition:** Demonstrate statistically credible improvement on prespecified measures without unacceptable privacy, safety, or cost regressions. No claim of universal superiority is warranted.

## 19. Open Research Questions

1. What minimum identity continuity is sufficient for useful subject-indexed memory?
2. Which episode features are causally useful rather than merely correlated?
3. How should the system represent conflicting or uncertain self-models?
4. Can a structural precedent be shared while guaranteeing appropriate privacy protection?
5. How should memory deletion propagate to derived structural artifacts?
6. What are the limits of transferring human autobiographical-memory analogies to AI?
7. When should a team be modeled as a subject versus a collection of individual subjects?
8. How can an AI assistant preserve user sovereignty when infrastructure is platform-owned?
9. When does subject indexing become more expensive than its decision benefit?
10. Can subject-aware counter-evidence prevent feedback-loop personalization failures?

## 20. Relationship to the UIERU Research Program

This extension complements, but does not require prior reading of, the UIERU core papers. In particular:

- **UIERU-002** defines canonical contracts, execution, guidance, and relay.
- **UIERU-003/004** examine Calling Path–Scoring Forest duality and forward multi-trail guidance.
- **UIERU-007/008** examine provenance-preserving relay and collective learning.
- **UIERU-009** examines residual-driven structural evolution and governed RSI.
- **SPEC-001/003/004** provide candidate contracts, relay semantics, and conformance requirements.

The broader Subjective Structural Intelligence (SSI) line is a related research direction, not a prerequisite for implementing this proposal.

## 21. Conclusion

A useful world model need not treat all experiences as interchangeable, and a useful memory system need not treat every observation as an objective fact or every lesson as a validated principle. **Subject indexing** offers an engineering mechanism for linking shared events to distinct perspectives, temporal histories, decision rights, and structural learning. Within UIERU, this can strengthen forward guidance, provenance-preserving relay, and governed structural RSI while retaining explicit boundaries between the subject, executor, evaluator, and platform. Whether the added structure improves performance enough to justify its cost remains an empirical question.

---

## Selected Research Background

These works provide background rather than proof of the proposed UIERU architecture:

1. Tulving, E. (1972). *Episodic and semantic memory*. In *Organization of Memory*. Academic Press.
2. Conway, M. A., & Pleydell-Pearce, C. W. (2000). The construction of autobiographical memories in the self-memory system. *Psychological Review*, 107(2), 261–288. https://doi.org/10.1037/0033-295X.107.2.261
3. Fivush, R. (2011). The development of autobiographical memory. *Annual Review of Psychology*, 62, 559–582. https://doi.org/10.1146/annurev.psych.121208.131702
4. Nelson, K., & Fivush, R. (2004). The emergence of autobiographical memory: A social cultural developmental theory. *Psychological Review*, 111(2), 486–511. https://doi.org/10.1037/0033-295X.111.2.486
5. Baddeley, A. (2000). The episodic buffer: A new component of working memory? *Trends in Cognitive Sciences*, 4(11), 417–423. https://doi.org/10.1016/S1364-6613(00)01538-2
6. Park, J. S., et al. (2023). Generative Agents: Interactive Simulacra of Human Behavior. *Proceedings of UIST 2023*. https://doi.org/10.1145/3586183.3606763

## Suggested Citation

Tan, Sizhe, and GPT-Obot. (2026). *UIERU-EXT-001: Subject-Indexed World Models and Structural Memory*. In *Universal Intelligence Evolution and Relay Unit*, v1.0.0. Research extension. Repository DOI: pending.

**License:** Refer to the repository-level license and citation metadata. No independent license is asserted here.
