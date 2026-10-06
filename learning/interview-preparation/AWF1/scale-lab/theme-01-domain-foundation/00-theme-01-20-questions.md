# AWF1 — Scale Lab — Theme 01: Domain Foundation

## 20 Scenario-Based Interview Questions & STAR Answers

**Stream:** AWF1 — HCM Core & Employee Central  
**Theme:** B01 — Domain Foundation  
**Target:** 20 unique architect-level scenarios  
**Answer method:** STAR — Situation → Task → Action → Result  
**Product posture:** HCM-first; SAP SuccessFactors Employee Central is an example, not the boundary.

---

## Q01. HCM Core as an Enterprise Capability

### Interview Question
A global organization has grown through acquisitions and has five HR systems. The CHRO asks for one common HCM foundation. How would you determine what HCM Core should own before selecting technology?

### STAR Answer
**Situation:** The organization has fragmented HR processes, systems, employee definitions and data ownership following acquisitions.

**Task:** I would determine the target HCM capability model and establish what belongs in the core before selecting a platform.

**Action:** I would map the HR operating model and employee lifecycle; define core capabilities; establish authoritative ownership for person, employment and organizational information; separate global standards from justified local variation; map upstream and downstream dependencies; and define architecture principles and measurable outcomes. Only then would I assess technology options.

**Result:** The organization gets a governed HCM foundation rather than simply replacing applications. Success would be measured through improved data quality, reduced duplication, standardized processes, lower manual effort and better employee experience.

### SAP SuccessFactors Employee Central Example
Employee Central could implement the HCM Core capability, but the capability model and system-of-record decisions remain platform-neutral.

### SME Probe
What would you refuse to standardize?

---

## Q02. Employee Lifecycle as a Core HCM Model

### Interview Question
A company says its HR systems work well individually, yet employees experience repeated data collection and inconsistent processes when moving from recruiting to onboarding to employment. How would you diagnose the problem?

### STAR Answer
**Situation:** Individual applications appear functional, but the employee journey breaks at handoffs and information is repeatedly captured.

**Task:** I would identify whether the root cause is process, data, integration, application boundaries or governance.

**Action:** I would map Plan → Recruit → Hire → Onboard → Employ and identify every handoff, source, owner and consumer of workforce information. I would remove duplicate capture, establish a common identity, define authoritative sources and design governed integrations.

**Result:** The employee experiences a continuous lifecycle, HR avoids duplicate administration, and downstream systems receive trusted information with fewer reconciliation issues.

### SAP SuccessFactors Employee Central Example
Employee Central could receive the worker/employment record from Recruiting and become the core source for downstream HR processes.

### SME Probe
Where is the biggest architectural failure: process, data, application, or governance? Why?

---

## Q03. HR Operating Model and HCM Architecture

### Interview Question
HR leadership wants a global shared-services model, while country HR teams want to retain independent processes. How would you design the HCM architecture around the operating model?

### STAR Answer
**Situation:** The enterprise wants centralized HR services, but local teams fear losing necessary autonomy.

**Task:** I would translate the target operating model into capabilities, decision rights, standardized services and controlled local exceptions.

**Action:** I would define global, regional and local capabilities; establish process ownership; classify local requirements as legal, business-critical or preference; and align application, workflow and data ownership to those decisions.

**Result:** Technology reinforces the operating model instead of encoding organizational conflict. The enterprise gains standardization where it creates value while retaining legitimate flexibility.

### SAP SuccessFactors Employee Central Example
Employee Central can support a common global core while country-specific requirements are governed through localization and controlled process variations.

### SME Probe
How would you prove the architecture supports the operating model rather than merely reflecting it?

---

## Q04. Workforce Structure and Organizational Design

### Interview Question
A business frequently reorganizes departments, cost centers and reporting relationships. HR and Finance maintain different structures. How would you establish a sustainable workforce-structure model?

### STAR Answer
**Situation:** HR and Finance need different organizational views, and frequent reorganizations create inconsistent structures.

**Task:** I would establish the business meaning, ownership and lifecycle of each organizational concept.

**Action:** I would define organization, department, position, cost center and reporting relationships; identify authoritative owners; define effective dating and approvals; and govern mappings between HR and Finance structures.

**Result:** Each function gets the structure it legitimately needs while enterprise mappings remain controlled and traceable. Reorganizations become easier and reconciliation decreases.

### SAP SuccessFactors Employee Central Example
Employee Central organizational objects can represent workforce structures while governed integration maintains required Finance relationships.

### SME Probe
What should happen when HR and Finance require different hierarchies?

---

## Q05. Person, Worker and Employment Relationships

### Interview Question
An enterprise uses the words person, employee, worker, contractor and contingent worker interchangeably. This creates reporting and access problems. How would you establish a common model?

### STAR Answer
**Situation:** Ambiguous workforce definitions cause inconsistent reporting, security and lifecycle processing.

**Task:** I would establish a common conceptual model and business glossary.

**Action:** I would distinguish human identity from work relationships, legal employment, assignments and contingent relationships. I would define lifecycle states, enterprise identifiers, ownership and reporting rules, then map applications to the model.

**Result:** Reporting becomes consistent, access decisions become more reliable, and multiple worker types can be supported without contradictory definitions.

### SAP SuccessFactors Employee Central Example
Employee Central can illustrate person and employment relationships, but the conceptual model must remain valid if the platform changes.

### SME Probe
Which definition would you use as the enterprise identity anchor, and why?

---

## Q06. Global Template versus Local Variation

### Interview Question
A global HCM program wants one process everywhere. Country HR leaders say local legal and operational requirements make this impossible. How would you decide what belongs in the global template?

### STAR Answer
**Situation:** Global standardization is challenged by country-specific requirements.

**Task:** I would distinguish mandatory localization from discretionary variation.

**Action:** I would classify each requirement as global policy, global process, legal/regulatory requirement, legitimate local business requirement or preference. I would standardize the first two, accommodate legally necessary differences, and require evidence and governance approval for other deviations.

**Result:** The enterprise gets a reusable global template without violating local obligations. The number and cost of exceptions can be measured and governed.

### SAP SuccessFactors Employee Central Example
Employee Central can support a global core with controlled country-specific data, rules and processes.

### SME Probe
How would you prevent local exceptions from becoming permanent complexity?

---

## Q07. HCM Core as the Foundation for Downstream HR

### Interview Question
Payroll, time, learning and talent teams each maintain their own employee attributes. Leadership wants to reduce reconciliation. What architecture would you propose?

### STAR Answer
**Situation:** Multiple HR applications maintain overlapping employee information, producing conflicting values.

**Task:** I would establish authoritative information domains and eliminate unnecessary duplicate ownership.

**Action:** I would classify workforce data into core and specialized domains, assign an authoritative owner to each, define who may create or change the data, distribute trusted changes through governed interfaces, and implement reconciliation controls.

**Result:** Duplicate maintenance decreases, downstream processes consume consistent information, and reconciliation effort falls.

### SAP SuccessFactors Employee Central Example
Employee Central can provide core worker and employment information to payroll, time and talent capabilities while specialized systems retain ownership of their own domains.

### SME Probe
Which data should never be independently re-created downstream?

---

## Q08. Employee and Manager Self-Service

### Interview Question
Employees complain that HR transactions require email and manual HR intervention. Leadership wants self-service but HR fears loss of control. How would you redesign the model?

### STAR Answer
**Situation:** High-volume HR transactions are manually handled, creating delays, while HR is concerned about inappropriate changes.

**Task:** I would identify which journeys can safely move to employee or manager self-service.

**Action:** I would map high-volume transactions, classify risk, define role-based permissions and approval controls, design guided workflows, and retain HR intervention for sensitive exceptions. I would measure adoption, completion time, error rate and satisfaction.

**Result:** Routine transactions become faster and more transparent without removing necessary controls. HR capacity shifts toward higher-value work.

### SAP SuccessFactors Employee Central Example
Employee Central self-service and workflows can implement the model, but experience and control design come first.

### SME Probe
Which HR processes should remain intentionally non-self-service?

---

## Q09. HR versus IT Ownership

### Interview Question
HR owns process decisions while IT owns platforms and integration. Projects repeatedly stall because neither side owns end-to-end outcomes. How would you establish accountability?

### STAR Answer
**Situation:** Application ownership is being confused with business accountability.

**Task:** I would establish explicit capability, process, data, product, architecture and security ownership.

**Action:** I would create governance with named business owners, data owners, product/platform owners, integration owners and security owners. I would define decision rights, outcome KPIs and escalation paths.

**Result:** HR remains accountable for business outcomes while IT provides technology governance and delivery. Decisions become faster and ownership becomes measurable.

### SAP SuccessFactors Employee Central Example
Employee Central can have an HR product owner while IT retains technical architecture, integration and platform governance.

### SME Probe
Who owns the quality of employee data: HR, IT, or both?

---

## Q10. Capability versus Application Thinking

### Interview Question
A CIO presents the application inventory and asks which systems should be retired. You are asked to advise on HCM modernization. How do you avoid making an application-led decision?

### STAR Answer
**Situation:** The organization is considering application rationalization before understanding the capabilities those applications provide.

**Task:** I would shift the decision from application inventory to business capability and value.

**Action:** I would map HCM capabilities and processes, map applications to those capabilities, identify duplication and gaps, assess strategic fit, risk, cost and experience, and evaluate retain, modernize, replace or retire options.

**Result:** Applications are rationalized based on business need rather than fashion or inventory size.

### SAP SuccessFactors Employee Central Example
Employee Central may consolidate several core-HR capabilities, but surrounding applications should be retained or replaced based on capability and architecture analysis.

### SME Probe
When is retaining an existing application architecturally better than consolidation?

---

## Q11. Trusted Employee Record

### Interview Question
Executives want a single employee record, but business units disagree on what “single source of truth” means. How would you define it?

### STAR Answer
**Situation:** Leaders want one trusted workforce view, but multiple systems legitimately own different information.

**Task:** I would define truth at the information-domain level.

**Action:** I would identify critical workforce domains, assign authoritative ownership, establish common definitions, control changes, govern identifiers and provide trusted distribution to consumers. I would distinguish a logical source of truth from a single physical database.

**Result:** The enterprise gets trusted workforce information without forcing every HR capability into one application.

### SAP SuccessFactors Employee Central Example
Employee Central may be authoritative for selected core workforce information while payroll, finance or specialist systems remain authoritative for their own domains.

### SME Probe
Can an enterprise have multiple systems of record and still have a trusted workforce view?

---

## Q12. HR Process Standardization

### Interview Question
Two regions perform the same employee change process with twelve steps in one region and four in another. Both claim their process is necessary. How would you assess them?

### STAR Answer
**Situation:** The same business outcome is achieved through significantly different processes.

**Task:** I would determine which differences create genuine value, control or compliance and which are historical complexity.

**Action:** I would compare outcomes, controls, legal requirements, customer experience, cycle time, error rates and root causes. I would remove unnecessary steps, design a common value stream and retain only justified variations.

**Result:** The enterprise gets a simpler standard process without weakening required controls, improving cycle time and operational cost.

### SAP SuccessFactors Employee Central Example
Employee Central workflows can implement the simplified process after process design is agreed.

### SME Probe
How would you handle a stakeholder who equates more approvals with better control?

---

## Q13. Workforce Data Ownership

### Interview Question
An employee's manager, department and location are frequently incorrect because three systems allow users to change them. What would you do?

### STAR Answer
**Situation:** Multiple write points create conflicting workforce data.

**Task:** I would establish authoritative ownership and eliminate uncontrolled competing updates.

**Action:** For each attribute I would define owner, authoritative source, permitted change actors, validation rules, effective dating and consumers. I would remove unnecessary write paths, introduce controlled integration and monitor data quality.

**Result:** Workforce data becomes more reliable, changes become traceable, and downstream systems receive consistent values.

### SAP SuccessFactors Employee Central Example
Employee Central can be the controlled write point for selected core workforce attributes, distributing approved changes through governed integrations.

### SME Probe
What is more important: a single source or a single accountable owner?

---

## Q14. HCM Architecture after an Acquisition

### Interview Question
A newly acquired company has a different HR operating model and strong local culture. The parent company wants rapid integration. How would you architect the transition?

### STAR Answer
**Situation:** The enterprise wants fast integration while the acquired business has different processes, data and technology.

**Task:** I would balance business continuity with convergence toward the target HCM architecture.

**Action:** I would assess capabilities, processes, data, legal requirements, technology debt and integration dependencies. I would define a transition state, coexistence pattern, migration waves, data cleansing and explicit legacy exit criteria.

**Result:** Integration proceeds in controlled waves without disrupting employees or payroll-critical operations, with a clear path to the target architecture.

### SAP SuccessFactors Employee Central Example
Employee Central could be the target HCM Core while the acquired system temporarily coexists through governed interfaces.

### SME Probe
What criteria would determine migration timing?

---

## Q15. Multinational HCM Operating Model

### Interview Question
A company operates in 40 countries and wants a common HCM platform. What architectural principles would you establish before designing the solution?

### STAR Answer
**Situation:** A multinational organization needs global consistency while operating under different legal and cultural conditions.

**Task:** I would define global architecture principles and localization governance before solution design.

**Action:** I would establish global-by-default and local-by-exception, common data definitions, clear ownership, privacy by design, reusable integration patterns, controlled localization, lifecycle governance and measurable adoption and quality outcomes.

**Result:** The organization gets a scalable global HCM foundation without turning every country into a separate solution.

### SAP SuccessFactors Employee Central Example
Employee Central can provide the global core while justified country capabilities and integrations address local requirements.

### SME Probe
How would you distinguish legitimate localization from local preference?

---

## Q16. Employee Experience versus Process Efficiency

### Interview Question
HR has reduced transaction processing time but employee satisfaction has fallen because processes have become rigid. As architect, how would you respond?

### STAR Answer
**Situation:** Operational efficiency improved, but employees now experience more friction.

**Task:** I would optimize for both process performance and employee outcomes.

**Action:** I would map the employee journey, collect experience data, identify friction points, distinguish policy constraints from technology limitations, and redesign the journey around employee needs while preserving mandatory controls.

**Result:** Experience improves without simply sacrificing efficiency. Measures include completion time, abandonment, first-time-right rate, support contacts and satisfaction.

### SAP SuccessFactors Employee Central Example
Employee Central self-service and guided workflows can support the redesigned journey, but UX and process decisions should precede configuration.

### SME Probe
Can the fastest HR process still be a poor employee experience? Explain.

---

## Q17. Compliance versus Global Standardization

### Interview Question
A global HCM team wants one employee-change process, but a country requires additional legal information and approvals. How would you design for compliance without creating a separate system?

### STAR Answer
**Situation:** A local legal requirement conflicts with global process standardization.

**Task:** I would satisfy the legal requirement while preserving the common process and architecture wherever possible.

**Action:** I would identify the exact legal requirement, determine mandatory data and approvals, keep the global process and core model intact where possible, introduce the minimum local control, protect sensitive information and formally govern the exception.

**Result:** Compliance is achieved without creating an unnecessary country-specific application or duplicate process.

### SAP SuccessFactors Employee Central Example
Employee Central country-specific capabilities can support local requirements while retaining a common HCM Core.

### SME Probe
Who should approve a country-specific deviation from the global template?

---

## Q18. Measuring HCM Core Business Value

### Interview Question
The program is technically successful, but executives ask what value HCM modernization has created. What measures would you propose?

### STAR Answer
**Situation:** Technology has been delivered, but leadership cannot see a clear business-value story.

**Task:** I would establish a benefits framework linked to transformation objectives.

**Action:** I would baseline data quality, process cycle time, manual effort, employee experience, HR service productivity, integration reliability, risk and decision quality before implementation. I would track post-go-live improvement and adoption.

**Result:** The program demonstrates measurable business value rather than technical completion, giving the CHRO evidence for continued investment.

### SAP SuccessFactors Employee Central Example
Employee Central adoption, workforce-data quality and lifecycle cycle-time measures can provide implementation evidence, while business outcomes remain primary.

### SME Probe
Which three metrics would you show the CHRO first?

---

## Q19. HCM Modernization Decision

### Interview Question
An existing HR platform is stable but expensive to change. A new platform promises better experience and integration but requires major migration. How would you make the recommendation?

### STAR Answer
**Situation:** The organization must choose between extending a stable legacy platform and undertaking major modernization.

**Task:** I would make the decision using evidence rather than technology preference.

**Action:** I would compare business capability fit, strategic alignment, total cost, risk, data quality, integration, experience, change impact, migration complexity and time to value. I would explicitly evaluate retain/modernize, coexist and replace scenarios.

**Result:** Leadership receives a transparent recommendation with trade-offs, investment implications and transition risk rather than a product-driven proposal.

### SAP SuccessFactors Employee Central Example
SAP SuccessFactors Employee Central could be one candidate, but the recommendation must remain platform-neutral and evidence-based.

### SME Probe
When is modernization better than replacement?

---

## Q20. HCM Core as an Enterprise Transformation Foundation

### Interview Question
The CHRO wants HCM modernization today, while the CIO expects the platform to support future analytics, automation and AI. How would you design HCM Core so today's solution does not become tomorrow's constraint?

### STAR Answer
**Situation:** The enterprise needs immediate HCM improvement while preparing for intelligent HR capabilities.

**Task:** I would design an architecture that delivers current business value while preserving future options.

**Action:** I would establish clear capability boundaries, governed workforce data, reusable integration, strong identity and security, experience-led processes, controlled extensibility and an architecture runway for analytics, automation and AI. I would avoid speculative complexity without a current business case.

**Result:** HCM Core becomes a durable enterprise workforce foundation. Future analytics, automation and AI can consume trusted data and services without repeatedly redesigning the core.

### SAP SuccessFactors Employee Central Example
Employee Central can provide the core workforce foundation, while analytics, automation and AI capabilities consume governed data and services through the broader ecosystem.

### SME Probe
What architectural decision made today would create the greatest constraint five years from now?

---

## Theme 01 Completion Standard

All 20 questions use the same STAR discipline:

**Situation → Task → Action → Result**

The set progresses from HCM domain foundations to operating model, workforce structure, information ownership, standardization, experience, modernization and enterprise transformation.

**Quality rule:** A candidate should be able to answer the core scenario without knowing SAP SuccessFactors. Product knowledge should strengthen the answer, not determine whether the candidate can reason about the problem.

**IDs:** HR-AWF1-B01-Q01 through HR-AWF1-B01-Q20.
