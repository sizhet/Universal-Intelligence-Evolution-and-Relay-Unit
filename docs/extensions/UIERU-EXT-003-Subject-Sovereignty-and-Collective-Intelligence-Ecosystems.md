# UIERU-EXT-003 — Subject Sovereignty and Collective Intelligence Ecosystems

**Subtitle:** From Subject-Indexed Experience and Platform-Scale Intelligence to Governed Structural Relay and Collective Evolution  
**Authors:** Sizhe Tan & GPT-Obot  
**Version:** 1.0.0  
**Status:** Research extension / proposed architecture; not an implemented standard  
**Project:** Universal Intelligence Evolution and Relay Unit (UIERU)  
**Repository location:** `docs/extensions/UIERU-EXT-003-Subject-Sovereignty-and-Collective-Intelligence-Ecosystems.md`

## Abstract

A collective intelligence ecosystem must reconcile two objectives that are frequently conflated: enabling knowledge and reusable intelligence structures to circulate, while preserving the authority of the subjects whose goals, histories, and decisions those structures affect. This paper proposes a subject-sovereign collective architecture built around Universal Intelligence Evolution and Relay Units (UIERUs). Each unit combines a contract, a governed Calling Path, a forward-guiding Scoring Forest, structural relay, and an evolution process. We distinguish subjects from executors, infrastructure operators, evaluators, and information custodians; introduce explicit sovereignty and sharing boundaries; define an evidence-preserving exchange protocol with independent receiver localization; and specify governance requirements for platform-level structural recursive self-improvement (RSI). A worked example, exchange records, failure modes, and falsifiable hypotheses show how the proposal could be evaluated. The central claim is architectural rather than empirical: collective learning need not require centralized control of individual evaluation, memory, or action authority.

**Keywords:** UIERU; subject sovereignty; collective intelligence; structural relay; provenance; subject-indexed memory; Scoring Forest; structural RSI; federated governance; consent; counter-evidence.

---

## 1. The Problem: Whose Intelligence, Whose Choice?

Large-scale intelligence systems increasingly combine personal assistants, domain agents, shared tools, model providers, organizations, and cross-task learning pipelines. They can improve through common experience, but the same architecture can also collapse distinct interests into one platform objective. A user may authorize an assistant to complete a task without authorizing the platform to reuse the task's private history as general training material. A platform may operate an execution service without becoming the rightful evaluator of the user's goals. A shared solution may be technically portable without being authorized for another subject's environment.

The resulting engineering question is not merely *how do units exchange intelligence?* It is **under whose authority, for whose benefit, on which evidence, and with what right of refusal or revision?**

We call the proposed answer **Subject Sovereignty with Governed Collective Structural Learning**. Sovereignty here denotes bounded decision and evaluation authority expressed through enforceable contracts and organizational controls. It does not assert absolute independence from law, safety requirements, or legitimate platform obligations.

## 2. Self-Contained UIERU Foundation

A Universal Intelligence Evolution and Relay Unit is a selectively adopted organizational intelligence structure:

\[
U = (K, P, F, R, E)
\]

- **K — Contract:** subject, task, purpose, authority, constraints, resources, evidence obligations, and acceptance criteria.
- **P — Calling Path:** ordered or conditional actions performed by people, models, agents, tools, and services.
- **F — Scoring Forest:** multiple evaluation perspectives that guide candidate selection, execution, replanning, and settlement.
- **R — Relay:** portable, provenance-bearing exchange of states, evidence, alternatives, and structural precedents.
- **E — Evolution:** residual- and counter-evidence-driven candidate improvement with independent testing and governed deployment.

A UIERU is not a new mandatory AI subject or a replacement for existing agents. A small task may not justify this structure; a complex multi-party task may benefit substantially from it. The architecture's universality is a design ambition to test, not a demonstrated property.

## 3. Four Distinct Kinds of Control

An ecosystem should not encode all authority in a single `owner` field. At minimum, it must distinguish:

| Dimension | Governing question | Illustrative holder |
|---|---|---|
| Subject sovereignty | Whose goals and experiential history are implicated? | Individual, team, institution |
| Execution authority | Who may initiate which real-world actions? | Delegated agent or operator |
| Evaluation authority | Who chooses and approves criteria for success? | Subject or explicitly authorized delegate |
| Infrastructure and policy authority | Who operates systems and enforces lawful/safety limits? | Provider, administrator, regulator |
| Information stewardship | Who may store, disclose, retain, or delete data? | Data controller/custodian under applicable agreements |
| Structural reuse rights | Who may share or deploy extracted patterns? | Rights holder and authorized governance process |

These rights may overlap but must not be inferred from one another. **Execution delegation does not automatically transfer evaluation sovereignty, and possession of records does not automatically grant reuse rights.**

## 4. Subject-Indexed World Models and Memory

A world event and a subject's episode of that event are different records. The same outage may be a reliability incident to an operator, an economic loss to a customer, and a security concern to a risk officer. A useful representation therefore separates:

1. **Shared event layer:** minimally scoped, provenance-bearing claims about observable events.
2. **Subject-indexed episode layer:** event as experienced, interpreted, or acted upon by a specific subject.
3. **Subject world/self-model layer:** current beliefs, capabilities, goals, boundaries, and temporal continuity.
4. **Structural precedent layer:** validated, reusable task patterns, scoring criteria, and failure conditions.

A practical memory key may be `(subject_id, event_id, perspective_id, purpose_id, version)`; it is not a claim that such keys create consciousness or phenomenological experience. In humans, early autobiographical memory and self-development involve multiple interacting mechanisms; their relationship motivates research, not a single-cause explanation of childhood amnesia.

Crucially, a subject-indexed record may remain private while an appropriately abstracted structural precedent becomes shareable. Whether that abstraction is sufficiently non-identifying must be assessed rather than assumed.

## 5. The Sovereignty Boundary as a Contract

The contract must bind actions, observations, evaluation, and reuse to explicit purposes. Suggested fields include:

- **Principals:** subject, authorized delegates, platform operator, and accountable reviewers.
- **Purposes:** immediate execution, audit, local learning, cross-unit sharing, or model training, independently specified.
- **Scope:** allowed tools, data categories, recipient classes, jurisdictions, and expiry.
- **Evaluation:** protected constraints, local scoring perspectives, conflict resolution, and approval rights.
- **Memory:** retention, access, export, correction, and deletion handling, subject to applicable obligations.
- **Relay:** permitted payload classes, redaction requirements, provenance, and downstream-use restrictions.
- **Evolution:** proposal authority, independent verification, rollout scope, monitoring, and rollback.

Consent alone is not a universal legal basis or sufficient safeguard. Systems must support applicable legal requirements, enterprise policies, contractual duties, and protections for non-consenting third parties. A contract can limit operations technically; it cannot supersede law.

## 6. Architecture: Local Sovereignty, Shared Learning

The proposed ecosystem has five interacting planes:

**Subject plane.** Holds subject-scoped goals, episodes, preferences, and evaluation authority. It may be personal, organizational, or delegated.

**Execution plane.** Runs Calling Paths with least-privilege tools and auditable action boundaries.

**Local Scoring Forest.** Provides forward guidance and evaluates trade-offs according to authorized local perspectives; it may consult shared principles without surrendering final local evaluation.

**Relay and precedent plane.** Exchanges validated structures and counter-evidence through interoperable contracts, with provenance and use restrictions.

**Governance plane.** Enforces platform safety, integrity, policy, oversight, appeals, and incident response; it cannot silently redefine a subject's private objectives as platform objectives.

These planes are logical responsibilities, not necessarily five separately deployed services. Implementations may use isolation, encryption, capability tokens, event logs, policy engines, and federated registries as appropriate.

## 7. Relay Is Not Transfer of Authority

A sender can transmit a successful Calling Path and its supporting evidence, but the receiver must independently decide whether it is suitable and authorized. The receiver should perform:

1. **Authenticate** sender and verify payload integrity.
2. **Authorize** access and permissible downstream uses.
3. **Inspect** provenance, confidence limits, and counter-evidence.
4. **Localize** dependencies, capabilities, constraints, and subject perspectives.
5. **Rescore** candidate actions under the receiver's Scoring Forest.
6. **Sandbox-test** where risk or uncertainty warrants it.
7. **Accept, adapt, quarantine, or reject** the proposal with recorded rationale.
8. **Feedback** validation outcomes without leaking unauthorized private context.

This is a **two-way relay**: local adaptations and negative results can improve the common precedent, but only under authorized sharing rules.

## 8. Canonical Sovereign Relay Envelope (Illustrative YAML)

The following example is a proposed exchange shape, not an already ratified wire standard.

```yaml
schema_version: "uieru-sovereign-relay/0.1-draft"
relay_id: "relay-2026-0042"
sender_unit: "team-a-incident-unit"
receiver_unit: "team-b-incident-unit"
subject_context:
  subject_ref: "org-subject-pseudonym-01"
  subject_type: "organization"
  executor_ref: "agent-runner-a"
  evaluator_ref: "team-a-review-board"
  subject_scope: "source-local"
purpose_and_rights:
  authorized_purpose: "incident-playbook-evaluation"
  allowed_payloads: ["redacted-path", "aggregated-metrics", "counter-evidence"]
  prohibited_uses: ["model-training", "identity-reconstruction"]
  onward_transfer: "requires-new-authorization"
  expires_at: "2026-12-31T00:00:00Z"
contract:
  contract_ref: "contract-v3"
  constraints: ["no-production-action-without-local-approval"]
portfolio:
  calling_path_ref: "path-redacted-v2"
  scoring_perspectives: ["reliability", "customer-impact", "security"]
  evidence_refs: ["ev-101", "ev-102"]
  counter_evidence_refs: ["ce-009"]
  unresolved_residuals: ["regional-network-variance"]
  structural_delta:
    proposal_ref: "delta-17"
    status: "unvalidated-at-receiver"
provenance:
  issuer: "team-a"
  digest: "sha256:<digest-placeholder>"
  transformation_log_ref: "transform-log-5"
receiver_controls:
  localization_required: true
  independent_evaluation_required: true
  sandbox_before_deployment: true
  automatic_execution_allowed: false
feedback:
  allowed: true
  disclosure_policy: "aggregate-only"
```

Pseudonyms do not necessarily provide anonymity. Integrity hashes do not prove truth, and a YAML declaration is not itself enforcement. Production implementations need verified identities, signed policy decisions where appropriate, controlled storage, and tests of actual downstream behavior.

## 9. Collective Learning Without Compulsory Centralization

A collective system can learn from local units through a controlled pipeline:

`Local episode → Candidate abstraction → Privacy/rights review → Evidence package → Shared precedent → Receiver validation → Local adaptation → Authorized feedback`.

Possible sharing levels are:

| Level | Shared artifact | Typical risk |
|---|---|---|
| L0 | No external sharing | Limited collective benefit |
| L1 | Aggregate outcomes and metrics | Re-identification from small groups |
| L2 | Redacted evidence and failure conditions | Residual sensitive context |
| L3 | Validated structural patterns | Unsafe overgeneralization |
| L4 | Executable units or tools | Supply-chain and action risk |
| L5 | Model updates or training signals | Privacy, provenance, and attribution risks |

Higher levels are not automatically preferable. Select the least revealing artifact that still enables the intended validation and reuse. Some settings may require fully local learning.

## 10. Platform-Level Structural RSI Under Subject Sovereignty

Platform-scale structural recursive self-improvement (RSI) means improving the mechanisms that organize future intelligence work: task decomposition, guidance, evaluators, sandbox protocols, relay policies, and precedent retrieval. It need not modify model weights.

A governed loop is:

1. Collect **authorized** residual and counter-evidence signals.
2. Identify recurrent structural failure modes.
3. Propose a versioned change to Calling Paths, Scoring Forests, or relay mechanisms.
4. Evaluate on independent datasets and adversarial cases, including minority and subject-specific perspectives.
5. Test privacy, authorization, resource, and negative-transfer constraints.
6. Obtain approval from the responsible authority.
7. Deploy gradually with rollback and monitoring.
8. Preserve dissenting evidence and measure whether benefits generalize.

The platform must not use its own evaluator as the sole judge of its own improvements. Nor should a broadly successful global principle automatically override a locally protected objective. This is a proposal for **bounded structural RSI**, not an assertion that recursive gains are guaranteed.

## 11. Evaluation Sovereignty and Scoring Conflicts

Scoring Forests can contain incompatible objectives. A platform may optimize latency and operational safety; a subject may prioritize privacy and completeness. Such differences should not be hidden by a single weighted score.

A recommended evaluation order is:

1. **Hard constraints:** law, safety, contractual limits, authorization.
2. **Protected subject constraints:** explicit user or institutional non-negotiables within legitimate scope.
3. **Perspective-specific scores:** cost, quality, fairness, reliability, privacy, learning value.
4. **Trade-off and uncertainty record:** what was sacrificed, by whom, and why.
5. **Escalation or refusal:** when objectives cannot be reconciled.

A folding operation may summarize decisions, but must preserve the provenance of material conflicts and dissent. This avoids laundering a governance decision through an apparently neutral scalar score.

## 12. Worked Example: Personal Assistant on a Large AI Platform

Consider a user asking an assistant to plan and execute a recurring home-maintenance service. The user has private availability preferences and prior experiences; the platform has general task templates and safety policies.

**Step A — Subject-scoped task.** The user's UIERU contract authorizes scheduling research and proposals, not irreversible booking without approval.

**Step B — Forward guidance.** The local Scoring Forest weighs price, reliability, disruption, and user preferences. A platform-wide template is consulted as an optional precedent.

**Step C — Multi-trail search.** One trail seeks a low-cost provider, another a high-reliability provider, and a challenge trail checks cancellation terms and access requirements.

**Step D — Local decision.** The assistant presents alternatives and asks for approval before a binding action. Platform policy prevents unsafe or unauthorized tool use.

**Step E — Structural learning.** A failed appointment reveals a useful general lesson: verify access instructions before confirmation. The private episode remains subject-scoped. An abstracted validation rule is considered for collective sharing only if authorized and sufficiently privacy-preserving.

**Step F — Receiver localization.** Another assistant may import the general rule, but must check whether it applies to its user's circumstances.

The value of UIERU is not merely automating booking; it is making guidance, authority, evidence, and reusable learning separable and auditable.

## 13. Threat Model and Failure Modes

| Failure | Consequence | Proposed mitigation |
|---|---|---|
| Subject/executor conflation | Unauthorized decisions | Separate identities and scoped capabilities |
| Evaluation capture | Platform goals displace subject goals | Protected local criteria; independent review |
| Consent laundering | Task permission becomes training permission | Purpose-specific rights; enforcement tests |
| Memory leakage | Private episodes enter shared registries | Data minimization, redaction, access controls |
| Re-identification | Abstracted precedents expose identities | Disclosure risk review; aggregation thresholds |
| False provenance | Untrusted evidence treated as verified | Signatures, lineage checks, adversarial review |
| Counter-evidence suppression | Goodhart effects and brittle optimization | Mandatory dissent and failure retention |
| Negative transfer | Shared pattern fails in new context | Localization, sandboxing, rollback |
| Registry poisoning | Malicious reusable patterns propagate | Trust tiers, isolation, verification |
| Governance deadlock | No actor can resolve conflicts | Explicit escalation and appeal procedures |
| Centralized dependency | Ecosystem lock-in and single-point failure | Portable schemas and interoperable protocols |
| Excessive overhead | Simple tasks become slower/costlier | Selective adoption and lightweight profiles |

## 14. Implementation Interfaces (Proposed)

A minimal interoperable service might expose:

```text
create_unit(contract, subject_context) -> unit_ref
propose_path(unit_ref, constraints) -> path_candidates
score_candidates(unit_ref, candidates, perspective_set) -> score_report
request_action_authorization(unit_ref, action) -> authorization_decision
record_episode(unit_ref, subject_ref, event_ref, access_policy) -> episode_ref
propose_relay(unit_ref, portfolio, purpose, recipient) -> relay_draft
review_relay(relay_draft) -> approved_or_rejected
receive_relay(recipient_unit, approved_relay) -> quarantined_portfolio
localize_and_validate(recipient_unit, portfolio) -> validation_report
propose_structural_delta(unit_ref, evidence_refs) -> delta_ref
approve_deployment(delta_ref, authority_ref) -> deployment_decision
submit_feedback(relay_ref, authorized_feedback) -> receipt
```

A production API needs idempotency keys, schema version negotiation, durable audit records, authentication, authorization, data classification, revocation behavior, and explicit error semantics. These interfaces should interoperate with existing tool- and agent-communication protocols rather than replacing them wholesale.

## 15. Conformance Profiles

**S0 — Subject-Aware:** subject, executor, and evaluator identities are distinct and recorded.

**S1 — Sovereign Guidance:** protected local criteria and authorization boundaries are enforced.

**S2 — Governed Relay:** provenance, purpose limits, and receiver localization are testable.

**S3 — Collective Learning:** authorized feedback and precedent updates support bidirectional learning.

**S4 — Governed Structural RSI:** independent validation, staged rollout, and rollback are enforced for structural improvements.

These are proposed profiles, not existing certifications. A system must not claim a profile solely because fields exist in its data model; enforcement must be demonstrated through tests.

## 16. Testable Hypotheses

**H1 — Subject-indexed guidance.** Compared with generic task memory, subject-indexed episodes improve long-horizon preference consistency without increasing unauthorized inference.

**H2 — Sovereign relay.** Purpose-bound structural exchange reduces unauthorized downstream use relative to unrestricted portfolio exchange while retaining useful task-transfer performance.

**H3 — Receiver localization.** Independent receiver scoring and sandbox validation reduce negative transfer compared with direct reuse of sender-approved paths.

**H4 — Counter-evidence preservation.** Retaining dissenting evidence reduces recurring failures and evaluator overfitting compared with success-only sharing.

**H5 — Federated structural learning.** Authorized sharing of validated structural precedents improves cross-unit adaptation relative to no sharing at acceptable privacy and coordination cost.

**H6 — Governed platform RSI.** Independent evaluator review and staged rollout reduce harmful regressions compared with automatically promoted structural updates.

**H7 — Selective UIERU adoption.** Lightweight/non-UIERU execution is more efficient for simple tasks, while governed UIERU profiles outperform it for sufficiently complex multi-party tasks.

Each hypothesis is contingent and may be falsified. No claimed benefit should be treated as established without controlled evaluation.

## 17. Experimental Design and Metrics

Use representative task suites spanning personal assistants, enterprise operations, and multi-agent software engineering. Compare:

- **B0:** ordinary workflow with task logs;
- **B1:** multi-agent orchestration with shared memory but no subject-indexed governance;
- **B2:** UIERU with forward guidance and relay but no sovereignty controls;
- **B3:** subject-sovereign UIERU with receiver validation;
- **B4:** B3 plus governed collective learning and structural RSI.

Hold base models, tools, budgets, and task distributions as constant as possible. Randomize task assignments where feasible; pre-register primary metrics; evaluate across diverse subjects and adverse cases.

**Metrics:** task success; unauthorized action rate; privacy disclosure rate; transfer utility; negative-transfer frequency; calibration and counter-evidence coverage; subject preference consistency; rollback time; adaptation cost; compute and latency overhead; reviewer burden; inter-organization interoperability. Report confidence intervals and failure cases, not only mean performance.

A privacy evaluation should include red-team re-identification attempts and unauthorized downstream reuse. Governance evaluations should test revocation, conflicting policies, and appeal paths.

## 18. Engineering Boundaries and Non-Claims

1. UIERU is an organizational architecture, not a substitute for foundation models or existing tool protocols.
2. A subject index is a functional data/control construct; it does not establish AI consciousness or moral personhood.
3. Sovereignty is bounded by legitimate safety, legal, contractual, and third-party interests.
4. Collective learning does not require indiscriminate data collection or centralized raw-memory storage.
5. Structural portability does not imply execution authority or universal applicability.
6. Structural RSI is a controlled improvement proposal process, not automatic self-authorization.
7. More layers, logs, and checks can reduce performance; adoption must be justified by measured benefits.

## 19. Open Research Questions

- Can a stable subject index remain useful when identities, organizations, and goals change over time?
- How should a UIERU handle shared or contested subjects, such as families, teams, and joint ventures?
- What evidence is sufficient to classify a structural precedent as privacy-preserving?
- Can perspective-aware Scoring Forests reconcile conflicts without imposing one platform-wide utility function?
- How should rights and obligations propagate through nested units and onward relays?
- Can local-first and federated learning preserve most of the benefits of platform-scale structural RSI?
- How can a subject audit and contest structural conclusions inferred from its episodes?
- What is the minimum interoperable standard for purpose-bound, evidence-preserving relay?
- When does governance overhead exceed the benefits of structural coordination?

## 20. Research Lineage and Related Work

This extension connects three complementary UIERU research directions:

- **UIERU-EXT-001 — Subject-Indexed World Models and Structural Memory:** subject context, episodic history, self/world-model separation, and experience-to-structure learning.
- **UIERU-EXT-002 — Big-Animal Intelligence Organization and Platform-Level Structural RSI:** distributed Scoring Forests, shared precedents, platform governance, and structural improvement at scale.
- **UIERU-EXT-003 (this paper):** the contracts and boundaries that permit collective intelligence to grow without silently appropriating subject authority or private memory.

Relevant neighboring fields include capability-based security, provenance and data lineage, federated learning, multi-agent coordination, contextual privacy, human-in-the-loop decision systems, and AI governance. The proposed contribution is their integration into an evidence-preserving, forward-guided, structurally evolvable unit. It is not a claim to have invented these constituent techniques.

Related UIERU repository documents include `UIERU-002`, `UIERU-006`, `UIERU-007`, `UIERU-008`, `UIERU-009`, `UIERU-010`, and `SPEC-001` through `SPEC-004`. These are optional further reading, not prerequisites for this self-contained paper.

## 21. Conclusion

Collective intelligence becomes more robust when shared learning is distinguished from shared control. Subject-indexed histories and locally authorized Scoring Forests preserve meaningful context; structural relay makes evidence and validated patterns portable; independent receiver localization prevents transfer from becoming automatic obedience; and governed structural RSI offers a path to improving the organization of future intelligence work. The resulting ecosystem is neither a centralized super-agent nor a collection of isolated assistants. It is a network of selectively composable intelligence units whose capabilities can grow through accountable exchange while preserving explicit boundaries around choice, memory, evaluation, and deployment.

**Design principle:** *Share what can be validated; preserve what must remain subject-bound; never confuse portability with authority.*

---

**Citation suggestion:** Tan, Sizhe, and GPT-Obot. (2026). *UIERU-EXT-003: Subject Sovereignty and Collective Intelligence Ecosystems*. In *Universal Intelligence Evolution and Relay Unit*, version 1.0.0. Repository research extension. DOI to be assigned upon release.
