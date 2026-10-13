# Scenario Category 11 — Data Migration & Imports

## Interview Practice Guide — 20 Scenario-Based Questions, STAR Answers & SME Probes

**Track:** SCALE — School of Career Acceleration  
**Target Role:** Tech Delivery Subject Matter Expert — SAP SuccessFactors Employee Central  
**Question IDs:** SCALE-EC-11-Q01 through SCALE-EC-11-Q20

## Learning outcome

Plan and govern Employee Central data migration and imports through source profiling, mapping, effective dating, dependency sequencing, controlled loads, error handling, reconciliation, security, cutover, and evidence-based acceptance.

> **Answer integrity and product accuracy:** STAR answers are illustrative models, not claims about personal experience. Adapt them truthfully. Validate supported import/API methods, object-specific requirements, limits, and recovery capabilities against the target tenant and current official SAP documentation. A successful file/job status alone does not prove business-data correctness.

---

## Q01 — Migration Scope and Data Ownership

### Interview Question
A program is moving worker and organizational data into Employee Central from multiple legacy systems. How do you establish migration scope and accountability?

### STAR Model Answer
- **Situation:** Multiple sources contain overlapping employee and organizational data with differing quality and ownership.
- **Task:** Define which data is in scope, who owns it, and what evidence proves it is ready.
- **Action:** I would inventory entities, fields, source systems, record volumes, history requirements, data owners, target structures, and consumers. I would define scope boundaries, retention/migration decisions, assumptions, and accountable owners. I would agree acceptance and reconciliation criteria with HR, data, security, and integration stakeholders.
- **Result:** The program would have a governed migration scope and clear ownership for decisions, remediation, and sign-off.

### SAP SuccessFactors Employee Central Example
Create a data-object inventory for the agreed worker/person, employment/job, and organizational structures actually in scope.

### SME Probe
What do you do when two legacy systems both claim to be the source of truth?

---

## Q02 — Source Data Profiling

### Interview Question
Initial profiling discovers missing values, invalid reference data, and inconsistent employee identifiers. How do you prepare the data for migration?

### STAR Model Answer
- **Situation:** Source defects could cause rejected imports, incorrect relationships, or misleading downstream data.
- **Task:** Quantify defects, prioritize remediation, and establish readiness criteria.
- **Action:** I would profile completeness, validity, uniqueness, consistency, and effective dates. I would segment defects by source, entity, population, impact, and owner; define cleansing or approved exception paths; and track remediation against agreed thresholds. I would test whether controls prevent the same defects from re-entering the migration dataset.
- **Result:** Readiness would be based on measurable data quality and accountable exception handling rather than informal assurance.

### SAP SuccessFactors Employee Central Example
Profile employee and organizational source records against target mandatory values and valid reference data confirmed for the configured EC model.

### SME Probe
Which defects can be corrected through a governed transformation, and which require a business owner decision?

---

## Q03 — Source-to-Target Mapping

### Interview Question
Legacy employee fields do not map one-to-one to the Employee Central data model. How do you create a defensible mapping?

### STAR Model Answer
- **Situation:** The legacy model represents concepts differently from the target and may contain fields with ambiguous meanings.
- **Task:** Produce a mapping that preserves business semantics and target lifecycle requirements.
- **Action:** I would define each source and target field, meaning, owner, transformations, value domain, effective dating, mandatory conditions, and downstream use. I would confirm mappings with business/data owners, document unresolved assumptions, and test representative records including exceptions. I would use standard target structures where appropriate and only introduce extensions when a justified gap remains.
- **Result:** The mapping would be reviewable, testable, and traceable from source meaning to target representation.

### SAP SuccessFactors Employee Central Example
Map representative legacy employee/job fields to the configured EC model and document transformations and valid values.

### SME Probe
How would you handle a legacy field with no exact target equivalent?

---

## Q04 — Identifier Strategy and Duplicate Records

### Interview Question
Source systems use different identifiers for the same worker, and some identifiers have been reused. How do you prevent duplicate or mislinked records?

### STAR Model Answer
- **Situation:** Identifier inconsistencies create identity resolution and relationship risks during migration.
- **Task:** Establish reliable matching rules and preserve the correct person/employment relationships.
- **Action:** I would profile key uniqueness and reuse, identify authoritative matching attributes, and define deterministic matching and exception review with data owners. I would not merge or discard records based on a single weak attribute. I would test duplicates, name changes, rehires, and other relevant edge cases under the approved identity policy.
- **Result:** Records would be linked through governed evidence, with ambiguous cases routed for resolution instead of guessed.

### SAP SuccessFactors Employee Central Example
Create a controlled matching/exceptions register and verify the resulting identifiers and relationships in test migration loads.

### SME Probe
What should happen when two records match on name and date of birth but other identifiers conflict?

---

## Q05 — Effective-Dated History Migration

### Interview Question
The business requires historical job changes and future-dated transactions to be preserved. What do you include in the migration design?

### STAR Model Answer
- **Situation:** The source holds multiple records per employee across past, current, and future states.
- **Task:** Preserve the intended chronology and make the history usable in the target.
- **Action:** I would define the required history window, record granularity, effective-date semantics, sequence handling, and correction rules. I would map event reasons and dependencies where appropriate, test same-date and overlapping records, and reconcile the final target timeline with the approved source history. I would confirm the supported import behaviour for the relevant object.
- **Result:** History would be accepted based on timeline correctness and business interpretation, not just record counts.

### SAP SuccessFactors Employee Central Example
Migrate a representative employee with historical, current, and future-dated Job Information records and compare resulting history in EC.

### SME Probe
Why can a chronologically sorted file still produce an incorrect employee timeline?

---

## Q06 — Foundation Object Dependency Sequence

### Interview Question
Employee records reference departments, locations, job classifications, and other values that have not yet been loaded. How do you sequence the migration?

### STAR Model Answer
- **Situation:** Dependent records cannot be created or validated because prerequisite reference data is missing.
- **Task:** Establish a safe load order and manage failures without duplicating accepted data.
- **Action:** I would map dependencies, identify authoritative prerequisite objects, and order load stages accordingly. I would validate references before loading dependents, separate source defects from sequencing failures, and define retry/exception handling. I would reconcile reference objects and their employee relationships after each stage.
- **Result:** The migration would follow a documented dependency plan with predictable recovery.

### SAP SuccessFactors Employee Central Example
Create a dependency graph for the organizational/reference objects and dependent employee records defined in the target EC data model.

### SME Probe
How do you identify circular or unresolved dependencies before a cutover load?

---

## Q07 — Mandatory Fields and Conditional Requirements

### Interview Question
Some target fields are mandatory only for specific populations or transaction types. How do you design migration transformations without inventing data?

### STAR Model Answer
- **Situation:** Legacy records lack values that may be required in the target under certain conditions.
- **Task:** Produce valid target records while preserving data integrity.
- **Action:** I would confirm the conditional rule and population scope with the data owner, determine if an authoritative source or approved derivation exists, and classify records that need business remediation. I would not insert arbitrary defaults merely to pass validation. I would test the transformation for in-scope and out-of-scope cases and retain a traceable exception report.
- **Result:** Migrated values would be valid and explainable, with unresolved cases handled through approved business decisions.

### SAP SuccessFactors Employee Central Example
Validate the field requirement and import behaviour for the configured object and transaction scope before creating transformation logic.

### SME Probe
What risks arise when a default value hides the fact that source data is missing?

---

## Q08 — Import Method Selection

### Interview Question
The team is choosing a supported import/API method for a large EC data load. How do you select the approach?

### STAR Model Answer
- **Situation:** Multiple data-entry mechanisms may exist, but they can differ in scope, validation, volume, permissions, and operational behaviour.
- **Task:** Choose a method appropriate to the object, data volume, governance, and recovery needs.
- **Action:** I would confirm current supported methods for the target object and release, requirements for effective-dated data, required operations, volume and file constraints, security, feedback/errors, retry, and audit evidence. I would run a controlled proof of concept and compare output/reconciliation. I would not assume an import tool supports every object or transaction.
- **Result:** The selected method would be justified by verified capability and tested operational fit.

### SAP SuccessFactors Employee Central Example
Validate available import or API options for the exact entity and tenant using current official documentation.

### SME Probe
What evidence do you need beyond the documentation page to approve the method for this project?

---

## Q09 — Trial Load and Error Handling

### Interview Question
The first test load rejects a large percentage of records. How do you turn the result into a productive remediation cycle?

### STAR Model Answer
- **Situation:** Rejections reveal mapping, dependency, data quality, or target validation issues.
- **Task:** Classify the errors, prioritize root causes, and produce a corrected repeatable load.
- **Action:** I would group errors by type, field, source pattern, and dependency; distinguish systemic mapping defects from isolated source issues; assign owners; and correct the upstream layer where appropriate. I would rerun a representative sample first, track reopened errors, and preserve accepted/rejected record status to ensure safe retry.
- **Result:** Remediation would reduce recurring error classes and improve load readiness with traceable evidence.

### SAP SuccessFactors Employee Central Example
Use import feedback from the actual tool to build an exception register with record key, error category, owner, correction and retest outcome.

### SME Probe
How do you prioritize errors when a small number of invalid records have very high business impact?

---

## Q10 — Reconciliation Beyond Record Counts

### Interview Question
The import reports that all expected records were accepted, but HR finds incorrect values and relationships. What reconciliation do you perform?

### STAR Model Answer
- **Situation:** Technical acceptance does not guarantee correct business content.
- **Task:** Verify record identity, critical fields, relationships, chronology, and downstream readiness.
- **Action:** I would reconcile by stable keys and business dimensions, compare critical source-to-target values, validate effective-dated sequences and object associations, and inspect rejected/omitted/duplicate cases. I would sample high-risk records and automate repeatable comparisons where approved. I would document residual differences and require business acceptance rather than declaring success based on counts.
- **Result:** Migration acceptance would be based on semantic accuracy and traceable exception handling.

### SAP SuccessFactors Employee Central Example
Compare selected source and target employee histories, organizational references, required fields, and agreed key business attributes.

### SME Probe
Which fields or relationships deserve 100% reconciliation rather than sampling?

---

## Q11 — Privacy and Secure Migration Files

### Interview Question
Migration files contain sensitive employee and compensation information and are being shared through broad team channels. How do you improve handling?

### STAR Model Answer
- **Situation:** Sensitive data is exposed to unnecessary recipients or stored without clear retention/access controls.
- **Task:** Enable migration work while minimizing data exposure.
- **Action:** I would classify data, restrict access to authorized roles, use approved encrypted storage/transfer, minimize fields in working extracts, and define retention/deletion rules with security and privacy owners. I would use synthetic/masked data for routine testing when feasible and document incident handling for misdirected files.
- **Result:** Migration would operate under a clear data-handling control model with accountable access and retention.

### SAP SuccessFactors Employee Central Example
Prepare a field-minimized migration test set and restrict real employee extracts to the approved migration workspace and roles.

### SME Probe
What is your response if a file containing sensitive employee data has already been sent to the wrong recipient?

---

## Q12 — Rehearse Cutover and Final Load

### Interview Question
A cutover requires a final delta load after source systems have continued to change. How do you ensure completeness?

### STAR Model Answer
- **Situation:** The migration snapshot may become stale before target cutover completes.
- **Task:** Move the final changes safely into the target and reconcile them with the agreed source-of-truth point.
- **Action:** I would define freeze/watermark strategy, last extraction point, delta criteria, change capture limitations, sequencing, validation, retry, and the responsible approvers. I would rehearse the cutover, include changes made during the transition window, reconcile the final population and critical fields, and define go/no-go and contingency criteria.
- **Result:** Cutover completion would be based on a proven final data state, not simply successful execution of the last file.

### SAP SuccessFactors Employee Central Example
Rehearse the actual extraction/delta method and compare source changes around the cutover boundary with target records.

### SME Probe
What if the source cannot be frozen and the integration cannot reliably detect every change since the snapshot?

---

## Q13 — Rollback and Recovery Planning

### Interview Question
A load introduces incorrect organizational values and the cutover team proposes reloading the original file. What do you assess first?

### STAR Model Answer
- **Situation:** The target contains incorrect data, but reload may overwrite valid changes or create further inconsistencies.
- **Task:** Choose a safe, authorized correction or recovery approach.
- **Action:** I would identify affected records, distinguish inserts from updates and other operations, review audit/backup and approved recovery options, and assess downstream processing since the load. I would coordinate with data owners to determine whether to correct, reverse, restore, or selectively reload using supported procedures. I would test the selected method and reconcile affected records afterward.
- **Result:** Recovery would be controlled and scoped, with evidence of restored business state and no unreviewed collateral changes.

### SAP SuccessFactors Employee Central Example
Use the actual supported recovery method and confirm consequences for record history and connected systems before execution.

### SME Probe
Why is reloading the original file not always a safe rollback?

---

## Q14 — Incremental Load and Idempotency

### Interview Question
A migration step is rerun after a timeout, and the team is unsure which records were committed. How do you avoid duplicate or contradictory data?

### STAR Model Answer
- **Situation:** A partial failure leaves uncertain processing state.
- **Task:** Establish accepted records and make rerun behaviour safe.
- **Action:** I would retrieve available job/error status, reconcile target records using stable keys and timestamps, and classify accepted, rejected, and uncertain records. I would verify the operation semantics and whether repeat execution is safe, then rerun only the controlled scope under an approved plan. I would record evidence and add checkpoint/reconciliation controls for future batches.
- **Result:** Reprocessing would be based on confirmed state rather than blindly rerunning the full dataset.

### SAP SuccessFactors Employee Central Example
Simulate an interrupted load and verify the behavior of repeated record submission using the actual load method and object.

### SME Probe
What must be confirmed when an operation is an update versus a create?

---

## Q15 — Mapping Event Reasons and Legacy Values

### Interview Question
Legacy systems use different action codes for hire, transfer, promotion, and termination. How do you map them to the target consistently?

### STAR Model Answer
- **Situation:** Source action codes carry business meaning that may not map one-to-one to the target taxonomy.
- **Task:** Preserve the semantics needed for lifecycle processing, reporting, and downstream integrations.
- **Action:** I would build a code crosswalk with HR data/process owners, define handling for unknown or ambiguous codes, and assess rules, effective dating, workflows, and consumer impacts. I would test each mapping with representative records and validate historical and downstream interpretation before approving the transformation.
- **Result:** The code mapping would be governed, documented, and traceable to business meaning.

### SAP SuccessFactors Employee Central Example
Map legacy lifecycle/action values to the configured target event-reason model only after confirming the target configuration and business policy.

### SME Probe
What should happen when two legacy codes appear similar but imply different downstream treatment?

---

## Q16 — Migration Impacts on RBP and Integration

### Interview Question
After migration, some employees are missing from reports and some users cannot access the records as expected. What do you check?

### STAR Model Answer
- **Situation:** The load may have created data but not the relationships or attributes required for expected access and consumption.
- **Task:** Determine whether the issue is data, security, reporting, or integration.
- **Action:** I would compare affected records with approved mappings and target expectations, inspect organizational/group-driving attributes, identifiers, effective dates, and valid reference relationships, and test user permissions and consumer outputs. I would identify whether records were incomplete, filtered, inaccessible, or not replicated, and assign remediation to the responsible layer.
- **Result:** Post-load issues would be corrected based on evidence, with regression checks for access and consumer completeness.

### SAP SuccessFactors Employee Central Example
Trace a migrated employee from source values through EC record relationships, RBP target population, and the actual downstream report/interface.

### SME Probe
How can missing organizational data create an access issue even when the employee record exists?

---

## Q17 — Cutover Reconciliation and Sign-Off

### Interview Question
The technical team says migration is complete, but HR has not reviewed exceptions. What evidence is required for sign-off?

### STAR Model Answer
- **Situation:** Technical loading has finished, but business acceptance and unresolved data quality are not fully evidenced.
- **Task:** Establish a go/no-go decision based on completeness, accuracy, controls, and accountable acceptance.
- **Action:** I would present source/target reconciliation, critical-field checks, history and relationships, rejected/omitted/duplicate records, resolved and unresolved exceptions, downstream validation, security checks, and business-owner sign-off. I would compare results with predefined thresholds and ensure residual risks have explicit owners and approvals.
- **Result:** Sign-off would reflect the actual target data state and business acceptance rather than the end of a technical job.

### SAP SuccessFactors Employee Central Example
Use the signed migration reconciliation and exception register for the actual objects and populations in scope.

### SME Probe
Who should accept residual data risk, and what evidence should accompany that decision?

---

## Q18 — Data Migration Metrics and Readiness

### Interview Question
Leadership asks whether the data migration is ready for cutover. Which measures and thresholds do you propose?

### STAR Model Answer
- **Situation:** The team needs a transparent readiness view rather than a subjective green status.
- **Task:** Define meaningful migration quality and operational indicators.
- **Action:** I would agree measures for record completeness, critical-field accuracy, duplicate rate, reference relationship validity, exception count/severity, rejected records, reconciliation variance, and resolution age. I would define denominator, population, source point, target point, and thresholds with business owners; verify metric reliability; and present unresolved risk explicitly.
- **Result:** Readiness would be judged against agreed evidence and thresholds, including exceptions that cannot be safely accepted.

### SAP SuccessFactors Employee Central Example
Build a migration scorecard using the actual source and target reconciliation data, with clear definitions and owner sign-off.

### SME Probe
Why can a high overall success percentage still conceal a cutover blocker?

---

## Q19 — Stakeholder Challenge to Data Remediation

### Interview Question
The business wants to load inconsistent data now and fix it after go-live to avoid delay. How do you respond?

### STAR Model Answer
- **Situation:** Schedule pressure encourages deferring data defects into production.
- **Task:** Separate acceptable exceptions from defects that threaten business, payroll, security, compliance, or downstream processing.
- **Action:** I would quantify and classify defects by impact, define the consequences of each, and identify safe workaround, containment, and owner only where appropriate. I would compare remediation time and downstream risk, present evidence to the decision owner, and require explicit acceptance for any allowed residual issue. I would block or escalate critical defects according to agreed go/no-go criteria.
- **Result:** The decision would balance timing and risk transparently, without disguising critical quality gaps as post-go-live tasks.

### SAP SuccessFactors Employee Central Example
Use the migration issue register to demonstrate which data defects affect transactions, access, reporting, or downstream consumers.

### SME Probe
What makes a data defect a cutover blocker rather than an acceptable post-go-live remediation?

---

## Q20 — Defend the Migration Strategy

### Interview Question
You must defend the EC migration strategy to HR leadership, data governance, security, integration, testing, and operations. What evidence pack do you present?

### STAR Model Answer
- **Situation:** Migration affects employee records, organizational dependencies, downstream processing, and operational readiness.
- **Task:** Demonstrate that data will move accurately, securely, and recoverably.
- **Action:** I would present scope and ownership, source-to-target mappings, profiling, cleansing, dependency sequencing, import method rationale, trial-load results, effective-date/history treatment, reconciliation, privacy/access controls, cutover and recovery approach, exception register, test evidence, and sign-off criteria. I would call out unsupported assumptions and unresolved risks explicitly.
- **Result:** Stakeholders could evaluate the plan against traceable requirements, validated data, and a controlled recovery strategy.

### SAP SuccessFactors Employee Central Example
Walk through an end-to-end rehearsal from source extraction to EC target record, reconciliation, downstream validation, and signed business acceptance.

### SME Probe
Which evidence gap would prevent you from recommending go-live even if all imports completed successfully?

---

# Rapid-Fire SME Probe Bank

1. Who owns migration data decisions?
2. How do you profile data readiness?
3. What makes a mapping defensible?
4. How do you resolve duplicate identifiers?
5. What does effective-dated history require?
6. Why does object dependency sequencing matter?
7. How should missing mandatory values be handled?
8. How do you select a supported load method?
9. How do you prioritize rejections?
10. Why are row counts insufficient?
11. How should sensitive migration files be handled?
12. How do you capture final deltas?
13. Why is reloading not always rollback?
14. What makes a rerun safe?
15. Who should sign off residual data risk?

# STAR Answer Quality Rubric

Score each dimension from 0 to 4 for coaching, not as a validated hiring assessment.

| Dimension | Strong evidence |
|---|---|
| Situation | Identifies migration scope, source conditions, and business risk. |
| Task / ownership | Defines accountable role and decision authority. |
| Action / reasoning | Shows mapping, dependency, effective-date, security, and reconciliation reasoning. |
| EC/migration depth | Considers target structures, supported load method, record history, and downstream impacts. |
| Result / evidence | Uses verified reconciliation or an honest measurement plan without invented metrics. |
| SME insight | Explains cutover risks, recovery, exceptions, and accountable sign-off. |
| Integrity | States product/version assumptions and separates experience from hypothetical approach. |

# Common Migration Anti-Patterns

- Loading before ownership and mapping are agreed.
- Treating record counts as proof of correct data.
- Using arbitrary defaults to force required fields through.
- Ignoring effective-dated history and dependency sequence.
- Re-running full files after uncertain partial processing.
- Sharing sensitive employee extracts broadly.
- Declaring migration complete before downstream and access validation.
- Accepting critical defects without accountable risk acceptance.
- Calling technical completion business readiness.

# Master Framework — Migration to Verified Data State

**Scope and ownership → Profile → Map → Cleanse → Sequence dependencies → Trial load → Reconcile → Fix/retest → Rehearse cutover → Sign-off → Monitor and improve.**

# Success Criteria

The candidate can answer all 20 scenarios in STAR format, justify the load strategy, manage mapping and dependency risks, validate historical and current data, explain safe reruns/recovery, and defend go/no-go decisions with business-level evidence.

## Source and Verification Guidance

This is an interview coaching blueprint, not a load-runbook for a specific tenant. Validate supported import/API options, object-specific requirements, limits, effective dating, audit, and recovery behaviour against the target EC tenant and current official SAP documentation. Record product/version and enabled scope before execution.
