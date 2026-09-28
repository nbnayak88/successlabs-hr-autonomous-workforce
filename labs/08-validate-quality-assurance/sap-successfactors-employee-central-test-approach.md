# SAP SuccessFactors Employee Central — Test Approach

**Program:** SAP SuccessFactors HRIS Modernization  
**Application:** SAP SuccessFactors Employee Central (EC)  
**Architecture Stream:** Applied Application Architecture (AA)  
**MIL Lab:** QAL — Quality Assurance Lab  
**Learning Intent:** VALIDATE  
**Industry Lens:** Energy / Pipeline Operations  
**Test Management:** Azure DevOps  
**Document Type:** Practical Test Approach

---

## 1. Purpose

This document explains **how testing will actually be performed** for SAP SuccessFactors Employee Central.

The Test Strategy defines **what quality must be achieved and why**.

The Test Approach defines **how the testing will be executed**.

The core principle is:

> **Do not test Employee Central as a collection of screens. Test it as the system of record supporting the employee lifecycle.**

The approach therefore combines:

**Business Process + Configuration + Data + Security + Workflow + Integration + End-to-End + Regression + Evidence**

---

# 2. Test Approach at a Glance

The EC testing approach follows:

```
Understand Business Process
          ↓
Identify Risk
          ↓
Design Business Scenarios
          ↓
Prepare Test Data
          ↓
Configure Test Users
          ↓
Execute Functional Tests
          ↓
Validate Workflow / Rules
          ↓
Validate Data
          ↓
Validate Integrations
          ↓
Execute E2E Scenarios
          ↓
Log & Triage Defects
          ↓
Retest
          ↓
Regression
          ↓
UAT
          ↓
Release Readiness
```

---

# 3. The EC Testing Mindset

For every Employee Central transaction, ask six questions:

| Question | Example |
|---|---|
| Who initiates? | HR Administrator |
| What data changes? | Job Information |
| What rule applies? | Business Rule |
| Who approves? | HR Manager |
| What becomes effective? | Future-dated job change |
| What downstream systems are affected? | Payroll / Reporting / Integrations |

This prevents testing from becoming:

> "I clicked Save and the screen worked."

Instead, the test asks:

> "Did the complete business transaction produce the correct organizational, employee, workflow, integration and downstream outcome?"

---

# 4. Approach 1 — Business-Process-Based Testing

## Objective

Start with the real HR process rather than with individual application features.

### Example: New Hire

Business process:

```
Recruit
  ↓
Select Candidate
  ↓
Onboard
  ↓
Create Employee
  ↓
Assign Organization
  ↓
Assign Position
  ↓
Assign Manager
  ↓
Assign Compensation
  ↓
Approve
  ↓
Replicate / Integrate
```

### How it will be tested

1. Identify the business process.
2. Identify actors.
3. Identify required data.
4. Identify configuration dependencies.
5. Identify integrations.
6. Identify expected outcomes.
7. Design positive and negative scenarios.
8. Execute.
9. Validate downstream impact.

### Example test scenario

**Scenario ID:** EC-HIRE-001

**Scenario:** Hire a salaried field employee.

**Preconditions:**

- Position exists.
- Department exists.
- Location exists.
- Manager exists.
- Appropriate test user is available.

**Test steps:**

1. Log in as authorized HR user.
2. Initiate new hire.
3. Enter personal information.
4. Select legal entity.
5. Select department.
6. Select position.
7. Assign manager.
8. Enter employment information.
9. Enter compensation information.
10. Submit workflow.
11. Approve transaction.
12. Verify employee record.
13. Verify downstream integration.

**Expected result:**

- Employee is created.
- Correct organizational data is assigned.
- Workflow completes.
- Effective date is correct.
- Required downstream data is generated.
- Unauthorized users cannot access restricted information.

---

# 5. Approach 2 — Risk-Based Testing

Not every EC function receives the same testing depth.

Prioritize:

**Business Criticality × Employee Impact × Integration Dependency × Failure Impact**

### Example

| Scenario | Risk | Testing Depth |
|---|---:|---|
| Employee Hire | High | Very High |
| Termination | Very High | Very High |
| Payroll-impacting Job Change | Very High | Very High |
| Manager Change | High | High |
| Department Change | High | High |
| Cosmetic label change | Low | Low |
| Optional report formatting | Low | Low |

### Example: Termination

Termination is high risk because an incorrect termination could affect:

- Employee access
- Payroll
- Benefits
- Time
- Reporting
- Downstream systems

Therefore the approach includes:

- Positive termination
- Future-dated termination
- Same-day termination
- Reversal
- Incorrect termination correction
- Manager visibility
- Security
- Payroll impact
- Integration impact
- Regression

---

# 6. Approach 3 — Positive / Negative / Boundary / Exception Testing

Each major EC transaction should have multiple scenario types.

## Example: Job Information Change

### Positive

Employee changes department successfully.

### Negative

Unauthorized user attempts the change.

### Boundary

Effective date equals current date.

### Exception

Required organizational field is missing.

### Future-dated

Change becomes effective next month.

### Backdated

Change is entered with a historical effective date.

### Sequential

Two job changes are entered for different future dates.

---

# 7. Approach 4 — Effective-Dated Testing

Effective dating is one of the most important EC testing concepts.

## Example

Employee currently belongs to:

**Operations Department**

A promotion becomes effective:

**1 November**

### Test

Create the promotion using an effective date of 1 November.

Validate:

### Before 1 November

Employee remains in the existing position.

### On/after 1 November

Employee has:

- New position
- New department where applicable
- New manager where applicable
- New compensation where applicable

### Additional tests

- Change the future-dated record.
- Delete/correct the future-dated change where permitted.
- Add another future-dated change.
- Enter a backdated correction.
- Validate downstream impact.

### Why this matters

A transaction can appear correct on the UI while the effective-dated history or downstream outcome is wrong.

---

# 8. Approach 5 — Workflow Testing

Workflows must be tested as a business control, not merely as a pop-up.

## Example

A promotion requires HR approval.

### Test flow

```
HR Initiates Promotion
        ↓
Business Rule Evaluates
        ↓
Workflow Triggered
        ↓
Approver Receives Request
        ↓
Approver Reviews
        ↓
Approve / Reject
        ↓
Employee Record Updated
```

### Positive test

Approver approves.

Expected:

- Transaction completes.
- Employee record changes.
- Correct effective date is maintained.

### Negative test

Approver rejects.

Expected:

- Transaction does not become effective.
- Appropriate status is recorded.
- Initiator receives expected notification where configured.

### Exception test

Approver is unavailable.

Validate configured delegation/escalation behavior.

---

# 9. Approach 6 — Business Rules Testing

Business Rules should be tested using combinations of:

- Trigger
- Condition
- Action
- Effective date
- User role
- Employee population

## Example

Rule:

> If employee is assigned to a specific employee group, require an additional field.

### Test matrix

| Employee Group | Field Provided | Expected |
|---|---|---|
| Group A | Yes | Pass |
| Group A | No | Validation |
| Group B | Yes | Pass |
| Group B | No | Pass |

### Testing approach

Do not test only the rule's happy path.

Test:

- Condition true
- Condition false
- Missing data
- Boundary values
- Multiple conditions
- Conflicting rules
- Effective-date behavior

---

# 10. Approach 7 — Role-Based Permission Testing

Security testing validates not only:

> "Can the transaction be completed?"

but:

> "Can the correct person complete it, and can everyone else not complete it?"

## Example

### HR Administrator

Can:

- Create employee
- Modify job information
- Terminate employee

### Manager

Can:

- View permitted employee information
- Initiate permitted transactions

### Employee

Can:

- View own permitted data
- Edit permitted self-service fields

### Test matrix

| Role | Action | Expected |
|---|---|---|
| HR Admin | Create employee | Allowed |
| Manager | Create employee | According to design |
| Employee | Create another employee | Denied |
| Manager | View restricted HR data | Denied |
| Employee | View another employee's restricted data | Denied |

Evidence should include screenshots or other appropriate execution evidence.

---

# 11. Approach 8 — Integration Testing

Employee Central should be tested as part of an ecosystem.

## Example

```
SmartRecruiters
       ↓
   Onboarding
       ↓
Employee Central
       ↓
Downstream Systems
       ↓
Payroll / Reporting
```

### Example: New Hire Integration

Test:

1. Candidate is selected.
2. Candidate moves to onboarding.
3. Onboarding completes.
4. Employee record is created in EC.
5. Employee ID is generated/assigned as designed.
6. Relevant employee data is transmitted.
7. Target system receives correct data.
8. Errors are handled appropriately.
9. Reconciliation confirms expected outcome.

### Integration validation dimensions

- Source data
- Trigger
- Transformation
- Mapping
- Transmission
- Target
- Error handling
- Retry
- Reconciliation

---

# 12. Approach 9 — Data Validation

For every critical transaction, validate both:

**UI outcome + underlying business data outcome**

## Example

Employee transfers from:

**Alberta Operations**

to:

**British Columbia Operations**

Validate:

- Department
- Location
- Position
- Manager
- Job information
- Effective date
- Compensation where applicable
- Employee history
- Downstream integration
- Reporting

### Three-level validation

**Level 1 — Record**

Did the transaction create/update the correct record?

**Level 2 — Field**

Are critical fields correct?

**Level 3 — Business**

Does the resulting employee state make business sense?

---

# 13. Approach 10 — Data Migration Testing

Migration testing is not:

> "The load completed successfully."

It is:

> "The migrated employee population is accurate, complete and usable."

## Example

100,000 employee records are migrated.

### Step 1 — Count reconciliation

Source:

**100,000**

Target:

**99,950**

Investigate:

**50 missing records**

### Step 2 — Field validation

Sample critical fields:

- Employee ID
- Employee status
- Department
- Location
- Manager
- Position

### Step 3 — Business validation

HR SMEs validate representative employees.

### Step 4 — Exception analysis

Classify:

- Missing
- Duplicate
- Transformation error
- Mapping error
- Expected exclusion
- Accepted exception

---

# 14. Approach 11 — End-to-End Employee Lifecycle Testing

This is one of the highest-value testing approaches.

## Example: Field Employee Lifecycle

```
Recruitment
    ↓
Candidate Selection
    ↓
Onboarding
    ↓
Employee Central
    ↓
Position / Job
    ↓
Manager
    ↓
Compensation
    ↓
Performance
    ↓
Time / Scheduling
    ↓
Payroll
    ↓
Reporting
```

### E2E scenario

> Hire a new field employee and validate the complete employee lifecycle across all relevant systems.

### What the Test Lead checks

- Business process
- Data
- Security
- Workflow
- Integration
- Timing
- Downstream systems
- Reporting
- Employee experience

---

# 15. Approach 12 — Regression Testing

Regression protects functionality that already works.

## Example

A new business rule is introduced for Job Information.

Potential impact:

- Hire
- Promotion
- Transfer
- Manager change
- Termination
- Workflow
- Integrations
- Reporting

### Regression approach

```
Change Introduced
       ↓
Impact Analysis
       ↓
Identify Affected Processes
       ↓
Select Regression Pack
       ↓
Execute
       ↓
Compare Results
       ↓
Defect?
       ↓
Retest
```

### Regression pack

At minimum include critical:

- Hire
- Job Change
- Promotion
- Transfer
- Termination
- Rehire
- Workflow
- Security
- Integration

---

# 16. Approach 13 — Defect-Based Testing

A defect is not closed merely because a developer changes configuration.

## Example

Defect:

> Promotion workflow incorrectly routes to the wrong approver.

### Initial evidence

Expected:

**HR Manager**

Actual:

**Department Manager**

### Fix

SI modifies workflow configuration.

### Retest

Execute the original failed scenario.

### Regression

Test other workflows that use the same configuration.

### Closure

Close only when:

- Original issue passes
- Evidence is captured
- Relevant regression passes
- Business impact is addressed

---

# 17. Approach 14 — UAT Approach

UAT should use realistic business scenarios rather than technical test cases.

## Example UAT Scenario

> As an HR Business Partner, process a promotion for a field employee effective next month and confirm that all required approvals, employee data, compensation information and downstream outcomes are correct.

### UAT execution

1. Business SME receives scenario.
2. SME receives test data.
3. SME executes the script.
4. SME records actual result.
5. SME attaches evidence.
6. Failures are logged.
7. Test Lead coordinates triage.
8. Fix is deployed.
9. SME retests.
10. Business owner provides acceptance.

---

# 18. Approach 15 — Smoke Testing

Before starting a major test cycle, perform a small smoke pack.

## EC Smoke Pack

- Login
- Employee search
- View employee
- Create/test transaction
- Workflow submission
- Approval
- Save
- Basic navigation
- Critical integration connectivity

### Purpose

Determine:

> **Is the environment stable enough for meaningful testing?**

If the smoke test fails, do not waste business tester capacity on a broken environment.

---

# 19. Approach 16 — Exploratory Testing

Scripted testing provides coverage.

Exploratory testing provides discovery.

## Example

After completing a manager-change scenario, explore:

- What if the manager is inactive?
- What if the manager changes simultaneously?
- What if the effective date is future-dated?
- What if required organizational data is missing?
- What if the transaction is rejected?
- What happens after the employee is terminated?

The goal is to identify defects not anticipated by scripted scenarios.

---

# 20. Approach 17 — Test Data / Persona Matrix

Build reusable personas.

| Persona | Example Purpose |
|---|---|
| New Employee | Hire / onboarding |
| Existing Employee | Job change |
| Manager | Approval / team changes |
| HR Administrator | Core transactions |
| HR Business Partner | Business validation |
| Terminated Employee | Termination / rehire |
| Rehire Employee | Rehire scenarios |
| Field Employee | Energy operational scenario |
| Corporate Employee | Corporate scenario |
| Restricted Employee | Security testing |

---

# 21. Approach 18 — Test Cycle Execution

A practical EC test cycle can follow:

```
DAY 0
Environment + Data + User Readiness
        ↓
DAY 1
Smoke Testing
        ↓
DAY 2–5
Functional Execution
        ↓
DAY 4–7
Defect Fix + Retest
        ↓
DAY 6–8
Integration / E2E
        ↓
DAY 8–10
Regression
        ↓
Cycle Exit
```

The exact duration depends on the program plan; the important point is that execution, defect fixing, retest and regression are planned together rather than sequentially at the very end.

---

# 22. Approach 19 — Daily Test Management

The Test Lead should run a daily control loop:

### Morning

**Where are we?**

- Planned
- Executed
- Passed
- Failed
- Blocked

### Midday

**What is preventing progress?**

- Environment
- Data
- Defects
- Tester availability
- Integration

### Afternoon

**What changed?**

- New defects
- Fixes
- Retests
- Regression
- Risks

### End of Day

**What does leadership need to know?**

- Progress
- Critical failures
- Risks
- Decisions
- Next-day priorities

---

# 23. Approach 20 — Azure DevOps Execution Model

Recommended structure:

```
Test Plan
│
├── Functional
│   ├── Hire
│   ├── Job Change
│   ├── Termination
│   ├── Rehire
│   └── Workflow
│
├── SIT
│   ├── Recruiting → EC
│   ├── Onboarding → EC
│   ├── EC → Downstream
│   └── EC → Payroll
│
├── E2E
│   ├── Hire-to-Pay
│   ├── Transfer-to-Pay
│   └── Termination-to-Pay
│
├── UAT
│
└── Regression
```

Each test case should be linked to appropriate requirements and defects.

---

# 24. Worked Example — Employee Promotion

This is the complete approach in one scenario.

## Business requirement

HR must be able to promote an employee effective on a future date.

## Risk

Incorrect promotion data could affect:

- Position
- Manager
- Compensation
- Payroll
- Reporting
- Employee history

## Test data

Employee:

**EMP10025**

Current:

**Operations Analyst**

Future:

**Senior Operations Analyst**

Effective date:

**1 November**

## Test cases

### TC01 — Positive

Create promotion successfully.

### TC02 — Workflow

Verify correct approver.

### TC03 — Effective Date

Verify old state before 1 November and new state from 1 November.

### TC04 — Negative

Unauthorized user attempts promotion.

### TC05 — Missing Data

Required promotion field is missing.

### TC06 — Integration

Validate downstream employee/job data.

### TC07 — Regression

Verify hire, transfer and termination workflows remain unaffected.

## Expected outcome

- Promotion is recorded.
- Correct effective date is maintained.
- Workflow routes correctly.
- Authorized user can execute.
- Unauthorized user is prevented.
- Downstream data is correct.
- Regression pack passes.

---

# 25. Worked Example — Employee Termination

## Business requirement

HR must terminate an employee and ensure downstream processes receive the correct status.

## Test approach

### Positive

Terminate employee using correct reason and effective date.

### Future-dated

Schedule termination for a future date.

### Negative

Attempt termination without required data.

### Security

Unauthorized user attempts termination.

### Integration

Verify downstream systems receive the appropriate employee status.

### Reversal / correction

Validate the supported process for correcting an erroneous termination.

### Regression

Validate related employee lifecycle transactions.

## Risk

Termination has potentially significant consequences for:

- Payroll
- Benefits
- Time
- Access
- Reporting
- Compliance

Therefore it receives high testing priority.

---

# 26. Worked Example — Rehire

Rehire scenarios should be explicitly tested rather than assumed to behave like hire.

### Scenarios

- Rehire former employee
- Rehire into different department
- Rehire under different manager
- Rehire with changed position
- Rehire with different compensation
- Rehire with future effective date
- Rehire where historical information must remain available

### Validate

- Employee identity
- Employment history
- New employment record
- Organizational assignment
- Permissions
- Workflow
- Downstream integrations
- Reporting

---

# 27. Worked Example — Manager Change

## Scenario

An employee's manager changes effective next month.

### Validate

**Before effective date**

Old manager.

**On/after effective date**

New manager.

### Then validate:

- Employee hierarchy
- Manager visibility
- Workflow routing
- Reporting
- Approvals
- Security
- Downstream integrations

This is a good example of why an apparently simple EC transaction requires cross-functional testing.

---

# 28. Worked Example — Security

## Scenario

A manager should see permitted information only for direct reports.

### Tests

1. Manager views direct report.
2. Manager views permitted indirect report.
3. Manager attempts restricted data access.
4. Manager attempts unauthorized update.
5. Employee attempts another employee's data access.
6. HR administrator accesses required HR information.

### Expected

Access must align with the configured security model.

Security validation should be included in functional, regression and UAT testing where relevant.

---

# 29. Test Approach Decision Matrix

| Question | Approach |
|---|---|
| Does the business process work? | Business-process testing |
| Is high-risk functionality sufficiently covered? | Risk-based testing |
| Does the transaction work normally? | Positive testing |
| Does it fail correctly? | Negative testing |
| Does it work at limits? | Boundary testing |
| Does unusual business behavior work? | Exception testing |
| Do rules behave correctly? | Business-rule testing |
| Do approvals work? | Workflow testing |
| Are permissions correct? | Security testing |
| Does data flow correctly? | Integration testing |
| Is migrated data correct? | Data migration testing |
| Does the complete employee journey work? | E2E testing |
| Did a change break existing functionality? | Regression testing |
| Can business users accept the process? | UAT |
| Is the environment usable for testing? | Smoke testing |
| What defects exist outside scripted paths? | Exploratory testing |

---

# 30. Evidence Model

Every important test should produce evidence.

Possible evidence:

- Screenshot
- Test execution result
- Input data
- Output data
- Integration response
- Report output
- Workflow history
- Audit information
- Error message
- Reconciliation result

The evidence should answer:

> **What did we test, what did we expect, what actually happened, and why should we trust the result?**

---

# 31. Entry Criteria for EC Testing

Before execution begins:

- EC configuration is available
- Required business processes are configured
- Test environment is stable
- Test users are provisioned
- Test data is loaded
- Test cases are reviewed
- Required integrations are available
- Known blockers are documented
- Testers are trained

---

# 32. Exit Criteria for EC Testing

Exit should consider:

- Critical scenarios executed
- Required coverage achieved
- Critical scenarios passed
- Critical defects resolved or formally accepted
- Retesting completed
- Regression completed
- Integration scenarios validated
- Data issues understood
- Business acceptance achieved where applicable
- Residual risks documented

---

# 33. What the Test Lead Does Differently

A tester asks:

> **"Does this test pass?"**

A Test Lead asks:

> **"What does this result tell me about business readiness?"**

A functional tester asks:

> **"Does the transaction work?"**

A Test Lead asks:

> **"What other processes, systems, data and users could this transaction affect?"**

A defect manager asks:

> **"How many defects are open?"**

A Test Lead asks:

> **"Which open defects create unacceptable business risk?"**

This distinction is central to Test Lead-level thinking.

---

# 34. Interview Answer Framework

When asked:

> **"Explain your test approach for Employee Central."**

Use this structure:

### 1. Start with business processes

> "I start with the employee lifecycle and critical HR processes rather than isolated EC features."

### 2. Establish risk

> "I identify the transactions with the highest employee, payroll, regulatory and integration impact."

### 3. Design scenarios

> "For each critical process I build positive, negative, boundary, exception, security, integration and E2E scenarios."

### 4. Prepare data

> "I create realistic employee personas and effective-dated test data."

### 5. Execute

> "I execute functional testing first, followed by SIT, E2E, regression and UAT."

### 6. Manage defects

> "Defects are triaged according to business impact, retested after fixes and included in regression where appropriate."

### 7. Validate integrations

> "I verify that EC data reaches downstream systems correctly and reconcile the outcomes."

### 8. Measure readiness

> "Finally, I use coverage, execution, defect, integration, data and UAT evidence to assess residual risk and support the release decision."

---

# 35. The 80/20 EC Test Approach

If time is limited, master these scenarios first:

1. Hire
2. Job Information Change
3. Promotion
4. Transfer
5. Manager Change
6. Termination
7. Rehire
8. Future-Dated Change
9. Workflow
10. Business Rule
11. Role-Based Permission
12. Integration
13. Data Migration
14. E2E Employee Lifecycle
15. Regression

These scenarios cover a large proportion of the thinking required for an EC Test Lead interview.

---

# 36. Final Mental Model

Remember:

```
BUSINESS
   ↓
PROCESS
   ↓
RISK
   ↓
SCENARIO
   ↓
DATA
   ↓
EXECUTE
   ↓
EVIDENCE
   ↓
DEFECT
   ↓
RETEST
   ↓
REGRESSION
   ↓
E2E
   ↓
UAT
   ↓
RESIDUAL RISK
   ↓
GO-LIVE
```

The Test Approach is therefore:

> **Test the employee lifecycle, not the screen.**

And for every EC transaction:

> **Who initiates → What changes → What rule applies → Who approves → What becomes effective → What downstream systems change → What could fail?**

---

# 37. QAL Connection

This approach operationalizes the QAL principle:

> **Test the business, not just the button.**

The quality evidence chain becomes:

**Business Requirement → EC Scenario → Test Data → Execution → Evidence → Defect → Fix → Retest → Regression → Business Acceptance**

> **VALIDATE before you trust.**
