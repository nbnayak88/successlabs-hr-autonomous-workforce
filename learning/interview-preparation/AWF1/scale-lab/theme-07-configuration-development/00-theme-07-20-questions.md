# AWF1 — Scale Lab — Theme 07: Configuration / Development

## 20 Scenario-Based Interview Questions & STAR Answers

**Stream:** AWF1 — HCM Core & Employee Central  
**Theme:** B07 — Configuration / Development  
**Target:** 20 unique architect-level scenarios  
**Answer method:** STAR — Situation → Task → Action → Result  
**Product posture:** HCM-first; SAP SuccessFactors Employee Central is an example, not the boundary.

---

## Q01. Configuration versus Custom Development

### Interview Question
A business team asks developers to build a custom solution for a requirement that appears close to standard HCM capability. How would you decide whether to configure or develop?

### STAR Answer
**Situation:** The team is about to introduce custom code where standard capability may already exist.

**Task:** I would determine the lowest-complexity solution that meets the business outcome.

**Action:** I would validate the requirement, assess standard capability, challenge unnecessary process variation, evaluate configuration options and use custom development only where the requirement has clear business value that standard capability cannot satisfy.

**Result:** The solution remains maintainable and upgrade-friendly while legitimate differentiation is supported.

### SAP SuccessFactors Employee Central Example
I would evaluate standard Employee Central configuration before custom extensions or external development.

### SME Probe
What is your first question when someone requests custom development?

---

## Q02. Configuration Standards

### Interview Question
Different implementation teams configure the same HCM capability in different ways. How would you establish configuration standards?

### STAR Answer
**Situation:** Inconsistent configuration is increasing support and change complexity.

**Task:** I would create reusable configuration principles and governance.

**Action:** I would define naming conventions, design patterns, ownership, documentation, approval criteria and reusable templates. I would distinguish mandatory standards from context-dependent choices.

**Result:** Configuration becomes consistent, understandable and easier to maintain across implementations.

### SAP SuccessFactors Employee Central Example
Employee Central objects, rules, workflows and permissions can follow common configuration standards.

### SME Probe
Which configuration decisions should be standardized globally?

---

## Q03. Extension Strategy

### Interview Question
The HCM platform cannot represent a specialized workforce attribute required by the business. How would you design the extension?

### STAR Answer
**Situation:** A legitimate business requirement is outside the standard information model.

**Task:** I would extend the solution without compromising the core architecture.

**Action:** I would confirm ownership and lifecycle of the attribute, assess standard extension mechanisms, define validation and security, evaluate integration impact and document the extension's lifecycle and exit criteria.

**Result:** The business requirement is supported while technical debt and uncontrolled customization are minimized.

### SAP SuccessFactors Employee Central Example
Supported Employee Central extensibility mechanisms can be used where the attribute genuinely belongs in core workforce information.

### SME Probe
How do you decide whether an attribute belongs in the HCM core?

---

## Q04. Business Rules and Decision Logic

### Interview Question
An HCM process contains hundreds of business rules created by different teams. How would you rationalize them?

### STAR Answer
**Situation:** Rule proliferation makes behavior difficult to understand and change.

**Task:** I would establish a governed decision-logic model.

**Action:** I would inventory rules, identify duplicates and contradictions, separate policy from implementation logic, simplify decision tables and assign ownership. I would test rules against representative scenarios.

**Result:** Business logic becomes transparent, maintainable and easier to change safely.

### SAP SuccessFactors Employee Central Example
Employee Central business rules can be consolidated and governed through common design standards.

### SME Probe
When should a business rule be implemented outside the HCM platform?

---

## Q05. Workflow Configuration

### Interview Question
A manager-change workflow has become slow because every change requires several approvals. How would you redesign the configuration?

### STAR Answer
**Situation:** Workflow configuration is creating unnecessary cycle time.

**Task:** I would align workflow behavior with actual business controls.

**Action:** I would identify approval purpose, risk level and exception patterns; remove redundant approvals; automate low-risk decisions; and retain material controls.

**Result:** Transaction speed improves while governance remains proportionate to risk.

### SAP SuccessFactors Employee Central Example
Employee Central workflow configuration can support differentiated approval paths based on transaction type and risk.

### SME Probe
How do you prove an approval is actually adding control value?

---

## Q06. Effective-Dated Configuration

### Interview Question
The organization frequently changes managers, departments and positions. How would you configure the solution to preserve historical accuracy?

### STAR Answer
**Situation:** Workforce structures change frequently and historical reporting is essential.

**Task:** I would ensure configuration supports temporal business behavior.

**Action:** I would define effective dates, correction rules, future-dated changes, event sequencing and historical reporting requirements. I would test overlapping and backdated scenarios.

**Result:** Current and historical workforce states remain reliable.

### SAP SuccessFactors Employee Central Example
Employee Central effective-dated objects and employment information can support controlled historical and future changes.

### SME Probe
What is the biggest risk of incorrect effective dating?

---

## Q07. Validation and Data Entry Controls

### Interview Question
Employees frequently enter invalid organizational or personal information. How would you use configuration to prevent bad data?

### STAR Answer
**Situation:** Poor data quality is originating at the point of entry.

**Task:** I would prevent invalid information before it reaches downstream systems.

**Action:** I would define validation rules, required fields, reference data, conditional logic and controlled value lists based on business ownership.

**Result:** Data quality improves at source and downstream reconciliation decreases.

### SAP SuccessFactors Employee Central Example
Employee Central validation and business rules can enforce controlled data entry for core workforce information.

### SME Probe
Which validation belongs at source and which belongs downstream?

---

## Q08. Role and Permission Configuration

### Interview Question
HR wants broad access to employee data for convenience, while security insists on least privilege. How would you configure roles?

### STAR Answer
**Situation:** Usability and security requirements appear to conflict.

**Task:** I would design roles around legitimate business responsibilities.

**Action:** I would define personas, data sensitivity, functional permissions, field-level restrictions where available, segregation of duties and review cycles. I would test roles with real user scenarios.

**Result:** Users receive sufficient access without creating unnecessary exposure.

### SAP SuccessFactors Employee Central Example
Role-Based Permissions in Employee Central can implement controlled access aligned to HR personas.

### SME Probe
Why is role design a business architecture concern?

---

## Q09. Localization Configuration

### Interview Question
A global HCM process needs country-specific legal behavior. How would you configure localization without duplicating the global solution?

### STAR Answer
**Situation:** Local requirements need to coexist with a common global process.

**Task:** I would isolate necessary localization while preserving shared design.

**Action:** I would identify mandatory local rules, data and approvals; parameterize where possible; document deviations; and prevent local configuration from changing the global business meaning.

**Result:** Country requirements are met without creating uncontrolled forks of the solution.

### SAP SuccessFactors Employee Central Example
Country-specific configuration can support local requirements while maintaining a common Employee Central foundation.

### SME Probe
What is the difference between localization and customization?

---

## Q10. Configuration Transport and Change Control

### Interview Question
A configuration change works in development but causes unexpected behavior after deployment. How would you improve the configuration lifecycle?

### STAR Answer
**Situation:** Changes are moving between environments without sufficient control.

**Task:** I would establish a disciplined configuration lifecycle.

**Action:** I would define development, validation and production controls; version changes; document impact; require peer review; execute regression testing; and maintain rollback or recovery procedures.

**Result:** Configuration changes become predictable, traceable and safer to release.

### SAP SuccessFactors Employee Central Example
Employee Central configuration changes should follow controlled release and regression practices appropriate to the platform.

### SME Probe
Why can configuration require the same governance discipline as code?

---

## Q11. Custom Development Governance

### Interview Question
A development team has created several custom applications around HCM because standard functionality was considered too restrictive. How would you review the portfolio?

### STAR Answer
**Situation:** Custom applications may have created hidden duplication and lifecycle cost.

**Task:** I would assess whether each custom component still has a justified architectural role.

**Action:** I would map each application to capabilities, owners, data, integrations, users, cost and business value. I would classify components as retain, simplify, replace with standard capability or retire.

**Result:** Custom development becomes a governed portfolio rather than an unmanaged shadow HCM landscape.

### SAP SuccessFactors Employee Central Example
Custom applications around Employee Central should be evaluated against supported platform capabilities and integration architecture.

### SME Probe
What is the strongest signal that custom development has become technical debt?

---

## Q12. Reusable Configuration Patterns

### Interview Question
A global implementation repeatedly configures similar employee processes for different business units. How would you increase reuse?

### STAR Answer
**Situation:** Teams are solving similar problems independently.

**Task:** I would establish reusable patterns without forcing inappropriate standardization.

**Action:** I would identify common configuration structures, workflow patterns, validation rules and integration contracts; package reusable templates; and define approved variation points.

**Result:** Delivery becomes faster and more consistent while legitimate business differences remain configurable.

### SAP SuccessFactors Employee Central Example
Reusable Employee Central configuration patterns can accelerate deployment across organizational units.

### SME Probe
When does reuse become over-standardization?

---

## Q13. Configuration Performance

### Interview Question
A heavily configured HCM process becomes slow as transaction volume grows. How would you investigate?

### STAR Answer
**Situation:** Configuration complexity is affecting operational performance.

**Task:** I would determine whether rules, workflows, integrations, data volume or user behavior are causing the degradation.

**Action:** I would baseline performance, trace the transaction path, inspect rule complexity and dependencies, remove unnecessary processing and test under realistic volumes.

**Result:** Performance improves based on evidence rather than indiscriminate configuration changes.

### SAP SuccessFactors Employee Central Example
Employee Central business rules, workflows and integrations should be assessed together when investigating transaction performance.

### SME Probe
Why is optimizing one rule sometimes insufficient?

---

## Q14. Development for Integration

### Interview Question
A developer proposes embedding payroll-specific logic directly into the HCM core because it is faster to build. How would you respond?

### STAR Answer
**Situation:** A local implementation shortcut would create tight coupling between domains.

**Task:** I would preserve clear domain boundaries.

**Action:** I would identify ownership of payroll logic, define the integration contract and place domain-specific behavior with the appropriate system. I would evaluate the shortcut against lifecycle and change impact.

**Result:** The HCM core remains focused while payroll-specific behavior can evolve independently.

### SAP SuccessFactors Employee Central Example
Employee Central should exchange authoritative workforce information with payroll rather than absorb payroll-domain logic unnecessarily.

### SME Probe
What type of logic should never be duplicated across HR systems?

---

## Q15. Automated Testing of Configuration

### Interview Question
A configuration-heavy HCM solution has thousands of combinations and manual regression testing is becoming impossible. What would you do?

### STAR Answer
**Situation:** Configuration complexity is increasing regression risk and testing effort.

**Task:** I would make configuration behavior systematically testable.

**Action:** I would identify critical business rules and transaction paths, create reusable test data and automate repeatable regression scenarios where feasible. I would prioritize high-risk combinations and maintain traceability to requirements.

**Result:** Release confidence increases while regression effort becomes more sustainable.

### SAP SuccessFactors Employee Central Example
Employee Central workflows, business rules, permissions and lifecycle transactions can be included in automated or semi-automated regression suites.

### SME Probe
What should determine regression-test priority?

---

## Q16. Development Security

### Interview Question
A custom HCM extension needs access to sensitive employee data. How would you govern its development?

### STAR Answer
**Situation:** Custom development introduces another access path to sensitive workforce information.

**Task:** I would apply security-by-design.

**Action:** I would minimize data access, define service identities, enforce authorization, encrypt sensitive communication, log access, validate dependencies and conduct security testing before production.

**Result:** The extension meets its business purpose without creating uncontrolled data exposure.

### SAP SuccessFactors Employee Central Example
Custom services consuming Employee Central data should use governed APIs, scoped authorization and enterprise security controls.

### SME Probe
Why should an extension consume the minimum data necessary?

---

## Q17. Technical Debt in Configuration

### Interview Question
The HCM platform works, but nobody understands why many configurations exist. How would you reduce configuration debt?

### STAR Answer
**Situation:** Historical configuration has accumulated without clear ownership or rationale.

**Task:** I would make configuration understandable and intentional again.

**Action:** I would inventory configuration, identify unused or duplicated objects, trace important logic to business requirements, remove obsolete elements and document remaining design decisions.

**Result:** Supportability improves and future changes become safer.

### SAP SuccessFactors Employee Central Example
Employee Central rules, workflows, fields and permissions can be reviewed periodically for redundancy and obsolete behavior.

### SME Probe
How do you decide whether an undocumented configuration is safe to remove?

---

## Q18. Configuration for Organizational Change

### Interview Question
The organization restructures every quarter. How would you design configuration so frequent changes do not require development?

### STAR Answer
**Situation:** Organizational changes are triggering repeated technical work.

**Task:** I would separate business-variable data from stable application logic.

**Action:** I would use effective-dated organizational structures, reference data and parameterized rules where appropriate. I would remove hard-coded organizational assumptions and define governance for structural changes.

**Result:** Routine reorganizations can be handled through governed configuration and data changes rather than repeated development.

### SAP SuccessFactors Employee Central Example
Effective-dated organizational objects and configurable rules can support recurring organizational changes.

### SME Probe
What should never be hard-coded into HCM logic?

---

## Q19. Development Standards and Code Ownership

### Interview Question
Multiple teams build HCM extensions using different coding patterns and documentation. How would you establish engineering governance?

### STAR Answer
**Situation:** Inconsistent development practices increase security, maintenance and support risk.

**Task:** I would establish common engineering standards aligned to the architecture.

**Action:** I would define coding conventions, API standards, security controls, testing expectations, documentation, ownership, observability and lifecycle management. I would introduce architecture and peer reviews for material extensions.

**Result:** Extensions become maintainable enterprise assets rather than isolated team solutions.

### SAP SuccessFactors Employee Central Example
Extensions integrating with Employee Central should follow enterprise API, security, testing and observability standards.

### SME Probe
Which development standard has the greatest architecture impact?

---

## Q20. Configuration / Development as a Managed Capability

### Interview Question
The organization has hundreds of HCM configurations and custom extensions maintained by different vendors. What would you do to establish sustainable ownership?

### STAR Answer
**Situation:** Configuration and development have become fragmented across vendors and teams.

**Task:** I would establish a governed HCM engineering capability.

**Action:** I would create an inventory, define ownership, standards, release governance, architecture review, documentation, testing, observability and lifecycle controls. I would distinguish strategic extensions from temporary implementation artifacts.

**Result:** HCM configuration and development become a sustainable enterprise capability with controlled change and lower dependency on individual vendors.

### SAP SuccessFactors Employee Central Example
Employee Central configuration and extensions can be managed through a common engineering governance model across implementation partners and internal teams.

### SME Probe
What would you measure to know whether HCM engineering governance is working?

---

## Theme 07 Completion Standard

All 20 questions use the same STAR discipline:

**Situation → Task → Action → Result**

The set progresses from configuration-versus-development decisions through standards, extensions, business rules, workflow, effective dating, validation, permissions, localization, release control, reuse, performance, integration, testing, security, technical debt and sustainable HCM engineering governance.

**Quality rule:** A candidate should demonstrate that they can configure and extend HCM responsibly without turning every requirement into customization. Product knowledge should strengthen the answer, not replace engineering and architecture reasoning.

**IDs:** HR-AWF1-B07-Q01 through HR-AWF1-B07-Q20.
