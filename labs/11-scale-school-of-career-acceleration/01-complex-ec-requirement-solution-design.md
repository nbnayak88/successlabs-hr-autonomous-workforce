# Scenario Category 01 — Complex Employee Central Requirement & Solution Design

## Interview Practice Guide — 20 Scenario-Based Questions, STAR Answers & SME Probes

**Track:** SCALE — School of Career Acceleration  
**Target Role:** Tech Delivery Subject Matter Expert — SAP SuccessFactors Employee Central  
**Scenario Category:** Complex EC Requirement & Solution Design  
**Question IDs:** SCALE-EC-01-Q01 through SCALE-EC-01-Q20  
**Scope:** Business requirements, EC solution design, data and effective dating, standard-versus-extension decisions, rules, workflow, permissions, integrations, testing, governance, and stakeholder decisions.

## Learning outcome

By the end of this practice set, the candidate should be able to explain how to translate an ambiguous or complex HR requirement into a maintainable Employee Central solution, identify dependencies and risks, justify design decisions, and defend the solution to business and technical stakeholders.

## Answer-integrity and product-accuracy note

The STAR responses below are **illustrative model answers**, not claims about the candidate's personal experience. Replace contexts, actions, scope, tools, and results with genuine evidence. Do not invent project ownership, metrics, configuration, or outcomes. Where a question asks about a past event and the candidate has no direct example, state that honestly and answer using a clearly labelled hypothetical approach.

Employee Central behaviour can depend on the enabled features, configuration, release, data model, permissions, and integration design. Validate exact product behaviour in the target tenant and current SAP documentation before presenting a configuration-specific answer as fact. Treat country-specific legal or regulatory needs as requirements to validate with qualified specialists.

## How to use each scenario

1. Answer the interview question aloud before reading the model.
2. Use **Situation → Task → Action → Result**. Make the personal responsibility explicit.
3. Explain the Employee Central example and relevant assumptions.
4. Answer the **SME Probe** with evidence, trade-offs, failure modes, and alternatives.
5. Capture one improvement to your own answer and retry later without reading the model.

---

## Q01 — Translate an Ambiguous Business Requirement

### Interview Question
A global HR team says, “We need employee transfers to be faster and more consistent,” but cannot agree on the exact process. How would you turn this statement into an Employee Central requirement and solution?

### STAR Model Answer
- **Situation:** The request describes a desired outcome but does not define which transfer types, employee populations, approvals, data changes, or exceptions are in scope.
- **Task:** Establish a testable requirement and propose a solution that aligns to the operating process rather than prematurely configuring a feature.
- **Action:** I would facilitate discovery with HR operations, managers, data owners, security, reporting, and integration stakeholders. I would map the current and target process, transfer types, effective-date rules, event reasons, required fields, approval conditions, exception paths, and downstream consumers. I would separate mandatory controls from preferences; confirm source-of-truth ownership; assess standard EC capabilities; and document assumptions, acceptance criteria, and open decisions. I would validate the proposed design using representative scenarios before configuration.
- **Result:** The team would have an agreed requirement baseline, traceable design decisions, explicit acceptance criteria, and fewer ambiguities entering configuration and testing. I would claim quantified improvements only after measurement.

### SAP SuccessFactors Employee Central Example
For an internal transfer, assess the relevant Job Information changes, event reason, effective date, workflow, business rules, permissions, organizational assignments, and downstream impacts. Confirm exact behaviour in the target configuration.

### SME Probe
What evidence would make you conclude that the requirement is ready for design rather than still in discovery?

---

## Q02 — Standard Functionality Versus Extension

### Interview Question
A senior stakeholder requests custom logic for a transfer process. You suspect standard Employee Central configuration may meet the underlying need. How do you decide?

### STAR Model Answer
- **Situation:** A stakeholder has proposed a technical solution before the business need and standard options have been fully assessed.
- **Task:** Recommend a solution that meets the business outcome without adding unjustified complexity.
- **Action:** I would clarify the required outcome, mandatory constraints, exceptions, and acceptance criteria. I would map the requirement to supported standard capabilities and configuration options in the target tenant. I would compare alternatives on functional fit, maintainability, upgrade impact, security, auditability, data quality, integration dependencies, support skills, and total lifecycle cost. Any gap would be documented with evidence, then reviewed with product and architecture stakeholders before an extension was proposed.
- **Result:** The decision would be based on documented fit and trade-offs rather than preference for customization or standardization alone.

### SAP SuccessFactors Employee Central Example
Compare an appropriate combination of standard fields, event reasons, business rules, workflow configuration, and supported extensibility before designing a custom object or external component.

### SME Probe
If the standard approach covers 90% of the requirement but misses one mandatory exception, how would you assess the options?

---

## Q03 — Different Employee Populations and Local Variations

### Interview Question
A global transfer process must support several legal entities and employee populations, each with some different requirements. How would you design a scalable approach?

### STAR Model Answer
- **Situation:** The business wants a common global experience, but certain populations have legitimate variations in process, data, or approval needs.
- **Task:** Preserve global consistency while ensuring that the solution handles justified differences.
- **Action:** I would define the global baseline and record each proposed variation with its business rationale and owner. I would classify differences as data, process, configuration, security, integration, or policy concerns. I would evaluate whether variations can be handled through supported configuration and governed decision logic rather than duplicated designs. I would test representative employee populations and exceptions, and document where local validation is required.
- **Result:** The design would provide a controlled global pattern with visible, reviewable variations and clear ownership.

### SAP SuccessFactors Employee Central Example
Evaluate organizational assignments, event reasons, workflow conditions, rule applicability, target populations, and reporting/integration mappings across representative employee groups.

### SME Probe
What criteria would you use to reject a requested local variation?

---

## Q04 — Requirement Changes After Design Sign-Off

### Interview Question
After the solution design is approved, HR changes the transfer approval policy. Configuration has started and the planned test cases are already written. What do you do?

### STAR Model Answer
- **Situation:** A policy change arrives after design approval and affects work already in progress.
- **Task:** Incorporate the change through governance while making delivery and regression impacts visible.
- **Action:** I would record the change and its rationale, clarify effective timing and affected populations, then assess impacts on workflow routing, rules, permissions, documentation, integrations, test cases, and delivery dependencies. I would estimate effort and risk with the relevant owners, obtain the required decision, update traceability and versioned artifacts, and re-plan validation. I would not allow an undocumented configuration change to bypass approval.
- **Result:** The team would have a controlled decision, an updated scope baseline, and explicit regression coverage for affected behaviour.

### SAP SuccessFactors Employee Central Example
Reassess workflow conditions and participant determination alongside the transaction trigger, rule configuration, RBP, and any connected downstream process.

### SME Probe
What would you do if the stakeholder demands the change immediately but refuses to accept schedule or risk implications?

---

## Q05 — Conflicting Stakeholder Requirements

### Interview Question
HR Operations wants manager approval for every transfer, while HR leadership wants low-risk transfers to proceed without delay. How do you resolve the conflict?

### STAR Model Answer
- **Situation:** Stakeholders disagree about control and speed, and both positions are tied to legitimate concerns.
- **Task:** Establish decision criteria and recommend a design that preserves required governance without unnecessary friction.
- **Action:** I would map transfer types, risks, approval authority, policy obligations, employee experience, and operational workload. I would distinguish mandatory controls from preferences and model options such as risk-based routing only where supported and approved. I would explain operational, security, audit, and maintenance trade-offs and ask the accountable policy owner to approve the decision. I would document rationale and define measures to evaluate the outcome.
- **Result:** The decision would be explicit, accountable, and testable rather than an informal compromise hidden in configuration.

### SAP SuccessFactors Employee Central Example
Assess whether workflow conditions can support the approved routing model in the configured process, and test each route with appropriate user personas and transaction types.

### SME Probe
What is your responsibility if the business selects an option you believe creates a material control risk?

---

## Q06 — End-to-End Solution Impact

### Interview Question
A request appears to involve one Job Information field, but it may affect rules, approvals, security, reporting, and integrations. How do you assess the complete impact?

### STAR Model Answer
- **Situation:** A seemingly small change can affect multiple capabilities and downstream consumers.
- **Task:** Identify the change surface and make sure the design and tests cover the complete business transaction.
- **Action:** I would trace the field's purpose and ownership, effective dating, rule dependencies, workflow behaviour, permission exposure, reports, integrations, analytics, and operational procedures. I would consult the relevant technical owners, document upstream/downstream dependencies, and create an impact matrix linking each affected component to an acceptance test and owner. I would use controlled test records to verify end-to-end outcomes.
- **Result:** The change would be assessed across its lifecycle, and the team would have traceable ownership and validation evidence for each impacted component.

### SAP SuccessFactors Employee Central Example
For a Job Information change, validate the employee record, event reason, relevant rule/workflow path, permitted visibility, outbound payload, and downstream reporting where applicable.

### SME Probe
How would you find an undocumented downstream consumer before changing the field?

---

## Q07 — Effective-Dated Transfer and Conflicting Future Records

### Interview Question
An employee already has a future-dated promotion. HR now enters a transfer with an earlier effective date. How do you analyze the situation?

### STAR Model Answer
- **Situation:** Multiple future and effective-dated changes may interact, and an incorrect action can distort the employee's timeline.
- **Task:** Determine the intended business timeline and the correct supported transaction approach without losing valid history.
- **Action:** I would inspect the full relevant history and future-dated records, clarify the intended sequence with HR, and determine whether the new change should create a record, correct an existing one, or require another approved transaction approach. I would evaluate event reasons, rule/workflow triggers, effective-date sequencing, and downstream recalculation or interface effects. I would test the before-and-after timeline and confirm the outcome with the business and relevant product guidance.
- **Result:** The final data timeline would reflect the approved sequence, with history preserved and any downstream effects understood.

### SAP SuccessFactors Employee Central Example
Use a controlled test employee with past, current, and future Job Information records; verify record history and expected results in the configured tenant.

### SME Probe
How do you explain the difference between correcting an existing effective-dated record and entering a new business event?

---

## Q08 — Data Model Placement Decision

### Interview Question
The business asks for a new “transfer justification” attribute. How do you decide where it belongs in Employee Central?

### STAR Model Answer
- **Situation:** A new data requirement has been stated, but its lifecycle, ownership, and relationship to existing structures are not clear.
- **Task:** Choose an appropriate data representation while avoiding duplication and downstream ambiguity.
- **Action:** I would clarify whether the information describes the person, employment, job change, organizational entity, or a separate business process. I would assess whether an existing standard field or supported structure already represents it, how long the value must be retained, whether it needs effective dating, who may view or update it, and how reporting or integrations will consume it. If an extension is needed, I would document object/field design, governance, access, migration, and test implications.
- **Result:** The data placement would follow business meaning and lifecycle rather than merely locating the nearest available field.

### SAP SuccessFactors Employee Central Example
Assess standard Job Information fields, any available transaction context, and supported MDF/extensibility options in the target configuration before recommending a design.

### SME Probe
What risks arise when the same business concept is stored in two different places?

---

## Q09 — Foundation Object Dependency

### Interview Question
A transfer cannot be completed because the intended department or location is unavailable or inconsistent. How do you diagnose the problem?

### STAR Model Answer
- **Situation:** A transaction depends on valid organizational reference data, but the required value is missing or not selectable.
- **Task:** Identify whether the cause is master/reference data, effective dating, configuration, or authorization.
- **Action:** I would establish the expected organizational value and source of truth, check whether the relevant object and association are configured and valid for the effective date, compare the employee's context and available values, and review permissions and dependency constraints. I would correct the source data or configuration through approved governance, then test the transaction and downstream impacts.
- **Result:** The resolution would address the root cause rather than introducing a duplicate value or bypassing validation.

### SAP SuccessFactors Employee Central Example
Trace the relevant organizational Foundation Object, associations, effective validity, field configuration, permissions, and any dependent rule logic.

### SME Probe
How do you distinguish an invalid organizational value from a value the user cannot see because of permissions?

---

## Q10 — Business Rule Trigger and Rule Dependencies

### Interview Question
A Business Rule sets a field correctly in one transaction but fails in another, even though the screen looks similar. What is your diagnostic method?

### STAR Model Answer
- **Situation:** The same apparent user action produces inconsistent results in different transaction contexts.
- **Task:** Identify the actual cause without adding another overlapping rule blindly.
- **Action:** I would reproduce the issue with controlled records and compare transaction type, effective date, event reason, rule scenario, trigger, input availability, conditions, and execution timing. I would inspect dependencies between rules and any relevant object/field configuration. I would isolate a minimal failing case, correct the smallest verified cause, and test the original case plus positive, negative, boundary, and regression scenarios.
- **Result:** The correction would be evidence-based and accompanied by regression coverage to reduce the risk of breaking other employee transactions.

### SAP SuccessFactors Employee Central Example
Review the applicable rule assignment/trigger, data available at execution time, conditions, action, event reason, and effects on other employee populations in the tenant.

### SME Probe
How can you prove a rule is executing at the wrong time instead of having the wrong condition?

---

## Q11 — Workflow Not Triggered or Routed Incorrectly

### Interview Question
An employee transaction saves, but the expected approval workflow does not start—or starts with the wrong approver. How do you investigate?

### STAR Model Answer
- **Situation:** A transaction completes a data entry step but the approval path differs from the business expectation.
- **Task:** Trace the workflow from initiation to participant determination and identify the failing dependency.
- **Action:** I would confirm the transaction type, triggering event, workflow configuration, conditions, participant rules, manager/role relationships, organizational data, effective date, and relevant permissions. I would inspect available workflow status/audit evidence, reproduce with representative users, and validate the fix using both expected and exception routes. I would verify exact capabilities and diagnostics available in the configured release.
- **Result:** The workflow issue would be isolated to an evidenced configuration, data, or authorization cause, and the corrected route would be tested.

### SAP SuccessFactors Employee Central Example
Trace the change event through workflow initiation, conditions, participant resolution, approver access, and completion status.

### SME Probe
What evidence would distinguish a workflow trigger problem from a participant-resolution problem?

---

## Q12 — Role-Based Permissions and Sensitive Fields

### Interview Question
Managers should initiate transfers for their teams, HR Operations should process exceptions, and only a restricted group should view a sensitive field. How would you design and validate access?

### STAR Model Answer
- **Situation:** Multiple personas need different actions and data visibility within one HR process.
- **Task:** Support the process using least-privilege access while preventing unintended disclosure or unauthorized changes.
- **Action:** I would map personas to required actions, fields, and target populations. I would review applicable Role-Based Permissions, permission groups, target population rules, and field-level controls where supported. I would validate that the workflow does not expose sensitive data unnecessarily and test both allowed and denied actions with test users representing each role. I would retain evidence and obtain the appropriate security approval.
- **Result:** Access would be validated against explicit business requirements, including negative tests, rather than inferred from a successful administrator test.

### SAP SuccessFactors Employee Central Example
Test manager, HR administrator, restricted specialist, and unauthorized personas against the same representative transaction and sensitive field.

### SME Probe
Why is testing only with an administrator insufficient?

---

## Q13 — Global Template Versus Local Requirement

### Interview Question
A local HR team says the global Employee Central template cannot support a country-specific transfer process. How do you handle the claim?

### STAR Model Answer
- **Situation:** A local stakeholder requests a variation that may conflict with global process design.
- **Task:** Determine whether the difference is mandatory, valid, and best addressed through the existing template or a controlled variation.
- **Action:** I would gather the exact process and data requirement, request evidence for any legal or policy constraint, and involve qualified local specialists where relevant. I would compare the global design with supported product and configuration options, assess maintenance and integration impacts, and document the decision, owner, exception rationale, test coverage, and review point. I would avoid treating preference as a legal requirement without validation.
- **Result:** The local requirement would be resolved through a traceable design decision, with global consistency maintained where possible and justified variation where necessary.

### SAP SuccessFactors Employee Central Example
Assess whether the difference is driven by data, workflow, business rules, organizational structure, permissions, or a genuinely distinct process requirement.

### SME Probe
What would you do if the local team cannot provide evidence for the claimed mandatory requirement?

---

## Q14 — UAT Readiness and Acceptance Criteria

### Interview Question
Configuration is complete, but the business says it is “ready for UAT” without agreed acceptance criteria. What must happen before testing begins?

### STAR Model Answer
- **Situation:** A build is declared ready, but the team lacks objective agreement on expected behaviour and scope.
- **Task:** Make UAT executable, traceable, and capable of supporting a go/no-go decision.
- **Action:** I would map approved requirements to acceptance criteria, preconditions, test data, positive/negative/boundary cases, role coverage, effective-date cases, workflow routes, integrations, reporting, and regression needs. I would confirm environment readiness, defect triage, business test ownership, expected evidence, and entry/exit criteria. I would resolve critical gaps before calling the solution test-ready.
- **Result:** UAT would evaluate agreed business outcomes with traceable evidence rather than relying on informal demonstrations.

### SAP SuccessFactors Employee Central Example
Create an end-to-end transfer test matrix with roles, effective dates, event reasons, approval routes, expected Job Information outcomes, and downstream checks.

### SME Probe
What are examples of defects or missing evidence that should prevent UAT sign-off?

---

## Q15 — Integration Contract and Downstream Impact

### Interview Question
An EC transfer changes job and organizational information, but the downstream system expects a different structure or timing. How would you handle the interface dependency?

### STAR Model Answer
- **Situation:** The source transaction and downstream consumer do not agree on data, timing, or expected business meaning.
- **Task:** Identify the contract mismatch and preserve consistency across system boundaries.
- **Action:** I would define source-of-truth ownership, relevant fields, effective dates, identifiers, event/change semantics, mapping, required/optional values, and expected processing timing. I would work with integration owners to review transformation and error handling, test representative payloads and target results, and confirm monitoring and reconciliation. I would not assume a particular integration mechanism without checking the actual landscape.
- **Result:** The interface expectation would be explicit, tested, and owned by the appropriate teams, reducing ambiguity during change and support.

### SAP SuccessFactors Employee Central Example
Use a test transfer to validate the EC source record, mapped outbound representation, target acceptance, and reconciliation evidence in the real integration design.

### SME Probe
How do you determine which system should own a disputed data value?

---

## Q16 — Migration or Import Readiness for a New Design

### Interview Question
The solution design adds or changes a field that must be populated during an EC data load. What migration and validation questions must be answered?

### STAR Model Answer
- **Situation:** A configuration change affects the shape or quality of data required for migration/import or an existing load process.
- **Task:** Prevent incomplete, invalid, or inconsistent values from entering the employee data model.
- **Action:** I would identify the source, ownership, mapping, transformation, effective-date treatment, mandatory conditions, valid values, dependencies, permissions, and expected downstream consumers. I would profile data, define rejection and correction handling, reconcile counts and key fields, and rehearse the load in a controlled environment. I would test exceptions and post-load business transactions before sign-off.
- **Result:** The import would have documented mappings, validation, reconciliation, and accountable remediation rather than relying solely on a successful file-processing status.

### SAP SuccessFactors Employee Central Example
Validate representative records using the supported import/API method for the target process, and check the resulting EC records and dependent organizational values.

### SME Probe
What do you do when record counts reconcile but business-level values are still wrong?

---

## Q17 — Production Defect After Release

### Interview Question
After a transfer-related enhancement goes live, a subset of transactions produces incorrect results. How do you respond?

### STAR Model Answer
- **Situation:** A production change introduces an issue affecting only some transaction paths or employee populations.
- **Task:** Contain impact, protect data integrity, restore the service, and find the root cause.
- **Action:** I would assess severity, scope, affected records, business deadlines, and downstream consequences. I would follow incident and change procedures, preserve logs and examples, compare failing and successful transactions, and investigate configuration, data, rules, workflow, permissions, and interfaces. Any correction or rollback would be approved and rehearsed as appropriate. I would validate recovered records, execute focused regression tests, and document corrective and preventive actions.
- **Result:** The incident would be handled through controlled containment and evidenced recovery, followed by prevention work rather than an untracked production tweak.

### SAP SuccessFactors Employee Central Example
Compare affected transaction history, rule/workflow evidence, relevant data, permissions, and connected-system outcomes for failed versus successful cases.

### SME Probe
What would make you pause further processing instead of applying a quick fix?

---

## Q18 — Quantify Value Without Inventing Metrics

### Interview Question
A leader asks you to prove that the redesigned EC process improved efficiency and quality. What measures would you propose?

### STAR Model Answer
- **Situation:** The organization wants evidence that a process redesign delivers business value, not just a completed configuration.
- **Task:** Define practical measures with a credible baseline and clear ownership.
- **Action:** I would agree measures such as transaction cycle time, approval wait time, rework rate, data error rate, first-time-right completion, exception volume, support tickets, and user feedback. I would define population and observation period, verify data sources, compare like-for-like baseline and post-release performance, and disclose confounding changes. I would report actual results only when evidence supports them.
- **Result:** Stakeholders would receive a transparent view of the intended and observed impact, including limitations and further improvement opportunities.

### SAP SuccessFactors Employee Central Example
Use approved operational reporting or analytics to compare comparable transfer populations before and after deployment; validate definitions and data quality first.

### SME Probe
How would you avoid claiming the EC change caused an improvement that was actually due to another process change?

---

## Q19 — Executive Challenge to the Recommended Design

### Interview Question
An executive rejects your recommended solution because it appears slower or more expensive than the requested shortcut. How do you defend your position?

### STAR Model Answer
- **Situation:** A stakeholder challenges a design decision and prioritizes short-term speed or cost.
- **Task:** Explain the recommendation in business terms and help the accountable decision-maker understand options and residual risk.
- **Action:** I would restate the business outcome, compare viable options, and show impacts on user experience, data integrity, access control, auditability, integration, supportability, and lifecycle cost. I would distinguish evidence from assumptions, explain the minimum acceptable controls, and state what new evidence could change my recommendation. If leadership accepts residual risk, I would ensure it is documented and approved by the appropriate owner.
- **Result:** The decision would be informed and traceable, whether the recommendation is accepted or not.

### SAP SuccessFactors Employee Central Example
Present a decision record comparing standard configuration, a governed exception, and any supported extension, with dependencies, cost/risk assumptions, and testing implications.

### SME Probe
How do you distinguish an architectural recommendation from a formal risk warning when evidence remains incomplete?

---

## Q20 — Integrated Employee Central Solution Defence

### Interview Question
You must present an end-to-end design for a complex employee transfer process to an interview panel acting as HR leadership, security, integration, testing, and operations. What would you present and how would you defend it?

### STAR Model Answer
- **Situation:** The panel needs confidence that the design meets the business need and is deliverable, secure, testable, and supportable.
- **Task:** Demonstrate end-to-end reasoning and explain what is known, what remains open, and how success will be verified.
- **Action:** I would begin with the business outcome and stakeholder journeys, then show the process and data model, effective-date assumptions, event reasons, relevant rules and workflow, RBP model, integration boundaries, exception paths, testing approach, release and support plan, and measurable acceptance criteria. I would compare alternatives, identify risks and dependencies, assign owners to open decisions, and explicitly flag product-version or local-policy assumptions requiring validation.
- **Result:** The panel could evaluate the proposal against clear criteria, understand residual risks, and make a grounded decision on readiness and next steps.

### SAP SuccessFactors Employee Central Example
Use a representative transfer scenario and trace it from initiation through approval and Job Information update to permissions, downstream processing, reporting, and support evidence.

### SME Probe
Which unresolved dependency would make you recommend a conditional approval rather than unconditional sign-off?

---

# Rapid-Fire SME Probe Bank

Use these after the 20 STAR scenarios. Answer each in 30–60 seconds and give a reason, not just a definition.

1. What makes a requirement testable?
2. When is configuration preferable to an extension?
3. How do effective dates alter the design?
4. How do you identify a data-model ownership issue?
5. What do you inspect when a rule works for one transaction but not another?
6. How do you distinguish workflow initiation failure from participant-resolution failure?
7. Why test with non-administrator personas?
8. How do you govern legitimate local variation?
9. What makes a solution UAT-ready?
10. What evidence supports a go/no-go decision?
11. How do you identify undocumented downstream consumers?
12. What must be reconciled after an import?
13. How do you contain a production defect safely?
14. Which metrics indicate better process outcomes?
15. How do you communicate residual risk to executives?

# SME Probe Ladder

For any scenario, progress through the following levels:

1. **Recall:** What capability or concept is involved?
2. **Reasoning:** Why is that capability appropriate?
3. **Application:** How would it work in the stated situation?
4. **Evidence:** What logs, data, configuration, or tests support the answer?
5. **Alternative:** What other options were considered?
6. **Failure:** What could go wrong and how would it be detected?
7. **Trade-off:** What cost, risk, usability, or maintenance trade-off was accepted?
8. **Measurement:** How would you know the solution worked?
9. **Governance:** Who owns the decision and residual risk?
10. **Reflection:** What would you change with hindsight?

# STAR Answer Quality Rubric

Score each dimension from 0 to 4. Use the rubric for coaching and self-reflection; it is not a validated hiring instrument.

| Dimension | 0 | 2 | 4 |
|---|---|---|---|
| Situation | Missing or unclear | Basic context | Specific, relevant business context |
| Task / ownership | No personal role | Shared role partly clear | Explicit individual responsibility and boundaries |
| Action / reasoning | Unsupported claim | Some logical steps | Ordered evidence-based diagnosis, design and trade-offs |
| EC relevance | Generic HR answer | Mentions EC features | Correctly connects EC data, process, rules/workflow, RBP and dependencies where relevant |
| Result / evidence | No outcome | Qualitative result | Verifiable outcome, defined measure, or transparent evidence plan |
| SME depth | No probe response | Addresses surface follow-up | Explains alternatives, risk, failure modes, governance and learning |
| Integrity | Exaggerated or invented claims | Some assumptions unstated | Clearly distinguishes personal experience, hypothetical actions, and verified facts |

**Coaching interpretation:** A low score identifies the next skill to practice; it does not label the candidate. Ask the learner to improve one dimension, retry the answer, and compare versions.

# Common Weak-Answer Patterns

- **Jumping straight to configuration:** clarify the business outcome and acceptance criteria first.
- **Treating “standard versus custom” as ideology:** evaluate supported fit, lifecycle, risk, and real constraints.
- **Ignoring effective dating:** validate record sequence, history, future changes, and event timing.
- **Testing only the happy path:** cover negative, boundary, security, population, integration, and regression cases.
- **Using “we” to hide ownership:** state what you personally did, what the team did, and who made the decision.
- **Inventing numbers:** use actual evidence or describe how you would measure the result.
- **Assuming feature behaviour:** validate the target release, configuration, and official product documentation.
- **Closing a defect without prevention:** document root cause, recovery evidence, regression, and preventive action.

# Master Framework — Complex EC Requirement to Controlled Delivery

Use this sequence for a new scenario:

**Understand outcome → Decompose process and populations → Model data and effective dates → Assess standard capability → Design rules/workflow/access → Map integrations and reporting → Test positive/negative/boundary cases → Govern and release → Measure outcomes → Improve.**

# Success Criteria

The candidate is ready to progress when they can:

- Answer all 20 questions with a clear STAR structure without reading the model verbatim.
- Make personal ownership and assumptions explicit.
- Connect business requirements to appropriate Employee Central design considerations.
- Explain effective dating, data-model choices, rules/workflows, permissions, and dependencies when relevant.
- Identify upstream/downstream impacts and propose credible validation evidence.
- Defend trade-offs and describe how failures would be contained and prevented.
- Explain outcome measures without fabricating achievements.
- Respond to SME probes with reasoning, alternatives, evidence, risks, and governance.

## Source and Verification Guidance

Treat this pack as a coaching blueprint, not a product configuration specification. Confirm exact feature behaviour, supported capabilities, rule assignments, APIs/integration patterns, and security options against the target Employee Central tenant and current official SAP documentation. Validate local policy and regulatory assertions with qualified specialists. Record the product version, enabled scope, country assumptions, and review status before using answers in a live implementation or production decision.
