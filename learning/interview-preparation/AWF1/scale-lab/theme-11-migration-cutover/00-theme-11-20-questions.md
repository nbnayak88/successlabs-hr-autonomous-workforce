# AWF1 Theme 11 — Migration & Cutover

## 20 Scenario-Based Interview Questions & STAR Answers

**Stream:** AWF1 — HCM Core & Employee Central  
**Theme:** 11 — Migration & Cutover  
**Target:** 20 scenarios  
**Answer method:** STAR — Situation → Task → Action → Result  
**Product posture:** HCM-first and architecture-first. SAP SuccessFactors Employee Central is an example, not the boundary.

---

## HR-AWF1-B11-Q01 — Migration Strategy

### Interview Question
How would you define a migration strategy for a global HCM transformation?

### STAR Answer
**Situation:** A global organization was moving from fragmented legacy HR systems to a common HCM platform.

**Task:** I needed to determine what data should move, how it should move, and what could safely remain in legacy systems.

**Action:** I classified data into active master data, required history, reference data, transactional data, and archival information. I assessed business value, legal retention, data quality, target capability, volume, dependency, and migration complexity. I then defined migration waves, ownership, validation, reconciliation, and cutover principles.

**Result:** The program had a deliberate migration scope instead of attempting to move everything simply because it existed in legacy systems.

### SAP SuccessFactors Employee Central Example
I would distinguish active worker and employment data from historical information that may be retained in an approved archive or legacy repository rather than unnecessarily migrated into Employee Central.

### SME Probe
What criteria would make you deliberately leave historical HR data outside the new HCM platform?

---

## HR-AWF1-B11-Q02 — Data Migration Scope

### Interview Question
How do you determine the correct scope of data for HCM migration?

### STAR Answer
**Situation:** Business stakeholders wanted all legacy HR data migrated, while the technical team was concerned about complexity and data quality.

**Task:** I needed an evidence-based migration scope.

**Action:** I assessed each data domain against business process dependency, regulatory need, reporting requirement, employee experience, historical value, target-system capability, quality, and retention obligations. I separated “needed for day-one operations” from “valuable for historical reference.”

**Result:** The migration scope became smaller, more defensible, and aligned with business outcomes.

### SAP SuccessFactors Employee Central Example
Worker, employment, job, organization, manager, and required effective-dated information would be assessed separately from obsolete or low-value legacy records.

### SME Probe
Why is “migrate everything” usually a poor migration strategy?

---

## HR-AWF1-B11-Q03 — Source-to-Target Mapping

### Interview Question
How would you create a source-to-target mapping for HCM migration?

### STAR Answer
**Situation:** Legacy HR systems used different field names, codes, structures, and business definitions.

**Task:** I needed a mapping that preserved business meaning rather than simply matching column names.

**Action:** I documented source attribute, business definition, target attribute, transformation, default behavior, validation, ownership, effective dating, and exception handling. I involved business data owners in semantic decisions and maintained version-controlled mapping specifications.

**Result:** Mapping became a governed business artifact rather than an undocumented technical spreadsheet.

### SAP SuccessFactors Employee Central Example
Legacy employee status or organizational codes would be mapped to the appropriate Employee Central values through approved transformation rules.

### SME Probe
What should happen when there is no valid target equivalent for a legacy value?

---

## HR-AWF1-B11-Q04 — Data Cleansing Before Migration

### Interview Question
How would you handle poor-quality legacy HR data before migration?

### STAR Answer
**Situation:** Legacy systems contained duplicate employees, invalid organizational references, inconsistent codes, and incomplete records.

**Task:** I needed to improve data quality without allowing cleansing to become an endless project.

**Action:** I profiled data, prioritized defects by migration and business risk, assigned data ownership, defined cleansing rules, and established thresholds for acceptable quality. I automated repeatable corrections where safe and escalated ambiguous business decisions to data owners.

**Result:** Migration defects decreased and business users understood their responsibility for data quality.

### SAP SuccessFactors Employee Central Example
Duplicate worker identities, invalid manager relationships, obsolete organizations, and inconsistent employment statuses would be identified before loading Employee Central.

### SME Probe
Who owns the quality of migrated HR data: IT or the business?

---

## HR-AWF1-B11-Q05 — Mock Migration

### Interview Question
Why are mock migrations important in an HCM transformation?

### STAR Answer
**Situation:** The program had a complex migration but only one planned production cutover.

**Task:** I needed to expose migration defects before the final window.

**Action:** I executed multiple mock migrations using increasingly production-like data and timing. I measured extraction, transformation, loading, reconciliation, error correction, and business validation. Each rehearsal generated improvements to mapping, tooling, sequencing, and runbooks.

**Result:** Migration execution became repeatable and final cutover risk decreased significantly.

### SAP SuccessFactors Employee Central Example
Mock loads into Employee Central would validate worker, employment, organization, manager, and effective-dated data before production migration.

### SME Probe
What makes a mock migration useful rather than merely a practice load?

---

## HR-AWF1-B11-Q06 — Migration Reconciliation

### Interview Question
How would you prove that migrated HCM data is complete and accurate?

### STAR Answer
**Situation:** A migration load completed successfully from a technical perspective, but business stakeholders needed evidence that the target data was trustworthy.

**Task:** I needed multi-level reconciliation.

**Action:** I compared record counts, key identifiers, critical attributes, relationships, effective dates, organizational structures, statuses, and selected financial or payroll-relevant attributes where applicable. I combined automated reconciliation with business sampling and exception analysis.

**Result:** The team could distinguish successful loading from successful migration.

### SAP SuccessFactors Employee Central Example
I would reconcile source and Employee Central worker populations, employment relationships, manager assignments, organizations, statuses, and effective-dated records.

### SME Probe
Why can record-count reconciliation alone produce false confidence?

---

## HR-AWF1-B11-Q07 — Historical Data Migration

### Interview Question
How would you decide which historical HR data should be migrated?

### STAR Answer
**Situation:** Years of historical employee information existed in legacy systems, but the target platform had different capabilities and retention considerations.

**Task:** I needed to preserve necessary history without overloading the new platform.

**Action:** I classified history by legal requirement, operational need, reporting value, employee access need, audit relevance, volume, and target-system suitability. I defined a strategy for migrated history, archived history, and retained legacy access.

**Result:** Historical continuity was preserved without turning the new HCM platform into a repository for every legacy record.

### SAP SuccessFactors Employee Central Example
Only history required for supported employee processes, reporting, compliance, or agreed business use would be considered for Employee Central migration.

### SME Probe
What is the difference between historical accessibility and historical migration?

---

## HR-AWF1-B11-Q08 — Effective-Dated Migration

### Interview Question
What makes effective-dated HCM migration particularly challenging?

### STAR Answer
**Situation:** Legacy HR systems stored employee changes using different effective-date models.

**Task:** I needed to preserve the intended employee timeline in the target system.

**Action:** I analyzed date semantics, sequence of changes, future-dated records, overlapping validity periods, correction records, and retroactive changes. I created transformation rules that preserved business chronology and tested multiple lifecycle timelines.

**Result:** Employee histories were represented more accurately and fewer date-related defects appeared after migration.

### SAP SuccessFactors Employee Central Example
Employee Central effective-dated records would be loaded in the correct chronological and business-valid sequence for job, organization, manager, and employment changes.

### SME Probe
What would you do when the source system permits overlapping effective dates that the target does not?

---

## HR-AWF1-B11-Q09 — Identity Matching and Duplicate Prevention

### Interview Question
How would you prevent duplicate employees during migration?

### STAR Answer
**Situation:** Different legacy systems used different employee identifiers and contained inconsistent personal information.

**Task:** I needed reliable identity matching before creating target worker records.

**Action:** I established a master identity strategy using trusted identifiers and controlled matching rules. I investigated ambiguous matches manually, created exception queues, and prevented automated creation when confidence was insufficient.

**Result:** Duplicate worker creation risk was reduced and identity integrity improved.

### SAP SuccessFactors Employee Central Example
Legacy employee identifiers would be mapped to the target person and employment identifiers with controlled handling of rehires and multiple employment relationships.

### SME Probe
Why is name plus date of birth usually insufficient as a universal identity key?

---

## HR-AWF1-B11-Q10 — Migration of Organizational Structures

### Interview Question
How would you migrate organizational structures when the legacy and target models differ?

### STAR Answer
**Situation:** The legacy organization used departments and reporting units differently from the target's organizational model.

**Task:** I needed to preserve business meaning while adopting the target architecture.

**Action:** I separated business semantics from legacy technical structures and mapped legal entities, business units, departments, locations, positions, and reporting relationships according to the target operating model. I involved HR and organizational design owners in unresolved mappings.

**Result:** The target organization became usable for future processes instead of reproducing legacy structural problems.

### SAP SuccessFactors Employee Central Example
Legacy organizational objects would be mapped into the appropriate Employee Central organizational structures with clear ownership and effective dating.

### SME Probe
When should migration become an opportunity to redesign the organization rather than reproduce it?

---

## HR-AWF1-B11-Q11 — Migration and Integrations

### Interview Question
How do you manage integrations during HCM migration?

### STAR Answer
**Situation:** Loading migrated employee data while downstream interfaces were active could create duplicate or premature transactions.

**Task:** I needed to control downstream impact during migration.

**Action:** I mapped migration-dependent interfaces, established freeze and suppression rules where required, controlled activation sequencing, created reconciliation checkpoints, and defined which transactions should be replayed versus ignored. I tested the integration state during mock cutovers.

**Result:** The migration did not unintentionally trigger uncontrolled downstream processing.

### SAP SuccessFactors Employee Central Example
During Employee Central migration, interfaces to payroll, identity, finance, time, and other consumers would be controlled according to the cutover design.

### SME Probe
What is the risk of allowing all outbound integrations to run normally during a bulk migration?

---

## HR-AWF1-B11-Q12 — Data Freeze Strategy

### Interview Question
How would you design a data freeze before HCM cutover?

### STAR Answer
**Situation:** Legacy HR data continued changing while the final migration extract was being prepared.

**Task:** I needed to establish a controlled point where source data became stable enough for final migration.

**Action:** I defined the freeze scope, start time, allowed emergency changes, approval process, communication, reconciliation, and final delta capture. I ensured critical HR operations had documented alternatives during the freeze.

**Result:** The final target state could be reconciled to a known source state.

### SAP SuccessFactors Employee Central Example
Before final Employee Central migration, controlled changes to worker and employment data would be frozen or captured through an agreed delta process.

### SME Probe
Why is a total business freeze not always necessary?

---

## HR-AWF1-B11-Q13 — Delta Migration

### Interview Question
How would you handle changes that occur after the initial migration load?

### STAR Answer
**Situation:** A long migration window meant employee data continued changing after the initial extraction.

**Task:** I needed a reliable mechanism to capture and load changes without repeating the entire migration.

**Action:** I defined delta criteria, timestamps or change indicators, sequencing, dependency handling, duplicate prevention, reconciliation, and final delta validation. I tested multiple delta cycles during mock migrations.

**Result:** The target could converge on the agreed production source state without unnecessary full reloads.

### SAP SuccessFactors Employee Central Example
A final delta could capture hires, transfers, manager changes, terminations, or corrections occurring after the initial Employee Central load.

### SME Probe
What is the greatest risk when delta logic is based only on technical timestamps?

---

## HR-AWF1-B11-Q14 — Cutover Runbook

### Interview Question
What should a migration cutover runbook contain?

### STAR Answer
**Situation:** Multiple teams were responsible for extraction, transformation, loading, integrations, validation, and business sign-off.

**Task:** I needed one executable source of truth for cutover.

**Action:** I documented each activity, owner, dependency, start condition, expected duration, evidence, success criterion, escalation path, and rollback or recovery action. I included technical and business checkpoints and rehearsed the runbook during mock cutovers.

**Result:** Cutover execution became coordinated and measurable.

### SAP SuccessFactors Employee Central Example
The runbook could sequence source freeze, extraction, transformation, target loading, integration activation, reconciliation, business validation, and go/no-go.

### SME Probe
What makes a cutover runbook executable rather than descriptive?

---

## HR-AWF1-B11-Q15 — Migration Failure and Recovery

### Interview Question
What would you do if a critical migration load failed during cutover?

### STAR Answer
**Situation:** A target load failed for a critical employee population during the production migration window.

**Task:** I needed to protect data integrity and decide whether to correct, reload, or recover.

**Action:** I stopped dependent activities, isolated the failure scope, preserved evidence, assessed source and target state, corrected the root cause, and determined whether a controlled retry or recovery path was safe. I reconciled before allowing downstream processing to continue.

**Result:** The team avoided compounding a partial migration failure with uncontrolled downstream transactions.

### SAP SuccessFactors Employee Central Example
If a critical Employee Central load failed, I would prevent dependent integrations from acting on an incomplete target state until reconciliation confirmed readiness.

### SME Probe
When should you stop a migration instead of continuing with partial success?

---

## HR-AWF1-B11-Q16 — Parallel Run and Legacy Coexistence

### Interview Question
When would you use a parallel run during HCM migration?

### STAR Answer
**Situation:** The organization could not tolerate uncertainty around critical employee and payroll data after migration.

**Task:** I needed to compare old and new processing before fully retiring the legacy environment.

**Action:** I defined the scope and duration of parallel processing, comparison criteria, reconciliation ownership, data synchronization boundaries, and exit criteria. I avoided indefinite dual maintenance by establishing a firm decision date.

**Result:** Business confidence increased while the organization retained a controlled fallback during transition.

### SAP SuccessFactors Employee Central Example
Core employee processes or downstream payroll-related outputs could be compared between legacy HCM and the target landscape where the operating model justified it.

### SME Probe
What is the biggest architectural risk of prolonged parallel operation?

---

## HR-AWF1-B11-Q17 — Cutover Rehearsal

### Interview Question
How would you conduct a realistic HCM cutover rehearsal?

### STAR Answer
**Situation:** The first planned production cutover involved many interdependent teams.

**Task:** I needed to test not only migration steps but also timing and human coordination.

**Action:** I recreated the production sequence as closely as practical, including data volumes, dependencies, freeze activities, migration duration, reconciliation, integration activation, validation, decision checkpoints, and recovery actions. I measured elapsed time and captured every deviation.

**Result:** The final runbook became based on observed execution rather than estimates.

### SAP SuccessFactors Employee Central Example
A mock Employee Central cutover would exercise final extraction, transformation, load, integration controls, reconciliation, and business validation using production-like volumes where feasible.

### SME Probe
What should be measured during a cutover rehearsal besides whether the load succeeded?

---

## HR-AWF1-B11-Q18 — Business Validation After Migration

### Interview Question
How do you involve HR business users in migration validation?

### STAR Answer
**Situation:** Technical reconciliation passed, but HR leaders wanted confidence that employees and organizational structures looked correct from a business perspective.

**Task:** I needed meaningful business validation without asking users to inspect millions of records.

**Action:** I created representative validation populations covering countries, employee types, managers, organizations, lifecycle states, and high-risk records. Business users validated critical attributes and scenarios while automated reconciliation covered volume and consistency.

**Result:** Business acceptance complemented technical validation without creating an impractical review burden.

### SAP SuccessFactors Employee Central Example
HR administrators and business representatives could validate representative employee records, manager relationships, organizational assignments, and lifecycle states in Employee Central.

### SME Probe
How do you select a representative business validation sample?

---

## HR-AWF1-B11-Q19 — Legacy Decommissioning Readiness

### Interview Question
How would you decide whether a legacy HCM system is ready for decommissioning?

### STAR Answer
**Situation:** The new HCM platform was live, but legacy systems still contained historical data and some dependent processes.

**Task:** I needed to avoid retiring a system before all required capabilities and records were safely transitioned.

**Action:** I verified business process replacement, data retention and archive access, integration retirement, reporting dependencies, security, operational ownership, contractual dependencies, audit requirements, and business sign-off. I created a controlled decommissioning plan rather than treating go-live as automatic retirement.

**Result:** Legacy retirement became an evidence-based architectural decision.

### SAP SuccessFactors Employee Central Example
After Employee Central adoption, legacy HR repositories and interfaces would be assessed individually for retention, replacement, archive, or retirement.

### SME Probe
What dependency is most often forgotten before decommissioning legacy HR systems?

---

## HR-AWF1-B11-Q20 — Migration as Transformation

### Interview Question
How would you ensure HCM migration creates a better workforce data foundation instead of simply copying the past?

### STAR Answer
**Situation:** The organization wanted to modernize HCM but had a temptation to reproduce legacy structures and data practices in the new platform.

**Task:** I needed migration to support the future operating model.

**Action:** I used migration as a controlled transformation opportunity: cleanse obsolete data, standardize definitions, rationalize organizational structures, establish ownership, preserve required history, improve data quality, and validate the target information model. I separated mandatory historical continuity from legacy design habits.

**Result:** The target HCM environment became a cleaner foundation for analytics, integration, employee experience, automation, and future AI capabilities.

### SAP SuccessFactors Employee Central Example
Employee Central migration would establish governed worker and employment data suitable for downstream HR processes, analytics, integrations, and future intelligent HR capabilities.

### SME Probe
How do you prevent “migration” from becoming a disguised legacy-system replication exercise?

---

# Theme 11 Completion Standard

A learner completes **Theme 11 — Migration & Cutover** only when they can:

- Define migration scope and strategy based on business value and risk.
- Design source-to-target mappings and data-cleansing controls.
- Handle effective dating, identity matching, organizational structures, history, and deltas.
- Design mock migrations, reconciliation, freeze strategies, and cutover rehearsals.
- Control integrations during migration and manage partial-failure recovery.
- Explain parallel run, legacy coexistence, and decommissioning decisions.
- Lead executable cutover runbooks and business validation.
- Treat migration as transformation of the HR data foundation rather than simple data copying.

**Quality rule:** Every scenario must demonstrate Situation → Task → Action → Result, include an HCM migration/cutover decision, provide an SAP SuccessFactors Employee Central example, and end with an SME Probe.

**Scenario IDs:** HR-AWF1-B11-Q01 → HR-AWF1-B11-Q20

**Target achieved:** 20 unique scenario-based interview questions + 20 STAR answers.
