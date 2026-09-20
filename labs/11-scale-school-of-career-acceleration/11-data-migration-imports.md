# Scenario Category 11 — Data Migration & Imports

## Target Role
**Tech Delivery Subject Matter Expert — SAP SuccessFactors Employee Central**

## Objective
Prepare for SME-level interview scenarios involving Employee Central data migration, imports, legacy-data transformation, sequencing, effective dating, Foundation Objects, employee data, historical records, validation, error handling, cutover, reconciliation, and migration governance.

> **Interview principle:** Migration is not simply uploading files. Demonstrate a controlled lifecycle: **discover → map → cleanse → transform → sequence → load → validate → reconcile → cut over → stabilize**.

---

# 1. Designing an End-to-End Employee Central Migration

### Scenario Question
A company is moving from a legacy HR system to Employee Central with 50,000 employees. How would you approach the migration?

### STAR Answer

**Situation**  
The organization needed to migrate employee and organizational data from a legacy HR platform into Employee Central while maintaining data quality and business continuity.

**Task**  
I needed to define a migration strategy that covered scope, data mapping, dependencies, sequencing, validation, cutover, and reconciliation.

**Action**
1. Defined migration scope and business objectives.
2. Identified source systems and data owners.
3. Classified data into Foundation Objects, employee/person data, employment data, Job Information, compensation-related data, and other required domains.
4. Created source-to-target mapping.
5. Identified mandatory fields, dependencies, and transformations.
6. Established data-cleansing rules.
7. Defined load sequencing based on dependencies.
8. Performed trial migrations and reconciliation.
9. Defined cutover, freeze, rollback, and support procedures.
10. Established post-load validation and business sign-off.

**Result**  
The migration became a controlled business transformation with measurable data quality and traceability rather than a one-time bulk upload.

### Follow-up Questions
- How would you sequence the migration?
- How would you handle historical data?
- What if the legacy data is incomplete?
- How would you define migration success?

---

# 2. Migration Sequencing and Dependencies

### Scenario Question
You need to load Foundation Objects, positions, employee data, and Job Information. What sequence would you use and why?

### STAR Answer

**Situation**  
The migration objects had dependencies that meant some records could not be loaded before their referenced master data existed.

**Task**  
I needed to establish a sequence that minimized load failures and dependency issues.

**Action**
1. Analyzed object relationships and mandatory references.
2. Loaded foundational organizational/reference data first.
3. Loaded dependent organizational structures such as positions where applicable.
4. Loaded person and employment records.
5. Loaded Job Information and other dependent employee data.
6. Planned effective-dated and historical loads separately where required.
7. Executed trial loads before production cutover.
8. Validated referential integrity after each stage.
9. Reconciled counts and key attributes before proceeding.

**Result**  
The load sequence reduced dependency failures and made troubleshooting more localized and manageable.

### Follow-up Questions
- What happens if a referenced Foundation Object is missing?
- How would you handle circular dependencies?
- Would historical data always be loaded in the same sequence?

---

# 3. Legacy Data Has Inconsistent Values

### Scenario Question
The legacy system contains multiple values for the same department, inconsistent job codes, and obsolete locations. How would you handle this before migration?

### STAR Answer

**Situation**  
Legacy master data was inconsistent and could not be loaded directly into the standardized Employee Central model.

**Task**  
I needed to cleanse and transform the data without silently changing business meaning.

**Action**
1. Profiled the legacy data.
2. Identified duplicate, obsolete, invalid, and inconsistent values.
3. Created a source-to-target value mapping.
4. Worked with business data owners to determine the correct target values.
5. Defined transformation and defaulting rules.
6. Segregated records requiring manual remediation.
7. Validated the transformed data against Employee Central master-data standards.
8. Performed sample loads and reconciliation.
9. Obtained business sign-off before production migration.

**Result**  
Legacy inconsistencies were addressed before they became Employee Central data-quality problems.

### Follow-up Questions
- Who should approve value mappings?
- How would you handle records with no valid target value?
- How would you preserve auditability of transformations?

---

# 4. Employee Import Fails Because of Missing Dependencies

### Scenario Question
A large employee import fails because many records reference departments that do not exist in Employee Central. How would you respond?

### STAR Answer

**Situation**  
The employee data itself was structurally valid, but referenced organizational values that had not been loaded or mapped correctly.

**Task**  
I needed to recover the migration without repeatedly uploading invalid records.

**Action**
1. Reviewed the import error output.
2. Identified all missing referenced values.
3. Compared the failed references against the approved target master-data list.
4. Determined whether the issue was missing master data or incorrect source mapping.
5. Corrected the Foundation Object data or transformation mapping.
6. Validated the dependency population.
7. Retested a representative sample.
8. Reprocessed the failed employee population.
9. Reconciled successful and failed records separately.

**Result**  
The dependency issue was corrected at its source and the affected employee population was successfully migrated.

### Follow-up Questions
- Why should you avoid repeatedly rerunning the same failed file?
- How would you identify all missing dependencies?
- What controls would prevent this before the next migration cycle?

---

# 5. Migrating Historical Employee Data

### Scenario Question
The business wants five years of employee history in Employee Central. How would you determine what should be migrated?

### STAR Answer

**Situation**  
The organization wanted historical continuity but did not want to migrate unnecessary or low-value legacy information.

**Task**  
I needed to define a history strategy balancing business reporting, legal requirements, data quality, migration effort, and system usability.

**Action**
1. Identified business reporting and historical-analysis requirements.
2. Identified legally or operationally required history.
3. Classified historical records by business value and data quality.
4. Determined which history could be represented in Employee Central and which should remain in an archive or legacy repository.
5. Defined effective-dated migration rules.
6. Validated historical sequencing.
7. Performed sample historical migrations.
8. Compared legacy and Employee Central history.
9. Obtained business sign-off on historical completeness.

**Result**  
The organization migrated meaningful historical information while avoiding unnecessary legacy-data clutter.

### Follow-up Questions
- Should every legacy record be migrated?
- How would you handle conflicting historical dates?
- What if the legacy history is incomplete?

---

# 6. Future-Dated Data During Migration

### Scenario Question
The legacy system contains current employee information plus approved changes that become effective next month. How would you migrate this data?

### STAR Answer

**Situation**  
The migration included both current-state and future-state employee records.

**Task**  
I needed to preserve the intended lifecycle while preventing future changes from becoming effective prematurely.

**Action**
1. Identified current and future-dated records separately.
2. Validated effective dates and event reasons.
3. Determined whether future transactions should be loaded before go-live.
4. Established the correct load sequence.
5. Tested multiple effective-dated records for the same employee.
6. Validated current-state reporting.
7. Validated future-state reporting.
8. Reconciled dates, events, and key attributes.
9. Confirmed downstream integration behavior after cutover.

**Result**  
The migrated employee records preserved both current and approved future states without prematurely changing operational data.

### Follow-up Questions
- What if a future change is cancelled after migration?
- How would you test multiple future events?
- How could future-dated records affect integrations?

---

# 7. Migration Cutover Weekend

### Scenario Question
The production migration is planned for a weekend. How would you organize the cutover?

### STAR Answer

**Situation**  
A large production migration had to occur within a defined business downtime window.

**Task**  
I needed to establish a controlled cutover plan with clear sequencing, validation, ownership, and contingency procedures.

**Action**
1. Established the source-system freeze window.
2. Captured the final source extract.
3. Confirmed production target readiness.
4. Validated migration files before execution.
5. Executed loads in dependency order.
6. Monitored errors and load counts.
7. Performed technical and business validation.
8. Reconciled source versus target.
9. Completed integration smoke tests.
10. Defined go/no-go and rollback criteria.
11. Established hypercare support and escalation.

**Result**  
The migration moved into production through a controlled cutover with measurable validation gates and a clear recovery approach.

### Follow-up Questions
- What are your go/no-go criteria?
- When would you stop a migration?
- How would you handle a partial production load?
- Who signs off?

---

# 8. Migration Reconciliation

### Scenario Question
The migration report says 50,000 employees were loaded successfully, but HR reports that some employee records have incorrect managers and departments. How would you investigate?

### STAR Answer

**Situation**  
Technical load counts indicated success, but business validation identified incorrect employee attributes.

**Task**  
I needed to determine why technical success did not equal business correctness.

**Action**
1. Defined the expected source-to-target reconciliation rules.
2. Compared source and target populations.
3. Identified the exact employee population with mismatches.
4. Compared source values, transformed values, and target values.
5. Checked mapping and lookup logic.
6. Reviewed effective dates and organizational dependencies.
7. Corrected the transformation or source data.
8. Reprocessed the affected population.
9. Reconciled again using both record counts and business attributes.
10. Updated migration validation controls.

**Result**  
The discrepancy was resolved and migration acceptance criteria were strengthened to include business-level data validation rather than only technical load counts.

### Follow-up Questions
- What reconciliation dimensions would you use?
- How would you automate reconciliation?
- What is more important: record count or data accuracy?

---

# 9. Import Error Management

### Scenario Question
A migration import returns thousands of errors. The project team wants to fix the file manually and reload it. What approach would you take?

### STAR Answer

**Situation**  
A bulk import generated a large number of errors, creating pressure for rapid manual correction.

**Task**  
I needed to determine whether the errors represented one common root cause or many independent issues.

**Action**
1. Categorized errors by type.
2. Identified the highest-frequency error patterns.
3. Determined whether failures were caused by missing dependencies, invalid values, formatting, mandatory fields, effective dates, or configuration.
4. Fixed systemic issues first.
5. Regenerated the affected data using controlled transformation logic.
6. Tested a smaller sample.
7. Re-ran the corrected population.
8. Reconciled errors and successful records.
9. Documented recurring validation rules for future migration cycles.

**Result**  
The team avoided inefficient record-by-record correction and addressed systemic migration defects at their source.

### Follow-up Questions
- How would you prioritize thousands of errors?
- When is manual correction acceptable?
- How would you prevent the same errors in the next cycle?

---

# 10. SME Ownership of Migration Governance

### Scenario Question
You are the Employee Central SME responsible for migration quality. Multiple teams are supplying employee, organization, position, and payroll-related data. How would you govern the migration?

### STAR Answer

**Situation**  
Multiple teams owned different data domains and were producing migration inputs with varying standards.

**Task**  
I needed to establish a single migration governance model while retaining domain ownership.

**Action**
1. Created a migration data-domain inventory.
2. Assigned data owners for each domain.
3. Established source-to-target mapping standards.
4. Defined mandatory-field and data-quality rules.
5. Created migration templates and naming conventions.
6. Established validation and sign-off checkpoints.
7. Controlled migration versions and changes.
8. Defined reconciliation metrics.
9. Established defect classification and escalation.
10. Maintained a migration runbook covering trial loads, cutover, rollback, and hypercare.

**Result**  
Migration became a governed delivery process with clear accountability, measurable quality, and repeatable execution.

### Follow-up Questions
- Who owns data quality?
- What migration KPIs would you track?
- How would you manage conflicting data-owner decisions?
- How would you prepare for a second migration wave?

---

# Rapid-Fire SME Probes

1. What are the major stages of Employee Central migration?
2. Why is migration sequencing important?
3. What is source-to-target mapping?
4. Why is data cleansing required before migration?
5. How do Foundation Objects affect employee imports?
6. How do you handle effective-dated historical data?
7. How do you handle future-dated records?
8. What is a trial migration?
9. What is migration reconciliation?
10. What is a migration cutover plan?
11. What are go/no-go criteria?
12. How do you handle partial migration failure?
13. How do you classify import errors?
14. How do you validate business correctness?
15. What should a migration runbook contain?
16. How do you control migration file versions?
17. Who owns migration data quality?
18. How do you handle sensitive employee data during migration?

---

# Master Migration Framework

Use this sequence in an interview:

**DISCOVER → MAP → CLEANSE → TRANSFORM → SEQUENCE → LOAD → VALIDATE → RECONCILE → CUTOVER → STABILIZE**

### 1. DISCOVER
Understand:
- Source systems
- Data domains
- Volumes
- History
- Data owners
- Business requirements

### 2. MAP
Create source-to-target mappings:
- Field
- Data type
- Mandatory status
- Value mapping
- Default
- Transformation
- Business owner

### 3. CLEANSE
Identify:
- Duplicates
- Invalid values
- Obsolete values
- Missing mandatory data
- Inconsistent organizational structures

### 4. TRANSFORM
Convert source data into Employee Central-compatible values while preserving business meaning.

### 5. SEQUENCE
Load objects in dependency order.

### 6. LOAD
Execute controlled trial, mock, and production loads.

### 7. VALIDATE
Validate:
- Technical load status
- Mandatory fields
- Referential integrity
- Effective dates
- Business rules
- Key employee attributes

### 8. RECONCILE
Compare:
**Legacy Source ↔ Transformation Layer ↔ Employee Central**

### 9. CUTOVER
Execute:
- Freeze
- Final extract
- Production load
- Validation
- Integration smoke tests
- Go/no-go

### 10. STABILIZE
Perform:
- Hypercare
- Defect resolution
- Reconciliation
- Documentation
- Knowledge transfer
- Post-migration review

---

# Migration Validation Pyramid

Validate at four levels:

### Level 1 — File Validation
- Format
- Headers
- Data types
- Required columns

### Level 2 — Technical Validation
- Import success
- Object references
- Dependencies
- Error counts

### Level 3 — Data Validation
- Employee attributes
- Organizational relationships
- Effective dates
- Historical records

### Level 4 — Business Validation
- HR process usability
- Reporting accuracy
- Lifecycle correctness
- Payroll/integration readiness

> A technically successful import is not necessarily a successful migration.

---

# Migration Reconciliation Checklist

At minimum, reconcile:

- Total employee count
- Active employee count
- Inactive/terminated population
- Person identifiers
- Employment identifiers
- Manager relationships
- Department
- Division
- Business unit
- Location
- Position
- Job classification
- Effective dates
- Event reasons where applicable
- Country/legal entity
- Key sensitive-data fields
- Error population
- Integration-relevant attributes

---

# Cutover Readiness Checklist

Before production migration, verify:

- Source freeze agreed
- Final extract validated
- Migration templates approved
- Mapping signed off
- Dependencies loaded/planned
- Trial migration completed
- Critical defects closed
- Reconciliation approach approved
- Security/RBP validated
- Integration readiness confirmed
- Go/no-go criteria defined
- Rollback/recovery approach documented
- Business validation owners identified
- Hypercare team available

---

# Common Anti-Patterns

Avoid answers such as:

- "We can upload the legacy data as-is."
- "The technical team owns all data cleansing."
- "If the import says successful, migration is complete."
- "We can fix all errors manually."
- "Historical data is always migrated."
- "Future-dated records can be treated like current records."
- "Dependencies can be fixed after the employee import."
- "Record counts are enough for reconciliation."
- "Rollback is unnecessary if the load is mostly successful."

Instead, demonstrate **data ownership, dependency analysis, controlled transformation, effective-dated thinking, trial migration, reconciliation, cutover discipline, and business validation**.

---

# Strong SME Answer Pattern

For any migration scenario:

1. **Define migration scope and business objective.**
2. **Identify source and data owners.**
3. **Map source to target.**
4. **Cleanse and transform data.**
5. **Identify dependencies and load sequence.**
6. **Run trial/mock migration.**
7. **Validate technical and business correctness.**
8. **Reconcile source and target.**
9. **Execute controlled cutover.**
10. **Stabilize and govern post-migration.**

---

# Category Success Criteria

The candidate is ready for this category when they can:

- Design an end-to-end Employee Central migration.
- Explain source-to-target mapping.
- Identify and manage data dependencies.
- Design Foundation Object and employee-data load sequencing.
- Handle legacy data cleansing and transformation.
- Explain historical and future-dated migration.
- Manage trial and mock migrations.
- Design production cutover and recovery.
- Troubleshoot bulk import errors systematically.
- Perform technical and business reconciliation.
- Establish migration governance and ownership.
- Connect migration quality to downstream integrations and HR business processes.

---

## Interview Positioning

For a Tech Delivery SME interview, frame migration expertise as:

**Legacy Data → Data Quality → Mapping → Transformation → EC Data Model → Dependency Sequence → Controlled Load → Validation → Reconciliation → Cutover → Hypercare**

The strongest answers show that migration is an **HR transformation and data-quality discipline**, not simply a file-upload activity.
