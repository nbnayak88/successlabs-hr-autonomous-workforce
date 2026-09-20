# Application Management Services Lab — General Handbook

**Lab:** Application Management Services Lab (AMS)  
**Track:** 08 — AMS  
**Learning Intent:** **SUPPORT**  
**Maturity Stage:** Intermediate  
**Core Intention:** Sustain, optimize, and continuously improve live enterprise systems.  
**Student Outcome:** Develop a long-term system ownership mindset.

> **Support is the intent.** Go-live is not the finish line. AMS is the discipline of keeping live enterprise systems reliable, useful, secure, supportable and continuously improving over time.

---

## 1. Purpose

The Application Management Services Lab develops the capability to **own live systems over their lifecycle** through incident resolution, root-cause analysis, monitoring, service management, change management and continuous improvement.

AMS establishes the long-term value loop:

**Operate → Observe → Support → Diagnose → Resolve → Prevent → Optimize → Improve**

The lab moves beyond ticket closure toward **system stewardship**.

---

## 2. AMS Philosophy

1. **Support is your intent** — sustain, optimize and improve live enterprise systems.
2. **Own it like it's yours** — treat the system as a long-term responsibility.
3. **Resolve the root, not the symptom** — prevent recurrence rather than repeatedly patching.
4. **Monitor proactively** — detect problems before users experience them where possible.
5. **Optimize continuously** — stable systems can still become better.
6. **Grow at the Intermediate level** — patience and ownership define operational maturity.
7. **Support across the 11 GICS sectors** — service expectations and business consequences vary.
8. **Stewardship serves the mission** — sustained systems sustain better experiences.

---

# 3. The Universal 22 Pahacha — AMS Context

The **22 Pahacha** remain universal across all 20 Labs. AMS changes the interpretation and evidence expected at each step.

| # | Pahacha | AMS interpretation |
|---|---|---|
| 1 | Domain Foundation | Understand the business criticality and operating context of the live system. |
| 2 | Product & Technology Knowledge | Understand the application's capabilities, dependencies and support boundaries. |
| 3 | Business Process & Operating Context | Understand how users depend on the system in daily operations. |
| 4 | Data & Information Model | Understand production data, dependencies, integrity and ownership. |
| 5 | Requirement Analysis | Clarify incidents, service requests, changes and improvement needs. |
| 6 | Solution Design Awareness | Understand intended architecture and design before making live changes. |
| 7 | Configuration / Development Awareness | Understand configuration and code that may influence live behavior. |
| 8 | Architecture & Integration Awareness | Identify upstream/downstream dependencies and integration impact. |
| 9 | Implementation Awareness | Understand controlled change, release and deployment procedures. |
| 10 | Migration & Data Readiness Awareness | Recognize data changes and migrations that can affect live operations. |
| 11 | Testing & Quality Awareness | Validate fixes and changes before production release. |
| 12 | Release, Adoption & Support Awareness | **Core AMS capability:** manage sustainable live-service support and change. |
| 13 | Troubleshooting Mindset | Diagnose incidents systematically using evidence. |
| 14 | Incident & Defect Awareness | Distinguish incidents, defects, service requests, problems and changes. |
| 15 | Complex Scenario Thinking | Handle recurring incidents, dependencies, competing priorities and business-critical failures. |
| 16 | Optimization & Continuous Improvement | Identify trends and continuously improve service quality. |
| 17 | Stakeholder Management | Coordinate users, business owners, support teams and technical specialists. |
| 18 | Communication & Collaboration | Keep stakeholders informed during incidents, changes and improvements. |
| 19 | Advisory & Trusted SME | Provide informed recommendations based on operational evidence. |
| 20 | Automation, AI & Intelligent Products | Identify opportunities for monitoring, ticket classification, knowledge retrieval, anomaly detection and remediation with appropriate controls. |
| 21 | Transformation & Business Value | Connect service improvements to reliability, productivity and business outcomes. |
| 22 | Strategic Mastery & Future Vision | Evolve support from reactive maintenance toward intelligent lifecycle stewardship. |

---

# 4. Six Universal Themes

| Theme | AMS interpretation |
|---|---|
| **KNOW** | Understand the live application, business processes, users and dependencies. |
| **DESIGN** | Design support models, monitoring, change controls and improvement approaches. |
| **DELIVER** | Resolve incidents, execute changes and maintain service continuity. |
| **SOLVE** | Find root causes and prevent recurrence. |
| **INFLUENCE** | Coordinate stakeholders and communicate service decisions. |
| **TRANSFORM** | Continuously improve the live service and evolve the operating model. |

---

# 5. AMS Service Health Canvas

Use this canvas for a live-system support scenario.

| Dimension | Questions |
|---|---|
| Business Service | What business service does the application enable? |
| Criticality | What happens if it is unavailable or degraded? |
| Users | Who depends on it? |
| Incident | What is happening? |
| Impact | Who/what is affected? |
| Urgency | How quickly must it be addressed? |
| Dependencies | Which systems, integrations or data are involved? |
| Evidence | What logs, metrics or observations exist? |
| Root Cause | Why did the issue occur? |
| Resolution | What restored service? |
| Prevention | What will prevent recurrence? |
| Change | Is a controlled change required? |
| Monitoring | How can the issue be detected earlier? |
| Knowledge | What should be documented for future support? |
| Value | What service improvement results? |

---

# 6. Incident Management

A disciplined incident lifecycle is:

**Detect → Log → Classify → Prioritize → Diagnose → Restore → Validate → Communicate → Close**

### Incident classification should consider
- Business impact
- Number of users affected
- Service criticality
- Data impact
- Security implications
- Regulatory implications
- Availability impact
- Workaround availability

Incident management focuses first on **restoring service safely**.

---

# 7. Root-Cause & Problem Management

Repeated incidents are signals.

Use:

**Symptom → Evidence → Pattern → Root Cause → Corrective Action → Preventive Action → Verification**

Ask:

- Has this happened before?
- What common conditions exist?
- What changed before the issue?
- Is there a systemic dependency?
- Is the workaround masking the real problem?
- What permanent corrective action is required?

> **If the same incident keeps returning, the problem is not truly resolved.**

---

# 8. Service Request vs Incident vs Problem vs Change

| Type | Primary question |
|---|---|
| **Incident** | What service disruption or degradation must be restored? |
| **Service Request** | What standard service does the user need? |
| **Problem** | What underlying cause must be addressed to prevent recurrence? |
| **Change** | What controlled modification is required to the environment? |

Correct classification improves routing, prioritization, reporting and governance.

---

# 9. Proactive Monitoring

Monitor before users report problems where feasible.

### Technical signals
- Availability
- Response time
- Error rates
- Integration failures
- Job failures
- Capacity
- Queue/backlog
- Resource utilization

### Business signals
- Transaction completion
- Processing delays
- Failed business events
- User-impact indicators
- SLA performance

The goal is not simply more alerts.

**The goal is earlier understanding and action.**

---

# 10. SLA & Service Management

Service commitments should be measurable.

Track:

- Response time
- Resolution time
- Availability
- SLA breaches
- Backlog
- Reopen rate
- Recurrence rate
- First-contact resolution where applicable
- User/business impact
- Change success rate

Use trends to identify systemic problems rather than treating each ticket as an isolated event.

---

# 11. Knowledge Management

Every significant resolution should increase organizational knowledge.

Capture:

- Symptoms
- Context
- Diagnosis
- Root cause
- Resolution
- Workaround
- Verification
- Preventive action
- Related incidents
- Related changes
- Monitoring recommendation

The objective is:

**Solve once → Document → Reuse → Prevent recurrence**

---

# 12. Change Management

AMS changes should be controlled.

A meaningful change should identify:

- Business reason
- Scope
- Risk
- Dependencies
- Implementation plan
- Test evidence
- Backout plan
- Communication
- Approval
- Deployment window
- Validation
- Post-change monitoring

> **Never let urgency become an excuse for uncontrolled change.**

---

# 13. Continuous Improvement Framework

Use the loop:

**Measure → Analyze → Improve → Implement → Observe → Repeat**

Look for:

- Recurring incidents
- Manual effort
- Performance bottlenecks
- Poor user experience
- Excessive alerts
- Knowledge gaps
- Support-process friction
- Automation opportunities
- Unnecessary customizations
- Weak monitoring

---

# 14. AMS Troubleshooting Framework

When an incident occurs:

1. Confirm the reported symptom.
2. Establish business impact.
3. Identify affected users/processes.
4. Check recent changes.
5. Review monitoring and logs.
6. Trace integrations and dependencies.
7. Check data conditions.
8. Reproduce where safe.
9. Isolate the likely cause.
10. Restore service using the safest appropriate action.
11. Validate business recovery.
12. Document the resolution.
13. Determine whether problem management is required.
14. Identify preventive action.

**Evidence first. Restore safely. Learn afterward.**

---

# 15. AMS Quality Model

Evaluate service maturity across:

### Reliability
Does the service operate consistently?

### Responsiveness
Are issues detected and addressed promptly?

### Recoverability
Can service be restored safely?

### Preventability
Are recurring issues being eliminated?

### Maintainability
Can support teams understand and change the system safely?

### Observability
Can teams see what is happening?

### User Experience
Does the service meet user expectations?

### Business Value
Does support protect and improve business outcomes?

---

# 16. 11 GICS Sector Lens

| Sector | AMS consideration |
|---|---|
| Energy | Operational continuity, safety, assets and field/service dependencies. |
| Materials | Production continuity, operational systems and supply dependencies. |
| Industrials | Manufacturing, maintenance, asset and supply-chain availability. |
| Consumer Discretionary | Customer experience, commerce and channel availability. |
| Consumer Staples | High-volume transaction continuity and operational reliability. |
| Health Care | Service continuity, sensitive data, privacy and safety implications. |
| Financials | Transaction integrity, controls, auditability and regulatory obligations. |
| Information Technology | Platform reliability, integrations, security and rapid technology change. |
| Communication Services | High-scale service availability and customer-impact management. |
| Utilities | Reliability, customer service, operational continuity and regulatory obligations. |
| Real Estate | Property, lease, financial and stakeholder service continuity. |

Support must be **context-aware**, especially where downtime or data issues have significant consequences.

---

# 17. Typical AMS Activities

- Incident management
- Service-request handling
- Problem management
- Root-cause analysis
- Application monitoring
- SLA tracking
- Change management
- Release support
- Knowledge management
- Runbook development
- Recurring-issue analysis
- Performance optimization
- Automation analysis
- User communication
- Service reviews
- Continuous-improvement initiatives

---

# 18. Evidence Portfolio

A learner should progressively build:

1. Service definition
2. Application support model
3. Incident classification framework
4. Incident case analysis
5. Root-cause analysis
6. Problem record
7. Monitoring design
8. SLA/service dashboard
9. Change request
10. Change implementation plan
11. Backout plan
12. Knowledge article
13. Support runbook
14. Recurring-incident analysis
15. Continuous-improvement backlog
16. Automation opportunity assessment
17. Sector-specific service scenario
18. Service review / retrospective

The portfolio demonstrates **long-term system ownership**, not merely ticket handling.

---

# 19. AMS Rule Book — Operationalized

### Do
- Own live systems as long-term responsibilities.
- Resolve root causes.
- Monitor proactively.
- Improve continuously.
- Handle tickets with discipline.
- Communicate clearly during issues.
- Tune support to sector needs.
- Document resolutions.
- Reuse knowledge.
- Treat AMS as strategic stewardship.

### Don't
- Treat support as a temporary visit.
- Patch symptoms repeatedly.
- Wait for users to discover every problem.
- Assume stable means optimized.
- Close tickets without true resolution.
- Ignore recurring issues.
- Apply identical service expectations everywhere.
- Solve problems without documenting them.
- Leave users without meaningful updates.
- Treat AMS as low-value maintenance.

---

# 20. Learning Journey

### KNOW
Understand the live service, users, business processes and dependencies.

### DESIGN
Design support, monitoring, change and improvement mechanisms.

### DELIVER
Restore services, implement controlled changes and maintain continuity.

### SOLVE
Find root causes and prevent recurrence.

### INFLUENCE
Coordinate stakeholders and communicate operational decisions.

### TRANSFORM
Continuously improve service quality and evolve the support model.

---

# 21. Connection to the 20-Lab Ecosystem

- **Discover** establishes product and ecosystem understanding.
- **Flow** establishes the business processes being supported.
- **Design** establishes intended architecture.
- **Run** develops daily operational awareness.
- **Build** realizes the solution.
- **Move** manages migration into the target landscape.
- **Connect** establishes system connectivity.
- **Validate** establishes quality before release.
- **Support** sustains the live system.
- **Prove** validates professional capability.
- **Scale** develops career capability.
- **Influence** applies operational insight to advisory and presales.
- **Lead** governs service delivery.
- **Prototype** explores improved service/product concepts.
- **Evolve** identifies future technology opportunities.
- **Share** communicates operational knowledge.
- **Document** preserves institutional support knowledge.
- **Engage** connects experts for complex issues.
- **Scan** provides sector context.
- **Innovate** explores future service-management models.

AMS is the **long-term stewardship layer that keeps enterprise value alive after go-live**.

---

# 22. Success Criteria

A learner demonstrates AMS capability when they can:

- Explain the business criticality of a live application.
- Classify incidents, requests, problems and changes appropriately.
- Diagnose incidents systematically.
- Resolve issues safely and validate service restoration.
- Perform root-cause analysis.
- Identify recurring problems.
- Design proactive monitoring.
- Understand and track service-level commitments.
- Execute controlled changes.
- Create useful support knowledge.
- Identify continuous-improvement opportunities.
- Recognize automation and AI opportunities responsibly.
- Adapt support to sector context.
- Communicate effectively during service disruption.
- Demonstrate long-term system ownership.

---

# 23. Mastery Statement

> **“I can own a live enterprise application through disciplined incident, problem, change and service management — restoring service safely, preventing recurrence and continuously improving business value.”**

---

## AMS Identity

**SUPPORT is not about closing tickets.**

It is about **sustaining value**.

The AMS professional connects:

**Live Service → Observe → Incident → Diagnosis → Resolution → Prevention → Optimization → Continuous Value**

> **Application Management Services Lab — Own what you build. Resolve the root. Monitor proactively. Keep the value alive.**
