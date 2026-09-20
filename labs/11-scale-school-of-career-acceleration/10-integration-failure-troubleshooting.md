# Scenario Category 10 — Integration Failure & Troubleshooting

## Target Role
**Tech Delivery Subject Matter Expert — SAP SuccessFactors Employee Central**

## Objective
Prepare for SME-level scenarios involving Employee Central integration incidents, failed jobs, missing records, incorrect payloads, mapping defects, authentication issues, data-quality problems, downstream failures, retries, reconciliation, root-cause analysis, and production recovery.

> **Interview principle:** Troubleshoot systematically. Do not jump directly to configuration changes or manual data fixes. Establish the expected business outcome, isolate the failure layer, preserve evidence, recover safely, reconcile the population, and implement preventive controls.

---

# 1. Integration Job Fails Completely

### Scenario Question
A critical nightly Employee Central integration fails completely. Payroll processing starts in a few hours. How would you handle the incident?

### STAR Answer

**Situation**  
A critical scheduled integration failed before a payroll processing window, creating a potential downstream data gap.

**Task**  
I needed to restore the data flow quickly while protecting data integrity and maintaining a clear audit trail.

**Action**
1. Established incident severity and business impact.
2. Identified the failed integration, execution time, and affected business process.
3. Reviewed execution logs and error messages.
4. Determined whether the failure occurred during authentication, extraction, transformation, transmission, or target processing.
5. Checked whether any records had already been successfully processed.
6. Avoided indiscriminate reruns that could create duplicates.
7. Corrected the root cause or applied an approved recovery action.
8. Reprocessed only the required population where supported.
9. Reconciled Employee Central against the payroll target.
10. Communicated status, impact, recovery, and follow-up actions.

**Result**  
The integration was restored with controlled reprocessing and verified downstream consistency before payroll processing.

### Follow-up Questions
- What if the error is intermittent?
- How would you prevent duplicate processing?
- What evidence would you preserve?
- When would you escalate to the integration or infrastructure team?

---

# 2. Only Some Employees Fail

### Scenario Question
An integration succeeds for 9,500 employees but fails for 500. How would you determine the root cause?

### STAR Answer

**Situation**  
The integration completed partially, leaving a subset of employees unsynchronized.

**Task**  
I needed to identify whether the failures shared a common data or processing characteristic.

**Action**
1. Extracted the failed employee population.
2. Compared successful and failed records.
3. Looked for common attributes such as country, legal entity, event type, organizational data, or missing fields.
4. Reviewed individual error messages and payloads.
5. Checked source-data completeness in Employee Central.
6. Investigated mapping and transformation behavior.
7. Determined whether the failure was systematic or record-specific.
8. Corrected source/configuration issues where appropriate.
9. Reprocessed the failed population.
10. Reconciled the final result against the expected population.

**Result**  
The failure pattern was isolated and the affected records were recovered without unnecessarily rerunning successful transactions.

### Follow-up Questions
- How would you identify the exact failed population?
- What if every failed employee belongs to one country?
- What if there is no obvious common attribute?

---

# 3. Payload Contains the Wrong Value

### Scenario Question
Employee Central shows the correct department, but the integration payload contains an incorrect department code. How would you troubleshoot?

### STAR Answer

**Situation**  
The source record was correct, but the outbound payload did not contain the expected value.

**Task**  
I needed to determine where the incorrect value was introduced.

**Action**
1. Verified the effective-dated Employee Central source record.
2. Confirmed the field selected by the integration.
3. Reviewed source-to-target mapping.
4. Checked transformation and lookup logic.
5. Validated code translations.
6. Compared the payload against the mapping specification.
7. Determined whether the issue originated in configuration, mapping, transformation, or source data.
8. Corrected the responsible layer.
9. Tested multiple organizational values.
10. Reprocessed affected records and reconciled the target.

**Result**  
The mapping defect was corrected without changing valid Employee Central source data.

### Follow-up Questions
- What if the EC value itself is wrong?
- How would you test all department codes?
- How would you prevent a mapping regression?

---

# 4. Authentication Failure

### Scenario Question
An integration that has worked for months suddenly fails with an authentication error. What would you investigate?

### STAR Answer

**Situation**  
A previously stable interface began failing at the authentication stage.

**Task**  
I needed to determine whether credentials, certificates, authorization, endpoint configuration, or external security changes caused the failure.

**Action**
1. Confirmed the exact authentication error.
2. Checked whether the failure affected all records.
3. Reviewed credential or certificate expiry.
4. Verified authentication configuration and permissions.
5. Checked endpoint or security-policy changes.
6. Confirmed whether the target system had changed its authentication requirements.
7. Coordinated credential or certificate rotation through the approved process.
8. Retested connectivity before full execution.
9. Monitored the next scheduled execution.
10. Documented the incident and renewal control.

**Result**  
Connectivity was restored without changing unrelated integration logic, and a preventive credential-expiry control was established.

### Follow-up Questions
- How would you avoid storing credentials insecurely?
- What if the certificate has expired?
- How would you distinguish authentication from authorization failure?

---

# 5. Duplicate Records After a Retry

### Scenario Question
An integration failed after sending data to the target. The support team reran it, and duplicate transactions appeared downstream. How would you handle it?

### STAR Answer

**Situation**  
A retry occurred after uncertain delivery status and resulted in duplicate downstream processing.

**Task**  
I needed to restore correct downstream state and prevent repeated duplication.

**Action**
1. Established which records were successfully transmitted before the failure.
2. Compared source, integration logs, payloads, and target records.
3. Identified duplicate transactions and their business impact.
4. Coordinated approved target-side correction.
5. Determined whether the interface supported idempotency or unique business keys.
6. Reviewed retry behavior and failure-handling design.
7. Introduced clearer processing-status controls.
8. Tested failure-after-send scenarios.
9. Reconciled the complete population.
10. Documented the recovery and preventive action.

**Result**  
Duplicate records were controlled and the retry process became safer for future incidents.

### Follow-up Questions
- What is idempotency?
- How can unique business keys help?
- What should happen when delivery status is unknown?

---

# 6. Effective-Dated Record Is Not Replicated

### Scenario Question
An employee has a future-dated job change in Employee Central, but the downstream system receives the current job information instead. How would you investigate?

### STAR Answer

**Situation**  
The downstream system received an older effective state instead of the expected future-dated transaction.

**Task**  
I needed to determine whether the issue was caused by source-data selection, integration filtering, effective-dated retrieval, or target processing.

**Action**
1. Confirmed the employee's current and future-dated Job Information.
2. Verified the effective date and event reason.
3. Reviewed integration selection criteria.
4. Checked how the integration retrieves effective-dated records.
5. Determined whether future records should be transmitted before their effective date.
6. Reviewed payload chronology.
7. Checked target-system processing rules.
8. Tested multiple effective-dated changes for the same employee.
9. Corrected the responsible configuration or business rule.
10. Reconciled source and target effective states.

**Result**  
The integration behavior was aligned with the agreed business-effective-date model.

### Follow-up Questions
- What if there are three future-dated changes?
- What if the future change is cancelled?
- How would you test same-day changes?

---

# 7. Integration Is Slow and Times Out

### Scenario Question
A high-volume EC integration that normally completes in one hour now takes five hours and eventually times out. How would you troubleshoot?

### STAR Answer

**Situation**  
Integration execution time increased significantly and threatened the downstream processing window.

**Task**  
I needed to identify the performance bottleneck and restore acceptable processing time.

**Action**
1. Compared current execution time with historical performance.
2. Identified whether the slowdown occurred during extraction, transformation, transmission, or target processing.
3. Reviewed population and data-volume changes.
4. Checked filtering and whether unnecessary fields or records were being processed.
5. Reviewed pagination and batching behavior where applicable.
6. Checked target-system response times.
7. Identified repeated calls or inefficient transformations.
8. Tested optimization changes in a controlled environment.
9. Measured performance before and after the change.
10. Established monitoring thresholds.

**Result**  
The performance bottleneck was isolated and the integration was optimized without compromising required data.

### Follow-up Questions
- What metrics would you monitor?
- How would you distinguish source latency from target latency?
- How could data-volume growth affect the design?

---

# 8. Integration Works in Test but Fails in Production

### Scenario Question
An integration passes all test cases but fails immediately after production deployment. How would you approach the incident?

### STAR Answer

**Situation**  
The integration behaved correctly in the test environment but failed in production.

**Task**  
I needed to isolate environment-specific differences rather than assuming the functional design was incorrect.

**Action**
1. Compared production and test configuration.
2. Checked endpoint and authentication settings.
3. Compared permissions and service accounts.
4. Validated production data characteristics.
5. Reviewed environment-specific mappings and value translations.
6. Checked network or connectivity dependencies.
7. Compared deployment versions.
8. Reproduced the smallest failing scenario.
9. Corrected the environment-specific issue.
10. Performed controlled production validation and documented the deployment checklist gap.

**Result**  
The production defect was isolated without unnecessarily redesigning the validated integration.

### Follow-up Questions
- What environment differences are commonly missed?
- How would you improve deployment controls?
- What should be validated before go-live?

---

# 9. Downstream System Rejects Valid EC Data

### Scenario Question
Employee Central and the outbound payload are both correct, but the receiving payroll system rejects the transaction. What would you do?

### STAR Answer

**Situation**  
The source and outbound interface were correct, but the target rejected the transaction.

**Task**  
I needed to determine whether the target's validation, master data, interface contract, or processing rules caused the rejection.

**Action**
1. Captured the target rejection message.
2. Verified the exact payload received.
3. Confirmed that the outbound mapping matched the interface contract.
4. Checked target-side master data and code availability.
5. Determined whether the target expected a different sequence or prerequisite record.
6. Coordinated with the target-system team.
7. Corrected the target dependency or interface mapping where appropriate.
8. Reprocessed the affected records.
9. Reconciled the target result.
10. Added a validation or monitoring control to detect similar conditions earlier.

**Result**  
The target-side dependency was resolved while preserving the correct Employee Central source data.

### Follow-up Questions
- Who owns the defect?
- What if the target team says the payload is invalid?
- How would you prove the outbound interface was correct?

---

# 10. SME Root-Cause Analysis and Permanent Fix

### Scenario Question
The same integration incident has occurred three times in six months. Each time, support manually fixes the affected records. As the EC SME, what would you do differently?

### STAR Answer

**Situation**  
A recurring integration defect was being treated as separate incidents rather than as a systemic problem.

**Task**  
I needed to move the team from repeated recovery to permanent root-cause elimination.

**Action**
1. Reviewed the history of all related incidents.
2. Identified common failure conditions.
3. Performed structured root-cause analysis.
4. Determined whether the issue was caused by data, configuration, integration design, environment, or operational process.
5. Quantified affected populations and business impact.
6. Designed a permanent corrective action.
7. Added automated validation or monitoring where appropriate.
8. Added regression scenarios covering the failure condition.
9. Updated support documentation and ownership.
10. Tracked recurrence after deployment.

**Result**  
The recurring issue was converted from a manual support problem into a controlled improvement with measurable prevention.

### Follow-up Questions
- How would you distinguish root cause from symptom?
- What would you include in an RCA document?
- How would you prove the permanent fix worked?
- When would you raise a problem-management record?

---

# Rapid-Fire SME Probes

1. What are the major layers of integration troubleshooting?
2. How do you distinguish source-data defects from integration defects?
3. How do you distinguish mapping defects from target-system defects?
4. What evidence should you collect before changing configuration?
5. How do you handle partial integration failures?
6. What is idempotency?
7. Why is retry logic important?
8. How do you prevent duplicate processing?
9. How do you troubleshoot authentication failures?
10. How do you troubleshoot authorization failures?
11. How do you investigate stale effective-dated data?
12. How do you investigate integration performance degradation?
13. How do you handle an unknown delivery status?
14. What is reconciliation?
15. What makes an RCA strong?
16. When should a recurring incident become a problem-management item?
17. How do you design preventive monitoring?

---

# Master Integration Incident Framework

Use this sequence during troubleshooting:

**IMPACT → SCOPE → SOURCE → SELECTION → TRANSFORMATION → PAYLOAD → TRANSPORT → TARGET → RECONCILE → RCA → PREVENT**

### 1. IMPACT
What business process is affected?

Examples:
- Payroll
- Hiring
- Identity provisioning
- Time processing
- Reporting
- Compliance

### 2. SCOPE
How many records are affected?

Determine:
- All employees
- Specific countries
- Specific events
- Specific organizational units
- Specific execution window

### 3. SOURCE
Is Employee Central data correct?

Validate:
- Object
- Field
- Effective date
- Event reason
- Source value

### 4. SELECTION
Did the integration select the expected records?

Check:
- Filters
- Dates
- Event criteria
- Population
- Incremental logic

### 5. TRANSFORMATION
Was the source value converted correctly?

Check:
- Mapping
- Lookups
- Code translations
- Defaults
- Data types

### 6. PAYLOAD
What exactly was sent?

Never assume the payload is correct merely because the EC screen is correct.

### 7. TRANSPORT
Did the message successfully reach the target?

Check:
- Authentication
- Authorization
- Endpoint
- Connectivity
- Certificates
- Timeouts

### 8. TARGET
Did the receiving system accept and process it?

Check:
- Validation
- Master data
- Interface contract
- Processing sequence
- Target-side errors

### 9. RECONCILE
Compare:

**Expected EC State ↔ Outbound Payload ↔ Target State**

### 10. RCA
Identify the actual root cause rather than the visible symptom.

### 11. PREVENT
Implement:
- Validation
- Monitoring
- Alerting
- Regression testing
- Documentation
- Process improvement

---

# Incident Severity Thinking

When prioritizing an integration incident, consider:

| Factor | Questions |
|---|---|
| Business Impact | Is payroll, hiring, termination, or another critical process blocked? |
| Population | One employee or thousands? |
| Timing | Is there a payroll or business deadline? |
| Data Risk | Is incorrect or sensitive data being propagated? |
| Recoverability | Can the transaction be safely reprocessed? |
| Duplicate Risk | Could retry create duplicate transactions? |
| Regulatory Impact | Could the failure affect compliance or statutory processing? |
| Recurrence | Is this a one-time event or a repeated defect? |

---

# Evidence Collection Checklist

Before changing configuration, capture where possible:

- Integration execution ID
- Timestamp
- Error message
- Failed employee population
- Successful population
- Employee Central source record
- Effective date
- Event reason
- Integration filter
- Outbound payload
- Transformation/mapping result
- Authentication status
- Target response
- Target-side error
- Previous successful execution
- Recent configuration/deployment changes

This prevents troubleshooting from becoming guesswork.

---

# Recovery Strategy

Use the safest recovery sequence:

**STOP → ASSESS → CONTAIN → CORRECT → REPROCESS → RECONCILE → MONITOR**

### STOP
Prevent additional incorrect processing when necessary.

### ASSESS
Determine scope and business impact.

### CONTAIN
Prevent the problem from spreading.

### CORRECT
Fix the actual cause or approved recovery condition.

### REPROCESS
Retry only the required population using controlled mechanisms.

### RECONCILE
Confirm source and target consistency.

### MONITOR
Watch subsequent executions for recurrence.

---

# Common Anti-Patterns

Avoid answers such as:

- "I would rerun the integration immediately."
- "I would manually fix all employees in the target."
- "The payload must be correct because EC is correct."
- "The integration team owns every integration problem."
- "I would change the mapping until it works."
- "We can ignore a partial failure."
- "Authentication errors are always password issues."
- "The last successful run proves the integration is healthy."
- "The issue is fixed once the current records are corrected."

Instead, demonstrate **evidence-based diagnosis, controlled recovery, source-of-truth discipline, reconciliation, RCA, and prevention**.

---

# Strong SME Answer Pattern

For any integration incident, structure the response as:

1. **Quantify business impact.**
2. **Identify the affected population.**
3. **Confirm the Employee Central source data.**
4. **Validate integration selection criteria.**
5. **Inspect transformation and mapping.**
6. **Inspect the actual payload.**
7. **Validate transport and security.**
8. **Inspect target-system response.**
9. **Reconcile source and target.**
10. **Implement root-cause correction and preventive controls.**

---

# Category Success Criteria

The candidate is ready for this category when they can:

- Diagnose complete and partial integration failures.
- Isolate source, filter, transformation, payload, transport, and target failures.
- Troubleshoot authentication and authorization issues.
- Handle duplicate processing and retry risks.
- Diagnose effective-dated replication problems.
- Analyze integration performance degradation.
- Handle test-versus-production differences.
- Troubleshoot target-system rejection.
- Design safe recovery and reprocessing.
- Perform structured root-cause analysis.
- Establish reconciliation and monitoring.
- Convert recurring incidents into permanent improvements.

---

## Interview Positioning

For a Tech Delivery SME interview, demonstrate this mindset:

**Do not ask only "Why did the integration fail?"**

Ask:

**What business event occurred? → What should have happened? → What actually happened? → Where did the two diverge? → How do we recover safely? → How do we prove recovery? → How do we prevent recurrence?**

That demonstrates the difference between a configuration resource and an **Employee Central Tech Delivery SME who can own production outcomes end-to-end**.
