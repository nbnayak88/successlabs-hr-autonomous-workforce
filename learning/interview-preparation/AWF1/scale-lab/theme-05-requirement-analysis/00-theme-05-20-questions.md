# AWF1 — Scale Lab — Theme 05: Requirement Analysis

## 20 Scenario-Based Interview Questions & STAR Answers

**Stream:** AWF1 — HCM Core & Employee Central  
**Theme:** B05 — Requirement Analysis  
**Target:** 20 unique architect-level scenarios  
**Answer method:** STAR — Situation → Task → Action → Result  
**Product posture:** HCM-first; SAP SuccessFactors Employee Central is an example, not the boundary.

---

## Q01. Business Requirement versus Solution Request

### Interview Question
HR leadership asks for a new HCM feature because “the current system cannot do it.” How would you determine the actual requirement?

### STAR Answer
**Situation:** The stakeholder has presented a technology solution rather than a clearly defined business need.

**Task:** I would uncover the underlying business problem and desired outcome before evaluating technology.

**Action:** I would clarify the current process, pain point, affected users, business impact, desired outcome, constraints and success measures. I would then separate the requirement from the requested solution.

**Result:** The team solves the real business problem rather than automatically implementing the requested feature.

### SAP SuccessFactors Employee Central Example
Before proposing an Employee Central configuration or extension, I would validate whether the underlying requirement is process, data, policy or technology related.

### SME Probe
What questions help you distinguish a requirement from a solution preference?

---

## Q02. Requirement Discovery Across Stakeholders

### Interview Question
HR, employees, managers and IT describe the same HCM problem differently. How would you establish a reliable requirement baseline?

### STAR Answer
**Situation:** Different stakeholders have conflicting expectations and definitions of success.

**Task:** I would establish a shared understanding of the problem and outcomes.

**Action:** I would conduct stakeholder interviews, process walkthroughs, journey mapping and data analysis. I would identify common needs, conflicting needs, mandatory constraints and persona-specific requirements.

**Result:** Requirements become traceable to stakeholder outcomes rather than individual opinions.

### SAP SuccessFactors Employee Central Example
Employee Central requirements can be gathered across HR administrators, employees, managers, HRBPs and technical teams before solution design.

### SME Probe
Whose requirement wins when stakeholder requirements conflict?

---

## Q03. Current-State Process Discovery

### Interview Question
The HR team provides a process document, but employees say the real process is different. How would you validate requirements?

### STAR Answer
**Situation:** Documented processes do not match operational reality.

**Task:** I would discover the actual current state before defining the target requirement.

**Action:** I would observe transactions, interview users, analyze exceptions and measure handoffs, rework and manual work. I would compare documented, perceived and actual processes.

**Result:** Requirements are based on real operational behavior and root causes rather than outdated documentation.

### SAP SuccessFactors Employee Central Example
Employee lifecycle transactions can be traced through actual HR operations before defining Employee Central requirements.

### SME Probe
Why can process observation reveal requirements that interviews miss?

---

## Q04. Functional versus Non-Functional Requirements

### Interview Question
A global HCM team has documented hundreds of functional requirements but almost nothing about performance, security or availability. How would you correct the requirement baseline?

### STAR Answer
**Situation:** Functional requirements are detailed, but quality attributes are largely absent.

**Task:** I would establish a balanced requirement model.

**Action:** I would define functional requirements alongside security, privacy, availability, performance, scalability, auditability, usability, integration, supportability and regulatory requirements. I would make each measurable where possible.

**Result:** Solution evaluation and architecture decisions can be based on complete requirements rather than feature coverage alone.

### SAP SuccessFactors Employee Central Example
Employee Central requirements should include permissions, integration, audit, performance expectations and employee experience alongside functional capabilities.

### SME Probe
Which non-functional requirement is most commonly missed in HCM projects?

---

## Q05. Requirement Prioritization

### Interview Question
The business has 300 HCM requirements and wants all of them in the first release. How would you prioritize them?

### STAR Answer
**Situation:** The requirement backlog exceeds delivery capacity.

**Task:** I would prioritize based on business value and risk rather than stakeholder volume.

**Action:** I would assess regulatory necessity, business criticality, employee impact, dependency, risk reduction, complexity and time to value. I would distinguish must-have outcomes from preferences.

**Result:** The first release focuses on high-value capabilities while lower-priority requirements remain visible and governed.

### SAP SuccessFactors Employee Central Example
Core employee lifecycle, legal and security requirements would normally be assessed ahead of cosmetic or low-value enhancements.

### SME Probe
What makes a requirement truly “must have”?

---

## Q06. Global versus Local Requirements

### Interview Question
A global HCM program receives different requirements from 30 countries. How would you identify which requirements should enter the global template?

### STAR Answer
**Situation:** Local teams submit overlapping and sometimes contradictory requirements.

**Task:** I would separate common enterprise needs from legitimate localization.

**Action:** I would classify requirements as global policy, common process, legal/regulatory, local business necessity or preference. I would identify reusable patterns and govern exceptions.

**Result:** The global template remains scalable while legitimate local requirements are explicitly accommodated.

### SAP SuccessFactors Employee Central Example
Country-specific Employee Central requirements can be mapped to a common global core with controlled localization.

### SME Probe
What evidence should be required for a local exception?

---

## Q07. Requirement Traceability

### Interview Question
A critical HCM requirement was implemented, but nobody can explain which business outcome it supports. How would you improve traceability?

### STAR Answer
**Situation:** Requirements have become disconnected from business outcomes and delivered features.

**Task:** I would create end-to-end traceability.

**Action:** I would link business objective → requirement → process → capability → solution component → test → acceptance evidence → business outcome. I would establish ownership and change control.

**Result:** Stakeholders can understand why each significant requirement exists and whether it delivered value.

### SAP SuccessFactors Employee Central Example
Employee Central configuration and extensions can be traced back to approved business requirements and acceptance criteria.

### SME Probe
What should happen to a requirement that has no measurable business value?

---

## Q08. Ambiguous Requirements

### Interview Question
A requirement says, “The system should provide flexible employee changes.” What would you do before accepting it?

### STAR Answer
**Situation:** The requirement is too ambiguous to design or test reliably.

**Task:** I would make the requirement testable and architecturally meaningful.

**Action:** I would clarify actors, transaction types, rules, timing, authorization, exceptions, data, integrations and measurable acceptance criteria.

**Result:** The requirement becomes specific enough for design, estimation and testing.

### SAP SuccessFactors Employee Central Example
Instead of “flexible employee changes,” the requirement could specify which employment attributes can change, who can initiate them, approvals, effective dates and downstream impacts.

### SME Probe
What makes a requirement testable?

---

## Q09. Requirement Conflicts

### Interview Question
HR wants employees to update personal information directly, while compliance requires validation before certain changes. How would you resolve the requirement conflict?

### STAR Answer
**Situation:** Experience and control requirements appear to conflict.

**Task:** I would preserve both outcomes where possible.

**Action:** I would classify data by sensitivity and risk, enable self-service for low-risk attributes, introduce validation or approval for sensitive changes and define audit requirements.

**Result:** Employees receive convenient self-service while compliance controls remain intact.

### SAP SuccessFactors Employee Central Example
Employee Central self-service and workflow controls can implement differentiated change paths.

### SME Probe
How do you avoid resolving every conflict by simply choosing one stakeholder?

---

## Q10. Requirement Dependency Mapping

### Interview Question
A business requests a new employee status, but the change affects payroll, identity, reporting and integrations. How would you analyze the requirement?

### STAR Answer
**Situation:** A seemingly simple HCM change has enterprise-wide dependencies.

**Task:** I would identify the full impact before approving the requirement.

**Action:** I would map affected processes, data entities, applications, interfaces, security roles, reports, controls and downstream consumers. I would identify sequencing and change dependencies.

**Result:** The organization avoids implementing a local change that creates downstream defects.

### SAP SuccessFactors Employee Central Example
A new employment status in Employee Central may require updates to payroll, identity provisioning, integrations and analytics.

### SME Probe
What dependency is most often missed when analyzing HCM requirements?

---

## Q11. Data Requirements

### Interview Question
A business process requirement is approved, but nobody has defined what employee data is needed to execute it. How would you close the gap?

### STAR Answer
**Situation:** The functional requirement exists without an information requirement.

**Task:** I would translate the process into explicit data needs.

**Action:** I would identify required entities, attributes, source, owner, quality rules, effective dating, security classification and downstream consumers. I would identify data that is derived rather than stored.

**Result:** The solution can be designed with clear information requirements and fewer late-stage data defects.

### SAP SuccessFactors Employee Central Example
Employee Central requirements can define required person, employment, organizational and workflow information before configuration begins.

### SME Probe
Why should data requirements be defined before solution configuration?

---

## Q12. Requirement for Employee Experience

### Interview Question
HR says, “Make the employee experience simple.” How would you turn that statement into actionable requirements?

### STAR Answer
**Situation:** The desired experience is expressed as a broad aspiration.

**Task:** I would translate experience intent into observable requirements.

**Action:** I would define personas, journeys, tasks, effort, accessibility, language, navigation, completion time, error tolerance and support needs. I would establish measurable experience outcomes.

**Result:** Experience becomes a design and acceptance criterion rather than a subjective statement.

### SAP SuccessFactors Employee Central Example
Employee Central self-service requirements can include task completion, guidance, approvals and mobile experience expectations.

### SME Probe
How would you measure “simple”?

---

## Q13. Security and Privacy Requirements

### Interview Question
A new HCM process collects sensitive employee information, but the requirement document only describes business functionality. What would you do?

### STAR Answer
**Situation:** Sensitive information is being introduced without explicit security and privacy requirements.

**Task:** I would make protection requirements part of the baseline.

**Action:** I would classify data, define legitimate access, segregation of duties, retention, consent or lawful basis where relevant, audit, masking and data minimization requirements.

**Result:** Security and privacy are designed into the solution rather than added after development.

### SAP SuccessFactors Employee Central Example
Sensitive Employee Central data should be governed through permissions, data protection controls and enterprise privacy policies.

### SME Probe
Why should privacy requirements be defined before solution design?

---

## Q14. Integration Requirements

### Interview Question
The business says a new HR process must “integrate with payroll.” What questions would you ask?

### STAR Answer
**Situation:** The integration requirement is too broad to design.

**Task:** I would turn the statement into a precise integration contract.

**Action:** I would clarify data objects, direction, trigger, frequency, latency, volume, transformation, error handling, reconciliation, security and ownership.

**Result:** The integration can be designed, estimated and tested against explicit business requirements.

### SAP SuccessFactors Employee Central Example
An Employee Central to payroll integration would define worker data, triggering events, timing, transformation, monitoring and reconciliation requirements.

### SME Probe
Who should define integration SLAs: business or technology?

---

## Q15. Requirement Change Control

### Interview Question
A senior executive introduces a major HCM requirement halfway through implementation and expects no impact to timeline. How would you respond?

### STAR Answer
**Situation:** A late requirement threatens scope, schedule and architecture.

**Task:** I would evaluate the change objectively without blocking legitimate business needs.

**Action:** I would assess business value, regulatory urgency, dependencies, architecture impact, testing effort, migration impact and delivery risk. I would present options and trade-offs through formal change governance.

**Result:** Leadership can make an informed decision rather than assuming change has no cost.

### SAP SuccessFactors Employee Central Example
A late Employee Central change should be assessed for configuration, integration, data migration, security and regression-testing impact.

### SME Probe
What makes a change urgent enough to bypass normal prioritization?

---

## Q16. Requirements for Migration

### Interview Question
A new HCM solution has been selected, but migration requirements have not been defined. What would you establish?

### STAR Answer
**Situation:** Technology selection has occurred without understanding information migration needs.

**Task:** I would establish migration requirements before committing to implementation scope.

**Action:** I would identify in-scope history, current data, relationships, quality thresholds, transformation rules, retention requirements, reconciliation, cutover timing and business validation.

**Result:** Migration becomes an explicit business requirement rather than a late technical activity.

### SAP SuccessFactors Employee Central Example
Employee Central migration requirements should define worker history, organizational structures, identifiers, effective dates and reconciliation expectations.

### SME Probe
What historical data should not automatically be migrated?

---

## Q17. Requirements for Reporting and Analytics

### Interview Question
Executives request “real-time workforce analytics” without defining the decisions the analytics should support. How would you refine the requirement?

### STAR Answer
**Situation:** The requested technology characteristic is not tied to a decision or business outcome.

**Task:** I would define the analytical decision requirement first.

**Action:** I would identify decisions, KPIs, personas, data sources, refresh needs, history, drill-down, security and actionability. I would then determine whether real-time data is actually required.

**Result:** Analytics investment is aligned to decisions rather than an unnecessary technical specification.

### SAP SuccessFactors Employee Central Example
Employee Central operational data can support selected workforce insights while broader analytics may require an enterprise analytical architecture.

### SME Probe
When is real-time analytics genuinely necessary?

---

## Q18. Requirements for Automation

### Interview Question
HR wants to automate every employee transaction. How would you determine which processes are suitable for automation?

### STAR Answer
**Situation:** Automation is being treated as an objective rather than a means to an outcome.

**Task:** I would identify processes where automation creates measurable value without unacceptable risk.

**Action:** I would assess volume, stability, rule clarity, exception rates, data quality, risk, human judgment and employee impact. I would prioritize deterministic, repeatable and low-risk activities while preserving human intervention where judgment is material.

**Result:** Automation reduces effort and errors while maintaining appropriate human control.

### SAP SuccessFactors Employee Central Example
Routine employee changes can use rules, workflows and integrations, while sensitive or exceptional decisions retain appropriate human review.

### SME Probe
What makes a process unsuitable for full automation?

---

## Q19. Requirement Validation with Prototypes

### Interview Question
Stakeholders cannot agree on what they need because the requirement is abstract. How would you use prototyping?

### STAR Answer
**Situation:** Written requirements are producing different interpretations.

**Task:** I would create a lightweight representation that allows stakeholders to validate the intended outcome.

**Action:** I would prototype the journey, data capture, workflow or interaction; review it with representative users; record decisions and convert validated behavior into explicit requirements and acceptance criteria.

**Result:** Ambiguity decreases before expensive configuration or development begins.

### SAP SuccessFactors Employee Central Example
A prototype of an employee-change journey can validate fields, workflow, approvals and experience before Employee Central configuration.

### SME Probe
Why should a prototype not become an accidental production design?

---

## Q20. Requirements as the Foundation for Architecture

### Interview Question
A program wants to start solution architecture immediately, but requirements are still fragmented. What would you do?

### STAR Answer
**Situation:** Architecture decisions are being made before the problem and constraints are sufficiently understood.

**Task:** I would establish a minimum viable requirement baseline while allowing architecture discovery to proceed iteratively.

**Action:** I would define business outcomes, critical capabilities, priority processes, information needs, integration dependencies, security constraints and non-functional requirements. I would maintain traceability and refine requirements as architecture evidence emerges.

**Result:** Architecture becomes evidence-driven while the program avoids waiting for a perfect requirements document before learning.

### SAP SuccessFactors Employee Central Example
Employee Central architecture can evolve through iterative requirement validation, but core business, data, integration and security constraints should be established early.

### SME Probe
How do you balance “requirements first” with iterative architecture?

---

## Theme 05 Completion Standard

All 20 questions use the same STAR discipline:

**Situation → Task → Action → Result**

The set progresses from problem discovery and stakeholder analysis through process discovery, prioritization, traceability, data, security, integration, migration, analytics, automation, prototyping, change control and architecture readiness.

**Quality rule:** A candidate should demonstrate that they can discover, challenge, structure, prioritize and validate HCM requirements before jumping to product configuration. Product knowledge should strengthen the answer, not replace requirement reasoning.

**IDs:** HR-AWF1-B05-Q01 through HR-AWF1-B05-Q20.
