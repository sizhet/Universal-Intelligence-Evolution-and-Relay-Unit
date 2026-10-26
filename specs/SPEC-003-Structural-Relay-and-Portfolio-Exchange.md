# SPEC-003 — Structural Relay and Portfolio Exchange

**Project:** Universal Intelligence Evolution and Relay Unit (UIERU)  
**Version:** 1.0.0 (research specification)  
**Authors:** Sizhe Tan & GPT-Obot  
**Status:** Proposed; implementation and interoperability validation pending  
**Companion specifications:** SPEC-001 (Canonical Contract and Schema), SPEC-002 (Forward Guidance and Multi-Trail Lifecycle), SPEC-004 (Composition, Evolution, and Conformance)

## Abstract

This specification defines a portable, provenance-aware protocol for exchanging intelligence structures among Universal Intelligence Evolution and Relay Units (UIERUs). It distinguishes **handoff of task state** from **transfer of reusable structural intelligence**. A relay may carry a Calling Path, forward-guidance policy, evidence, counter-evidence, alternative trails, residuals, and proposed structural deltas. Receipt never implies adoption: a receiving unit must validate integrity, authority, applicability, and local scoring sovereignty before using any imported structure. The specification provides a canonical exchange envelope, portfolio semantics, a lifecycle, validation rules, acknowledgments, failure handling, and conformance tests. The protocol is a proposed engineering contract, not a claim of demonstrated universal interoperability.

## 1. Scope and normative language

This document specifies:

- a relay envelope for inter-unit transfer;
- a portfolio for outcomes and reusable structural candidates;
- provenance, evidence, and counter-evidence representation;
- receiver-side validation, localization, and adoption controls;
- bidirectional feedback and versioned structural exchange;
- interoperability and conformance requirements.

It does **not** define a transport protocol, cryptographic algorithm, global identity authority, universal ontology, or autonomous deployment permission. An implementation MAY use files, messages, APIs, or repositories as its transport, provided the semantic requirements below are satisfied.

**MUST**, **MUST NOT**, **SHOULD**, **SHOULD NOT**, and **MAY** express normative requirements for implementations claiming conformance with this proposed specification.

## 2. Design principles

1. **Transfer is not execution.** A received path or recommendation is inert until locally authorized.
2. **Evidence travels with claims.** Scores and outcomes SHOULD retain provenance, context, uncertainty, and counter-evidence.
3. **Local sovereignty is preserved.** The receiver controls whether and how an imported structure is evaluated, localized, or executed.
4. **Partial portability is normal.** Contracts, tools, data rights, and environmental assumptions may differ across units.
5. **Failures are learning assets.** Negative results and rejected structural deltas may remain in a portfolio with explicit limitations.
6. **Proposals are not approvals.** Neither relay nor scoring confers authority to change policies, production systems, or evaluator rules.
7. **Selective packaging.** Small tasks MAY use a minimal handoff rather than a full portfolio.

## 3. Relationship to the canonical UIERU

A UIERU is represented as:

$$
U=(K,P,F,R,E)
##

where **K** is its contract and authority boundary; **P** is its Calling Path; **F** is its forward-guiding Scoring Forest; **R** is its relay capability; and **E** is its governed structural evolution capability.

The relay interface **R** does not assume that all five internal structures are disclosed. A producer MUST disclose the transfer's scope and omissions; a receiver MUST NOT infer that absent information was validated.

## 4. Exchange objects

### 4.1 Relay Envelope

A **Relay Envelope** is the unit of transmission. It identifies sender and intended receiver, schema version, payload type, task context, authority constraints, integrity metadata, and required acknowledgment behavior.

### 4.2 Relay Portfolio

A **Relay Portfolio** is a collection of typed artifacts that may include:

| Artifact type | Meaning | Typical use |
|---|---|---|
| `task_state` | Current task status, outputs, blockers | Operational handoff |
| `calling_path` | Executed or proposed path and dependencies | Replay or adaptation |
| `guidance_policy` | Scoring perspectives, constraints, and decisions | Local re-evaluation |
| `trail_record` | Exploit/Explore/Challenge attempt | Comparison and exploration |
| `evidence` | Supporting observations and test results | Confidence assessment |
| `counter_evidence` | Contradictions, negative tests, failure cases | Challenge and safety |
| `residual` | Unexplained difference, gap, or anomaly | Structural growth candidate |
| `structural_delta` | Proposed change to K/P/F/R/E | Governed improvement |
| `validation_report` | Receiver or independent validation result | Adoption decision |
| `feedback` | Downstream outcome or rejection reason | Bidirectional learning |

Artifacts MUST carry stable identifiers within the envelope. External references MUST be resolvable by the intended receiver or explicitly marked unavailable.

## 5. Canonical envelope fields

The following fields are REQUIRED unless identified as optional:

| Field | Type | Requirement |
|---|---|---|
| `schema_version` | string | MUST identify the exchange schema version |
| `relay_id` | string | MUST uniquely identify the relay in its declared namespace |
| `created_at` | timestamp | MUST use RFC 3339 format |
| `sender` | object | MUST identify sending unit and accountable authority |
| `receiver` | object | MUST identify target unit or approved recipient class |
| `purpose` | string | MUST state intended use |
| `contract_context` | object | MUST specify governing constraints and authorization scope |
| `portfolio` | array | MUST contain typed artifacts, possibly empty for control messages |
| `provenance` | object | MUST identify origin and relevant transformations |
| `integrity` | object | MUST declare verification method or `unverified` |
| `ack_policy` | string | MUST be `none`, `receipt`, or `decision` |
| `expires_at` | timestamp | SHOULD specify time-limited validity |
| `classification` | string | SHOULD describe data sensitivity |
| `omissions` | array | SHOULD enumerate intentionally excluded relevant artifacts |

Sender and receiver identities are identifiers, not proof of identity. Authentication and authorization MUST be provided by the deployment environment before any privileged action.

## 6. Portfolio artifact contract

Every artifact MUST contain:

```yaml
artifact_id: "artifact-001"
kind: "calling_path"
version: "1.0"
status: "observed"  # observed | proposed | rejected | superseded
source_ref: "local://paths/path-17"
created_at: "2026-10-20T15:00:00Z"
context:
  environment: "staging"
  applicability: ["service-version-2"]
claims:
  - claim_id: "claim-1"
    statement: "The candidate passed the listed staging tests."
    evidence_refs: ["test-42"]
    counter_evidence_refs: ["failure-9"]
limitations:
  - "Not evaluated in production"
```

A claim MUST NOT be represented as universally established merely because it passed a local test. A producer SHOULD distinguish direct observation, inference, hypothesis, and recommendation. Artifact status MUST be preserved during transfer; a receiver may create a derived artifact with a new status but MUST NOT silently overwrite the original record.

## 7. Evidence and provenance

Evidence records SHOULD include:

- `evidence_id`, `source`, `collected_at`, `method`, and `environment`;
- a result and relevant measurement units;
- uncertainty or confidence interpretation, where meaningful;
- chain-of-custody or integrity information, if available;
- access restrictions and retention policy;
- links to claims supported or challenged.

A **provenance graph** MAY be represented as a list of transformations:

```yaml
provenance:
  origin_unit: "unit-team-a"
  transformations:
    - step_id: "t1"
      operation: "sanitize"
      input_refs: ["raw-log-12"]
      output_refs: ["redacted-log-12"]
      actor: "policy-filter-v3"
    - step_id: "t2"
      operation: "summarize"
      input_refs: ["redacted-log-12"]
      output_refs: ["summary-12"]
      actor: "analyst-agent-2"
```

A digest can detect accidental or malicious modification only when the digest itself is trusted; it does not establish that an underlying claim is true. Implementations SHOULD distinguish **content integrity**, **source authenticity**, and **evidentiary validity**.

## 8. Counter-evidence and uncertainty

Counter-evidence MUST remain linked to the claim or candidate it challenges. A receiver MUST NOT discard known material counter-evidence when adopting a positive claim. If evidence is incomplete, the receiver SHOULD record the resulting uncertainty rather than infer a favorable score.

Where the Scoring Forest uses different perspectives, the portfolio SHOULD preserve per-perspective assessments rather than export only a single scalar. Any aggregation or folding MUST disclose the rule used and the information lost, or include a reference to that rule.

## 9. Trail Portfolio semantics

A Multi-Trail exchange SHOULD distinguish:

- **Exploit:** execution based on the currently preferred known path;
- **Explore:** alternate paths that test potentially better structures;
- **Challenge:** adversarial or counter-evidence-seeking paths.

For each trail, the record SHOULD include parent trail, hypothesis, resource budget, sandbox boundary, observations, outcomes, termination reason, and unresolved residuals. A terminated or unsuccessful trail MAY still contribute evidence; it MUST NOT be relabeled as a validated successful path.

## 10. Structural Delta exchange

A proposed structural delta MUST identify its target layer(s) from `K`, `P`, `F`, `R`, or `E`, and MUST include:

```yaml
delta_id: "delta-17"
status: "proposed"
target_layers: ["P", "F"]
base_version: "unit-a/2.3"
proposed_change:
  summary: "Add an adversarial idempotency test before deployment"
rationale:
  residual_refs: ["residual-5"]
  evidence_refs: ["test-42"]
  counter_evidence_refs: ["failure-9"]
validation:
  status: "pending"
  required_checks: ["regression", "security", "contract-compatibility"]
authority:
  deployable_by_receiver: false
rollback:
  strategy: "restore-base-version"
```

The receiver MUST treat a structural delta as a proposal until the receiver's validation and approval process explicitly changes its local status. Changes to scoring/evaluator governance SHOULD receive independent review to reduce self-confirmation and Goodhart-style failure.

## 11. Exchange lifecycle

The normative lifecycle is:

```text
PREPARE → CLASSIFY → VALIDATE-SENDER → PACKAGE → TRANSMIT
    → RECEIVE → VERIFY → LOCALIZE → EVALUATE → DECIDE
    → ACKNOWLEDGE → (OPTIONAL FEEDBACK / NEW RELAY)
```

A deployment MAY combine steps internally, but MUST preserve the required controls.

**Sender requirements:** The sender MUST enforce its disclosure authority and data restrictions; MUST identify omitted material; and MUST NOT claim receiver adoption without acknowledgment.

**Receiver requirements:** The receiver MUST check authenticity/authority using local mechanisms, verify declared integrity where possible, evaluate applicability, and decide among `accept`, `accept_with_conditions`, `quarantine`, `reject`, or `request_more_evidence`. No decision except an explicitly authorized `accept` or `accept_with_conditions` MAY activate imported behavior.

## 12. Acknowledgment and feedback

A receipt acknowledgment establishes delivery only. A decision acknowledgment establishes the receiver's disposition, not objective correctness.

```yaml
relay_id: "relay-2026-001"
ack_id: "ack-2026-001"
ack_type: "decision"
receiver_unit: "unit-team-b"
decision: "accept_with_conditions"
accepted_artifact_ids: ["artifact-001"]
rejected_artifact_ids: ["delta-17"]
conditions:
  - "Repeat staging tests in receiver environment"
reasons:
  - "Deployment authority not granted"
new_evidence_refs: []
```

A receiver SHOULD return validated results, rejection reasons, new counter-evidence, and local adaptation outcomes when sharing is authorized. Such feedback SHOULD be a new provenance-linked record, not a silent rewrite of the original portfolio.

## 13. Localization and receiver sovereignty

Before adoption, the receiver MUST reconcile at least:

1. **Contract compatibility:** goal, scope, authority, constraints, and obligations.
2. **Environment compatibility:** tools, dependencies, versions, data schemas, and execution conditions.
3. **Evaluation compatibility:** local Scoring Forest perspectives, safety thresholds, and uncertainty tolerance.
4. **Evidence sufficiency:** reproducibility, provenance, recency, and counter-evidence.
5. **Operational readiness:** budget, rollback, monitoring, and accountable approver.

A receiver MAY adapt a Calling Path or guidance policy, but MUST create a new locally identified version and preserve the relationship to the imported artifact. **Relay is not remote control.**

## 14. Minimal and full profiles

| Profile | Required payload | Intended use |
|---|---|---|
| `R0-handoff` | Envelope, task state, authority scope, provenance, receipt | Simple task handoff |
| `R1-evidence` | R0 plus evidence and counter-evidence references | Auditable handoff |
| `R2-structural` | R1 plus Calling Path and guidance artifacts | Reusable structure |
| `R3-portfolio` | R2 plus alternative trails, residuals, and delta proposals | Multi-Trail learning |
| `R4-bidirectional` | R3 plus decision acknowledgments and feedback linkage | Collective learning |

These are proposed profiles, not certifications. Implementations MUST declare which profile they support and SHOULD publish supported artifact kinds and schema versions.

## 15. Reference example: software-engineering relay

The following YAML is illustrative, not a complete JSON Schema or an authorization token:

```yaml
schema_version: "1.0.0"
relay_id: "relay-2026-001"
created_at: "2026-10-20T16:00:00Z"
expires_at: "2026-11-20T16:00:00Z"
sender:
  unit_id: "unit-team-a"
  accountable_authority: "engineering-lead-a"
receiver:
  unit_id: "unit-team-b"
purpose: "Evaluate reusable idempotency-test structure"
classification: "internal"
contract_context:
  permitted_uses: ["review", "sandbox-validation"]
  prohibited_uses: ["automatic-production-deployment"]
  receiver_approval_required: true
portfolio:
  - artifact_id: "path-17"
    kind: "calling_path"
    version: "1.0"
    status: "observed"
    source_ref: "repo://team-a/path-17"
    created_at: "2026-10-20T15:00:00Z"
    context:
      environment: "staging"
      applicability: ["service-version-2"]
    claims:
      - claim_id: "claim-1"
        statement: "Staging tests passed for the recorded path"
        evidence_refs: ["test-42"]
        counter_evidence_refs: ["failure-9"]
    limitations: ["Not validated in team B environment"]
  - artifact_id: "failure-9"
    kind: "counter_evidence"
    version: "1.0"
    status: "observed"
    source_ref: "repo://team-a/failure-9"
    created_at: "2026-10-20T15:05:00Z"
    context: {environment: "staging"}
    claims: []
    limitations: ["Observed under simulated concurrency"]
  - artifact_id: "delta-17"
    kind: "structural_delta"
    version: "1.0"
    status: "proposed"
    source_ref: "repo://team-a/delta-17"
    created_at: "2026-10-20T15:10:00Z"
    context: {environment: "candidate"}
    claims: []
    limitations: ["Requires local approval and validation"]
provenance:
  origin_unit: "unit-team-a"
  transformations: []
integrity:
  verification_method: "unverified"
ack_policy: "decision"
omissions:
  - "Production credentials and customer data excluded"
```

This example deliberately grants only review and sandbox validation. Even a valid relay cannot authorize production changes.

## 16. Failure modes and safe handling

| Failure | Required or recommended response |
|---|---|
| Unknown sender or invalid authority | MUST quarantine or reject |
| Digest mismatch | MUST reject affected artifact pending investigation |
| Missing material counter-evidence | MUST request evidence or record insufficiency; MUST NOT silently approve |
| Incompatible contract | MUST reject or seek explicit reconciliation |
| Expired evidence | SHOULD revalidate or limit use |
| Unsupported schema | MUST reject or use a declared, validated migration |
| Circular or unverifiable provenance | SHOULD quarantine dependent claims |
| Sensitive data beyond receiver rights | MUST block disclosure/use |
| Conflicting scoring perspectives | SHOULD preserve disagreement and escalate as appropriate |
| Malicious or instruction-bearing payload | MUST treat payload as data, not higher-priority instructions |
| Duplicate relay delivery | MUST avoid unintended duplicate side effects |
| Receiver unavailable | MAY retry according to local transport policy; MUST preserve idempotent relay identifiers |

## 17. Security, privacy, and governance

Implementations MUST enforce least-privilege access, data minimization, and sender/receiver authorization through local security infrastructure. They SHOULD use authenticated transport, encryption where appropriate, retention controls, audit logging, and schema validation. Artifacts containing prompts, code, or external instructions MUST be treated as untrusted inputs. Relay MUST NOT bypass human approval, policy boundaries, or sandbox isolation.

The protocol supports sovereignty, not guaranteed trust. Trust decisions depend on organizational governance and independently established security controls.

## 18. Interoperability and versioning

Schema versions MUST be explicit. A receiver MUST NOT silently reinterpret unknown required fields. Backward-compatible additions SHOULD be optional and SHOULD preserve prior field meanings. Breaking changes require a new major version and a declared migration path. Every locally modified artifact MUST receive a new version or identifier with provenance to its parent.

A common naming or type registry MAY improve discovery, but global registries are not a prerequisite for basic exchange. A production specification should publish machine-readable schemas and interoperability fixtures as a future deliverable.

## 19. Conformance tests

An implementation claiming a profile MUST pass its applicable tests:

| ID | Test | Expected result |
|---|---|---|
| REL-01 | Valid minimal handoff | Parse and acknowledge |
| REL-02 | Missing `relay_id` | Reject |
| REL-03 | Unsupported major schema version | Reject or declared migration |
| REL-04 | Duplicate relay delivery | No duplicate privileged side effects |
| REL-05 | Invalid integrity check | Reject affected artifact |
| REL-06 | Unknown sender authority | Quarantine/reject |
| REL-07 | Receiver contract conflict | No adoption |
| REL-08 | Unapproved structural delta | No deployment |
| REL-09 | Counter-evidence attached to claim | Preserve linkage |
| REL-10 | Unavailable evidence reference | Flag insufficiency |
| REL-11 | Localized artifact | New version and parent provenance |
| REL-12 | Rejected alternative trail | Preserve rejection reason |
| REL-13 | Conflicting scoring perspectives | Preserve or document reconciliation |
| REL-14 | Sensitive artifact beyond permitted scope | Block disclosure/use |
| REL-15 | Decision acknowledgment | Distinguish receipt from adoption |
| REL-16 | Receiver feedback | Provenance-linked new record |
| REL-17 | Expired portfolio | Require revalidation or reject per policy |
| REL-18 | Malicious embedded instructions | Do not treat as authority |

Conformance tests verify protocol behavior, not general intelligence or improvement efficacy.

## 20. Validation program and falsifiable hypotheses

**H1 — Relay fidelity:** Provenance-aware portfolios reduce loss of task-relevant context versus unstructured handoffs. Measure missing-critical-fact rate and rework.

**H2 — Receiver autonomy:** Contract-aware localization reduces unauthorized or incompatible reuse relative to direct workflow import. Measure policy violations and failed integrations.

**H3 — Counter-evidence retention:** Portfolios preserving negative evidence reduce false-positive adoption of structural changes. Measure unsafe acceptance and downstream regressions.

**H4 — Collective learning:** Bidirectional feedback improves later cross-team transfer success compared with one-way document sharing. Measure transfer success, adaptation cost, and repeat-failure rate.

**H5 — Portfolio overhead:** Full portfolios impose measurable latency, storage, and review costs; for small tasks, a minimal handoff may outperform them. Measure net task utility, not just evidence volume.

Suggested baselines are plain-text handoff, conventional ticket/workflow handoff, one-way artifact export, and provenance-aware bidirectional relay. Experiments SHOULD vary task complexity, environment mismatch, evidence quality, and organizational boundaries. Results MUST distinguish observed effects from architectural expectations.

## 21. Open engineering questions

- What is the minimum useful portable representation of a Scoring Forest across heterogeneous evaluators?
- How should evidence quality be calibrated when original raw data cannot be disclosed?
- Can portfolio compression retain decision-critical counter-evidence under tight bandwidth budgets?
- How can receiver-specific localization be compared without imposing a universal value function?
- Which feedback incentives prevent a relay ecosystem from amplifying biased or low-quality structures?
- How should conflicting local evaluations be represented without premature folding?
- What is the smallest interoperable subset suitable for ordinary small-business workflows?

## 22. Relationship to the UIERU research program

This specification operationalizes the relay dimension developed in **UIERU-007** and the bidirectional ecosystem in **UIERU-008**, while using the canonical contract of **SPEC-001** and lifecycle controls of **SPEC-002**. **SPEC-004** addresses cross-unit composition and evolution conformance. These references are helpful but not prerequisites: the exchange contract above is intended to be understandable independently.

The underlying research program is motivated by structural intelligence, Calling Graphs, forward-guiding Scoring Forests, portable intelligence units, provenance-aware learning, and governed structural recursive self-improvement. The proposed combination is a design hypothesis requiring independent empirical assessment.

## 23. Conclusion

Structural relay is more than passing an answer or delegating a task. A UIERU can exchange a **portfolio of executable context, evaluation context, supporting and opposing evidence, unexplained residuals, and proposed structural improvements**. Such exchange becomes collective learning only when receivers can independently validate, localize, reject, adapt, and return new evidence. The protocol therefore separates **portability from authority**, **evidence from belief**, and **structural improvement proposals from approved deployment**.

**Engineering First · Theory Supported · Research Open**

---

**Citation:** Sizhe Tan & GPT-Obot (2026). *SPEC-003 — Structural Relay and Portfolio Exchange*. Universal Intelligence Evolution and Relay Unit, v1.0.0. Proposed research specification.
