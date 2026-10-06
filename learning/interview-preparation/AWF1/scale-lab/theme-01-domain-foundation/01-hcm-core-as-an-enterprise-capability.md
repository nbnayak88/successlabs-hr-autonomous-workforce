# AWF1 — Theme 01 — Question 01
## HCM Core as an Enterprise Capability

### Interview Question
A global organization has grown through multiple acquisitions. Each business unit has developed its own way of maintaining employee information, managing organizational structures, and supporting HR processes.

The CHRO now wants to establish a common HCM foundation across the enterprise. Some stakeholders argue that the organization should first select a modern HCM platform. Others argue that the organization must first clarify its HR operating model, processes, data ownership, and global-versus-local requirements.

As the HCM / HR Technology Architect, how would you approach this situation? What would you establish before deciding on the technology solution, and how would you explain the role of HCM Core in the wider enterprise?

---
## What This Question Is Testing
This is not primarily a product-selection question. It tests whether the candidate understands that HCM Core is an enterprise capability and information foundation, rather than simply an HR application.

A strong candidate should connect: Business strategy → HR operating model → workforce processes → employee information → HCM capabilities → technology architecture → enterprise outcomes.

## Situation
- Multiple acquired businesses
- Different HR processes
- Different definitions of employee and organizational data
- Multiple HR systems
- Regional variations
- Duplicate or inconsistent employee information
- Pressure from leadership to create a common HCM foundation

The immediate temptation is to start with technology selection. The architect's responsibility is to determine what the enterprise needs to standardize, what must remain locally different, and what capabilities and information should form the foundation of the future HCM ecosystem.

## Task
1. Understand the business and HR operating model.
2. Identify the core HCM capabilities required across the enterprise.
3. Understand the employee lifecycle and critical HR processes.
4. Establish ownership of workforce information.
5. Identify global standards versus legitimate local variations.
6. Define the role of HCM Core within the broader HR ecosystem.
7. Identify downstream and upstream dependencies.
8. Establish architecture principles before selecting or configuring technology.
9. Define measurable outcomes for the transformation.

## Strong Answer — STAR
### Situation
I would first recognize that the organization does not have a technology problem alone. It has an operating-model, process, information and architecture problem created by organizational growth and acquisitions. The different systems are symptoms of the underlying fragmentation.

My first objective would therefore be to establish a common understanding of how the enterprise manages its workforce rather than immediately selecting a product.

### Task
My responsibility would be to define the target HCM Core capability and determine what should be globally standardized, what genuinely needs local variation, which workforce information is authoritative, which processes belong in the core, which systems consume or contribute information, how HCM Core supports the broader employee lifecycle, and what business outcomes the target architecture must deliver.

### Action
1. Start with the enterprise HCM capability model. Identify capabilities such as workforce/person management, employment management, organizational management, position/work structure, job and role structures, manager and employee relationships, workforce lifecycle events, HR workflows, workforce data governance, and reporting foundations.

2. Map the employee lifecycle: Plan → Recruit → Hire → Onboard → Develop → Perform → Reward → Move → Leave → Rehire. Identify information and HCM capabilities required at each stage.

3. Establish the HCM information foundation. Identify Person, Employment, Job, Position, Organization, Location, Legal Entity, Manager Relationship, Worker Status, and relevant reference information. For each domain establish Owner → Source → Definition → Quality Rules → Consumers → Change Authority.

4. Separate global standards from local requirements. Standardize where variation creates unnecessary complexity; localize where there is legitimate business, legal, or regulatory justification.

5. Define HCM Core in the ecosystem. Consider Recruiting, Onboarding, Time, Payroll, Learning, Performance and Talent, Compensation, Identity and Access Management, Finance, Enterprise Reporting, Workforce Analytics, and external HR applications.

6. Establish architecture principles: business capability before product; clear system-of-record ownership; API/event-led integration where appropriate; security and privacy by design; global-by-default, local-by-exception; configuration before customization; experience-led HR; data quality as a business responsibility; and architecture designed for change.

7. Only then evaluate technology. SAP SuccessFactors Employee Central could be considered as an HCM Core platform. It may provide capabilities for core workforce information, employment relationships, organizational structures, workflows, and effective-dated HR data. The product decision remains an implementation decision against the target capability and architecture.

8. Define measurable outcomes such as reduction in duplicate employee records, improvement in workforce-data quality, reduction in manual HR administration, reduction in process cycle time, percentage of workforce covered by common processes, governed integration coverage, reconciliation effort, HR service productivity, and employee/manager self-service adoption.

### Result
The outcome would be more than replacing multiple HR applications. The aim is a trusted HCM foundation with consistent workforce information, clear data ownership, common HR capabilities, controlled local variation, better integration, improved employee and manager experience, stronger governance, and a foundation for analytics, automation, and AI.

## Architecture Signals
| Architecture Lens | Expected Signal |
|---|---|
| Enterprise | HCM aligned with enterprise strategy and operating model |
| Business | Workforce capabilities linked to business outcomes |
| Domain | Strong HR/HCM domain understanding |
| Process | Employee lifecycle and HR operating processes |
| Data | Workforce information ownership and quality |
| Application | Clear role of HCM Core in the landscape |
| Integration | Relationships with surrounding HR and enterprise systems |
| Security | Workforce-data protection and access governance |
| UI/UX | Employee and manager experience |
| Technology | Platform and integration choices |
| AI | Future readiness for automation and intelligent HR |
| Industry | Awareness of sector/regulatory context |

## SME Probe
Suppose the organization selects SAP SuccessFactors Employee Central as its HCM Core platform. Six months later, Finance argues that the finance system should remain the authoritative source for organizational structures, while HR argues that Employee Central should own them. How would you resolve the conflict?

A strong candidate should discuss business ownership → information domain → accountability → process → source of truth → integration → governance → decision rights.

## Reflection
The deepest lesson is: HCM Core is not fundamentally about where employee data is stored. It is about how an enterprise defines, governs, and manages its workforce.

A mature HCM architect therefore starts with: What workforce capability does the enterprise need? Rather than: Which HCM product should we configure?

## Candidate Answer Spine
Business problem → HCM capability model → employee lifecycle → information ownership → global/local model → ecosystem architecture → technology decision → governance → measurable outcome

## Quality Classification
- Level: Architect / Senior Consultant
- Primary BAISI Theme: 01 — Domain Foundation
- AWF1 ID: HR-AWF1-B01-Q01
- Product dependency: Low
- SAP SuccessFactors dependency: Example only
- Primary capability assessed: HCM domain understanding
- Secondary capabilities: Enterprise thinking, business architecture, data architecture, application architecture, integration thinking
- Status: Draft for review — do not treat as locked until reviewed