# AWF1 — Scale Lab — Theme 04: Data & Information Model

## 20 Scenario-Based Interview Questions & STAR Answers

**Stream:** AWF1 — HCM Core & Employee Central  
**Theme:** B04 — Data & Information Model  
**Target:** 20 unique architect-level scenarios  
**Answer method:** STAR — Situation → Task → Action → Result  
**Product posture:** HCM-first; SAP SuccessFactors Employee Central is an example, not the boundary.

---

## Q01. Defining the HCM Information Model

### Interview Question
A global organization has different definitions for employee, worker, position and assignment. How would you establish a common HCM information model?

### STAR Answer
**Situation:** Inconsistent business definitions are producing inconsistent reporting, integrations and processes.

**Task:** I would establish a shared conceptual and logical information model before changing applications.

**Action:** I would define core entities, relationships, identifiers, lifecycle states and ownership; align terminology through a business glossary; and map existing applications to the model.

**Result:** HR, IT and downstream systems gain a common language and a stable information foundation.

### SAP SuccessFactors Employee Central Example
Employee Central can implement many core worker and employment concepts, but the enterprise information model should remain platform-independent.

### SME Probe
What is the difference between a business glossary and a data model?

---

## Q02. Person, Employment and Assignment

### Interview Question
An organization stores person, employment and assignment information in one large employee table. Reporting becomes ambiguous when workers hold multiple assignments. How would you redesign the model?

### STAR Answer
**Situation:** A flat employee structure cannot represent complex workforce relationships accurately.

**Task:** I would separate identity from employment and assignment relationships.

**Action:** I would model the person independently, then represent employment relationships, assignments, organizational relationships and effective dates explicitly. I would define identifiers and cardinality for each relationship.

**Result:** The model supports multiple workforce relationships without duplicating the person identity.

### SAP SuccessFactors Employee Central Example
Employee Central's person and employment concepts can illustrate the separation between human identity and employment relationships.

### SME Probe
Why is treating every employment relationship as a separate person dangerous?

---

## Q03. Enterprise Identifier Strategy

### Interview Question
An employee has different IDs in HR, payroll, identity and finance systems. How would you design an enterprise identifier strategy?

### STAR Answer
**Situation:** Multiple identifiers are causing reconciliation and integration errors.

**Task:** I would establish a stable enterprise identity while preserving system-specific identifiers where required.

**Action:** I would define an enterprise person/worker identifier, map legacy identifiers, establish ownership and lifecycle rules, and create controlled cross-reference mappings for downstream systems.

**Result:** Integrations become more reliable and identity reconciliation becomes measurable.

### SAP SuccessFactors Employee Central Example
Employee Central can participate in enterprise identity mapping while retaining relevant external IDs for payroll and other systems.

### SME Probe
Should the enterprise identifier ever be reused after a worker leaves?

---

## Q04. Effective-Dated Workforce Information

### Interview Question
HR needs to answer, “Who was this employee's manager and department on a specific historical date?” How would your information model support that?

### STAR Answer
**Situation:** Current-state data cannot reliably reconstruct historical workforce relationships.

**Task:** I would make temporal information a first-class design concern.

**Action:** I would define effective dates, event dates, validity periods, correction rules and historical retention. I would ensure changes create traceable states rather than simply overwriting previous values.

**Result:** The enterprise can reconstruct workforce state for reporting, audit and compliance.

### SAP SuccessFactors Employee Central Example
Effective-dated organizational and employment information in Employee Central can support historical workforce views.

### SME Probe
What is the difference between effective dating and audit history?

---

## Q05. Data Ownership by Information Domain

### Interview Question
HR, Finance and IT each claim ownership of employee location and cost-center data. How would you resolve the conflict?

### STAR Answer
**Situation:** Ambiguous ownership creates competing updates and inconsistent workforce information.

**Task:** I would establish ownership based on business meaning and authoritative responsibility.

**Action:** I would define information domains, authoritative sources, data owners, stewards, update rights and consumption patterns. Where concepts overlap, I would define explicit mappings rather than duplicate ownership.

**Result:** Each critical attribute has accountable governance and downstream consumers know which source to trust.

### SAP SuccessFactors Employee Central Example
Employee Central may own selected workforce attributes while Finance remains authoritative for financial structures.

### SME Probe
What evidence should determine data ownership?

---

## Q06. Master Data versus Transaction Data

### Interview Question
A team wants to copy every employee attribute into every downstream system. How would you challenge this approach?

### STAR Answer
**Situation:** Broad replication is increasing data duplication and synchronization risk.

**Task:** I would distinguish master/reference information from transactional and derived information.

**Action:** I would classify data domains, define authoritative ownership, distribute only required information and establish purpose-based interfaces.

**Result:** Data movement becomes intentional, reducing redundancy, privacy exposure and reconciliation effort.

### SAP SuccessFactors Employee Central Example
Core workforce information can be distributed from Employee Central while specialist applications retain ownership of their own transactional domains.

### SME Probe
When is replication justified?

---

## Q07. Data Quality as an Architecture Concern

### Interview Question
The HCM platform is technically stable, but 8% of employee records contain data-quality issues. What would you do?

### STAR Answer
**Situation:** Poor workforce data is affecting reporting, processes and downstream integrations.

**Task:** I would treat data quality as an operating and architecture problem, not simply a cleanup exercise.

**Action:** I would profile errors, identify root causes, assign data owners, define quality rules, prevent invalid entry at source and establish monitoring and remediation workflows.

**Result:** Data quality improves sustainably because defects are prevented rather than repeatedly corrected.

### SAP SuccessFactors Employee Central Example
Validation rules and controlled data entry can help prevent invalid core employee information, supported by governance and monitoring.

### SME Probe
Why is data cleansing alone insufficient?

---

## Q08. Data Lifecycle Management

### Interview Question
The organization retains all employee information indefinitely because nobody wants to delete HR data. How would you design a responsible data lifecycle?

### STAR Answer
**Situation:** Uncontrolled retention increases privacy, security and operational risk.

**Task:** I would establish lifecycle rules aligned with legal, business and regulatory requirements.

**Action:** I would classify information, define retention periods, archival rules, legal holds, deletion triggers and access controls. I would distinguish active, archived and legally required records.

**Result:** The enterprise retains what it needs while reducing unnecessary exposure and storage complexity.

### SAP SuccessFactors Employee Central Example
Employee data lifecycle policies should be implemented using supported retention and purge capabilities where appropriate.

### SME Probe
Who should approve HR data-retention rules?

---

## Q09. Sensitive HCM Information

### Interview Question
A new analytics initiative wants to combine employee demographic, compensation and performance data. How would you architect access to the information?

### STAR Answer
**Situation:** Combining datasets creates valuable insight but increases sensitivity and privacy risk.

**Task:** I would enable legitimate analysis while enforcing purpose limitation and least privilege.

**Action:** I would classify sensitive attributes, define approved analytical purposes, minimize data, apply role-based access and masking where appropriate, and establish audit and review controls.

**Result:** Analytics can create value without exposing sensitive workforce information unnecessarily.

### SAP SuccessFactors Employee Central Example
Sensitive employee attributes can be governed through application permissions and broader enterprise data-security controls.

### SME Probe
Why should data minimization be considered before access control?

---

## Q10. Data Model and Integration Contracts

### Interview Question
An HCM source changes an employee attribute name and several integrations fail. How would you prevent this class of problem?

### STAR Answer
**Situation:** Tight coupling between source data structures and integrations creates fragility.

**Task:** I would establish governed information contracts.

**Action:** I would define canonical meanings, API/interface contracts, versioning rules, change impact analysis and backward-compatibility practices. Consumers should depend on stable business semantics rather than accidental source structures.

**Result:** Data-model evolution becomes controlled and integration failures decrease.

### SAP SuccessFactors Employee Central Example
Employee Central APIs and integration mappings should use governed contracts rather than undocumented field dependencies.

### SME Probe
What should be versioned: the field, the API, or the business contract?

---

## Q11. Workforce Hierarchy and Organizational Data

### Interview Question
HR needs organizational hierarchy while Finance needs legal entities and cost-center structures. How would you represent both without creating conflicting masters?

### STAR Answer
**Situation:** Different functions need different legitimate organizational views.

**Task:** I would model distinct concepts and their governed relationships.

**Action:** I would separate organizational units, positions, legal entities, cost centers and reporting relationships; assign ownership; and maintain effective-dated mappings where structures intersect.

**Result:** Each function gets accurate information without pretending that all organizational concepts are identical.

### SAP SuccessFactors Employee Central Example
Employee Central organizational structures can map to financial structures through controlled integration.

### SME Probe
Why should one hierarchy not be forced to represent every business dimension?

---

## Q12. Data Lineage

### Interview Question
The CHRO questions a workforce KPI because HR, payroll and analytics reports show different numbers. How would you resolve the disagreement?

### STAR Answer
**Situation:** Different reports use different definitions, sources or transformation logic.

**Task:** I would establish traceability from business metric to source data.

**Action:** I would define the KPI, identify authoritative data, document transformations and filters, trace lineage through integration and analytics layers, and reconcile discrepancies.

**Result:** Leadership receives a trusted metric with transparent lineage and an agreed definition.

### SAP SuccessFactors Employee Central Example
Employee Central can be one source in the lineage, but the final KPI may combine information from payroll, organizational and analytical sources.

### SME Probe
Can two technically correct reports still produce different business answers?

---

## Q13. Data Integration and Change Propagation

### Interview Question
An employee changes department and the update reaches payroll immediately but finance two days later. How would you determine whether this is a data or integration problem?

### STAR Answer
**Situation:** The same business change has inconsistent propagation timing.

**Task:** I would analyze the information lifecycle and integration contract.

**Action:** I would identify source ownership, event timing, transformation, interface frequency, processing queues and target acceptance. I would compare the required business SLA with the actual propagation pattern.

**Result:** The organization can distinguish a valid batch design from an integration failure and correct the architecture where necessary.

### SAP SuccessFactors Employee Central Example
Employee Central changes can trigger different integration patterns depending on downstream business requirements.

### SME Probe
Who defines the required data-propagation SLA?

---

## Q14. Duplicate Employee Records

### Interview Question
An acquisition introduces duplicate people into the HCM landscape. How would you detect and resolve them without damaging legitimate records?

### STAR Answer
**Situation:** Duplicate identities are affecting reporting and lifecycle processing.

**Task:** I would establish controlled identity matching and survivorship rules.

**Action:** I would define matching criteria, confidence thresholds, authoritative attributes and manual review paths. I would preserve auditability and avoid merging records solely on weak matches.

**Result:** Duplicate identities are reduced while legitimate distinct workers remain protected.

### SAP SuccessFactors Employee Central Example
Identity matching and controlled data migration can be used when consolidating employee records into a core HCM platform.

### SME Probe
Which attributes make a reliable identity match?

---

## Q15. Data Migration Quality

### Interview Question
A legacy HCM migration is 95% complete, but the remaining 5% contains complex employee records. Leadership wants to load everything immediately. How would you respond?

### STAR Answer
**Situation:** The migration has high completion but unresolved complex records may compromise data integrity.

**Task:** I would protect business-critical data quality rather than optimize for a percentage-complete metric.

**Action:** I would classify unresolved records by business impact, cleanse and validate high-risk data, establish exception handling and reconciliation, and define explicit acceptance criteria.

**Result:** Migration readiness is based on trustworthy workforce data, not simply volume loaded.

### SAP SuccessFactors Employee Central Example
Employee Central migration should include validation, reconciliation and controlled handling of legacy exceptions.

### SME Probe
When should a migration be stopped despite a high load percentage?

---

## Q16. Data Access versus Data Availability

### Interview Question
An executive says, “If the data is in our HCM system, every HR analyst should be able to use it.” How would you respond?

### STAR Answer
**Situation:** Data availability is being confused with unrestricted data access.

**Task:** I would balance analytical usefulness with privacy and legitimate need.

**Action:** I would classify data, define personas and purposes, apply least-privilege access, minimize sensitive attributes and establish audit and review mechanisms.

**Result:** Analysts get the information required for their responsibilities without creating unnecessary exposure.

### SAP SuccessFactors Employee Central Example
Employee Central permissions can be aligned to HR roles while broader analytics access is governed through the enterprise data platform.

### SME Probe
What is the principle of least privilege in an HCM analytics context?

---

## Q17. Canonical HCM Data Model

### Interview Question
Your architecture team proposes creating a canonical employee data model for every HR integration. When would you support this approach?

### STAR Answer
**Situation:** Multiple integrations use inconsistent representations of workforce information.

**Task:** I would determine whether a canonical model creates enough reuse to justify its governance cost.

**Action:** I would identify shared high-value domains, define stable business semantics, assess transformation complexity and establish ownership and versioning. I would avoid creating a massive canonical model for information that has no common reuse.

**Result:** A focused canonical model reduces integration complexity without becoming another rigid enterprise master.

### SAP SuccessFactors Employee Central Example
Core person and employment concepts may be suitable for canonical integration semantics across HR systems.

### SME Probe
When can a canonical model become an anti-pattern?

---

## Q18. Data Governance Operating Model

### Interview Question
The HCM program has created data standards, but nobody follows them after go-live. What would you change?

### STAR Answer
**Situation:** Data governance exists as documentation but not as operational behavior.

**Task:** I would embed governance into processes, technology and accountability.

**Action:** I would assign data owners and stewards, define quality KPIs, automate validation where possible, integrate standards into change management and review data-quality exceptions regularly.

**Result:** Data governance becomes part of daily operations rather than a project deliverable.

### SAP SuccessFactors Employee Central Example
Core employee data governance can be embedded through controlled configuration, validation, permissions and operational monitoring.

### SME Probe
What makes a data standard enforceable?

---

## Q19. HCM Information Architecture for Analytics and AI

### Interview Question
The enterprise wants predictive workforce analytics and AI agents, but workforce data is fragmented across HR applications. What information architecture would you establish first?

### STAR Answer
**Situation:** Advanced analytics and AI are constrained by inconsistent workforce information.

**Task:** I would create a trusted information foundation before scaling intelligence use cases.

**Action:** I would establish common definitions, authoritative sources, identifiers, lineage, quality controls, privacy boundaries and governed access. I would then expose trusted information products to analytics and AI capabilities.

**Result:** Analytics and AI can operate on reliable workforce context rather than inconsistent application data.

### SAP SuccessFactors Employee Central Example
Employee Central can contribute authoritative core workforce data to SAP analytics and Business AI scenarios when the surrounding information architecture is governed.

### SME Probe
Why is trusted data more important than model sophistication for HR AI?

---

## Q20. HCM Data as Enterprise Workforce Intelligence

### Interview Question
The CEO wants one trusted view of the workforce combining HR, Finance, operations and strategic workforce data. How would you design the information architecture?

### STAR Answer
**Situation:** Workforce decisions require information distributed across enterprise domains.

**Task:** I would create an integrated workforce information architecture without forcing every domain into one system.

**Action:** I would define shared workforce concepts, domain ownership, identifiers, lineage, integration contracts, analytical data products, security and governance. I would distinguish operational systems of record from the enterprise analytical workforce view.

**Result:** Leaders gain a trusted workforce perspective while source systems retain clear accountability for their domains.

### SAP SuccessFactors Employee Central Example
Employee Central can provide core workforce information into an enterprise workforce data architecture alongside Finance, operations and analytics sources.

### SME Probe
What is the difference between a single source of truth and a single view of truth?

---

## Theme 04 Completion Standard

All 20 questions use the same STAR discipline:

**Situation → Task → Action → Result**

The set progresses from HCM information modeling through identity, effective dating, ownership, quality, lifecycle, sensitive data, integration contracts, lineage, migration, governance, canonical models and workforce intelligence.

**Quality rule:** A candidate should demonstrate that they can reason about HCM information as an enterprise architecture concern. Product knowledge should strengthen the answer, not replace data architecture reasoning.

**IDs:** HR-AWF1-B04-Q01 through HR-AWF1-B04-Q20.
