# Scenario Category 14 — Production Incident & Hypercare

## Target Role
**Tech Delivery Subject Matter Expert — SAP SuccessFactors Employee Central**

## Objective
Prepare for SME-level scenarios involving Employee Central production incidents, go-live stabilization, hypercare, business impact assessment, incident triage, emergency fixes, rollback, stakeholder communication, root-cause analysis, monitoring, and transition to steady-state support.

> **Interview principle:** A production SME does not start by changing configuration. Start with **business impact, scope, evidence, containment, safe recovery, validation, communication, RCA, and prevention**.

---

# 1. Critical Hiring Process Fails Immediately After Go-Live

### Scenario Question
The day after Employee Central go-live, HR administrators cannot complete new-hire transactions. What would you do?

### STAR Answer

**Situation**  
A critical employee lifecycle process was blocked immediately after production go-live.

**Task**  
I needed to stabilize the business process quickly while identifying the underlying defect.

**Action**
1. Declared the appropriate incident severity.
2. Quantified affected users and hiring transactions.
3. Reproduced the issue using a controlled production scenario where permitted.
4. Compared production configuration against the validated release baseline.
5. Checked RBP, data model, Business Rules, workflow, and integration dependencies.
6. Determined whether the issue was introduced by configuration, deployment, data, or environment.
7. Applied the safest approved workaround if available.
8. Implemented and validated the permanent fix through the emergency-change process.
9. Re-tested the complete hire lifecycle.
10. Monitored subsequent hiring transactions during hypercare.

**Result**  
The hiring process was restored with controlled production change and the incident was converted into a documented preventive action.

### Follow-up Questions
- What would you check first?
- When would you use a workaround?
- How would you communicate to HR leadership?
- What evidence would you capture?

---

# 2. Production Defect Affects Only One Country

### Scenario Question
Employee Central works normally for most countries, but employees in one country cannot complete job changes. How would you investigate?

### STAR Answer

**Situation**  
A production issue was isolated to one geographic population.

**Task**  
I needed to determine whether the defect was caused by country-specific configuration, data, security, workflow, or integration behavior.

**Action**
1. Established the exact affected population.
2. Compared an affected user with a working user from another country.
3. Compared country-specific configuration and data.
4. Checked RBP target populations.
5. Reviewed country-specific fields and validations.
6. Checked Business Rules and workflow conditions.
7. Assessed integration dependencies.
8. Identified the smallest reproducible scenario.
9. Applied a controlled fix.
10. Performed regression testing for both affected and unaffected countries.

**Result**  
The country-specific defect was isolated without introducing unnecessary global configuration changes.

### Follow-up Questions
- How would you prove it is country-specific?
- What if the configuration is globally shared?
- How would you avoid fixing the symptom?

---

# 3. Incorrect Employee Data Appears After Go-Live

### Scenario Question
After migration, HR discovers that thousands of employees have incorrect organizational information. What is your immediate response?

### STAR Answer

**Situation**  
Post-go-live validation identified a large population of incorrect employee data.

**Task**  
I needed to contain the issue, determine its scope, and recover accurately without creating additional data corruption.

**Action**
1. Assessed business impact.
2. Identified whether the issue was still actively propagating through integrations.
3. Contained downstream propagation where appropriate.
4. Compared source, migration files, Employee Central, and downstream data.
5. Segmented the population by error type.
6. Determined whether the root cause was mapping, transformation, configuration, or source data.
7. Corrected the source defect.
8. Reprocessed only the affected population through an approved method.
9. Reconciled the complete population.
10. Established additional post-go-live validation.

**Result**  
The organization recovered the affected data while preventing the same defect from continuing to propagate.

### Follow-up Questions
- Would you immediately reload all employees?
- How would you prevent duplicate changes?
- What would you tell business stakeholders?

---

# 4. Workflow Approvals Stop Working in Production

### Scenario Question
Managers report that Employee Central transactions are saving but no approval workflow is being triggered. What would you do?

### STAR Answer

**Situation**  
A critical approval control stopped functioning after production deployment.

**Task**  
I needed to determine whether the issue was caused by transaction configuration, workflow criteria, permissions, or deployment differences.

**Action**
1. Identified the affected transaction types.
2. Reproduced with a controlled test user.
3. Confirmed the transaction itself was saving successfully.
4. Reviewed workflow trigger conditions.
5. Checked relevant RBP and workflow configuration.
6. Compared production against the approved configuration baseline.
7. Reviewed recent changes.
8. Determined whether the issue affected all populations or specific roles.
9. Implemented the approved fix and validated approval routing.
10. Monitored subsequent transactions.

**Result**  
Approval control was restored and production monitoring confirmed that the workflow was triggering correctly.

### Follow-up Questions
- How do you distinguish workflow failure from RBP failure?
- What is the risk if transactions continue without approval?
- Would you stop the process?

---

# 5. Production Integration Failure During Hypercare

### Scenario Question
The Employee Central-to-payroll integration fails during the first payroll cycle after go-live. How would you handle it?

### STAR Answer

**Situation**  
A critical downstream payroll interface failed during the first production payroll cycle.

**Task**  
I needed to protect payroll processing while recovering the interface safely.

**Action**
1. Established incident severity and payroll impact.
2. Identified the failed execution and affected population.
3. Determined whether the failure was complete or partial.
4. Preserved logs, payloads, and execution evidence.
5. Checked source data and integration selection.
6. Investigated mapping, transport, authentication, and target errors.
7. Coordinated with payroll and integration teams.
8. Reprocessed only the affected population after confirming retry safety.
9. Reconciled Employee Central and payroll.
10. Performed an RCA and introduced enhanced monitoring.

**Result**  
Payroll processing continued with controlled recovery and the interface entered subsequent cycles with stronger monitoring.

### Follow-up Questions
- What if some employees were already processed?
- How would you prevent duplicate payroll transactions?
- What should be included in the incident communication?

---

# 6. Emergency Production Fix

### Scenario Question
A defect is confirmed as critical, but the standard release process would take several days. The business asks you to fix production immediately. What would you do?

### STAR Answer

**Situation**  
A critical defect required urgent remediation outside the normal release cycle.

**Task**  
I needed to balance business urgency with production-change governance.

**Action**
1. Confirmed severity and business impact.
2. Identified whether an approved workaround existed.
3. Performed root-cause analysis to avoid an unsafe change.
4. Prepared the smallest viable production fix.
5. Defined risk, rollback, and validation criteria.
6. Obtained emergency-change approval.
7. Tested the fix in the closest available non-production environment.
8. Executed the production change with appropriate technical support.
9. Performed immediate business validation.
10. Scheduled full regression and permanent release governance afterward.

**Result**  
The critical business issue was addressed without bypassing essential production controls.

### Follow-up Questions
- What makes an emergency change different from normal deployment?
- When would you refuse a risky emergency fix?
- How would you validate rollback?

---

# 7. Go-Live Performance Degradation

### Scenario Question
Employee Central becomes significantly slower after go-live. Users report long response times for common HR transactions. How would you approach this?

### STAR Answer

**Situation**  
Production performance degraded after a major implementation or release.

**Task**  
I needed to determine whether the problem was configuration, data volume, integration activity, user load, or an external platform issue.

**Action**
1. Quantified affected transactions and users.
2. Identified when the degradation began.
3. Compared production performance with pre-go-live baselines.
4. Checked recent configuration and data changes.
5. Assessed high-volume imports and integrations.
6. Reviewed transaction-specific behavior.
7. Coordinated with platform and technical teams when required.
8. Applied safe workload or configuration controls where appropriate.
9. Monitored performance after remediation.
10. Documented the root cause and capacity/performance actions.

**Result**  
The performance issue was isolated and stabilized with measurable post-fix monitoring.

### Follow-up Questions
- How would you distinguish platform issues from configuration issues?
- What performance metrics matter?
- Could a migration or integration create the problem?

---

# 8. Security Incident During Hypercare

### Scenario Question
A user reports that they can see employee information outside their authorized population after go-live. What would you do?

### STAR Answer

**Situation**  
A potential RBP security defect was identified during hypercare.

**Task**  
I needed to protect employee data immediately while determining the scope and cause.

**Action**
1. Treated the issue as a security-sensitive incident.
2. Identified the affected user and visible population.
3. Determined whether other users had the same access.
4. Reviewed assigned permission roles, groups, and target populations.
5. Assessed sensitive data exposure.
6. Applied approved containment.
7. Corrected the underlying RBP configuration.
8. Performed positive and negative security testing.
9. Assessed whether audit or security escalation was required.
10. Documented remediation and added an access-review control.

**Result**  
Unauthorized visibility was contained and corrected with evidence-based security validation.

### Follow-up Questions
- Would you immediately remove all access?
- How would you determine the exposure population?
- What evidence should be retained?

---

# 9. Managing Hypercare Across Multiple Teams

### Scenario Question
During the first two weeks after go-live, HR, payroll, integration, security, and technical teams are raising incidents through different channels. How would you bring order to hypercare?

### STAR Answer

**Situation**  
Multiple teams were raising production issues without a consistent triage and ownership process.

**Task**  
I needed to create a coordinated hypercare operating model.

**Action**
1. Established a single incident intake mechanism.
2. Defined severity and priority criteria.
3. Created functional ownership categories.
4. Established daily triage.
5. Maintained an incident tracker with status and next action.
6. Identified recurring defects separately from one-time incidents.
7. Defined escalation paths.
8. Provided structured stakeholder updates.
9. Monitored critical business processes.
10. Defined exit criteria for hypercare.

**Result**  
Hypercare became a coordinated stabilization period rather than an uncontrolled stream of individual support requests.

### Follow-up Questions
- What are good hypercare exit criteria?
- How do you prevent incident duplication?
- How do you identify recurring problems?

---

# 10. Transitioning From Hypercare to BAU

### Scenario Question
The system is stable after six weeks of hypercare. How would you determine whether the solution is ready for steady-state support?

### STAR Answer

**Situation**  
Production stability had improved and the project needed to transition to normal operations.

**Task**  
I needed to ensure the support organization could own the solution without losing operational knowledge.

**Action**
1. Reviewed incident trends and unresolved defects.
2. Confirmed critical business processes were stable.
3. Verified integrations and reconciliation.
4. Reviewed recurring incident categories.
5. Completed knowledge transfer.
6. Validated support documentation and runbooks.
7. Confirmed monitoring and alerting.
8. Reviewed open technical debt and known issues.
9. Defined BAU ownership and escalation paths.
10. Obtained formal transition acceptance.

**Result**  
The solution transitioned to BAU with documented ownership, operational controls, and known-risk visibility.

### Follow-up Questions
- What are your hypercare exit criteria?
- What should remain on the known-issues list?
- How would you measure post-hypercare stability?

---

# Rapid-Fire SME Probes

1. What is hypercare?
2. How is hypercare different from BAU support?
3. What makes an incident critical?
4. What is incident containment?
5. What evidence should be collected during a production incident?
6. When should an emergency change be used?
7. What is rollback?
8. How do you handle a partial production failure?
9. How do you communicate during a major incident?
10. How do you distinguish incident from problem management?
11. What are good hypercare exit criteria?
12. What should a production runbook contain?
13. How do you monitor critical HR processes?
14. How do you handle a security-sensitive production incident?
15. How do you identify recurring production defects?
16. What should be included in an RCA?
17. How do you transition from project support to BAU?

---

# Master Production Incident Framework

Use this sequence in an interview:

**IMPACT → CONTAIN → EVIDENCE → ISOLATE → RECOVER → VALIDATE → COMMUNICATE → RCA → PREVENT → TRANSITION**

### 1. IMPACT
Determine:
- Business process affected
- Number of employees/users
- Countries
- Payroll impact
- Security impact
- Compliance impact
- Deadline sensitivity

### 2. CONTAIN
Prevent further incorrect processing or data propagation.

### 3. EVIDENCE
Capture:
- Error messages
- Logs
- Timestamps
- Affected users
- Employee examples
- Configuration changes
- Integration executions
- Payloads where relevant

### 4. ISOLATE
Determine whether the problem is:
- Configuration
- Data
- RBP
- Workflow
- Business Rule
- Integration
- Migration
- Environment/platform

### 5. RECOVER
Use the safest approved recovery mechanism:
- Workaround
- Correction
- Controlled retry
- Emergency change
- Rollback

### 6. VALIDATE
Validate:
- Technical fix
- Business transaction
- Downstream effects
- Security
- Reconciliation

### 7. COMMUNICATE
Provide:
- Current impact
- Known facts
- Action underway
- Owner
- Next checkpoint
- Expected business effect

### 8. RCA
Identify the underlying cause rather than documenting only the symptom.

### 9. PREVENT
Implement:
- Monitoring
- Validation
- Regression testing
- Process controls
- Documentation
- Automation

### 10. TRANSITION
Move the issue or solution into BAU with ownership and runbook coverage.

---

# Hypercare Command Center Checklist

During hypercare, monitor:

| Area | What to Monitor |
|---|---|
| Hire | Successful employee creation |
| Job Changes | Transaction completion and approvals |
| Manager Changes | Hierarchy and RBP behavior |
| Termination | Status and downstream propagation |
| Payroll | Replication/reconciliation |
| Integrations | Job success, failures, latency |
| RBP | Unexpected access |
| Workflow | Trigger and approval completion |
| Data Quality | Critical-field exceptions |
| Performance | Transaction response |
| User Adoption | Repeated user issues |

---

# Incident Severity Thinking

Consider:

| Factor | Key Question |
|---|---|
| Business Criticality | Is a core HR process blocked? |
| Population | One employee or thousands? |
| Payroll | Is payroll processing affected? |
| Security | Is employee data exposed? |
| Compliance | Is there regulatory risk? |
| Timing | Is a critical business deadline approaching? |
| Workaround | Is a safe workaround available? |
| Recoverability | Can the state be safely restored? |
| Recurrence | Is this a repeated issue? |

---

# Hypercare Exit Criteria

Do not define hypercare completion only by elapsed time.

Consider:

- No unresolved critical incidents
- Stable core employee lifecycle transactions
- Stable integrations
- Successful payroll reconciliation
- No known critical security defects
- Acceptable data-quality levels
- Support team trained
- Runbooks completed
- Monitoring operational
- Known issues documented
- BAU ownership accepted
- Stakeholder sign-off completed

---

# Common Anti-Patterns

Avoid answers such as:

- "I would immediately change production configuration."
- "The project team should fix every issue themselves."
- "If users can work around it, the incident is closed."
- "We can skip RCA after go-live."
- "Hypercare ends after two weeks regardless of stability."
- "Only technical teams need to know about a production incident."
- "A successful integration job means the business process is healthy."
- "Security incidents can wait until normal support hours."

Instead, demonstrate **business-impact assessment, controlled containment, evidence-based diagnosis, safe recovery, stakeholder communication, RCA, and measurable stabilization**.

---

# Strong SME Answer Pattern

For any production incident, structure the response as:

1. **Assess business impact.**
2. **Classify severity.**
3. **Contain further impact.**
4. **Collect evidence.**
5. **Isolate the failure layer.**
6. **Determine recovery strategy.**
7. **Communicate clearly.**
8. **Validate the recovery end-to-end.**
9. **Perform RCA and preventive action.**
10. **Track stability through hypercare and BAU transition.**

---

# Category Success Criteria

The candidate is ready for this category when they can:

- Lead a critical Employee Central production incident.
- Assess business, payroll, security, and compliance impact.
- Distinguish containment from permanent resolution.
- Troubleshoot configuration, data, workflow, RBP, and integration issues.
- Manage emergency production changes.
- Design a hypercare operating model.
- Define measurable hypercare exit criteria.
- Conduct production reconciliation.
- Communicate effectively with business and technical stakeholders.
- Perform RCA and preventive improvement.
- Transition a solution from project hypercare to BAU support.

---

## Interview Positioning

For a Tech Delivery SME interview, frame production ownership as:

**Business Impact → Containment → Diagnosis → Safe Recovery → Validation → Communication → RCA → Prevention → BAU**

The strongest answers demonstrate that the SME remains accountable for the **business outcome**, even when the technical root cause sits across configuration, integration, security, data, or another delivery team.
