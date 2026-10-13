# Scenario Category 12 — Data Quality & Reconciliation

## Interview Practice Guide — 20 Scenario-Based Questions, STAR Answers & SME Probes

**Track:** SCALE — School of Career Acceleration  
**Target Role:** Tech Delivery Subject Matter Expert — SAP SuccessFactors Employee Central  
**Question IDs:** SCALE-EC-12-Q01 through SCALE-EC-12-Q20

## Learning outcome

Define data quality, identify root causes, reconcile Employee Central records with source and consumer systems, manage exceptions, protect historical integrity, and establish sustainable ownership and controls.

> **Answer integrity and product accuracy:** The STAR responses are illustrative models. Replace them with real evidence and do not invent metrics. Confirm actual data, reporting, API, audit, and monitoring capabilities in the target tenant and current official product documentation. A technically successful transaction does not, by itself, prove business data is correct.

---

## Q01 — Establish a Data Quality Baseline

### Interview Question
The organization reports inconsistent employee and organizational data but has no agreed quality baseline. How do you establish one?

### STAR Model Answer
- **Situation:** Stakeholders report data issues without shared definitions, comparable measures, or an accountable owner.
- **Task:** Establish a meaningful baseline that can drive prioritized remediation and prevention.
- **Action:** I would define quality dimensions such as completeness, validity, uniqueness, consistency, accuracy, and timeliness. I would identify critical entities/fields, data sources, population boundaries, as-of dates, and business impact. I would profile a representative data set, validate findings with data owners, and define measures, thresholds, and remediation ownership.
- **Result:** The team would have a repeatable baseline and prioritized quality backlog rather than a subjective assessment.

### SAP SuccessFactors Employee Central Example
Profile selected EC person/employment/job and organizational attributes using approved data access and agreed business definitions.

### SME Probe
How do you distinguish a measurable data defect from a disagreement about the business definition?

---

## Q02 — Diagnose Conflicting Values Across Systems

### Interview Question
Employee Central and a downstream HR report show different departments for the same employee. How do you reconcile the discrepancy?

### STAR Model Answer
- **Situation:** Two sources show different values, and teams disagree about which is correct.
- **Task:** Determine whether the difference reflects source data, effective dates, replication timing, mapping, or reporting semantics.
- **Action:** I would align employee key, as-of date, population, and definition; trace the EC record history and target record; inspect transformation and extraction timing; then classify the variance. I would correct the responsible layer and rerun reconciliation, preserving any legitimate timing differences as documented exceptions.
- **Result:** The variance would have an evidenced cause and a repeatable reconciliation process.

### SAP SuccessFactors Employee Central Example
Compare the same employee's EC effective-dated record and downstream value at an agreed timestamp/as-of date.

### SME Probe
How can both systems be technically correct while showing different values?

---

## Q03 — Missing Critical Employee Data

### Interview Question
A report reveals that a subset of employees lacks a critical organizational or job attribute. What is your remediation approach?

### STAR Model Answer
- **Situation:** Missing data can block transactions, weaken reporting, or disrupt connected processing.
- **Task:** Correct existing records and prevent repeated defects.
- **Action:** I would identify the affected population and criticality, trace the source and owner of the value, and determine whether the gap originates in process, import, integration, permissions, or configuration. I would coordinate approved correction, validate dependent records and consumers, and assess whether preventive validation or upstream process changes are justified.
- **Result:** The issue would be remediated with root-cause and prevention evidence, not just a one-time data fill.

### SAP SuccessFactors Employee Central Example
Trace the missing field through the relevant EC transaction and any source/import process that maintains it.

### SME Probe
When should a missing value block a transaction rather than be handled through a controlled exception?

---

## Q04 — Duplicate or Ambiguous Records

### Interview Question
Data quality checks flag potentially duplicate employees, but some may be legitimate rehires or separate employment relationships. How do you resolve the list?

### STAR Model Answer
- **Situation:** Duplicate detection identifies suspicious records but cannot safely distinguish all valid scenarios.
- **Task:** Resolve true duplicates without damaging identity, history, or valid employment relationships.
- **Action:** I would define approved matching criteria, review key identifiers and lifecycle history, and classify records into confirmed duplicate, valid related record, or ambiguous case. I would involve authorized data owners for uncertain identities, document correction decisions, and verify downstream references before any merge or removal.
- **Result:** Only supported corrections would be made and ambiguous cases would remain governed exceptions rather than being destructively resolved by guesswork.

### SAP SuccessFactors Employee Central Example
Review person/employment identifiers and lifecycle history according to the target identity policy before correcting records.

### SME Probe
What evidence must be gathered before merging or deleting a suspected duplicate?

---

## Q05 — Effective-Dated Data Reconciliation

### Interview Question
EC shows the correct current department, but a historical headcount report is wrong. How do you investigate effective dating?

### STAR Model Answer
- **Situation:** Current state is correct, yet historical reporting does not reflect the employee's organization at the selected past date.
- **Task:** Identify whether the source record, as-of logic, extraction, or reporting transformation is incorrect.
- **Action:** I would inspect the full effective-dated timeline and compare it with the report date/filter, field selection, and downstream history retention. I would validate a small set of known employee changes, then correct the appropriate layer and regression-test current and historical views.
- **Result:** Historical and current reporting would align to their defined time semantics.

### SAP SuccessFactors Employee Central Example
Trace a controlled employee with multiple effective-dated Job Information records into the actual history/report path.

### SME Probe
Why is a snapshot of today's data insufficient for historical workforce reporting?

---

## Q06 — Data Quality Rules and Prevention

### Interview Question
The same invalid organizational values recur after cleanup. What preventive controls would you propose?

### STAR Model Answer
- **Situation:** Defects are repeatedly corrected but re-enter the system through normal operations or data feeds.
- **Task:** Reduce recurrence by addressing the point where invalid data originates.
- **Action:** I would trend defect causes and entry channels, identify the authoritative source and business owner, and assess supported validation, reference-data governance, process approvals, import/interface checks, and monitoring. I would introduce controls at the appropriate layers and measure both prevented errors and legitimate transaction friction.
- **Result:** The organization would move from repeated cleanup to root-cause prevention and ongoing measurement.

### SAP SuccessFactors Employee Central Example
Trace a recurring invalid value to the source transaction or load channel and test the preventive control against valid and invalid cases.

### SME Probe
Why might an EC UI validation fail to prevent the same defect from arriving via integration?

---

## Q07 — Reconciliation Control Design

### Interview Question
A downstream integration reports success but the business cannot verify completeness. How do you design reconciliation?

### STAR Model Answer
- **Situation:** Technical monitoring does not prove all expected records and values reached the target.
- **Task:** Establish business-level evidence of completeness and correctness.
- **Action:** I would define the population, keys, data fields, cutoff time, effective-date semantics, and acceptable exceptions. I would compare expected source records with extraction, delivered, accepted, and target states; classify omissions, duplicates, rejected values, and timing differences; and assign remediation owners. I would automate repeatable checks where approved and validate after recovery.
- **Result:** Reconciliation would be repeatable, owned, and tied to business outcomes.

### SAP SuccessFactors Employee Central Example
Build a record-level reconciliation for the EC population and actual downstream consumer using shared identifiers and agreed inclusion rules.

### SME Probe
What business measures catch wrong values if row counts and keys match?

---

## Q08 — Picklist and Reference Data Integrity

### Interview Question
Reports contain multiple labels for the same business category after a value change. How do you investigate and rationalize the data?

### STAR Model Answer
- **Situation:** Reference values and reporting categories are inconsistent across time or systems.
- **Task:** Preserve business meaning while establishing governed value usage.
- **Action:** I would identify source values, historical records, mapping tables, consumer logic, and approved value definitions. I would distinguish a label difference from a different underlying code or concept, then plan a governed crosswalk or correction. I would test historical reporting and integrations before implementing changes.
- **Result:** The organization would have consistent, documented reference semantics and controlled treatment of legacy values.

### SAP SuccessFactors Employee Central Example
Compare actual configured picklist/reference values and downstream code translations in the target landscape.

### SME Probe
Why should labels not be treated as stable integration keys without checking the contract?

---

## Q09 — Data Ownership and Stewardship

### Interview Question
HR Operations, HRIS, and Finance each correct the same employee data differently. How do you establish sustainable ownership?

### STAR Model Answer
- **Situation:** Multiple teams make conflicting changes because ownership and authority are unclear.
- **Task:** Establish who defines, approves, changes, and reconciles each data element.
- **Action:** I would map data elements to business definitions, authoritative sources, stewardship, update rights, approval rules, and consumer responsibilities. I would define conflict resolution, correction evidence, and escalation. I would validate the model against real exception cases and update the RACI/process documentation.
- **Result:** Data changes would be governed by clear ownership and consistent correction paths.

### SAP SuccessFactors Employee Central Example
Create a field-level data stewardship matrix for the selected EC attributes and connected systems.

### SME Probe
How should a data owner handle a value that is technically valid but violates an approved policy?

---

## Q10 — Migration and Reconciliation Exceptions

### Interview Question
A migration reconciliation identifies a small number of unresolved employee data differences just before go-live. How do you assess the risk?

### STAR Model Answer
- **Situation:** Most records reconcile, but a residual exception set remains at a critical cutover gate.
- **Task:** Decide whether the exceptions are acceptable, require remediation, or block go-live.
- **Action:** I would classify the differences by employee/process impact, security/privacy, downstream dependencies, reporting, and recoverability. I would identify owners and due dates, compare against predefined acceptance thresholds, and require explicit approval for any residual risk. I would not treat a low percentage as automatically acceptable if individual records are critical.
- **Result:** The go/no-go decision would be based on impact and documented acceptance, not just an aggregate success rate.

### SAP SuccessFactors Employee Central Example
Use the actual source/target reconciliation register and test high-risk residual records through the process they affect.

### SME Probe
How can one incorrect record be a cutover blocker even when overall reconciliation is 99.9%?

---

## Q11 — Invalid Data Entered Through Multiple Channels

### Interview Question
Invalid values arrive through UI entry, import, and integration even though field validation exists. How do you resolve the gap?

### STAR Model Answer
- **Situation:** The same business constraint is not enforced consistently across data-entry pathways.
- **Task:** Determine the appropriate control boundary for each channel and close the gap.
- **Action:** I would reproduce the rule via each channel, inspect supported validation behaviour, and determine whether control is missing in EC configuration, source validation, mapping, or target acceptance. I would document which layer is authoritative, add necessary checks with owners, and test all relevant channels.
- **Result:** The data quality control would cover the real entry landscape and its known limitations.

### SAP SuccessFactors Employee Central Example
Compare equivalent invalid test cases through the actual UI and configured import/integration methods.

### SME Probe
How do you avoid duplicating controls inconsistently in every layer?

---

## Q12 — Data Quality Dashboard and Thresholds

### Interview Question
Leadership requests a data-quality dashboard. What measures, filters, and governance are necessary to make it trustworthy?

### STAR Model Answer
- **Situation:** Stakeholders need visibility but a dashboard without agreed definitions can create false assurance.
- **Task:** Define clear quality metrics and ownership so the numbers drive action.
- **Action:** I would define each metric, denominator, source, population, as-of date, threshold, severity, owner, and refresh timing. I would separate record-level defect counts from business impact and distinguish new, open, aging, and resolved issues. I would validate calculations against manual samples and include limitations/known gaps in the dashboard guidance.
- **Result:** The dashboard would enable prioritization and accountability rather than simply displaying unqualified red/green scores.

### SAP SuccessFactors Employee Central Example
Build a dashboard from approved EC/reporting data, with traceability to the underlying records and quality rules.

### SME Probe
What controls prevent teams from improving a dashboard score by excluding difficult populations from the denominator?

---

## Q13 — Data Repair and Audit Trail

### Interview Question
A production data correction is urgent. How do you ensure the repair is approved, traceable, and safe?

### STAR Model Answer
- **Situation:** A data error affects an operational process and needs correction under time pressure.
- **Task:** Correct the data while preserving decision authority and evidence.
- **Action:** I would identify the authoritative value and affected records, obtain approval through the correct change/incident path, document before/after state and reason, and use a supported correction method. I would assess effective-dated history and downstream impacts, validate the result, and record any follow-up control.
- **Result:** The correction would be traceable, verified, and aligned with data governance.

### SAP SuccessFactors Employee Central Example
Follow the approved production data-fix process and verify the actual record history/audit evidence available in the tenant.

### SME Probe
What should happen if the correct value cannot be evidenced confidently?

---

## Q14 — Duplicate or Conflicting Reference Values

### Interview Question
Two departments appear to represent the same business unit but have different identifiers and downstream use. How do you rationalize them?

### STAR Model Answer
- **Situation:** Reference data duplication creates inconsistent assignments and reporting.
- **Task:** Establish the true business identity and safely consolidate or retain records.
- **Action:** I would compare definitions, ownership, validity dates, history, employee references, integration mappings, and reporting dependencies. I would validate with the business data owner which values are true duplicates versus legitimate historical/local variants. I would document a mapping/retirement strategy, test affected records and consumers, and reconcile the result.
- **Result:** The reference data would be rationalized based on verified semantics and downstream evidence.

### SAP SuccessFactors Employee Central Example
Trace the organizational objects to employee assignments, reports, and consuming interfaces before any consolidation.

### SME Probe
Why might two similarly named departments not be safe to merge?

---

## Q15 — Data Quality and Security/Access Issues

### Interview Question
Employees with missing organizational attributes also receive incorrect manager access. How do you diagnose and remediate the combined issue?

### STAR Model Answer
- **Situation:** Data defects may influence target population or role logic and create access errors.
- **Task:** Correct both the underlying data and any resulting access misalignment.
- **Action:** I would identify affected employee and user populations, validate the authoritative organizational values, trace the group/target-population criteria and effective dates, and assess immediate exposure. I would correct source data through approved governance, re-evaluate effective access, test allowed/denied cases, and document whether a permission redesign is also required.
- **Result:** The underlying quality issue and resulting security behaviour would be addressed with evidence for both.

### SAP SuccessFactors Employee Central Example
Compare employee organizational records, role scope, and access outcomes before and after the governed correction.

### SME Probe
Why should you not assume that fixing the data automatically proves access is correct?

---

## Q16 — Data Quality Incident with Payroll Impact

### Interview Question
An incorrect organizational or employment value may have affected a downstream payroll or time process. What is your response?

### STAR Model Answer
- **Situation:** A data-quality defect may have consequences beyond HR screens and reports.
- **Task:** Contain potential downstream impact, validate affected records, and recover under the proper owner.
- **Action:** I would identify the affected population and time window, engage the responsible HR/payroll/time owners, and trace source values, changes, interfaces, and downstream results. I would classify whether outcomes need correction, reconciliation, or specialist review; preserve evidence; and follow approved operational procedures. I would not assume correcting the EC value reverses downstream actions automatically.
- **Result:** The downstream effect would be assessed and resolved through accountable, evidenced recovery with preventive actions.

### SAP SuccessFactors Employee Central Example
Trace the actual field and integration dependency into the relevant downstream system and confirm the business result with its owner.

### SME Probe
Which downstream effects may be irreversible or require a separate correction process?

---

## Q17 — Measure Remediation Effectiveness

### Interview Question
After a data cleansing initiative, how do you prove that quality has improved and remained improved?

### STAR Model Answer
- **Situation:** A cleanup exercise reduces the visible defect list, but recurrence is not yet understood.
- **Task:** Verify genuine improvement and establish sustained prevention.
- **Action:** I would compare the same quality rules and comparable populations before and after, measure correction and recurrence rates, track aging exceptions, and inspect whether data was excluded or definitions changed. I would validate source data and introduce ongoing checks with accountable owners. I would report actual metrics only when supported by evidence.
- **Result:** The team would know whether remediation improved quality and whether preventive controls are working over time.

### SAP SuccessFactors Employee Central Example
Re-run the same approved data-quality checks after a defined interval and compare results by population and defect type.

### SME Probe
How do you prove sustained improvement if the initial baseline was incomplete?

---

## Q18 — Root Cause Across Data, Process, and Configuration

### Interview Question
A recurring data defect could come from manual entry, an import, a business rule, or an integration. How do you find the root cause?

### STAR Model Answer
- **Situation:** The same invalid value can originate from multiple pathways, and previous fixes have not stopped recurrence.
- **Task:** Identify the originating pathway and the control gap.
- **Action:** I would compare affected records by entry source, time, actor/process, payload, rule/configuration, and target validation. I would form hypotheses, test a small representative sample, and separate root cause from contributing factors and detection failure. I would assign actions to the responsible layer and verify recurrence reduction through subsequent monitoring.
- **Result:** Remediation would address the source of the defect instead of repeatedly correcting symptoms.

### SAP SuccessFactors Employee Central Example
Use available logs/history and controlled tests to trace the same defect class across UI, load, and integration paths that actually exist.

### SME Probe
How do you defend a root-cause statement when evidence proves only a contributing factor?

---

## Q19 — Executive Challenge to Data Quality Investment

### Interview Question
Leadership questions the cost of improving data quality and asks the team to accept existing defects. How do you make the case?

### STAR Model Answer
- **Situation:** Data remediation competes with delivery work and its benefits are not immediately visible.
- **Task:** Present a risk- and value-based prioritization rather than arguing that all defects are equally serious.
- **Action:** I would connect defect classes to business outcomes—employee transaction failure, payroll/time impact where relevant, reporting error, access risk, rework, integration failure, and auditability. I would estimate impact using evidence, rank remediation by severity and likelihood, and distinguish critical blockers from lower-risk improvements. I would propose staged work with owners and measurable acceptance.
- **Result:** Leadership could make a transparent investment decision based on demonstrated risk and expected business value.

### SAP SuccessFactors Employee Central Example
Use actual incident/rework and reconciliation evidence to prioritize high-impact EC data defects, clearly stating any estimate assumptions.

### SME Probe
How would you challenge an inflated benefit estimate from the business case?

---

## Q20 — Defend Data Quality and Reconciliation Controls

### Interview Question
You must present an EC data quality and reconciliation model to HR, data governance, security, reporting, and integration leadership. What would you include?

### STAR Model Answer
- **Situation:** Data is used by several processes and consumers, and the organization needs trust in both current and historical values.
- **Task:** Demonstrate a sustainable system of ownership, measurement, correction, and prevention.
- **Action:** I would present critical data definitions, owners, quality rules, profiling baseline, source-of-truth boundaries, effective-date semantics, reconciliation process, exception severity and aging, secure correction procedures, integration/report checks, KPIs, and governance cadence. I would include sample evidence, known limitations, unresolved risks, and plans to verify controls after remediation.
- **Result:** Stakeholders could approve a data-quality operating model based on measurable controls and accountable owners.

### SAP SuccessFactors Employee Central Example
Walk through one data defect from detection to source investigation, approved correction, downstream reconciliation, preventive control, and closure evidence.

### SME Probe
Which control proves the business data is right rather than merely that a technical process ran?

---

# Rapid-Fire SME Probe Bank

1. How do you define data quality?
2. How do you establish a reliable baseline?
3. How do you reconcile source and consumer values?
4. How do effective dates affect data comparison?
5. How do you identify true duplicates?
6. Why is prevention better than repeated cleanup?
7. What makes a reconciliation control business-complete?
8. How do you govern reference values?
9. Who owns data correction?
10. How should residual migration issues be assessed?
11. Why must UI and integration entry channels both be tested?
12. What makes a dashboard metric trustworthy?
13. How do you preserve audit evidence for data repairs?
14. Why are similarly named objects not always duplicates?
15. How can data quality affect access or payroll processes?

# STAR Answer Quality Rubric

Score each dimension from 0 to 4 as a coaching aid, not a validated hiring assessment.

| Dimension | Strong evidence |
|---|---|
| Situation | Defines the business impact and affected data/population. |
| Task / ownership | Identifies data owners, decision authority, and candidate contribution. |
| Action / reasoning | Uses profiling, traceability, root-cause and reconciliation steps. |
| EC/data depth | Considers effective dating, valid relationships, security, reporting and integrations as appropriate. |
| Result / evidence | Provides verified corrections or a transparent measurement plan, not fabricated metrics. |
| SME insight | Addresses prevention, exception handling, risk, and sustainable governance. |
| Integrity | Separates direct experience from hypothetical approach and identifies evidence limits. |

# Common Data Quality Anti-Patterns

- Measuring quality without defining population and metric semantics.
- Treating source-of-truth ownership as universal rather than field-specific.
- Fixing downstream values without understanding the authoritative source.
- Comparing records at different effective dates.
- Deleting possible duplicates without identity evidence.
- Treating row counts or successful jobs as proof of correctness.
- Cleaning data once without preventive controls.
- Letting dashboards hide difficult populations in the denominator.
- Claiming improvements without comparable baselines.

# Master Framework — Data Quality to Trusted Outcomes

**Define quality → Establish source and ownership → Profile → Segment impact → Trace root cause → Correct under governance → Reconcile source/target → Prevent recurrence → Monitor metrics → Review and improve.**

# Success Criteria

The candidate can answer all 20 scenarios in STAR format, explain data-quality dimensions, reconcile effective-dated records across system boundaries, prioritize defects by business impact, and design sustainable ownership and prevention.

## Source and Verification Guidance

This is an interview coaching blueprint, not a product-specific data-quality implementation guide. Validate the actual reporting, import, audit/history, access, and integration capabilities in the target Employee Central tenant and current official SAP documentation. Document metric definitions, data sources, population boundaries, product/version and assumptions before operational use.
