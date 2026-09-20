# Scenario Category 12 — Data Quality & Reconciliation

## Target Role
**Tech Delivery Subject Matter Expert — SAP SuccessFactors Employee Central**

## Objective
Prepare for SME-level interview scenarios involving Employee Central data quality, validation, duplicate detection, completeness, consistency, referential integrity, effective-dated accuracy, reconciliation, data-quality monitoring, remediation, and prevention.

> **Interview principle:** Data quality is not simply "checking whether imports succeeded." A strong SME can define the expected business state, identify quality dimensions, quantify exceptions, trace defects to their source, reconcile systems, and establish controls that prevent recurrence.

---

# 1. Designing an Employee Central Data Quality Framework

### Scenario Question
A global organization says Employee Central data quality is poor but cannot define what "poor" means. As the EC SME, how would you establish a data-quality framework?

### STAR Answer

**Situation**  
The organization was experiencing inconsistent HR data but lacked standardized measures for identifying and prioritizing data-quality problems.

**Task**  
I needed to create a practical framework that translated business expectations into measurable data-quality controls.

**Action**
1. Identified critical Employee Central data domains.
2. Defined data-quality dimensions such as completeness, accuracy, consistency, validity, uniqueness, timeliness, and integrity.
3. Identified business-critical fields and relationships.
4. Defined validation rules and exception thresholds.
5. Assigned data ownership by domain.
6. Established recurring quality monitoring.
7. Created remediation workflows for exceptions.
8. Defined reconciliation with downstream systems.
9. Established trend reporting and root-cause analysis.
10. Connected quality metrics to business processes such as payroll, hiring, and reporting.

**Result**  
Data quality became measurable and governable rather than being treated as an undefined operational concern.

### Follow-up Questions
- Which dimensions matter most for HR data?
- How would you prioritize defects?
- Who owns data quality?
- How would you measure improvement?

---

# 2. Missing Mandatory Employee Data

### Scenario Question
A data-quality report identifies thousands of employees with missing manager, department, or location values. How would you approach remediation?

### STAR Answer

**Situation**  
Critical organizational attributes were missing for a significant employee population.

**Task**  
I needed to determine whether the problem originated in migration, configuration, process execution, or ongoing maintenance.

**Action**
1. Quantified the affected population.
2. Segmented exceptions by country, business unit, employee type, and lifecycle event.
3. Identified which fields were business-critical.
4. Determined whether the fields were technically mandatory or only business-required.
5. Traced missing values back to the source process.
6. Identified whether the issue came from hire, transfer, import, integration, or manual maintenance.
7. Defined controlled remediation.
8. Added validation at the earliest practical point in the process.
9. Re-ran the quality check after correction.
10. Monitored recurrence.

**Result**  
The immediate population was remediated and the upstream process causing the omissions was addressed.

### Follow-up Questions
- Would you fix every record manually?
- How would you prioritize manager versus location?
- How would you prevent new omissions?

---

# 3. Duplicate Employee Records

### Scenario Question
HR suspects duplicate employee records exist in Employee Central. How would you investigate?

### STAR Answer

**Situation**  
The business suspected that multiple employee records represented the same person.

**Task**  
I needed to identify true duplicates without incorrectly merging legitimate records.

**Action**
1. Defined duplicate-detection criteria.
2. Compared stable identifiers and relevant personal attributes.
3. Segmented suspected duplicates by confidence level.
4. Checked employment history and rehire scenarios.
5. Determined whether multiple employment records were legitimate.
6. Validated against authoritative source documentation.
7. Escalated ambiguous cases to the appropriate HR data owner.
8. Corrected confirmed duplicates through controlled procedures.
9. Checked downstream integration impacts.
10. Reconciled affected populations after remediation.

**Result**  
True duplicate cases were isolated from legitimate multiple-employment or rehire scenarios, reducing the risk of incorrect data correction.

### Follow-up Questions
- Why is email address alone insufficient?
- How can rehire create false positives?
- What downstream systems could be affected?

---

# 4. Employee Central and Payroll Data Do Not Match

### Scenario Question
A reconciliation report shows that 2% of employees have different department, manager, or organizational values between Employee Central and payroll. What would you do?

### STAR Answer

**Situation**  
The two systems had inconsistent employee attributes.

**Task**  
I needed to determine whether Employee Central, the integration, or payroll contained the incorrect state.

**Action**
1. Confirmed the agreed system of record for each field.
2. Identified the mismatched population.
3. Compared effective dates in both systems.
4. Checked whether the integration transmitted the expected values.
5. Reviewed mapping and transformation logic.
6. Identified whether payroll had rejected, transformed, or failed to process the data.
7. Classified exceptions by root cause.
8. Corrected the responsible source or integration layer.
9. Reprocessed affected records.
10. Reconciled again after correction.

**Result**  
The mismatch population was reduced and root causes were categorized rather than treating every exception as a manual correction.

### Follow-up Questions
- What if payroll is actually the correct source for one field?
- How would you handle effective-date differences?
- What reconciliation frequency would you recommend?

---

# 5. Effective-Dated Data Inconsistency

### Scenario Question
An employee's current Job Information is correct, but historical records contain incorrect managers and departments. How would you approach this?

### STAR Answer

**Situation**  
Current-state data was correct, but historical effective-dated records were inconsistent.

**Task**  
I needed to determine whether historical correction was necessary and how to preserve auditability.

**Action**
1. Identified the business requirement for historical accuracy.
2. Reviewed the employee's complete effective-dated history.
3. Determined the exact point at which the historical inconsistency began.
4. Compared history against authoritative business records.
5. Assessed reporting, audit, payroll, and integration impacts.
6. Determined the appropriate correction approach.
7. Tested historical reporting after correction.
8. Preserved evidence and approval for historical changes.
9. Reconciled the employee's timeline.

**Result**  
Historical data was corrected only where business requirements justified it, while preserving traceability.

### Follow-up Questions
- Should historical data always be corrected?
- How would you avoid changing valid history?
- What if payroll history depends on the old value?

---

# 6. Data Quality After a Mass Organizational Change

### Scenario Question
After a global reorganization, thousands of employees have incorrect departments and managers. How would you manage the quality problem?

### STAR Answer

**Situation**  
A large organizational change introduced widespread employee-data inconsistencies.

**Task**  
I needed to identify whether the issue was caused by the transformation mapping, position structure, employee updates, or integration.

**Action**
1. Established the approved future-state organizational mapping.
2. Identified the affected employee population.
3. Compared expected versus actual organizational values.
4. Segmented errors by source and change type.
5. Identified common transformation or mapping defects.
6. Corrected the systemic cause.
7. Reprocessed the impacted population where appropriate.
8. Validated managers, departments, positions, and effective dates.
9. Reconciled the complete population.
10. Established post-change monitoring.

**Result**  
The organization corrected the mass data issue through a controlled remediation rather than thousands of independent manual fixes.

### Follow-up Questions
- How would you prioritize the remediation?
- What if the organizational mapping itself is disputed?
- How would you prove completeness?

---

# 7. Designing Data-Quality Rules

### Scenario Question
HR wants to automatically detect employees with invalid combinations such as a department belonging to one business unit while the employee is assigned to another. How would you design the control?

### STAR Answer

**Situation**  
The organization had cross-field inconsistencies that were not necessarily detected by simple mandatory-field validation.

**Task**  
I needed to design business-aware quality rules.

**Action**
1. Defined the valid business relationships.
2. Identified the authoritative reference data.
3. Created validation logic for valid combinations.
4. Determined whether validation should occur during transaction entry or through monitoring.
5. Classified exceptions by severity.
6. Created exception reporting.
7. Defined remediation ownership.
8. Tested valid and invalid combinations.
9. Monitored false positives.
10. Reviewed the rules periodically as organizational structures changed.

**Result**  
The organization gained proactive detection of relationship-level data-quality issues.

### Follow-up Questions
- Which rules should block a transaction?
- Which should only generate alerts?
- How would you avoid excessive false positives?

---

# 8. Data Quality and Integration Reconciliation

### Scenario Question
The integration technically succeeds every night, but the business still finds incorrect downstream employee data. What does that tell you?

### STAR Answer

**Situation**  
Integration execution status showed success, but business users continued to identify incorrect target data.

**Task**  
I needed to determine why technical success was not translating into business-data consistency.

**Action**
1. Distinguished technical monitoring from business reconciliation.
2. Compared source and target values for critical fields.
3. Identified records that were technically processed but business-invalid.
4. Reviewed transformation and code mapping.
5. Checked effective-dated behavior.
6. Classified discrepancies by root cause.
7. Added business-level reconciliation rules.
8. Established exception reporting.
9. Defined ownership for each discrepancy type.
10. Monitored quality trends after remediation.

**Result**  
The organization moved from job-status monitoring to meaningful source-to-target data-quality assurance.

### Follow-up Questions
- Why is "integration succeeded" not enough?
- What fields should be reconciled?
- How would you automate exception reporting?

---

# 9. Data-Quality Issue Is Caused by a Business Process

### Scenario Question
You discover that new hires consistently have incorrect location values because HR administrators select inconsistent values during onboarding. Would you solve this only with data cleansing?

### STAR Answer

**Situation**  
The same data-quality issue appeared repeatedly in newly created employee records.

**Task**  
I needed to address both existing defects and the upstream process causing them.

**Action**
1. Quantified the recurring defect.
2. Traced the issue to the hiring process.
3. Determined why users were selecting inconsistent values.
4. Reviewed UI options, validation, defaults, and reference data.
5. Simplified the available choices where appropriate.
6. Added validation or controlled defaults.
7. Updated process guidance and training.
8. Cleansed the existing affected population.
9. Monitored new-hire data quality after the change.

**Result**  
The solution shifted from repeated cleanup to prevention at the point of data creation.

### Follow-up Questions
- When should configuration change instead of training?
- How would you measure recurrence?
- How can automation improve data quality?

---

# 10. SME-Level Data Quality Governance

### Scenario Question
You are responsible for Employee Central data quality across multiple countries. How would you establish a sustainable governance model?

### STAR Answer

**Situation**  
Data-quality ownership was distributed across HR operations, HRIS, payroll, integrations, and local teams.

**Task**  
I needed to establish accountability and measurable quality controls without centralizing every operational activity.

**Action**
1. Defined critical data domains and owners.
2. Established common data-quality definitions.
3. Created quality KPIs and thresholds.
4. Established automated exception reporting.
5. Defined severity and remediation SLAs.
6. Established source-to-target reconciliation for critical interfaces.
7. Created root-cause categories.
8. Reviewed recurring issues through governance forums.
9. Prioritized structural fixes over repeated manual remediation.
10. Established periodic quality reviews and continuous-improvement actions.

**Result**  
Data quality became an ongoing governance capability with clear ownership, measurable performance, and continuous improvement.

### Follow-up Questions
- Which KPIs would you report to leadership?
- How would you compare data quality across countries?
- How would you prioritize competing remediation requests?
- What role can AI-assisted analysis play?

---

# Rapid-Fire SME Probes

1. What are the major dimensions of data quality?
2. What is data completeness?
3. What is data accuracy?
4. What is data consistency?
5. What is data uniqueness?
6. What is data validity?
7. What is referential integrity?
8. Why is effective dating important for data quality?
9. Why is record count alone insufficient for reconciliation?
10. How do you identify duplicate employee records?
11. How do you distinguish rehire from duplicate data?
12. What is source-of-truth analysis?
13. How do you reconcile EC and payroll?
14. When should a validation block a transaction?
15. When should a validation generate an alert?
16. How do you prioritize data-quality defects?
17. Who owns HR data quality?
18. How can AI assist data-quality analysis without replacing human validation?

---

# Master Data Quality Framework

Use this sequence in an interview:

**DEFINE → MEASURE → DETECT → CLASSIFY → TRACE → REMEDIATE → RECONCILE → PREVENT → GOVERN**

### 1. DEFINE
Define what "correct" means for each data domain.

### 2. MEASURE
Establish measurable quality dimensions and thresholds.

### 3. DETECT
Identify exceptions using validation, reports, imports, integrations, and analytics.

### 4. CLASSIFY
Categorize:
- Completeness
- Accuracy
- Consistency
- Validity
- Uniqueness
- Timeliness
- Referential integrity

### 5. TRACE
Identify the origin:
- Migration
- Manual entry
- Business rule
- Workflow
- Integration
- Reference data
- Organizational change

### 6. REMEDIATE
Correct the affected population using controlled processes.

### 7. RECONCILE
Compare expected and actual states across systems.

### 8. PREVENT
Introduce validation, automation, process improvements, or governance.

### 9. GOVERN
Track trends, ownership, SLAs, and recurring root causes.

---

# Data Quality Dimensions

| Dimension | EC Example | Possible Control |
|---|---|---|
| Completeness | Manager is missing | Mandatory validation/report |
| Accuracy | Wrong location | Source verification |
| Consistency | Department conflicts with business unit | Cross-field rule |
| Validity | Invalid organizational code | Reference-data validation |
| Uniqueness | Duplicate person record | Duplicate detection |
| Timeliness | Downstream data is stale | Reconciliation SLA |
| Integrity | Employee references invalid position | Referential validation |

---

# Reconciliation Framework

A strong reconciliation compares more than record counts.

### Level 1 — Population
**Did all expected employees arrive?**

### Level 2 — Record
**Does each employee have the expected record?**

### Level 3 — Attribute
**Are critical fields correct?**

### Level 4 — Relationship
**Are manager, position, department, and organizational relationships correct?**

### Level 5 — Effective Date
**Are current and historical states aligned?**

### Level 6 — Business Outcome
**Does the data support the intended HR process?**

---

# Data Quality Severity Model

When prioritizing issues, consider:

| Factor | Question |
|---|---|
| Business Impact | Does the defect block an HR process? |
| Population | How many employees are affected? |
| Sensitivity | Does it involve sensitive employee data? |
| Payroll Impact | Could compensation or payroll be affected? |
| Compliance | Could the issue create regulatory exposure? |
| Integration Impact | Is downstream data incorrect? |
| Recurrence | Is this a recurring defect? |
| Recoverability | Can it be corrected safely? |

---

# Root-Cause Categories

When analyzing recurring data-quality defects, classify the root cause:

- **Source Data** — incorrect upstream information
- **Configuration** — incorrect EC setup
- **Business Rule** — incorrect derivation or validation
- **Workflow** — incorrect approval/process behavior
- **RBP** — incorrect access enabling bad data
- **Reference Data** — incorrect Foundation Object/MDF values
- **Integration** — mapping/transformation/transport issue
- **Migration** — legacy transformation or load issue
- **Process** — unclear or inefficient HR process
- **User Behavior** — incorrect manual entry
- **Organizational Change** — outdated structures or mappings

This classification helps prevent repeated symptom-level fixes.

---

# Data Quality Improvement Loop

Use:

**DETECT → ANALYZE → CORRECT → VALIDATE → PREVENT → MONITOR**

A mature SME does not stop after correction.

The final question should always be:

> **"What control will stop this defect from returning?"**

---

# AI-Assisted Data Quality

The role requires applied AI usage rather than AI model development.

Potential SME use cases include:

- Identifying unusual employee-data patterns
- Comparing large reconciliation outputs
- Grouping error messages by likely root cause
- Detecting inconsistent organizational combinations
- Summarizing migration exceptions
- Generating first-draft validation scenarios
- Identifying recurring defect patterns
- Supporting test-data analysis
- Drafting reconciliation reports

Human validation remains essential, particularly for sensitive HR data and decisions affecting employee records.

---

# Common Anti-Patterns

Avoid answers such as:

- "If the import succeeded, the data is correct."
- "We can clean the data after every release."
- "Record count is enough for reconciliation."
- "Users are always responsible for bad data."
- "Make every field mandatory."
- "Fix the downstream system manually."
- "Duplicate employee records should always be merged."
- "Every data-quality issue should block the transaction."
- "Data quality is owned only by HR operations."

Instead, demonstrate **measurable quality dimensions, root-cause analysis, business ownership, reconciliation, prevention, and continuous monitoring**.

---

# Strong SME Answer Pattern

For any data-quality scenario:

1. **Define the expected business state.**
2. **Quantify the affected population.**
3. **Classify the quality defect.**
4. **Trace the defect to its source.**
5. **Assess business and downstream impact.**
6. **Remediate the affected population safely.**
7. **Reconcile against the expected state.**
8. **Implement preventive controls.**
9. **Assign ownership and SLA.**
10. **Monitor recurrence and improvement.**

---

# Category Success Criteria

The candidate is ready for this category when they can:

- Define a practical Employee Central data-quality framework.
- Explain major data-quality dimensions.
- Detect missing and inconsistent employee data.
- Investigate duplicate employee records.
- Reconcile Employee Central with payroll and other systems.
- Handle effective-dated inconsistencies.
- Manage data-quality problems after organizational changes.
- Design cross-field validation controls.
- Distinguish technical integration success from business-data correctness.
- Trace recurring defects to business processes.
- Establish data-quality governance and KPIs.
- Explain responsible AI-assisted data-quality analysis.

---

## Interview Positioning

For a Tech Delivery SME interview, frame data quality as:

**Business Definition → Data Standard → Validation → Detection → Root Cause → Remediation → Reconciliation → Prevention → Governance**

The strongest answers show that the EC SME does not merely correct bad records. They **design the HR technology ecosystem so that accurate data is created, validated, propagated, reconciled, and continuously governed**.
