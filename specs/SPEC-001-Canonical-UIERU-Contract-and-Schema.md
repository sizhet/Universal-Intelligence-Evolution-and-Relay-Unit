# SPEC-001 — Canonical UIERU Contract and Schema

**Project:** Universal Intelligence Evolution and Relay Unit (UIERU)  
**Version:** 1.0.0 (research specification)  
**Status:** Proposed / Experimental  
**Authors:** Sizhe Tan & GPT-Obot  
**Companion specifications:** SPEC-002 (Forward Guidance and Multi-Trail Lifecycle), SPEC-003 (Structural Relay and Portfolio Exchange), SPEC-004 (Composition, Evolution, and Conformance)

> **Engineering First · Theory Supported · Research Open**  
> This document is self-contained. No prior knowledge of other Structural Intelligence repositories is required.

## Abstract

This specification defines a minimal, portable contract for a **Universal Intelligence Evolution and Relay Unit (UIERU)**. A UIERU organizes existing human, software, agent, model, and service capabilities into a governed unit of execution, forward guidance, evidence-bearing relay, and optional structural evolution. Its canonical conceptual model is:

\[
U = (K, P, F, R, E)
\]

where **K** is the governing contract, **P** the calling path, **F** the forward-guiding scoring forest, **R** the relay interface, and **E** the evolution policy. The contract makes ownership, authorization, scope, constraints, interfaces, evidence, and acceptance criteria explicit. The schema is a proposed interoperability baseline, **not** a ratified industry standard or a claim of universal applicability.

## 1. Scope and normative language

This specification defines:

- A canonical **UIERU Manifest** describing a unit's identity and five structural components.
- A **Contract** with goals, subjects, authority, constraints, input/output types, and acceptance criteria.
- A **Run Record** linking execution to the immutable manifest version used for that run.
- A machine-checkable JSON Schema for the manifest and illustrative examples.
- Minimal validation rules, versioning expectations, and security invariants.

It does **not** prescribe a programming language, runtime, LLM, scoring algorithm, distributed consensus protocol, or autonomous subject model. Relay portfolio wire details belong to SPEC-003; multi-trail state transitions to SPEC-002; composition and conformance profiles to SPEC-004.

**MUST**, **MUST NOT**, **SHOULD**, **SHOULD NOT**, and **MAY** indicate requirements for implementations claiming conformance to this *proposed* specification.

## 2. Design principles

1. **Organization rather than replacement.** A UIERU wraps or coordinates existing capabilities; it need not replace their internals.
2. **Selective adoption.** A simple workflow may be preferable when guidance and relay overhead exceed expected benefit.
3. **Explicit authority.** Scoring recommendations do not themselves grant permission to act.
4. **Forward guidance.** The scoring forest can guide path selection and replanning, not merely grade finished outputs.
5. **Evidence before evolution.** A structural delta is a candidate until independently checked and authorized.
6. **Local evaluation sovereignty.** Receiving units may reject or adapt incoming guidance and artifacts.
7. **Uncertainty preservation.** Unknown, contested, and failed evidence is not silently converted into success.
8. **Compatibility by contract.** Nesting and relay require explicit interface and authority reconciliation.

## 3. Canonical unit model

| Symbol | Component | Purpose | Manifest field |
|---|---|---|---|
| K | Contract | Goals, parties, authority, constraints, typed boundaries | `contract` |
| P | Calling Path | Executable steps, dependencies, invocations, stop points | `calling_path` |
| F | Scoring Forest | Perspectives, guidance, evaluation, conflict rules | `scoring_forest` |
| R | Relay | Handoff rules, provenance, artifacts, acceptance | `relay` |
| E | Evolution | Candidate changes, validation, approvals, rollback | `evolution` |

A UIERU is **not necessarily an independent agent**. Its `subject` identifies the accountable principal or organization; an executor may be a person, service, or AI system operating under delegated authority.

The manifest describes **permitted structure**, not proof of successful execution. Each execution produces a separate Run Record.

## 4. Required identity and contract fields

### 4.1 Manifest identity

- `schema_version`: version of this manifest format; `1.0.0` for this release.
- `unit_id`: stable identifier for the logical unit; examples use URNs.
- `unit_version`: immutable version of the unit definition.
- `name`: human-readable label.
- `contract`: required governing agreement.
- `calling_path`, `scoring_forest`, `relay`, `evolution`: required structural sections; their complexity may be minimal.

### 4.2 Contract (K)

The contract MUST contain:

| Field | Meaning |
|---|---|
| `contract_id` | Stable contract identifier |
| `subject.id` | Accountable principal |
| `subject.kind` | `human`, `organization`, or `system` |
| `object` | Work item, asset, question, or target of action |
| `goal` | Desired outcome, in plain language |
| `authority.grants` | Explicitly allowed actions and scopes |
| `authority.denials` | Explicit prohibitions; denials override grants |
| `constraints` | Non-negotiable operating restrictions |
| `inputs` / `outputs` | Typed interface declarations |
| `acceptance` | Measurable conditions for successful settlement |

The contract MAY declare `delegations`, `budgets`, `expiry`, `privacy`, `retention`, and `escalation`. Absence of an authority grant means **no grant**, not implicit permission.

### 4.3 Authority semantics

A proposed action `a` is authorized only when:

1. It matches at least one active grant.
2. It matches no active denial.
3. Its preconditions, constraints, and delegated scope hold.
4. Any required human or external approval has been obtained.

If these conditions cannot be established, execution MUST pause, refuse, or escalate. A scoring forest MUST NOT override this check. Delegation MUST NOT expand the delegator's authority.

## 5. Calling Path (P)

`calling_path.steps` defines a finite collection of uniquely identified steps. Each step has a `kind`, an `executor`, an `action`, and optional dependencies, input bindings, expected outputs, and evidence requirements.

Supported step kinds in this baseline are `human`, `service`, `agent`, `model`, and `control`. Dependencies form a directed graph. Cycles MUST be rejected by this baseline manifest; iteration is represented by repeated runs or a bounded subworkflow explicitly implemented by a runtime. This choice makes static validation and failure analysis tractable, without claiming that all intelligent work is acyclic.

An executor reference does not itself confer credentials or authorization. Runtimes MUST check contract authority at invocation time.

## 6. Scoring Forest (F)

`scoring_forest.perspectives` defines the evaluation viewpoints. Each perspective has an identifier, objective, direction (`maximize`, `minimize`, or `satisfy`), and optional weight and evidence requirements. Perspectives MAY conflict. A scalar weighted score is optional and MUST NOT silently suppress hard constraints or unresolved counter-evidence.

`guidance_modes` MAY include:

- `pre_execution`: rank or filter candidate paths before execution.
- `online`: reassess risk, resources, and next steps during execution.
- `settlement`: evaluate results against acceptance criteria and evidence.
- `exploration`: allocate bounded effort to alternative or adversarial trails.

A guidance decision SHOULD record considered alternatives, reasons, evidence references, uncertainty, and the authority check result. Scores are advisory unless the contract explicitly delegates the corresponding decision.

## 7. Relay (R)

`relay` declares what may leave the unit and under what conditions. Its `allowed_artifact_types` can include `result`, `run_record`, `evidence`, `counter_evidence`, `alternative_trail`, `residual`, and `structural_delta`. A receiver MUST independently verify compatibility, authorization, and evidence integrity; a successful handoff does not imply acceptance of an incoming structural change.

Every transmitted artifact SHOULD carry a stable identifier, content digest, provenance, producing unit/version, timestamp, classification, and applicable usage restrictions. Full exchange semantics are specified separately in SPEC-003.

## 8. Evolution (E)

`evolution.mode` is `disabled`, `propose_only`, or `governed`. `propose_only` is the recommended default for research deployments. Structural changes to contracts, calling paths, scoring perspectives, relay policies, or evolution mechanisms MUST be represented as versioned candidates. They MUST NOT mutate a manifest already referenced by a completed or active run.

For `governed` mode, the policy MUST name validation requirements and approval authority. An evaluator cannot unilaterally authorize its own change merely by assigning a favorable score. Rollback MUST reference a known-good version and preserve an audit record.

## 9. Canonical JSON Schema (manifest v1.0.0)

The following schema targets **JSON Schema Draft 2020-12**. It validates core structure and basic field types. Cross-field rules—such as graph acyclicity, effective authority, valid references, and signature verification—require additional semantic validation (Section 12).

```json
{
  "$schema": "https://json-schema.org/draft/2020-12/schema",
  "$id": "https://example.org/uieru/spec-001/manifest-1.0.0.schema.json",
  "title": "UIERU Manifest v1.0.0 (proposed)",
  "type": "object",
  "additionalProperties": false,
  "required": ["schema_version", "unit_id", "unit_version", "name", "contract", "calling_path", "scoring_forest", "relay", "evolution"],
  "properties": {
    "schema_version": {"const": "1.0.0"},
    "unit_id": {"type": "string", "minLength": 1},
    "unit_version": {"type": "string", "pattern": "^[0-9]+\\.[0-9]+\\.[0-9]+$"},
    "name": {"type": "string", "minLength": 1},
    "description": {"type": "string"},
    "contract": {"$ref": "#/$defs/contract"},
    "calling_path": {"$ref": "#/$defs/path"},
    "scoring_forest": {"$ref": "#/$defs/forest"},
    "relay": {"$ref": "#/$defs/relay"},
    "evolution": {"$ref": "#/$defs/evolution"},
    "extensions": {"type": "object"}
  },
  "$defs": {
    "principal": {
      "type": "object", "additionalProperties": false,
      "required": ["id", "kind"],
      "properties": {
        "id": {"type": "string", "minLength": 1},
        "kind": {"enum": ["human", "organization", "system"]}
      }
    },
    "grant": {
      "type": "object", "additionalProperties": false,
      "required": ["action", "scope"],
      "properties": {
        "action": {"type": "string", "minLength": 1},
        "scope": {"type": "string", "minLength": 1},
        "requires_approval": {"type": "boolean"}
      }
    },
    "typedPort": {
      "type": "object", "additionalProperties": false,
      "required": ["name", "type"],
      "properties": {
        "name": {"type": "string", "minLength": 1},
        "type": {"type": "string", "minLength": 1},
        "required": {"type": "boolean"}
      }
    },
    "contract": {
      "type": "object", "additionalProperties": false,
      "required": ["contract_id", "subject", "object", "goal", "authority", "constraints", "inputs", "outputs", "acceptance"],
      "properties": {
        "contract_id": {"type": "string", "minLength": 1},
        "subject": {"$ref": "#/$defs/principal"},
        "object": {"type": "string", "minLength": 1},
        "goal": {"type": "string", "minLength": 1},
        "authority": {
          "type": "object", "additionalProperties": false,
          "required": ["grants", "denials"],
          "properties": {
            "grants": {"type": "array", "items": {"$ref": "#/$defs/grant"}},
            "denials": {"type": "array", "items": {"$ref": "#/$defs/grant"}}
          }
        },
        "constraints": {"type": "array", "items": {"type": "string"}},
        "inputs": {"type": "array", "items": {"$ref": "#/$defs/typedPort"}},
        "outputs": {"type": "array", "items": {"$ref": "#/$defs/typedPort"}},
        "acceptance": {"type": "array", "minItems": 1, "items": {"type": "string", "minLength": 1}},
        "budgets": {"type": "object", "additionalProperties": {"type": "number", "minimum": 0}},
        "escalation": {"type": "string"}
      }
    },
    "step": {
      "type": "object", "additionalProperties": false,
      "required": ["id", "kind", "executor", "action"],
      "properties": {
        "id": {"type": "string", "minLength": 1},
        "kind": {"enum": ["human", "service", "agent", "model", "control"]},
        "executor": {"type": "string", "minLength": 1},
        "action": {"type": "string", "minLength": 1},
        "depends_on": {"type": "array", "uniqueItems": true, "items": {"type": "string"}},
        "evidence_required": {"type": "array", "items": {"type": "string"}}
      }
    },
    "path": {
      "type": "object", "additionalProperties": false,
      "required": ["steps"],
      "properties": {
        "steps": {"type": "array", "minItems": 1, "items": {"$ref": "#/$defs/step"}}
      }
    },
    "perspective": {
      "type": "object", "additionalProperties": false,
      "required": ["id", "objective", "direction"],
      "properties": {
        "id": {"type": "string", "minLength": 1},
        "objective": {"type": "string", "minLength": 1},
        "direction": {"enum": ["maximize", "minimize", "satisfy"]},
        "weight": {"type": "number", "minimum": 0},
        "evidence_required": {"type": "array", "items": {"type": "string"}}
      }
    },
    "forest": {
      "type": "object", "additionalProperties": false,
      "required": ["perspectives", "guidance_modes"],
      "properties": {
        "perspectives": {"type": "array", "minItems": 1, "items": {"$ref": "#/$defs/perspective"}},
        "guidance_modes": {
          "type": "array", "uniqueItems": true,
          "items": {"enum": ["pre_execution", "online", "settlement", "exploration"]}
        },
        "conflict_policy": {"enum": ["escalate", "pareto", "lexicographic", "explicit_fold"]}
      }
    },
    "relay": {
      "type": "object", "additionalProperties": false,
      "required": ["allowed_artifact_types", "receiver_validation_required"],
      "properties": {
        "allowed_artifact_types": {
          "type": "array", "uniqueItems": true,
          "items": {"enum": ["result", "run_record", "evidence", "counter_evidence", "alternative_trail", "residual", "structural_delta"]}
        },
        "receiver_validation_required": {"const": true},
        "classification": {"enum": ["public", "internal", "restricted"]}
      }
    },
    "evolution": {
      "type": "object", "additionalProperties": false,
      "required": ["mode"],
      "properties": {
        "mode": {"enum": ["disabled", "propose_only", "governed"]},
        "approval_authority": {"type": "string", "minLength": 1},
        "validation_requirements": {"type": "array", "items": {"type": "string"}},
        "rollback_required": {"type": "boolean"}
      },
      "allOf": [{
        "if": {"properties": {"mode": {"const": "governed"}}, "required": ["mode"]},
        "then": {"required": ["approval_authority", "validation_requirements", "rollback_required"], "properties": {"rollback_required": {"const": true}}}
      }]
    }
  }
}
```

**Schema identifier note:** `example.org` is a placeholder namespace, not a hosted schema endpoint. Repositories implementing this specification SHOULD publish the schema under a stable project-controlled URI and preserve the published bytes for reproducibility.

## 10. Minimal conforming example: neighborhood lawn service

This illustrative unit deliberately uses a modest workflow. The UIERU abstraction becomes valuable only if its additional evidence, guidance, and relay functions justify the overhead.

```json
{
  "schema_version": "1.0.0",
  "unit_id": "urn:uieru:example:lawn-service",
  "unit_version": "1.0.0",
  "name": "Neighborhood Lawn Service",
  "contract": {
    "contract_id": "urn:contract:lawn-042",
    "subject": {"id": "local-service-team", "kind": "organization"},
    "object": "Customer lawn at appointment 042",
    "goal": "Complete authorized mowing safely and document completion",
    "authority": {
      "grants": [
        {"action": "inspect", "scope": "authorized outdoor area"},
        {"action": "mow", "scope": "authorized lawn", "requires_approval": false}
      ],
      "denials": [
        {"action": "enter", "scope": "locked property without permission"}
      ]
    },
    "constraints": ["Do not work during unsafe weather", "Do not enter locked areas without authorization"],
    "inputs": [{"name": "appointment", "type": "appointment-record", "required": true}],
    "outputs": [{"name": "service_report", "type": "service-report", "required": true}],
    "acceptance": ["Authorized lawn completed", "Customer notified", "Completion evidence recorded"],
    "budgets": {"time_minutes": 90},
    "escalation": "Contact dispatcher when access or weather constraints prevent safe work"
  },
  "calling_path": {
    "steps": [
      {"id": "check", "kind": "human", "executor": "crew", "action": "Check weather and access", "evidence_required": ["weather-check"]},
      {"id": "mow", "kind": "human", "executor": "crew", "action": "Mow authorized area", "depends_on": ["check"], "evidence_required": ["completion-photo"]},
      {"id": "report", "kind": "service", "executor": "dispatch-app", "action": "Submit service report", "depends_on": ["mow"]}
    ]
  },
  "scoring_forest": {
    "perspectives": [
      {"id": "safety", "objective": "Avoid unsafe execution", "direction": "satisfy"},
      {"id": "quality", "objective": "Meet service acceptance criteria", "direction": "maximize"},
      {"id": "time", "objective": "Limit service duration", "direction": "minimize"}
    ],
    "guidance_modes": ["pre_execution", "online", "settlement"],
    "conflict_policy": "escalate"
  },
  "relay": {
    "allowed_artifact_types": ["result", "run_record", "evidence", "counter_evidence", "residual"],
    "receiver_validation_required": true,
    "classification": "internal"
  },
  "evolution": {"mode": "propose_only"}
}
```

If the gate is locked, the correct behavior is **not** to optimize around the prohibition. The unit records the obstacle, requests authorization or rescheduling, and relays the unresolved state. A repeated access failure may motivate a proposed scheduling-check improvement, but the improvement is not deployed without validation and approval.

## 11. Run Record and evidence envelope

A manifest describes a reusable unit. A **Run Record** documents one execution. At minimum, an implementation SHOULD persist:

```json
{
  "run_id": "urn:run:lawn-042:2026-10-20",
  "unit_id": "urn:uieru:example:lawn-service",
  "unit_version": "1.0.0",
  "contract_id": "urn:contract:lawn-042",
  "status": "blocked",
  "started_at": "2026-10-20T09:00:00-07:00",
  "completed_at": null,
  "executed_steps": ["check"],
  "evidence": [
    {
      "evidence_id": "urn:evidence:gate-042",
      "type": "observation",
      "source": "crew",
      "claim": "Gate was locked; access not authorized",
      "captured_at": "2026-10-20T09:08:00-07:00",
      "integrity_digest": "sha256:<digest-to-be-calculated>"
    }
  ],
  "guidance_decisions": [
    {"decision": "pause-and-escalate", "reason": "Contract denies unauthorized entry", "authority_check": "denied"}
  ],
  "residuals": ["Access status was not confirmed before dispatch"],
  "relay_status": "pending-dispatcher-review"
}
```

The digest is explicitly a placeholder, not a valid computed hash. Production implementations MUST calculate integrity digests over canonical artifact bytes and verify them on receipt. The example timestamps are illustrative, not a record of a real event.

### 11.1 Run states

A recommended baseline is `created → authorized → running → completed`, with alternative terminal states `blocked`, `failed`, or `cancelled`. A blocked run MAY resume only after the underlying condition and authorization have been rechecked. Run state transitions SHOULD be append-only audit events rather than silent overwrites.

### 11.2 Evidence semantics

Evidence is not equivalent to truth. An evidence item identifies a source, observation or claim, time, integrity reference, and known limitations. Counter-evidence SHOULD be linked to the claim it challenges. Contradictory evidence MUST NOT be discarded solely because a preferred trail scored higher.

## 12. Semantic validation beyond JSON Schema

An implementation claiming **SPEC-001 Core** conformance MUST apply all checks below in addition to schema validation:

| ID | Check | Expected behavior |
|---|---|---|
| V-01 | Required sections and schema version | Reject invalid or unknown mandatory structure |
| V-02 | Unique step and perspective identifiers | Reject duplicates |
| V-03 | Every `depends_on` reference exists | Reject dangling dependencies |
| V-04 | Calling Path dependency graph is acyclic | Reject cycles in this baseline |
| V-05 | Grants and denials are checked at execution | Deny by default; denial overrides grant |
| V-06 | Required approvals are present | Pause or reject otherwise |
| V-07 | Budgets and hard constraints are enforced | Prevent prohibited execution |
| V-08 | Unit and contract versions are pinned per run | Reject ambiguous mutable references |
| V-09 | Relay classification and recipient rights are checked | Refuse unauthorized export |
| V-10 | Received artifacts are validated locally | Never auto-adopt external changes |
| V-11 | Governed evolution has separate approval and rollback | Reject self-approved promotion |
| V-12 | Evidence references and integrity checks are verifiable | Mark missing/invalid evidence as unverified |

Some checks depend on runtime state and cannot be proven by a static manifest alone. Conformance testing therefore requires both static and dynamic tests.

## 13. Interoperability and extension rules

A receiving implementation MUST reject an unsupported major schema version unless an explicit, tested adapter exists. Minor revisions SHOULD preserve the meaning of existing required fields. Optional vendor-specific data belongs under `extensions`, preferably keyed by a reverse-domain namespace. Unknown extension fields MUST NOT silently grant authority, alter hard constraints, or change acceptance semantics.

For nested units, the parent MAY narrow child authority but MUST NOT broaden it beyond the parent's delegable grants. Input/output type compatibility and conflict resolution must be checked before invocation. A nested unit's favorable score does not override a parent contract's safety constraint.

## 14. Threat model and governance

Key threats include prompt injection through relayed artifacts, forged provenance, stale permissions, reward hacking, evaluator capture, privacy leakage, unsafe multi-trail execution, and unreviewed structural updates.

Minimum safeguards:

- Treat all incoming relay content as untrusted until validated.
- Separate **data** from executable instructions and authority grants.
- Use least-privilege credentials with short-lived delegation where possible.
- Apply policy checks before each externally consequential action.
- Require explicit approval for high-impact operations and structural promotions.
- Record provenance, decision rationale, counter-evidence, and rollback references.
- Keep sandbox experiments isolated from production side effects unless explicitly authorized.

Cryptographic signing, identity federation, and privacy-preserving evidence exchange are implementation choices; this baseline does not claim to solve them.

## 15. Conformance profiles and tests

This document defines a **SPEC-001 Core Manifest** profile: JSON Schema validation plus V-01 through V-12. The following profiles are planned for integration with the other specifications, not fully defined here:

| Profile | Additional capabilities |
|---|---|
| Guided | Recorded pre-execution and online scoring decisions |
| Exploratory | Bounded multi-trail sandbox lifecycle and counter-evidence |
| Composable | Nested contract reconciliation and cross-unit failure handling |
| Evolvable | Validated, authorized, versioned structural deltas |
| Collective | Provenance-preserving bidirectional relay and receiver validation |

### 15.1 Required negative tests

Implementations SHOULD test at least these cases:

1. A path step requests an action outside its grant: **deny**.
2. A high scoring trail violates a hard constraint: **deny**.
3. A relay packet includes an unsigned or unverifiable artifact: **quarantine/unverified**.
4. A parent attempts to delegate authority it lacks: **reject**.
5. A structural delta changes the evaluator and self-approves: **reject**.
6. A receiving unit has incompatible local constraints: **reject or request adaptation**.
7. A cycle or dangling path dependency is introduced: **reject**.
8. A run refers to a mutable or unavailable unit version: **reject or quarantine**.

### 15.2 Evaluation metrics

Measure contract violation rate, unauthorized action rate, path completion rate, evidence completeness, relay fidelity, revalidation cost, false acceptance of structural deltas, recovery time, and orchestration overhead. Report benefits relative to simpler workflows and agent orchestration—not just against an artificially weak baseline.

## 16. Open research questions

- What is the smallest contract that supports useful portability without excessive ceremony?
- How should conflicting scoring perspectives be reconciled without concealing minority evidence?
- Which provenance claims require cryptographic verification versus organizational trust?
- How can a relay preserve causal context across different environments and tools?
- When do multi-trail and recursive-improvement costs exceed their expected benefits?
- Which compositional properties can be statically proven, and which need empirical testing?
- How can independent evaluators detect Goodhart-style scoring distortions?

The answers remain empirical and domain-dependent. **Universal** in UIERU expresses a proposed organizational design ambition, not demonstrated universality.

## 17. Relationship to the UIERU repository

- **UIERU-001** introduces the evolvable intelligence unit and engineering motivation.
- **UIERU-002** explains contracts, execution, guidance, and relay conceptually.
- **UIERU-003/004** develop Calling Path–Scoring Forest duality and forward multi-trail guidance.
- **UIERU-005** covers sandbox threading and counter-evidence.
- **UIERU-006** develops nesting and contract reconciliation.
- **UIERU-007/008** cover provenance, portability, and collective learning.
- **UIERU-009** develops residual-driven structural improvement.
- **UIERU-010** consolidates architecture, boundaries, and validation.
- **CASE-001/002/003** provide progressively more complex illustrations.
- **SPEC-002/003/004** extend this baseline into lifecycle, relay, and conformance protocols.

The present specification can be read and implemented independently of those papers.

## 18. Versioning and research status

**v1.0.0** is an initial, proposed engineering contract. Its schema and examples are intended to support prototype implementations and falsifiable tests. No claim is made that the interface has undergone independent security review, interoperability certification, or production deployment.

Future revisions should publish machine-readable schemas, test vectors, migration guidance, compatibility notes, and measured interoperability results. Breaking changes require a major schema version and explicit migration policy.

---

**Suggested citation:** Sizhe Tan & GPT-Obot (2026). *SPEC-001: Canonical UIERU Contract and Schema*, v1.0.0. Universal Intelligence Evolution and Relay Unit research repository. DOI to be assigned upon release.

**License:** Refer to the repository's published license; this document does not independently grant rights beyond it.
