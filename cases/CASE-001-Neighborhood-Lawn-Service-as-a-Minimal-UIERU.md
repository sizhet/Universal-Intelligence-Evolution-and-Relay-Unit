# CASE-001 — Neighborhood Lawn Service as a Minimal UIERU

**Project:** Universal Intelligence Evolution and Relay Unit (UIERU)  
**Version:** 1.0.0  
**Authors:** Sizhe Tan & GPT-Obot  
**Document type:** Engineering case study  
**Status:** Reference design and illustrative scenario; not an empirical performance claim

## Abstract

This case demonstrates a Universal Intelligence Evolution and Relay Unit (UIERU) through an ordinary neighborhood lawn-mowing service. The point is not to automate a small business or require artificial intelligence for a simple job. It is to show how an existing task can be organized as a reusable, guided, evidence-producing, and transferable intelligence unit. A customer request becomes an explicit contract; a calling path coordinates human and software actions; a small scoring structure guides choices before and during execution; a relay package preserves results and unresolved issues; and an evolution loop proposes improvements without silently changing the operating procedure. The case also identifies when the UIERU overhead is unjustified.

**Central principle:** UIERU is an organizational wrapper around existing capabilities, not a replacement for the worker, the customer, or their decision authority.

## 1. Why a lawn service?

A lawn service has a concrete objective, a visible execution path, meaningful constraints, observable results, and repeated work. It can be understood without prior familiarity with Structural Intelligence, SPO-SI, Scoring Forests, or Calling Graph theory. It also makes an important distinction clear: a *minimal* UIERU can be mostly human-operated, with a paper checklist or spreadsheet rather than an autonomous agent.

A homeowner requests mowing and edging for a small yard before the weekend. The service provider must confirm the property, agree on price and scope, check the weather, bring appropriate equipment, complete the work safely, and report completion. An ordinary checklist may already handle most of this. UIERU adds explicit guidance, portable evidence, and controlled improvement **only where their value exceeds their cost**.

## 2. The scenario and assumptions

The following values are illustrative, not market estimates.

| Attribute | Illustrative value |
|---|---|
| Customer request | Mow and edge a residential lawn |
| Proposed service window | Friday, 9:00–11:00 a.m. |
| Quoted price | $55, subject to customer acceptance |
| Site condition | Small yard; gate access must be confirmed |
| Provider | One human operator using a mower and trimmer |
| Tools | Phone, checklist, weather forecast, calendar, equipment |
| Success | Agreed scope completed safely, with customer confirmation |
| Important constraints | Weather, equipment safety, access, property protection, customer approval |

The operator retains authority over safety decisions and whether to perform the job. The customer retains authority over scope changes and payment. No autonomous component may expand the contract without appropriate approval.

## 3. The minimal UIERU structure

We use the canonical notation:

$$
U = (K, P, F, R, E)
$$

- **K — Contract:** who requests the work, what is authorized, goals, constraints, and acceptance criteria.
- **P — Calling Path:** the sequence of human and software actions needed to deliver the service.
- **F — Scoring Forest:** a compact, forward-guiding evaluation structure that helps choose and revise actions.
- **R — Relay:** a handoff record of execution, evidence, exceptions, and reusable knowledge.
- **E — Evolution:** a governed process for proposing and validating better procedures.

In this example, the Scoring Forest may be a few rules and a decision table. The term *forest* denotes the ability to represent multiple perspectives; it does not imply that a sophisticated model is necessary.

### 3.1 A simple operational picture

```text
Customer request
      |
      v
[K] Scope, authority, constraints, acceptance
      |
      v
[F] Forward guidance: weather, access, safety, schedule
      |
      v
[P] Confirm -> Prepare -> Travel -> Inspect -> Mow -> Edge -> Verify
      |                 ^                     |
      |                 |---- Replan if needed-|
      v
[R] Completion record + evidence + unresolved items
      |
      v
[E] Candidate improvement -> sandbox/check -> approval -> new version
      |
      +---- Reusable, locally validated guidance for the next job
```

The guidance function is active **before and during** the calling path, not merely a grade assigned after the lawn is mowed.

## 4. Contract K: define the job before doing it

A minimal contract should answer five questions:

1. **Who owns the decision?** Customer approves scope and price; operator controls safe execution.
2. **What is being done?** Mowing and edging, excluding additional landscaping.
3. **What counts as completion?** Agreed areas serviced, debris addressed as agreed, customer notified.
4. **What must not be violated?** Safety, property boundaries, weather restrictions, access permissions, and budget.
5. **What requires renegotiation?** Extra work, inaccessible areas, significant delay, or a changed price.

A lightweight machine-readable illustration:

```yaml
uieru_id: lawn-job-042
contract_version: "1.0"
subject:
  customer_role: requester_and_scope_approver
  operator_role: execution_and_safety_authority
object:
  task: mow_and_edge_residential_lawn
  scope: agreed_front_and_back_yard
  exclusions: [hedge_trimming, chemical_treatment]
goals:
  - complete_agreed_scope
  - avoid_property_damage
  - obtain_customer_confirmation
constraints:
  customer_approval_required_for_scope_change: true
  unsafe_conditions: stop_and_reassess
  gate_access: confirm_before_arrival
acceptance:
  - agreed_areas_serviced
  - exceptions_disclosed
  - completion_message_sent
```

This is a conceptual example, **not** a claim that a finalized UIERU schema already exists. The formal specification belongs in `specs/SPEC-001-Canonical-UIERU-Contract-and-Schema.md`.

## 5. Calling Path P: organize existing capabilities

The calling path is a set of callable actions, not necessarily a software-only workflow.

| Step | Actor or tool | Output | Possible exception |
|---|---|---|---|
| 1. Intake | Customer and operator | Agreed request | Scope unclear |
| 2. Confirm | Phone or messaging | Access and time confirmed | No response |
| 3. Check | Weather and operator | Go / postpone decision | Rain or unsafe conditions |
| 4. Prepare | Operator | Equipment ready | Equipment failure |
| 5. Execute | Operator | Lawn serviced | Obstacle or unexpected scope |
| 6. Inspect | Operator | Quality and safety check | Missed area |
| 7. Close | Customer and operator | Completion and payment status | Disputed scope |
| 8. Relay | Checklist or app | Reusable job record | Missing evidence |

The path should expose decision points. A rigid script that always proceeds from weather check to mowing is not sufficient: if the conditions become unsafe, the path must stop or replan.

## 6. Scoring Forest F: guidance before, during, and after work

For this small task, four evaluation perspectives are enough:

| Perspective | Example question | Priority |
|---|---|---|
| Safety | Is it safe to mow now? | Hard constraint |
| Contract fidelity | Is this within approved scope? | Hard constraint |
| Service quality | Will the result satisfy acceptance criteria? | Important objective |
| Cost and efficiency | Can the work be completed with reasonable travel and effort? | Optimization objective |

The critical distinction is between **constraints** and **trade-offs**. A high efficiency score must never compensate for a safety violation or unauthorized extra work. Therefore, the guidance logic first filters inadmissible actions and only then ranks feasible alternatives.

A conceptual decision rule is:

$$
\mathcal{A}_{\mathrm{feasible}}(s) = \{a \in \mathcal{A}(s) : C_i(a,s) = \mathrm{true}\ \forall i\}
$$

$$
a^* \in operatorname*{argmax}_{a \in \mathcal{A}_{\mathrm{feasible}}(s)} V(a \mid s, K, F)
$$

Here, `s` is the observed situation; `C_i` are mandatory constraints; and `V` is an illustrative, context-dependent valuation function. No universal weighting is presumed.

### 6.1 Forward guidance examples

**Before dispatch:** If rain is forecast during the service window, evaluate postponement before loading the truck.  
**At the property:** If the gate is locked, contact the customer rather than entering without permission.  
**During execution:** If the mower fails, compare safe repair, equipment substitution, or rescheduling.  
**After execution:** Evaluate quality and capture evidence; do not confuse this retrospective assessment with the earlier guidance process.

## 7. A minimal Multi-Trail decision

Suppose rain threatens the appointment. The operator may consider three tracks:

- **Trail A — Exploit:** proceed at the original time if conditions remain safe.
- **Trail B — Explore:** offer an earlier or later authorized time window.
- **Trail C — Challenge:** test the assumption that the yard will be safe and accessible; seek counter-evidence from updated forecasts or site observations.

These are **candidate plans**, not three simultaneous physical mowing jobs. Only an authorized, safe plan can be executed. Trails may be evaluated cheaply on paper or in a sandbox, and discarded alternatives can be recorded without being enacted.

| Trail | Supporting evidence | Counter-evidence | Decision |
|---|---|---|---|
| A: original window | Customer preference | Increasing rain risk | Conditional |
| B: revised window | Forecasted dry interval | Customer may be unavailable | Ask customer |
| C: challenge assumptions | Updated forecast and site check | Forecast uncertainty persists | Recheck near dispatch |

The purpose of Multi-Trail reasoning is to improve decision quality under uncertainty, not to multiply work unnecessarily.

## 8. Worked execution: an access problem

At 8:30 a.m., the operator receives a confirmation that the back gate is locked and the customer is away.

1. **Observe:** The current path cannot reach the backyard.
2. **Check K:** The operator has no authority to force access or substitute unapproved work.
3. **Generate feasible options:** Complete only the authorized accessible area, reschedule the backyard, or postpone the whole visit.
4. **Use F:** Compare customer convenience, schedule impact, quality, and contract compliance, subject to hard constraints.
5. **Seek approval:** The customer authorizes front-yard service today and backyard service tomorrow, with an agreed revised price.
6. **Execute P:** Update the calling path and perform the authorized subset.
7. **Record R:** Preserve the changed scope, authorization, completed work, and pending backyard task.
8. **Propose E:** Add an explicit gate-access confirmation to future intake checklists.

The improvement is not automatically adopted merely because it appears useful. It is reviewed and tested against its cost and relevance.

## 9. Relay R: more than a completion message

A conventional message might say: “Front lawn done; back gate locked.” A UIERU relay record makes the handoff actionable and auditable.

```yaml
relay_id: lawn-job-042-handoff-1
uieru_id: lawn-job-042
contract_version: "1.1"
status: partially_completed
completed:
  - front_lawn_mowed
  - front_edges_trimmed
pending:
  - back_lawn_after_customer_access
approvals:
  - type: scope_and_schedule_revision
    approved_by: customer
    evidence_ref: customer-message-042b
observations:
  - back_gate_locked
  - access_unavailable_at_arrival
counter_evidence:
  - assumption: back_yard_access_was_available
    observation: gate_locked
    effect: original_plan_invalidated
candidate_delta:
  id: delta-gate-confirmation-v1
  proposal: confirm_back_gate_access_before_dispatch
  status: proposed_not_approved
next_owner: operator
next_action: reconfirm_access_before_return
provenance:
  records: [job-checklist-042, customer-message-042b]
```

The relay package contains **state**, **evidence**, **authority**, **open work**, and **candidate learning**. It does not silently turn a proposed change into an approved procedure. Private customer details should be minimized and access-controlled.

## 10. Evolution E: one small structural delta

Repeated gate-access failures suggest a process change:

```text
Observed residual:
  Trips wasted because backyard access was not confirmed
           |
           v
Candidate structural delta:
  Add "confirm gate access" to pre-dispatch checklist
           |
           v
Validation:
  Compare missed-access rate, added messaging effort,
  customer friction, and exceptions across future jobs
           |
           v
Human approval -> versioned procedure -> monitoring
           |
           +--> retain / revise / roll back
```

This is **structural evolution** only in a modest operational sense: the reusable calling path and guidance procedure change. It is not evidence of autonomous recursive self-improvement. Stronger recursive-improvement claims require independent experiments, evaluation governance, and explicit authorization.

## 11. Bidirectional relay across a small service team

Suppose a second operator receives the same route template. The first operator can share a sanitized checklist improvement and supporting observations. The second operator does not have to accept it unchanged: a property with open access or different scheduling conditions may not benefit from the extra confirmation step.

A valid exchange follows:

```text
Operator A -> Candidate procedure + evidence + scope of validity
Operator B -> Local applicability check + trial + observations
Operator B -> Feedback, exceptions, and revised evidence
Operator A -> Reassess generality; keep or narrow the rule
```

This is the smallest plausible example of **bidirectional collective learning**. The learning claim is conditional: sharing alone does not establish improvement; local verification and measurable benefit are required.

## 12. Composition: when the job grows

A one-person job can be one UIERU. A larger property may require two coordinated units:

- **Parent unit:** manages customer contract, schedule, budget, acceptance, and final relay.
- **Child unit A:** mowing and edging.
- **Child unit B:** debris collection and cleanup, if separately authorized.

The parent reconciles overlapping constraints and preserves each child’s evidence. It cannot grant a child permission that the customer never gave. A child’s good quality score does not override a parent-level contract violation.

Composition is optional. Splitting a five-minute task into multiple units may be counterproductive.

## 13. Minimal implementation without special AI infrastructure

The smallest viable deployment can use:

1. A standard request/approval form for **K**.
2. A checklist with exception branches for **P**.
3. A decision table with hard constraints and priorities for **F**.
4. A completion/handoff record for **R**.
5. A change log and trial process for **E**.

A spreadsheet or lightweight application is sufficient. An LLM can help draft messages or summarize evidence, but its outputs should not be treated as authority, ground truth, or permission to act.

## 14. Comparison against simpler alternatives

| Approach | Strength | Missing or optional capability |
|---|---|---|
| Informal memory | Almost no setup cost | Weak consistency and handoff |
| Checklist | Reliable sequence | Limited dynamic guidance and learning |
| Workflow software | Repeatable execution | May lack explicit evidence and counter-evidence |
| Conventional agent | Flexible tool use | May lack stable contract boundaries and governed relay |
| Minimal UIERU | Contract + guidance + execution + relay + evolution | Adds modeling and maintenance overhead |

The appropriate baseline for this case is usually **a good checklist**, not a sophisticated AI agent. A UIERU should be preferred only if it demonstrably improves relevant outcomes.

## 15. Testable hypotheses and measurements

These are hypotheses, **not established results**.

| Hypothesis | Measurement | Comparison |
|---|---|---|
| H1: explicit pre-dispatch guidance reduces avoidable failed visits | Failed dispatches per 100 jobs | Existing checklist |
| H2: evidence-rich relay improves handoff quality | Missing-information incidents, clarification time | Plain-text completion note |
| H3: contract checks reduce unauthorized scope changes | Unauthorized change rate | Existing workflow |
| H4: counter-evidence prompts reduce preventable mistakes | Preventable incident rate | No challenge step |
| H5: validated structural deltas improve repeat-job performance | Outcome improvement net of process cost | Frozen baseline procedure |

Suggested evaluation design: define the baseline, record initial failure rates, pilot on comparable jobs, separate weather/seasonality effects, include customer experience, and report the administrative burden. Do not infer causality from a single anecdote.

## 16. Failure modes and safeguards

| Failure mode | Safeguard |
|---|---|
| Excessive forms for trivial jobs | Minimal profile and optional adoption |
| A score hides a hard safety violation | Hard constraints before optimization |
| Unauthorized scope expansion | Explicit customer approval |
| False or stale observations | Timestamp and provenance checks |
| Sharing customer-sensitive information | Data minimization and access control |
| Poor improvement generalized to every property | Local validation and scope-of-validity labels |
| Automated procedure changes without review | Versioning, approval, rollback |
| Too many exploratory trails | Cost limits and selective branching |

## 17. What this case demonstrates—and does not

**Demonstrates conceptually:**

- A UIERU can be built around an existing human workflow.
- Forward guidance can be simple, explicit, and useful.
- Multi-Trail analysis can evaluate alternatives without executing all of them.
- Relay can carry authorization, evidence, exceptions, and proposed improvements.
- Structural evolution can begin with a small, versioned checklist change.

**Does not demonstrate empirically:**

- That UIERU outperforms a good conventional checklist.
- That every lawn service needs a Scoring Forest.
- That multi-trail branching always improves decisions.
- That sharing a procedure automatically produces collective learning.
- That a minimal service unit establishes general autonomous intelligence.

The broader research program must validate these claims through controlled comparison and clear boundaries.

## 18. Generalization to other domains

The same pattern may be investigated in appliance repair, field inspections, small logistics operations, software maintenance, and administrative services. The relevant transfer is **not** the lawn-specific checklist; it is the organizational pattern:

```text
Explicit authority and acceptance
      +
Callable execution path
      +
Forward guidance under constraints
      +
Evidence-preserving handoff
      +
Validated procedural change
      =
Candidate minimal UIERU
```

Transferability remains conditional on domain risk, interface compatibility, local authority, available evidence, and the economic cost of coordination.

## 19. Conclusion

The neighborhood lawn service makes UIERU concrete. A task does not become an intelligence unit simply by attaching an AI label or storing a transcript. The useful structure arises when **contract, execution, forward guidance, relay, and governed evolution** are made explicit and coordinated. The unit can be mostly human-operated and technologically modest. Its value must be measured against simpler alternatives.

The essential engineering ambition is **selective structural containerization**: make the right activities easier to coordinate, transfer, inspect, and improve—without forcing every activity into a container or displacing the people who own its decisions.

## Repository connections

- `docs/UIERU-001-From-Calling-Paths-to-Evolvable-Intelligence-Units.md` — foundational motivation.
- `docs/UIERU-002-Canonical-UIERU-Contracts-Execution-Guidance-and-Relay.md` — canonical five-part unit.
- `docs/UIERU-003-Calling-Path-and-Scoring-Forest-Duality.md` — path/guidance relationship.
- `docs/UIERU-004-Forward-Guidance-and-Multi-Trail-Intelligence.md` — multi-trail guidance.
- `docs/UIERU-007-Structural-Relay-Provenance-and-Intelligence-Portability.md` — relay and provenance.
- `docs/UIERU-009-Residual-Driven-Structural-Evolution-and-Recursive-Improvement.md` — governed deltas.
- `specs/SPEC-001-Canonical-UIERU-Contract-and-Schema.md` — proposed contract schema.
- `figures/Fig-001-UIERU-in-Motion-From-Task-to-Relay-and-Evolution.png` — optional visual overview.

---

**Citation guidance:** Cite this case as an illustrative engineering reference design, not as an empirical study or proof of performance.

**Authors:** Sizhe Tan & GPT-Obot  
**Version:** 1.0.0  
**Project:** Universal Intelligence Evolution and Relay Unit (UIERU)
