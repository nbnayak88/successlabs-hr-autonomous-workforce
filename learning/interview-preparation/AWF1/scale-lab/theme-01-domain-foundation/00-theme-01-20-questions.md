# AWF1 — Scale Lab — Theme 01: Domain Foundation

## 20 Scenario-Based Interview Questions — Finance-Pattern Structure

**Stream:** AWF1 — HCM Core & Employee Central  
**Theme:** B01 — Domain Foundation  
**Target:** 20 unique architect-level scenarios  
**Product posture:** HCM-first; SAP SuccessFactors Employee Central is an example, not the boundary.

---

## Q01. HCM Core as an Enterprise Capability

### Interview Scenario
A global organization has grown through acquisitions and has five HR systems. The CHRO asks for one common HCM foundation. How would you determine what HCM Core should own before selecting technology?

### What a Strong Candidate Should Demonstrate
Start with business capabilities and the HR operating model; map the employee lifecycle; define information ownership; separate global standards from legitimate local variation; define ecosystem boundaries and outcomes; then evaluate platforms against the target architecture.

### SAP SuccessFactors Employee Central Example
SAP SuccessFactors Employee Central can be an implementation example, but the capability model must remain platform-neutral.

### SME Probe
What would you refuse to standardize?

### Interviewer Quality Signal
A strong answer should show business context, HR domain reasoning, architectural judgment, trade-offs, and measurable outcomes rather than product memorization.

---

## Q02. Employee Lifecycle as a Core HCM Model

### Interview Scenario
A company says its HR systems work well individually, yet employees experience repeated data collection and inconsistent processes when moving from recruiting to onboarding to employment. How would you diagnose the problem?

### What a Strong Candidate Should Demonstrate
Map the lifecycle and handoffs rather than reviewing applications in isolation. Identify where identity, employment and organizational information is created, transformed and reused; remove duplicate capture and clarify ownership at each transition.

### SAP SuccessFactors Employee Central Example
Employee Central could receive a worker from Recruiting and provide core data to downstream processes, but the architecture should be driven by lifecycle continuity.

### SME Probe
Where is the biggest architectural failure: process, data, application, or governance? Why?

### Interviewer Quality Signal
A strong answer should show business context, HR domain reasoning, architectural judgment, trade-offs, and measurable outcomes rather than product memorization.

---

## Q03. HR Operating Model and HCM Architecture

### Interview Scenario
HR leadership wants a global shared-services model, while country HR teams want to retain independent processes. How would you design the HCM architecture around the operating model?

### What a Strong Candidate Should Demonstrate
Translate the operating model into capabilities, decision rights, standardized services and local exceptions. Align application boundaries and workflow ownership to that model; avoid encoding organizational politics directly into technology.

### SAP SuccessFactors Employee Central Example
Employee Central can support a common core while country-specific processes remain controlled through appropriate local capabilities and integrations.

### SME Probe
How would you prove the architecture supports the operating model rather than merely reflecting it?

### Interviewer Quality Signal
A strong answer should show business context, HR domain reasoning, architectural judgment, trade-offs, and measurable outcomes rather than product memorization.

---

## Q04. Workforce Structure and Organizational Design

### Interview Scenario
A business frequently reorganizes departments, cost centers and reporting relationships. HR and Finance maintain different structures. How would you establish a sustainable workforce-structure model?

### What a Strong Candidate Should Demonstrate
Define organization concepts and their business purpose first. Identify authoritative ownership, effective dates, approval authority and downstream consumers. Separate organizational relationships used for HR from those needed for financial control while governing their mappings.

### SAP SuccessFactors Employee Central Example
Employee Central organizational objects and relationships can illustrate the model, with governed integration to Finance.

### SME Probe
What should happen when HR and Finance require different hierarchies?

### Interviewer Quality Signal
A strong answer should show business context, HR domain reasoning, architectural judgment, trade-offs, and measurable outcomes rather than product memorization.

---

## Q05. Person, Worker and Employment Relationships

### Interview Scenario
An enterprise uses the words person, employee, worker, contractor and contingent worker interchangeably. This creates reporting and access problems. How would you establish a common model?

### What a Strong Candidate Should Demonstrate
Create a business glossary and conceptual information model. Distinguish the human identity from work relationships, legal employment and assignments. Define lifecycle states, identifiers and ownership before configuring applications.

### SAP SuccessFactors Employee Central Example
Employee Central can illustrate person/employment concepts, but the conceptual model must survive a platform change.

### SME Probe
Which definition would you use as the enterprise identity anchor, and why?

### Interviewer Quality Signal
A strong answer should show business context, HR domain reasoning, architectural judgment, trade-offs, and measurable outcomes rather than product memorization.

---

## Q06. Global Template versus Local Variation

### Interview Scenario
A global HCM program wants one process everywhere. Country HR leaders say local legal and operational requirements make this impossible. How would you decide what belongs in the global template?

### What a Strong Candidate Should Demonstrate
Classify requirements into global policy, global process, local legal requirement, local business requirement and preference. Standardize the first categories where appropriate and require explicit evidence for deviations.

### SAP SuccessFactors Employee Central Example
Employee Central can implement a global core with controlled country-specific attributes, rules and processes.

### SME Probe
How would you prevent local exceptions from becoming permanent complexity?

### Interviewer Quality Signal
A strong answer should show business context, HR domain reasoning, architectural judgment, trade-offs, and measurable outcomes rather than product memorization.

---

## Q07. HCM Core as the Foundation for Downstream HR

### Interview Scenario
Payroll, time, learning and talent teams each maintain their own employee attributes. Leadership wants to reduce reconciliation. What architecture would you propose?

### What a Strong Candidate Should Demonstrate
Define the core workforce information set and authoritative ownership. Identify which domains are mastered in HCM Core and which remain specialized. Establish governed interfaces and reconciliation controls rather than copying uncontrolled master data.

### SAP SuccessFactors Employee Central Example
Employee Central can provide core worker and employment data to payroll, time and talent capabilities.

### SME Probe
Which data should never be independently re-created downstream?

### Interviewer Quality Signal
A strong answer should show business context, HR domain reasoning, architectural judgment, trade-offs, and measurable outcomes rather than product memorization.

---

## Q08. Employee and Manager Self-Service

### Interview Scenario
Employees complain that HR transactions require email and manual HR intervention. Leadership wants self-service but HR fears loss of control. How would you redesign the model?

### What a Strong Candidate Should Demonstrate
Identify high-volume employee and manager journeys, assess risk, design role-based workflows and controls, and move appropriate transactions to self-service. Retain human intervention for exceptions and sensitive decisions.

### SAP SuccessFactors Employee Central Example
Employee Central workflows and self-service can illustrate the implementation, but the experience and control model come first.

### SME Probe
Which HR processes should remain intentionally non-self-service?

### Interviewer Quality Signal
A strong answer should show business context, HR domain reasoning, architectural judgment, trade-offs, and measurable outcomes rather than product memorization.

---

## Q09. HR versus IT Ownership

### Interview Scenario
HR owns process decisions while IT owns platforms and integration. Projects repeatedly stall because neither side owns end-to-end outcomes. How would you establish accountability?

### What a Strong Candidate Should Demonstrate
Create capability and decision ownership rather than application ownership. Use a governance model covering business owner, data owner, product/platform owner, integration owner and security owner. Establish outcome-based KPIs.

### SAP SuccessFactors Employee Central Example
Employee Central can have HR product ownership while IT governs technical architecture without transferring business accountability.

### SME Probe
Who owns the quality of employee data: HR, IT, or both?

### Interviewer Quality Signal
A strong answer should show business context, HR domain reasoning, architectural judgment, trade-offs, and measurable outcomes rather than product memorization.

---

## Q10. Capability versus Application Thinking

### Interview Scenario
A CIO presents the application inventory and asks which systems should be retired. You are asked to advise on HCM modernization. How do you avoid making an application-led decision?

### What a Strong Candidate Should Demonstrate
Start with capabilities and processes, map applications to them, identify duplication and gaps, then evaluate strategic fit, cost, risk and experience. Retirement should follow capability decisions, not precede them.

### SAP SuccessFactors Employee Central Example
Employee Central may consolidate several core-HR capabilities, but not every surrounding HR application should automatically be replaced.

### SME Probe
When is retaining an existing application architecturally better than consolidation?

### Interviewer Quality Signal
A strong answer should show business context, HR domain reasoning, architectural judgment, trade-offs, and measurable outcomes rather than product memorization.

---

## Q11. Trusted Employee Record

### Interview Scenario
Executives want a single employee record, but business units disagree on what 'single source of truth' means. How would you define it?

### What a Strong Candidate Should Demonstrate
Define the information domains that require authoritative ownership. A single source of truth does not mean one physical database; it means clear ownership, consistent definitions, controlled changes and trusted distribution.

### SAP SuccessFactors Employee Central Example
Employee Central may serve as the authoritative source for selected workforce master data while other systems remain authoritative for specialized domains.

### SME Probe
Can an enterprise have multiple systems of record and still have a trusted workforce view?

### Interviewer Quality Signal
A strong answer should show business context, HR domain reasoning, architectural judgment, trade-offs, and measurable outcomes rather than product memorization.

---

## Q12. HR Process Standardization

### Interview Scenario
Two regions perform the same employee change process with twelve steps in one region and four in another. Both claim their process is necessary. How would you assess them?

### What a Strong Candidate Should Demonstrate
Compare outcomes, controls, legal requirements, customer experience, cycle time and root causes. Separate necessary controls from historical workarounds. Design a common value stream and permit justified variations.

### SAP SuccessFactors Employee Central Example
Employee Central workflows can implement the resulting standard process, but configuration should follow process simplification.

### SME Probe
How would you handle a stakeholder who equates more approvals with better control?

### Interviewer Quality Signal
A strong answer should show business context, HR domain reasoning, architectural judgment, trade-offs, and measurable outcomes rather than product memorization.

---

## Q13. Workforce Data Ownership

### Interview Scenario
An employee's manager, department and location are frequently incorrect because three systems allow users to change them. What would you do?

### What a Strong Candidate Should Demonstrate
Define each data element's owner, authoritative source, permitted change actors, validation rules, effective dating and downstream consumers. Remove competing write paths where possible and establish data-quality monitoring.

### SAP SuccessFactors Employee Central Example
Employee Central can be the controlled write point for selected core workforce attributes, with integrations distributing approved changes.

### SME Probe
What is more important: a single source or a single accountable owner?

### Interviewer Quality Signal
A strong answer should show business context, HR domain reasoning, architectural judgment, trade-offs, and measurable outcomes rather than product memorization.

---

## Q14. HCM Architecture after an Acquisition

### Interview Scenario
A newly acquired company has a different HR operating model and strong local culture. The parent company wants rapid integration. How would you architect the transition?

### What a Strong Candidate Should Demonstrate
Assess capabilities, processes, data, legal constraints and technology debt. Define transitional coexistence, target-state principles, migration waves and integration boundaries. Avoid forcing immediate standardization where business continuity is at risk.

### SAP SuccessFactors Employee Central Example
Employee Central could become the target HCM Core, while the acquired system temporarily coexists through governed interfaces.

### SME Probe
What criteria would determine migration timing?

### Interviewer Quality Signal
A strong answer should show business context, HR domain reasoning, architectural judgment, trade-offs, and measurable outcomes rather than product memorization.

---

## Q15. Multinational HCM Operating Model

### Interview Scenario
A company operates in 40 countries and wants a common HCM platform. What architectural principles would you establish before designing the solution?

### What a Strong Candidate Should Demonstrate
Use global-by-default and local-by-exception; common data definitions; clear ownership; privacy by design; controlled localization; reusable integration patterns; lifecycle governance; and measurable adoption and quality outcomes.

### SAP SuccessFactors Employee Central Example
Employee Central can provide a global core while country-specific capabilities and integrations address justified requirements.

### SME Probe
How would you distinguish legitimate localization from local preference?

### Interviewer Quality Signal
A strong answer should show business context, HR domain reasoning, architectural judgment, trade-offs, and measurable outcomes rather than product memorization.

---

## Q16. Employee Experience versus Process Efficiency

### Interview Scenario
HR has reduced transaction processing time but employee satisfaction has fallen because processes have become rigid. As architect, how would you respond?

### What a Strong Candidate Should Demonstrate
Measure both operational efficiency and experience. Map journeys, identify friction, distinguish policy constraints from technology limitations, and redesign around employee outcomes while retaining necessary controls.

### SAP SuccessFactors Employee Central Example
Employee Central can provide self-service and guided workflows, but experience design should precede configuration.

### SME Probe
Can the fastest HR process still be a poor employee experience? Explain.

### Interviewer Quality Signal
A strong answer should show business context, HR domain reasoning, architectural judgment, trade-offs, and measurable outcomes rather than product memorization.

---

## Q17. Compliance versus Global Standardization

### Interview Scenario
A global HCM team wants one employee-change process, but a country requires additional legal information and approvals. How would you design for compliance without creating a separate system?

### What a Strong Candidate Should Demonstrate
Treat compliance as an architectural constraint. Keep the common process and core data model where possible, introduce only the required local controls, protect sensitive information, and govern the exception explicitly.

### SAP SuccessFactors Employee Central Example
Employee Central country-specific capabilities can illustrate how local requirements can coexist with a global core.

### SME Probe
Who should approve a country-specific deviation from the global template?

### Interviewer Quality Signal
A strong answer should show business context, HR domain reasoning, architectural judgment, trade-offs, and measurable outcomes rather than product memorization.

---

## Q18. Measuring HCM Core Business Value

### Interview Scenario
The program is technically successful, but executives ask what value HCM modernization has created. What measures would you propose?

### What a Strong Candidate Should Demonstrate
Create a benefits framework across data quality, process efficiency, experience, risk, service productivity, integration reliability and decision quality. Establish baselines before implementation and track outcomes after adoption.

### SAP SuccessFactors Employee Central Example
Employee Central adoption, data quality and lifecycle cycle-time measures can provide implementation evidence, but business outcomes remain the primary measure.

### SME Probe
Which three metrics would you show the CHRO first?

### Interviewer Quality Signal
A strong answer should show business context, HR domain reasoning, architectural judgment, trade-offs, and measurable outcomes rather than product memorization.

---

## Q19. HCM Modernization Decision

### Interview Scenario
An existing HR platform is stable but expensive to change. A new platform promises better experience and integration but requires major migration. How would you make the recommendation?

### What a Strong Candidate Should Demonstrate
Compare business capability fit, strategic alignment, total cost, risk, data quality, integration, experience, change impact and time to value. Consider modernization, coexistence and replacement as explicit options.

### SAP SuccessFactors Employee Central Example
SAP SuccessFactors Employee Central could be one candidate, but the recommendation should be platform-neutral and evidence-based.

### SME Probe
When is modernization better than replacement?

### Interviewer Quality Signal
A strong answer should show business context, HR domain reasoning, architectural judgment, trade-offs, and measurable outcomes rather than product memorization.

---

## Q20. HCM Core as an Enterprise Transformation Foundation

### Interview Scenario
The CHRO wants HCM modernization today, while the CIO expects the platform to support future analytics, automation and AI. How would you design HCM Core so today's solution does not become tomorrow's constraint?

### What a Strong Candidate Should Demonstrate
Design clear capability boundaries, governed workforce data, reusable integration, strong identity and security, experience-led processes, extensibility principles and an architecture runway for analytics, automation and AI. Keep future options open without overengineering today's solution.

### SAP SuccessFactors Employee Central Example
Employee Central can provide the core workforce foundation, while analytics, automation and AI capabilities consume governed data and services through the broader ecosystem.

### SME Probe
What architectural decision made today would create the greatest constraint five years from now?

### Interviewer Quality Signal
A strong answer should show business context, HR domain reasoning, architectural judgment, trade-offs, and measurable outcomes rather than product memorization.

---

## Theme 01 Completion Standard

All 20 questions are intentionally different scenarios. The set progresses from HCM domain foundations to operating model, workforce structure, information ownership, standardization, experience, modernization, and enterprise transformation.

**Quality rule:** A candidate should be able to answer the core scenario without knowing SAP SuccessFactors. Product knowledge should strengthen the answer, not determine whether the candidate can reason about the problem.

**IDs:** `HR-AWF1-B01-Q01` through `HR-AWF1-B01-Q20`.
