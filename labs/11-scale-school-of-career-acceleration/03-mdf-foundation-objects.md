# Scenario Category 03 — MDF & Foundation Objects

## Interview Practice Guide — 20 Scenario-Based Questions, STAR Answers & SME Probes

**Track:** SCALE — School of Career Acceleration  
**Target Role:** Tech Delivery Subject Matter Expert — SAP SuccessFactors Employee Central  
**Question IDs:** SCALE-EC-03-Q01 through SCALE-EC-03-Q20

## Learning outcome

Demonstrate when and how to reason about Foundation Objects and Metadata Framework (MDF), including business meaning, object selection, effective dating, associations, data ownership, security, integrations, data migration, and lifecycle governance.

> **Answer integrity and verification:** These STAR responses are illustrative models, not claims about your personal experience. Replace all context, action, ownership, tools, and results with genuine evidence. Validate exact object behaviour, availability, relationships, and supported configuration in the target tenant and current official SAP documentation. Product scope and enabled features may change what is possible.

## Practice method

Answer aloud first. Then compare the answer against the model, explain a trade-off, and answer the SME probe. State assumptions and do not invent metrics or hands-on experience.

---

## Q01 — Foundation Object or MDF Object?

### Interview Question
A stakeholder requests a new organizational concept that seems similar to an existing Foundation Object. How do you decide whether to reuse an existing structure, extend it, or introduce a separate MDF object?

### STAR Model Answer
- **Situation:** A new business concept is requested, but the team has not established whether it is an existing organizational concept, an attribute of one, or a separate managed entity.
- **Task:** Select a data structure that represents the business meaning correctly and can be governed across the lifecycle.
- **Action:** I would clarify the definition, ownership, cardinality, lifecycle, effective dating, valid values, user actions, reporting, integrations, and security needs. I would inspect standard structures and current tenant configuration first. If no suitable structure exists, I would evaluate an MDF design with explicit relationships and governance, documenting why reuse is insufficient.
- **Result:** The decision would be grounded in semantic fit and lifecycle requirements, with clear ownership and downstream impact.

### SAP SuccessFactors Employee Central Example
Compare the business meaning and supported usage of the relevant organizational structure with a governed extensible-object option before proposing configuration.

### SME Probe
What evidence would demonstrate that a proposed MDF object duplicates an existing business concept?

---

## Q02 — Foundation Object Association Failure

### Interview Question
An employee's Job Information transaction cannot select the expected department, location, or other organizational value. How would you investigate?

### STAR Model Answer
- **Situation:** A required organizational value is missing from a transaction even though stakeholders believe it exists.
- **Task:** Determine whether the problem is the data, effective validity, association, field setup, or user access.
- **Action:** I would verify the intended source of truth, object status and validity dates, relevant associations and required dependencies, and the employee's transaction context. I would compare access using representative roles and inspect the applicable field configuration. After identifying the cause, I would correct it through governed data/configuration changes and test both selection and downstream behaviour.
- **Result:** The resolution would correct the cause without creating duplicate organizational values or bypassing validation.

### SAP SuccessFactors Employee Central Example
Trace the target organizational object, relevant relationships, validity, field setup, and role access in the target tenant.

### SME Probe
How would you isolate an association issue from an invalid effective date?

---

## Q03 — Design Associations and Cardinality

### Interview Question
A custom business object needs to relate to a legal entity, department, and employee. How would you design and validate the relationships?

### STAR Model Answer
- **Situation:** The business concept involves several entities, and an unclear relationship model could create inconsistent records.
- **Task:** Define relationship semantics and constraints that reflect the business process.
- **Action:** I would clarify cardinality, ownership, lifecycle, whether each relationship is mandatory or optional, effective-date requirements, and how users will create/read/update records. I would review supported association options and constraints in the configured platform, then test valid, invalid, missing-reference, and lifecycle-change cases. I would document the model and the rationale.
- **Result:** The object relationship design would be explicit, testable, and maintainable.

### SAP SuccessFactors Employee Central Example
Create an entity-relationship sketch that identifies each object, association direction, cardinality, and expected validation before implementing the actual supported configuration.

### SME Probe
What can go wrong when the technical association permits more relationships than the business process intends?

---

## Q04 — Effective Dating for Reference Data

### Interview Question
An organizational value changes from a future date. Existing employee records and future transactions may reference it. What do you validate?

### STAR Model Answer
- **Situation:** A change to reference data could affect employee transactions across multiple dates.
- **Task:** Preserve the intended organizational timeline and avoid invalidating current or future processes.
- **Action:** I would confirm the business effective date, inspect related record histories and planned changes, determine how the object and association behave over time in the tenant, and identify affected employee populations, rules, reports, and integrations. I would test before/after dates and exception cases, then document the cutover and communication needs.
- **Result:** The change would have a verified effective-date impact assessment and controlled implementation plan.

### SAP SuccessFactors Employee Central Example
Test representative Job Information records before and after the organizational object's change date and check dependent values.

### SME Probe
Why should you avoid assuming the same effective-dating semantics across every object type?

---

## Q05 — MDF Object Lifecycle and Ownership

### Interview Question
A custom object has been created, but teams disagree on who maintains its records and decides when values are retired. How do you establish governance?

### STAR Model Answer
- **Situation:** The object is technically available but lacks clear business ownership and lifecycle rules.
- **Task:** Establish accountable stewardship so the object remains accurate and usable.
- **Action:** I would document the business owner, data steward, create/update authority, approval requirements, valid-value management, retention, effective dating, support ownership, and consumer responsibilities. I would define change control and reconciliation, then ensure user permissions and operational runbooks reflect the agreed model.
- **Result:** The object would have an owner and governed lifecycle rather than becoming an unmanaged repository.

### SAP SuccessFactors Employee Central Example
Create a concise object stewardship record covering purpose, owner, permitted changes, lifecycle, related objects, integrations, and review cadence.

### SME Probe
Who should decide whether an object value is obsolete: the technical owner or the business data owner?

---

## Q06 — Standard Object Versus Custom Object

### Interview Question
A team wants a custom object to represent a department because the existing structure does not contain one desired attribute. How do you challenge or validate this design?

### STAR Model Answer
- **Situation:** A broad custom-object proposal may duplicate an established organizational concept.
- **Task:** Avoid fragmentation while meeting the genuine information requirement.
- **Action:** I would identify which requirement is missing: an attribute, a relationship, a process, or a separate entity. I would review standard extension options and supported capabilities, assess impacts on reporting, permissions, effective dating, migration, and integration, and compare lifecycle support costs. I would document the rationale and obtain architecture/data-owner review before a separate object is approved.
- **Result:** The selected approach would maintain a coherent data model and avoid unnecessary duplication.

### SAP SuccessFactors Employee Central Example
Evaluate whether the required attribute or association can be addressed within the supported standard organizational model before proposing a separate representation.

### SME Probe
What downstream costs arise if departments are represented in two competing structures?

---

## Q07 — MDF Security and Record Visibility

### Interview Question
A custom object contains sensitive workforce information. Business users must maintain their own records, while HR specialists can review a wider population. How do you design access?

### STAR Model Answer
- **Situation:** The object needs differentiated record and action access.
- **Task:** Protect sensitive data while enabling legitimate process responsibilities.
- **Action:** I would classify the data, identify personas and permitted actions, assess object-level and field-level controls supported in the configured platform, define target populations, and review workflow and reporting exposure. I would use least privilege and test permitted and denied operations with representative personas before release.
- **Result:** The access model would be documented and verified through role-based test evidence.

### SAP SuccessFactors Employee Central Example
Validate create/read/update/delete permissions only as appropriate to the user role and process, including whether unrelated records remain inaccessible.

### SME Probe
How would you prove that a user cannot infer sensitive information through reporting even if direct object access is restricted?

---

## Q08 — Valid Values and Data Validation

### Interview Question
Users create inconsistent values in a custom object because free text is being used for a controlled category. How do you redesign the data quality control?

### STAR Model Answer
- **Situation:** Uncontrolled input is creating inconsistent terminology and unreliable reporting.
- **Task:** Improve consistency without blocking legitimate new business needs.
- **Action:** I would define the business vocabulary and value owner, assess supported validation and controlled-value mechanisms, determine how legacy values should be mapped, and consider imports and integration channels. I would establish an approval path for new values and test valid, invalid, blank, retired, and migrated values.
- **Result:** Values would be more consistent and governable, with a documented transition approach for existing data.

### SAP SuccessFactors Employee Central Example
Use supported picklist or validation capabilities appropriate to the object and verify behaviour in UI and non-UI entry paths.

### SME Probe
How do you introduce a new valid value without breaking historical reports or downstream mapping?

---

## Q09 — MDF Object Not Available to a User

### Interview Question
An object works for an administrator but not for the intended business user. How do you isolate the issue?

### STAR Model Answer
- **Situation:** The object exists and is configurable, yet the operational user cannot perform the expected action.
- **Task:** Identify whether the cause is permissions, target population, object configuration, workflow, or record validity.
- **Action:** I would reproduce the issue using the affected persona, compare required and effective permissions, check target population rules and object/field access, inspect the object's lifecycle and associations, and review the user journey. I would test the minimum correction and negative-access cases without granting broad administrator rights.
- **Result:** The defect would be isolated and corrected with least-privilege validation.

### SAP SuccessFactors Employee Central Example
Compare the same object action under administrator, intended business role, and out-of-scope role, recording the differences.

### SME Probe
Why is “it works for the admin” weak evidence of production readiness?

---

## Q10 — Importing or Migrating MDF Data

### Interview Question
A new MDF object must be populated with data from a legacy repository. What steps protect data integrity?

### STAR Model Answer
- **Situation:** Legacy values must be migrated into a newly governed structure with relationships and constraints.
- **Task:** Load accurate data in dependency order and prove that records and relationships are correct.
- **Action:** I would profile source data, define field mappings and transformation rules, identify mandatory values and reference dependencies, decide how duplicates and retired values are handled, and choose the supported loading mechanism for the target object. I would run a controlled sample, analyze errors, reconcile accepted/rejected records, and validate object relationships, security, reports, and integrations after load.
- **Result:** The migration would have traceable mappings, exception ownership, and business-level reconciliation instead of relying on file success alone.

### SAP SuccessFactors Employee Central Example
Load a representative sample through the approved mechanism for the target object in a non-production environment and verify records and associations.

### SME Probe
What is your response if the record count matches but some object relationships are incorrect?

---

## Q11 — Picklist and Reference-Value Change

### Interview Question
The business wants to retire a value used by an MDF object, but legacy records and downstream systems still reference it. What do you do?

### STAR Model Answer
- **Situation:** A reference value is no longer preferred, but it has historical and integration dependencies.
- **Task:** Manage the lifecycle change without losing historical meaning or breaking consumers.
- **Action:** I would identify record usage, effective dates, reports, rules, integrations, and legal/business retention needs. I would choose a supported retirement or mapping approach, document the crosswalk, test historical and current use, and coordinate consumer changes. I would define ownership for residual records and monitor the transition.
- **Result:** The value change would be governed, traceable, and compatible with approved historical and downstream requirements.

### SAP SuccessFactors Employee Central Example
Validate how the configured object and consuming systems represent retired or replacement values before applying changes.

### SME Probe
When is retaining a legacy value safer than rewriting historical records?

---

## Q12 — Object Association and Reporting Failure

### Interview Question
A report cannot correctly connect MDF records to the employee or organizational entity they describe. How do you diagnose the issue?

### STAR Model Answer
- **Situation:** Object records exist, but reporting relationships are incomplete, ambiguous, or incorrectly interpreted.
- **Task:** Determine whether the data relationship, report join, effective date, or transformation is responsible.
- **Action:** I would define the expected relationship and grain, inspect actual keys and associations, compare source and report values, and review effective-date logic and any replication layer. I would classify missing references versus reporting-logic defects, correct the proper layer, and test representative records.
- **Result:** The reporting output would be aligned with the data model and its intended business meaning.

### SAP SuccessFactors Employee Central Example
Trace a record from the object through the configured relationship and report mapping, and check whether the expected key is maintained and valid.

### SME Probe
How do you prevent a report join from multiplying records when the relationship is not one-to-one?

---

## Q13 — Object Dependency and Creation Sequence

### Interview Question
A migration fails because a custom record references an organizational value that has not been loaded yet. How do you plan dependency management?

### STAR Model Answer
- **Situation:** Data load order does not respect object dependencies.
- **Task:** Establish a safe sequence and clear failure recovery for dependent records.
- **Action:** I would map dependencies and identify parent/reference records, define an ordered load plan, validate prerequisite records before dependent loads, and specify how rejected records are corrected and retried. I would include reconciliation and repeatability checks so a retry does not create duplicates.
- **Result:** The load process would follow an explicit dependency graph and have controlled recovery steps.

### SAP SuccessFactors Employee Central Example
Build a dependency sequence for organizational/reference records and the dependent custom objects, and test missing-reference handling.

### SME Probe
How would you design a retry so that previously accepted records are not duplicated?

---

## Q14 — MDF Versus Business Rule Logic

### Interview Question
A requirement asks for a new object because the team wants to store the result of a calculation that could potentially be derived from existing information. How do you decide where the logic and data belong?

### STAR Model Answer
- **Situation:** The proposed data model may store redundant derived values rather than representing a distinct business entity.
- **Task:** Choose a maintainable approach that preserves correctness and traceability.
- **Action:** I would clarify whether the value is a persistent business record, an attribute, a derived result, or a transaction decision. I would assess calculation timing, need for history, auditability, consumers, performance, and supported rule/reporting capabilities. I would compare storing versus deriving the value and document recalculation, effective-date, and data-quality implications.
- **Result:** The design would avoid unnecessary duplication or stale derived values while meeting the reporting and process need.

### SAP SuccessFactors Employee Central Example
Evaluate standard fields/rules or supported calculated/reporting mechanisms against a separate MDF record, based on actual requirements and platform capabilities.

### SME Probe
What risks arise if a stored calculated value is not refreshed when its source data changes?

---

## Q15 — Avoid an MDF “Shadow System”

### Interview Question
Over time, teams have created several MDF objects that duplicate employee, department, and location details. How would you simplify the design safely?

### STAR Model Answer
- **Situation:** Custom objects duplicate existing concepts and create multiple sources of conflicting information.
- **Task:** Rationalize the data model while protecting current processes and historical records.
- **Action:** I would inventory objects, owners, fields, relationships, usage, integrations, reports, and access. I would identify the authoritative source for each concept, map dependencies, and prioritize duplicates by risk and business impact. I would design a phased convergence or retirement plan with data reconciliation, consumer migration, stakeholder approval, and rollback/contingency steps appropriate to the change.
- **Result:** The organization would have a governed path toward fewer competing definitions and clearer accountability.

### SAP SuccessFactors Employee Central Example
Create an object inventory and dependency map before retiring or replacing any custom object.

### SME Probe
What evidence is required before declaring a custom object safe to retire?

---

## Q16 — Transport and Environment Differences

### Interview Question
An MDF object behaves differently in test and production after a configuration promotion. How do you analyze the difference?

### STAR Model Answer
- **Situation:** A change works in one environment but not another, making environment/configuration drift a possible cause.
- **Task:** Isolate the difference without applying an uncontrolled production fix.
- **Action:** I would compare the relevant object metadata/configuration, permissions, associations, valid values, dependencies, feature settings, and data setup between environments. I would reproduce the issue, identify any missing prerequisite or environment-specific assumption, and follow the approved correction and deployment procedure. I would include a verification checklist for future promotions.
- **Result:** The issue would be resolved through a controlled environment comparison, with reusable deployment checks.

### SAP SuccessFactors Employee Central Example
Compare the exact supported configuration and reference data in the two tenants rather than assuming the object definition alone was transported identically.

### SME Probe
How do you prevent a manual production correction from creating configuration drift?

---

## Q17 — API or Integration Access to MDF Data

### Interview Question
An integration needs to read or maintain MDF records. What must you validate before confirming the interface design?

### STAR Model Answer
- **Situation:** A downstream process depends on custom object data and requires a reliable, authorized access path.
- **Task:** Ensure the interface supports the needed operations and behaves safely for errors, duplicates, and changes.
- **Action:** I would confirm the object's supported API/integration exposure in the target release, authentication and authorization model, fields and relationships exposed, effective-dating semantics, paging/volume, error responses, retry/idempotency, monitoring, and data minimization. I would test representative create/read/update and failure cases only for operations actually supported and required.
- **Result:** The interface would have an explicit contract and appropriate control evidence before production use.

### SAP SuccessFactors Employee Central Example
Verify available object/API behaviour with the official documentation and configured tenant, then exercise the exact operation and authorization scope in a non-production environment.

### SME Probe
What would you do if an operation appears available in documentation but is disabled or restricted in the target environment?

---

## Q18 — Auditability and Change History

### Interview Question
An auditor asks who changed a critical custom object value, why it changed, and which records were affected. How would you prepare the evidence?

### STAR Model Answer
- **Situation:** A key business value affects decisions, but its ownership and change evidence may be spread across systems or processes.
- **Task:** Demonstrate change accountability and traceability.
- **Action:** I would determine which audit/history capabilities are actually enabled and applicable, collect approved change records, effective dates, user/action evidence, approvals, and related business transactions, and correlate them with downstream changes where needed. I would identify gaps honestly and recommend stronger governance, logs, and periodic review if evidence is incomplete.
- **Result:** The response would distinguish available evidence from assumptions and define remediation for any auditability gaps.

### SAP SuccessFactors Employee Central Example
Check the actual history/audit facilities and change-management records available for the configured object and related transaction.

### SME Probe
How would you respond if the required history was not captured and cannot be reconstructed reliably?

---

## Q19 — Performance, Volume and Maintainability

### Interview Question
A custom object and its associations are increasingly used by integrations and reports. The team fears the design will become difficult to maintain. What would you assess?

### STAR Model Answer
- **Situation:** A once-small data model is becoming central to multiple processes and consumers.
- **Task:** Ensure continued fitness, supportability, and controlled change as usage grows.
- **Action:** I would quantify consumers, transaction volume, query/report patterns, failure/rework, governance workload, and dependency complexity. I would review field/object necessity, duplication, relationship design, access requirements, and available platform limits using current documentation and actual observations. I would prioritize simplification, monitoring, and ownership improvements based on evidence rather than speculate about performance.
- **Result:** The team would have a risk-based improvement plan grounded in actual usage and verified platform constraints.

### SAP SuccessFactors Employee Central Example
Inventory integrations and reports consuming the object, test representative workloads within supported guidance, and prioritize the actual bottlenecks found.

### SME Probe
How would you distinguish a data-model problem from an inefficient downstream query or integration implementation?

---

## Q20 — Defend the MDF/Foundation Object Design

### Interview Question
You are asked to defend an Employee Central extension design before HR, security, data governance, integration, and enterprise architecture stakeholders. What would you present?

### STAR Model Answer
- **Situation:** The proposed object affects multiple domains and needs a design decision that will remain supportable over time.
- **Task:** Demonstrate the rationale, controls, dependencies, and evidence for the design.
- **Action:** I would present the business definition, standard-capability assessment, entity and relationship model, effective-dating needs, ownership, access model, valid-value governance, migration approach, reporting/integration lineage, testing plan, and operational owner. I would compare alternatives, identify residual risks, and label any product-version or tenant behaviour that still requires verification.
- **Result:** Stakeholders could make a traceable decision based on business fit, data integrity, security, integration, and lifecycle supportability.

### SAP SuccessFactors Employee Central Example
Walk through one real or controlled scenario from object creation/maintenance through association validation, authorization, reporting, and downstream use.

### SME Probe
Which unresolved issue would be a release blocker, and which could be accepted with a documented mitigation?

---

# Rapid-Fire SME Probe Bank

1. What is the first question before creating an MDF object?
2. How do you distinguish a Foundation Object concept from a separate business entity?
3. Why do cardinality and association direction matter?
4. How do you test effective-dated reference data?
5. Who owns object lifecycle and value retirement?
6. What makes an object a duplicate of standard EC data?
7. How do you prove least-privilege object access?
8. How should invalid values be governed?
9. Why is administrator testing insufficient?
10. How do you reconcile a data load beyond record counts?
11. How do you handle legacy values?
12. What causes report joins to multiply records?
13. How do you manage object dependency sequencing?
14. When should derived information not be stored?
15. What evidence is required before retiring a custom object?

# STAR Answer Quality Rubric

Score each dimension 0–4 as a coaching aid, not as a validated hiring assessment.

| Dimension | Strong evidence |
|---|---|
| Situation | Describes the business need and why object design mattered. |
| Task / ownership | States personal responsibility and decision boundaries honestly. |
| Action / reasoning | Demonstrates standard-first analysis, relationship/lifecycle thinking, and evidence. |
| EC/MDF depth | Connects the design to supported object capabilities, associations, permissions, and consumers. |
| Result / verification | Identifies validation, reconciliation, or measurable evidence without invented claims. |
| SME insight | Addresses failure modes, alternatives, governance, security, and residual risk. |
| Answer integrity | Separates direct experience from a proposed approach and avoids fabricated metrics. |

# Common Weak-Answer Patterns

- Creating an object before checking standard capability.
- Duplicating an existing organizational or employee concept.
- Designing relationships without cardinality or lifecycle clarity.
- Ignoring effective dates, existing data, or downstream consumers.
- Relying on administrator access as proof.
- Treating a successful import as proof of correct business relationships.
- Retiring values or objects without tracing usage.
- Assuming all MDF/API features behave identically across releases or tenants.
- Claiming audit evidence or outcomes that have not been verified.

# Master Framework — Foundation Object & MDF Decisions

**Define business concept → Check standard model → Determine entity and lifecycle → Design associations → Govern values and ownership → Apply security → Map consumers → Plan migration → Test/reconcile → Operate and evolve.**

# Success Criteria

The learner can answer all 20 scenarios in STAR format, explain why a structure is appropriate, defend its relationships and lifecycle, identify security and integration/reporting implications, and describe the evidence required to safely maintain or retire it.

## Source and Verification Guidance

This is an interview coaching pack, not a configuration specification. Validate current support for object types, associations, effective dating, permissions, APIs, imports, audit/history, and any platform limits with the target tenant and current official SAP documentation. Record product version, enabled scope, and assumptions before using the design in implementation.
