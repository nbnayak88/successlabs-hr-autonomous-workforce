# Scenario Category 02 — Employee Central Data Model

## Interview Practice Guide — 20 Scenario-Based Questions, STAR Answers & SME Probes

**Track:** SCALE — School of Career Acceleration  
**Target Role:** Tech Delivery Subject Matter Expert — SAP SuccessFactors Employee Central  
**Scenario Category:** Employee Central Data Model  
**Question IDs:** SCALE-EC-02-Q01 through SCALE-EC-02-Q20

## Learning outcome

Demonstrate how to reason about Employee Central data placement, person and employment concepts, Job Information, effective dating, history, Foundation Object relationships, extensibility, data ownership, security, reporting, integration and data quality.

> **Answer integrity:** STAR responses are illustrative models, not claims about a candidate's personal work. Replace all role, action, tools, scope, and outcome statements with genuine evidence. If you have not personally handled a situation, clearly label your answer as a proposed approach. Do not invent metrics. Validate feature behaviour against the target tenant, enabled scope, release and current official SAP documentation.

## How to practice

Answer each question without reading the model, then compare your answer for business context, personal ownership, reasoning, evidence, result and SME-level trade-offs. Note product-version, configuration or country assumptions explicitly.

---

## Q01 — Choose the Correct Data Structure

### Interview Question
A stakeholder requests a new field for an employee transfer. How do you determine whether the information belongs in Personal Information, Employment Information, Job Information, an organizational object, or an extensible structure?

### STAR Model Answer
- **Situation:** A new information requirement arrives without a clear definition of what the value represents or how it will be used.
- **Task:** Select the appropriate data representation while avoiding duplication, incorrect lifecycle behaviour, and downstream ambiguity.
- **Action:** I would establish business meaning, ownership, scope, change frequency, effective-dating needs, retention, access, reporting, and integration consumers. I would inspect existing standard structures and field semantics first, then consider supported extensibility only if a real gap remains. I would document the decision and validate it with HR process, data, security, and integration owners.
- **Result:** The proposed data placement would be traceable to the business meaning and would include the required lifecycle and consumer controls.

### SAP SuccessFactors Employee Central Example
Compare whether the attribute describes the person, an employment relationship, the employee's job state, or an organizational entity; then verify the available target data model.

### SME Probe
What evidence would persuade you that an existing standard field should not be repurposed?

---

## Q02 — Person, Employment and Job Concepts

### Interview Question
An integration team wants to use one employee identifier as the universal key for a person, an employment relationship, and a job assignment. What would you assess before agreeing?

### STAR Model Answer
- **Situation:** A cross-system design assumes that related but distinct worker concepts can always be represented by a single identifier.
- **Task:** Protect identity and relationship semantics across hiring, rehire, multiple employment scenarios where supported, job changes, and downstream consumers.
- **Action:** I would map the identity concepts actually used in the tenant and target systems, document identifier ownership and cardinality, and examine how each lifecycle event is represented. I would agree stable cross-system keys, effective-date behaviour, and mapping rules with integration and data owners. I would test hires, changes, terminations and rehire or multiple-employment cases only where they are relevant to the configured scope.
- **Result:** The interface contract would preserve the intended identity relationships and handle lifecycle edge cases explicitly.

### SAP SuccessFactors Employee Central Example
Review the configured use of person and employment identifiers and the target system's key requirements rather than assuming that every implementation handles these concepts identically.

### SME Probe
How would you diagnose a duplicate-person issue without merging records prematurely?

---

## Q03 — Effective-Dated Record Design

### Interview Question
A future-dated job change exists, and HR now needs a correction to an earlier date. How do you decide the correct data operation?

### STAR Model Answer
- **Situation:** The employee's timeline contains historical, current, and future records that may interact.
- **Task:** Apply the intended business event without corrupting history or creating an unintended timeline.
- **Action:** I would reconstruct the complete effective-dated history, confirm the intended chronology and business reason, and determine whether the operation should insert, correct, or otherwise manage an existing record using supported behaviour. I would check event reason, rule/workflow effects, downstream timing, and reporting. I would validate before-and-after record states with controlled test cases.
- **Result:** The resulting timeline would match the approved business chronology and have documented downstream implications.

### SAP SuccessFactors Employee Central Example
Use controlled past/current/future Job Information records to validate the intended result in the target tenant.

### SME Probe
What is the risk of testing only the employee's current view?

---

## Q04 — Historical Data Integrity

### Interview Question
A business report shows an employee's current department when it should show the department at the time of a past transaction. How would you investigate?

### STAR Model Answer
- **Situation:** The report may be using current-state information where historical effective-dated information is required.
- **Task:** Determine whether the issue originates in EC records, report logic, data extraction, or downstream transformation.
- **Action:** I would confirm the reporting question and date semantics, compare source record history with the report output, and inspect joins, filters, effective-date selection, and integration/load timing with the report owner. I would isolate a minimal test case and validate both historical and current reporting behaviour before changing the source or consumer.
- **Result:** The root cause would be evidenced, with a correction and regression tests that protect historical accuracy.

### SAP SuccessFactors Employee Central Example
Compare effective-dated source records with the report's selection logic and any replicated data store.

### SME Probe
How can a technically correct current-state extract still be wrong for an audit or workforce trend report?

---

## Q05 — Foundation Object Relationships

### Interview Question
A new department is created but employees cannot select it in a Job Information transaction. What data-model dependencies would you investigate?

### STAR Model Answer
- **Situation:** A required organizational value exists but is not usable in the expected transaction.
- **Task:** Identify whether the cause is object validity, association, effective date, configuration, or permissions.
- **Action:** I would confirm the source of truth and object ownership, inspect validity dates and required relationships, and review associations and dependencies in the applicable data model. I would also compare user access and transaction context. I would fix the verified source/configuration issue through governed change, then test both selection and downstream use.
- **Result:** The organizational value would be available only in the intended context, with relationships and data governance intact.

### SAP SuccessFactors Employee Central Example
Trace the department and related organizational objects, validity, associations, and Job Information field setup in the tenant.

### SME Probe
What distinguishes an association design issue from an effective-date validity issue?

---

## Q06 — Standard Field Versus Extension

### Interview Question
The business asks for a new custom field even though a similar standard field exists. What is your evaluation method?

### STAR Model Answer
- **Situation:** Similar-looking fields could represent different business concepts or lifecycle semantics.
- **Task:** Avoid duplication while ensuring that the chosen field can satisfy the requirement.
- **Action:** I would compare definitions, purpose, availability, effective dating, value constraints, ownership, security, reporting, integrations, and supported configuration. I would verify whether the standard field is semantically correct rather than selecting it by name alone. If an extension is required, I would document the gap, lifecycle, owner, permission model, migration needs, and downstream impacts.
- **Result:** The choice would be justified through business meaning and lifecycle fit, not convenience.

### SAP SuccessFactors Employee Central Example
Use data dictionary and configured metadata in the tenant to confirm the existing field's semantics and usage before proposing an extension.

### SME Probe
What future risks arise from two fields that users treat as interchangeable but have different definitions?

---

## Q07 — MDF and Data Model Boundaries

### Interview Question
A new business process appears to require a custom object. How do you decide whether MDF is appropriate and how it should relate to Employee Central data?

### STAR Model Answer
- **Situation:** The requirement contains information that may not fit an existing standard employee or organizational structure.
- **Task:** Determine whether a supported extensible object is justified and design it with clear relationships and controls.
- **Action:** I would confirm the business concept, lifecycle, ownership, cardinality, effective-dating needs, permissions, workflows, reporting, and integration consumers. I would inspect standard alternatives first, then design the minimum viable object and associations if required. I would review naming, governance, migration, and supportability with the solution owner and verify exact capabilities in the target environment.
- **Result:** The extension would serve a defined purpose and have documented data ownership and lifecycle controls.

### SAP SuccessFactors Employee Central Example
Document the proposed object purpose, fields, associations, security, valid values, and downstream uses before configuration.

### SME Probe
How would you prevent an MDF object from becoming a shadow copy of standard EC data?

---

## Q08 — Data Ownership and Source of Truth

### Interview Question
HR and Finance each claim ownership of an employee organizational attribute, and the values differ across systems. How do you resolve the data ownership conflict?

### STAR Model Answer
- **Situation:** Conflicting values exist because ownership and update responsibilities are not explicit across systems.
- **Task:** Establish an authoritative value and governed synchronization approach.
- **Action:** I would clarify the business meaning and lifecycle, identify who creates and approves the data, examine current process and integration paths, and distinguish system-of-record ownership from downstream use. I would involve accountable business and data governance owners, define change authority, mappings, reconciliation rules, and conflict handling, then validate the agreed approach with representative records.
- **Result:** Ownership, allowed changes, and reconciliation responsibilities would be explicit and auditable.

### SAP SuccessFactors Employee Central Example
For a field shared across EC and connected finance or directory systems, document the authoritative source, replication direction, timing, and error-handling policy.

### SME Probe
What would you do if the designated system of record contains a value that violates an approved business rule?

---

## Q09 — Data Quality Controls

### Interview Question
A new EC report reveals that many employee records contain missing or inconsistent organizational values. What is your plan?

### STAR Model Answer
- **Situation:** Data-quality issues threaten reporting, transactions, and downstream integrations.
- **Task:** Quantify the problem, identify root causes and prevent recurrence.
- **Action:** I would define quality dimensions such as completeness, validity, consistency, uniqueness, and timeliness. I would segment defects by object, population, effective date, and source; identify process/configuration/import causes; agree correction ownership; and prioritize by business impact. I would introduce appropriate preventive validation and monitoring, then track remediation and recurrence.
- **Result:** The team would have a baseline, accountable remediation plan, and measurable ongoing controls rather than a one-off cleanup.

### SAP SuccessFactors Employee Central Example
Profile selected employee and organizational data, investigate the source of invalid values, and test the preventive control without blocking valid transactions.

### SME Probe
How would you distinguish a data-quality rule from a business rule that enforces process policy?

---

## Q10 — Picklists, Valid Values and Consistency

### Interview Question
A picklist value is renamed or retired, and existing employee records and integrations still use the old value. How do you plan the change?

### STAR Model Answer
- **Situation:** A valid-value change may affect records, user experience, reports, interfaces and historical interpretation.
- **Task:** Make the change without silently breaking existing data or downstream mappings.
- **Action:** I would identify current and historical usage, field dependencies, integrations, reports, rules, imports, and governance requirements. I would decide whether the value should be translated, retired, replaced, or remain available for historical purposes based on supported behaviour and policy. I would plan sequencing, mapping/version handling, test current and historical records, and communicate operational impacts.
- **Result:** The value change would be controlled and traceable, with explicit handling for legacy values and downstream consumers.

### SAP SuccessFactors Employee Central Example
Inspect configured picklist usage and verify the supported behaviour for the specific field and environment before updating values.

### SME Probe
Why can a display-label change still break integration or analytics logic?

---

## Q11 — Required Fields and Conditional Data

### Interview Question
The business wants a field mandatory for permanent employees but optional for a different employee group. How do you design the data rule?

### STAR Model Answer
- **Situation:** A field requirement varies by population or business context.
- **Task:** Enforce completeness without blocking valid transactions that legitimately lack the value.
- **Action:** I would confirm the population criteria, data ownership, process stage, exception cases, and the consequences of missing data. I would assess supported configuration and rule options, define clear conditions and messages, and consider effective dating, imports, APIs, and integrations as well as the user interface. I would test qualifying and non-qualifying populations plus boundary cases.
- **Result:** Data validation would align to approved policy and reduce bad data without unnecessarily blocking transactions.

### SAP SuccessFactors Employee Central Example
Validate the configured mandatory/conditional behaviour across relevant transaction paths and interfaces, not only one screen.

### SME Probe
What could happen if the rule is enforced in one entry channel but not another?

---

## Q12 — Data Security and Field Visibility

### Interview Question
A field is visible to an administrator but hidden from the intended HR specialist. How would you investigate without broadening access unnecessarily?

### STAR Model Answer
- **Situation:** A user reports missing data, but access requirements differ across roles.
- **Task:** Identify whether the issue is permissions, target population, field configuration, or the data itself.
- **Action:** I would reproduce with a representative user, compare required actions and population scope with configured permissions, examine field-level controls where supported, and verify that the user meets the relevant group criteria. I would assess any privacy implications and test both intended access and denied access after a minimal governed change.
- **Result:** The access issue would be resolved with evidence while preserving least privilege.

### SAP SuccessFactors Employee Central Example
Compare an approved HR specialist persona with an administrator and an out-of-scope persona on the same record and field.

### SME Probe
Why should you avoid granting broad administrator permissions as a troubleshooting shortcut?

---

## Q13 — Data Model Impact on Reporting

### Interview Question
A new attribute is added to support workforce reporting. What should be evaluated before it is considered ready for use by analytics teams?

### STAR Model Answer
- **Situation:** A new field could be technically available but still lack clear reporting semantics and governance.
- **Task:** Ensure the field produces interpretable, governed, and reliable information for the intended use.
- **Action:** I would define business meaning, granularity, ownership, allowed values, effective-date interpretation, retention, security, and expected refresh timing. I would trace the extraction/replication path, mapping, transformations and report calculations. I would validate sample outputs with business owners and include data-quality and regression checks.
- **Result:** Analytics consumers would receive a governed field with documented semantics and tested lineage.

### SAP SuccessFactors Employee Central Example
Trace the EC field through the configured reporting or replication mechanism and validate how historical and current values are represented.

### SME Probe
How would you detect a semantic mismatch between an EC field and a downstream warehouse column?

---

## Q14 — Data Model and Integration Contract

### Interview Question
The downstream system expects a value that is optional in Employee Central. The integration starts failing when the field is blank. What do you do?

### STAR Model Answer
- **Situation:** The source model permits a state that the receiving system does not handle.
- **Task:** Agree a valid contract and handle missing-value behaviour safely.
- **Action:** I would confirm the field's business meaning, source ownership, valid/nullable states and the target system's actual requirement. I would determine whether the target requirement is justified, whether source data should be corrected, or whether an approved transformation/default/exception path is appropriate. I would document the contract and test blank, populated, invalid, and historical cases with integration owners.
- **Result:** The integration would have an explicit, tested treatment of missing values instead of relying on accidental defaults.

### SAP SuccessFactors Employee Central Example
Test representative EC payloads and target responses, then validate data mapping, error reporting and reconciliation against the actual interface.

### SME Probe
When is adding a default value dangerous because it hides a real data-quality defect?

---

## Q15 — Import and Data Load Readiness

### Interview Question
A bulk import is planned after a data-model update. What controls do you use to protect data integrity?

### STAR Model Answer
- **Situation:** Bulk processing can amplify mapping, validity, dependency, or data-quality defects.
- **Task:** Validate records before load and prove that the resulting business state is correct.
- **Action:** I would confirm field/object requirements, supported import method, reference values, identifiers, effective dates, mandatory fields, permissions, and dependency sequencing. I would profile source data, trial-load a representative sample, reconcile rejected and accepted records, and compare post-load values to approved expectations. I would define remediation and rollback/restore approach according to the actual tool and data operation.
- **Result:** Load readiness would be based on controlled evidence and reconciliation, not merely successful file submission.

### SAP SuccessFactors Employee Central Example
Use the supported import/API path for the relevant object and confirm resulting records, error details, and downstream impact in a non-production environment.

### SME Probe
Which checks must take place after the load even when the import reports success?

---

## Q16 — Duplicate or Conflicting Records

### Interview Question
A data load or integration creates duplicate or conflicting employee information. How do you find the cause and recover safely?

### STAR Model Answer
- **Situation:** Duplicate or contradictory data appears and may affect HR transactions or downstream consumers.
- **Task:** Establish the correct business state and prevent the defect from recurring.
- **Action:** I would identify affected keys and lifecycle events, compare source and target records, review retry/idempotency and mapping behaviour where relevant, and determine whether the issue arose from source duplicates, integration replay, incorrect identifiers, or process design. I would coordinate a governed correction, reconcile affected populations, and improve monitoring or duplicate prevention.
- **Result:** The data would be restored to the approved state with evidence and preventive actions.

### SAP SuccessFactors Employee Central Example
Trace the employee/person identifiers and relevant record history across EC and the integration pathway, based on the actual architecture.

### SME Probe
Why should you not delete suspected duplicates before confirming identity, history, and downstream references?

---

## Q17 — Data Model Change Governance

### Interview Question
A developer proposes changing an existing field or association to meet a new request quickly. What review would you require?

### STAR Model Answer
- **Situation:** A small data-model change could alter existing transaction, reporting, security, or integration behaviour.
- **Task:** Ensure that the change is justified, backward-aware, testable, and governed.
- **Action:** I would assess semantic compatibility, consumers, effective dating, constraints, permissions, migration needs, reporting, integration mappings, and configuration dependencies. I would require a documented impact assessment and decision record, with appropriate peer review and regression coverage. I would sequence deployment and define monitoring or rollback/mitigation based on the change.
- **Result:** The change would proceed only with an understood impact and a controlled acceptance path.

### SAP SuccessFactors Employee Central Example
Review field/object dependencies and the relevant deployment package/configuration process in the environment before promoting the change.

### SME Probe
How do you distinguish a backward-compatible change from a change that silently alters the meaning of existing data?

---

## Q18 — Reconcile Source and Target Data

### Interview Question
EC and a downstream reporting system show different headcount or organizational assignments. How do you approach reconciliation?

### STAR Model Answer
- **Situation:** Two systems report different results, and stakeholders disagree on which is correct.
- **Task:** Identify whether the variance is caused by data, timing, definition, mapping, or reporting logic.
- **Action:** I would align metric definitions and as-of dates, segment records by population and organizational dimension, compare record-level keys, and inspect extraction timing, filters, mapping and transformation. I would classify variances, assign corrections to the appropriate owner, and repeat reconciliation after remediation. I would document accepted timing differences and unresolved issues.
- **Result:** Stakeholders would have a repeatable reconciliation process and clear explanation of residual differences.

### SAP SuccessFactors Employee Central Example
Compare EC source records and downstream records at the same effective date and population boundary, using the real extraction and transformation rules.

### SME Probe
How do you avoid false variances caused by different definitions of active employee or as-of date?

---

## Q19 — Diagnose a Data-Model Defect from Symptoms

### Interview Question
A Job Information transaction fails only for one location and only for future-dated changes. How would you isolate the cause?

### STAR Model Answer
- **Situation:** A narrowly scoped data defect suggests an interaction between population, organizational data, effective date, and configuration.
- **Task:** Identify the causal condition without weakening controls for every employee.
- **Action:** I would compare a successful and failing record, vary one factor at a time, and inspect location validity, organizational relationships, effective-dated references, rule conditions, workflow criteria, permissions, and integration validation. I would isolate a minimal reproduction, confirm the root cause, implement the smallest safe correction, and test adjacent locations and dates.
- **Result:** The resolution would be targeted, evidence-based, and accompanied by regression tests for the affected dimensions.

### SAP SuccessFactors Employee Central Example
Build a controlled test matrix across location, effective date, transaction type, and user role. Verify exact rule and data behaviour in the tenant.

### SME Probe
What test design helps distinguish an interaction defect from two unrelated configuration defects?

---

## Q20 — Defend a Target Data Model to an Architecture Panel

### Interview Question
You must defend an Employee Central data-model proposal to HR, integration, security, analytics, and enterprise architecture stakeholders. What evidence do you present?

### STAR Model Answer
- **Situation:** A proposed data structure affects multiple business and technical domains, each with different success criteria.
- **Task:** Demonstrate that the design represents the business correctly and is supportable across the lifecycle.
- **Action:** I would present business definitions, ownership, entity relationships, identifiers, effective dating, standard-versus-extension rationale, valid values, permission model, integration/reporting lineage, migration approach, data-quality controls, and test evidence. I would identify assumptions and alternative designs, state residual risks, and assign owners to unresolved decisions. I would separate verified tenant behaviour from requirements that still need product or specialist confirmation.
- **Result:** Stakeholders could assess the proposal on traceability, data integrity, security, integration fit, and maintainability rather than on the diagram alone.

### SAP SuccessFactors Employee Central Example
Use a representative employee lifecycle scenario to trace the proposed entities and fields from entry through validation, access, integration, and reporting.

### SME Probe
Which missing evidence would prevent you from approving the data model even if the diagram looks technically sound?

---

# Rapid-Fire SME Probe Bank

1. What question do you ask before adding a field?
2. How do person, employment and job information differ conceptually?
3. Why does effective dating matter?
4. How do you distinguish insert and correction scenarios?
5. What is the role of Foundation Object relationships?
6. When should you consider MDF/extensibility?
7. Who owns the value when systems disagree?
8. How do you measure data quality?
9. Why can a picklist label change affect downstream systems?
10. How do conditional requirements affect import and API channels?
11. How do you prove least-privilege access?
12. How should reporting lineage be documented?
13. What is the difference between successful import and valid business data?
14. How do you investigate duplicates safely?
15. What belongs in a data-model change decision record?

# STAR Answer Quality Rubric

Score each area from 0 to 4 as a coaching aid; it is not a validated hiring assessment.

| Dimension | Strong evidence |
|---|---|
| Situation | Explains the business context, affected population, and why the data issue mattered. |
| Task / ownership | States personal responsibility and decision boundaries honestly. |
| Action / reasoning | Shows ordered analysis of meaning, lifecycle, dependencies, alternatives, and evidence. |
| EC data-model depth | Correctly considers person/employment/job semantics, effective dating, Foundation Objects/MDF, or relevant dependencies. |
| Result / verification | Describes a verifiable outcome, reconciliation, test evidence, or a transparent measurement plan. |
| SME insight | Explains trade-offs, failure modes, security, governance, and what could change the recommendation. |
| Answer integrity | Clearly separates actual personal experience from hypothetical approach and avoids invented metrics. |

# Common Weak-Answer Patterns

- **Choosing fields by label:** validate business meaning, owner, lifecycle, and consumers.
- **Ignoring effective dating:** review past/current/future state and chronology.
- **Creating extensions too early:** assess standard capability and existing structures first.
- **Treating source-of-truth as obvious:** document ownership, authority, and conflict handling.
- **Testing only in the UI:** consider supported imports, APIs, integrations, reports, and security where applicable.
- **Equating successful load with clean data:** reconcile business-level values and relationships.
- **Correcting duplicates without traceability:** validate identity, history, and downstream references first.
- **Inventing outcomes:** report actual evidence or define how the outcome would be measured.

# Master Framework — Employee Central Data Model Reasoning

**Define meaning → Establish ownership → Identify entity and lifecycle → Assess effective dating → Reuse standard structures → Model relationships → Apply security and quality controls → Trace consumers → Test and reconcile → Govern change.**

# Success Criteria

The candidate is ready to progress when they can answer all 20 questions with clear STAR structure, justify data placement, reason about effective-dated history, explain object relationships and source ownership, identify security and downstream impacts, and show how they would validate the result.

## Source and Verification Guidance

This pack is a coaching blueprint, not a substitute for product documentation. Validate exact data-model capabilities, object semantics, effective-dating behaviour, permissions, import/API paths, and reporting/integration behaviour against the target EC tenant and current official SAP documentation. Record relevant version, enabled scope, and assumptions before using the answers for implementation decisions.
