# Scenario Category 17 — Stakeholder & Requirement Conflict

## Target Role
**Tech Delivery Subject Matter Expert — SAP SuccessFactors Employee Central**

## Objective

Prepare for SME-level interview scenarios where stakeholders disagree on requirements, business teams request exceptions, global and local HR teams have competing priorities, or technical constraints conflict with desired business outcomes.

> **Interview principle:** An SME should not simply accept the loudest stakeholder's request or reject requirements because they are difficult to configure. The objective is to establish the business outcome, clarify constraints, evaluate options, explain trade-offs, and guide stakeholders toward a governed solution.

---

# 1. Two Stakeholders Want Different EC Processes

### Scenario Question
Global HR wants one standardized Employee Central process, while a regional HR team insists on a country-specific process. How would you handle the conflict?

### STAR Answer

**Situation**  
Global HR wanted process consistency, while the regional team believed local requirements required variation.

**Task**  
I needed to determine whether the regional requirement was genuinely necessary and design a solution that balanced standardization with legitimate local needs.

**Action**
1. Facilitated a requirement clarification session.
2. Separated business outcomes from requested system behavior.
3. Identified statutory, policy, operational, and preference-based requirements.
4. Classified requirements as global, local, mandatory, or optional.
5. Assessed whether standard EC functionality could support the variation.
6. Evaluated configuration and maintenance impact.
7. Presented options with trade-offs.
8. Recommended a controlled global design with isolated local variation where justified.
9. Obtained stakeholder agreement.
10. Documented the design decision and governance ownership.

**Result**  
The disagreement was converted into an evidence-based design decision rather than a configuration debate.

### Follow-up Questions
- What if the regional stakeholder refuses the global design?
- How do you distinguish a statutory requirement from a preference?
- When would you recommend customization?
- Who makes the final decision?

---

# 2. Business Requests a Custom Solution

### Scenario Question
A senior business stakeholder asks for a custom EC solution because they believe standard functionality is insufficient. What would you do?

### STAR Answer

**Situation**  
The stakeholder had a strong preference for a custom design based on the current business process.

**Task**  
I needed to understand the actual business need before accepting the requested technical solution.

**Action**
1. Asked the stakeholder to describe the desired business outcome.
2. Captured current-state pain points.
3. Demonstrated relevant standard capabilities.
4. Evaluated configuration options.
5. Considered process simplification.
6. Assessed integration, security, upgrade, and support implications.
7. Compared standard, configurable, and custom options.
8. Presented trade-offs transparently.
9. Agreed on the option that best met the business objective within governance constraints.
10. Documented the decision and rationale.

**Result**  
The discussion shifted from "build what I asked for" to "solve the business problem sustainably."

### Follow-up Questions
- What if the stakeholder has executive sponsorship?
- What if standard functionality requires business-process change?
- How do you communicate technical debt?

---

# 3. Conflicting Requirements From HR and Payroll

### Scenario Question
HR wants an Employee Central process optimized for employee experience, while Payroll requires additional controls that make the process more complex. How would you resolve the conflict?

### STAR Answer

**Situation**  
HR and Payroll had valid but competing objectives.

**Task**  
I needed to design an end-to-end process that protected payroll correctness without unnecessarily degrading employee experience.

**Action**
1. Mapped the complete employee lifecycle process.
2. Identified the non-negotiable payroll controls.
3. Identified employee-experience pain points.
4. Separated mandatory controls from process preferences.
5. Explored automation and validation options.
6. Assessed workflow and timing.
7. Evaluated alternative designs.
8. Used evidence from testing to demonstrate impact.
9. Facilitated agreement on the target process.
10. Documented ownership and control points.

**Result**  
Both teams understood the dependencies and agreed on a process that balanced payroll integrity with usable employee experience.

### Follow-up Questions
- What if Payroll refuses any change?
- What if the business wants to remove a control?
- How would you prove the risk?

---

# 4. Stakeholder Changes Requirements During Build

### Scenario Question
A business stakeholder changes a major requirement after configuration has already started. How would you respond?

### STAR Answer

**Situation**  
A significant requirement changed during implementation, potentially affecting configuration and testing.

**Task**  
I needed to determine the impact without creating uncontrolled scope or delivery risk.

**Action**
1. Clarified the new business requirement.
2. Compared it with the approved baseline.
3. Performed impact analysis across EC data model, rules, workflow, RBP, integration, migration, and testing.
4. Estimated effort and timeline impact.
5. Identified affected deliverables.
6. Presented options and consequences.
7. Routed the change through the agreed change-control process.
8. Updated design documentation after approval.
9. Replanned impacted testing.
10. Communicated the decision to all affected teams.

**Result**  
The requirement was accommodated through controlled change management rather than silent scope expansion.

### Follow-up Questions
- What if the change is legally mandatory?
- What if the deadline cannot move?
- What if the stakeholder says the change is "small"?

---

# 5. Stakeholder Disagrees With Your SME Recommendation

### Scenario Question
You recommend using standard Employee Central functionality, but the stakeholder strongly disagrees. How would you handle it?

### STAR Answer

**Situation**  
The stakeholder preferred a different solution from the one I recommended.

**Task**  
My responsibility was to explain the design rationale and ensure the decision was based on business and technical evidence.

**Action**
1. Listened carefully to the stakeholder's concerns.
2. Reconfirmed the business outcome.
3. Demonstrated the standard capability.
4. Explained limitations honestly.
5. Presented alternative options.
6. Compared impact on usability, maintainability, integration, security, and future releases.
7. Asked stakeholders to validate the priorities.
8. Used a prototype or scenario-based demonstration where useful.
9. Escalated only if a decision could not be reached at working level.
10. Recorded the final decision and rationale.

**Result**  
The discussion remained professional and evidence-based, even when the preferred solution differed.

### Follow-up Questions
- How do you disagree without damaging the relationship?
- What if the stakeholder is more senior?
- When should an SME escalate?

---

# 6. Global Template vs Local Business Need

### Scenario Question
A global template team says a local HR process must follow the global design, while the local team says the template does not support its operational reality. What would you do?

### STAR Answer

**Situation**  
Global standardization and local operational requirements were in conflict.

**Task**  
I needed to determine whether the local difference was justified and whether it could be accommodated without fragmenting the global model.

**Action**
1. Conducted structured requirement discovery with both teams.
2. Identified the underlying business outcome.
3. Categorized local requirements.
4. Distinguished statutory obligations from local preferences.
5. Assessed standard EC capabilities.
6. Identified configuration options that preserve the global model.
7. Evaluated the cost of local deviation.
8. Presented options and trade-offs.
9. Established governance for any approved exception.
10. Documented the global/local design boundary.

**Result**  
The organization had a transparent mechanism for managing local variation without uncontrolled divergence.

### Follow-up Questions
- How would you prevent every country from requesting exceptions?
- What belongs in the global template?
- How would you govern approved deviations?

---

# 7. Technical Team and Business Team Disagree

### Scenario Question
The business says a requirement is straightforward, while the technical team says it has significant integration and security implications. How would you mediate?

### STAR Answer

**Situation**  
The teams had different perceptions of the complexity of the requirement.

**Task**  
I needed to create a shared understanding rather than allowing either team to dominate the discussion.

**Action**
1. Restated the requirement in business terms.
2. Mapped the impacted EC objects and processes.
3. Identified integration and security dependencies.
4. Demonstrated where complexity originated.
5. Distinguished essential requirements from optional behavior.
6. Explored simpler alternatives.
7. Quantified delivery and operational implications.
8. Facilitated a decision based on agreed priorities.
9. Updated the solution design.
10. Communicated the decision to all stakeholders.

**Result**  
Both teams understood the actual impact and could make a transparent decision.

### Follow-up Questions
- What if technical constraints are unacceptable to the business?
- How do you explain technical complexity to non-technical stakeholders?
- How do you avoid overengineering?

---

# 8. Executive Wants a Fast Go-Live

### Scenario Question
An executive stakeholder asks the team to accelerate go-live even though critical EC testing is incomplete. What would you do?

### STAR Answer

**Situation**  
Business pressure required an accelerated go-live, but testing had unresolved risks.

**Task**  
I needed to provide a clear risk-based recommendation without unnecessarily blocking the business.

**Action**
1. Identified exactly which testing remained incomplete.
2. Classified open defects by business impact.
3. Distinguished critical controls from lower-risk issues.
4. Assessed affected employee populations.
5. Identified minimum evidence required for production readiness.
6. Presented risk and mitigation options.
7. Proposed a focused validation plan if appropriate.
8. Defined explicit go/no-go criteria.
9. Escalated unresolved acceptance decisions to the appropriate business owner.
10. Documented the decision and residual risk.

**Result**  
The executive received a transparent view of readiness and risk rather than a simple technical yes/no response.

### Follow-up Questions
- What makes a defect go-live blocking?
- Who owns business risk?
- What evidence would you present to leadership?

---

# 9. Requirements Are Ambiguous

### Scenario Question
A stakeholder says, "We need managers to have more flexibility in Employee Central." The requirement is too vague to configure. How would you proceed?

### STAR Answer

**Situation**  
The stakeholder communicated an outcome without defining the required system behavior.

**Task**  
I needed to convert the vague request into a precise, testable requirement.

**Action**
1. Asked what managers should be able to do.
2. Identified affected employee populations.
3. Clarified fields and transactions.
4. Asked for examples of desired and undesired outcomes.
5. Identified security implications.
6. Clarified approval requirements.
7. Identified workflow and business-rule implications.
8. Converted the requirement into acceptance criteria.
9. Validated the interpretation with the stakeholder.
10. Only then moved to solution design.

**Result**  
The ambiguous request became a measurable requirement with clear acceptance criteria.

### Follow-up Questions
- What questions would you ask first?
- How do you identify hidden requirements?
- How do you prevent assumptions from entering configuration?

---

# 10. SME Must Say No to a Requirement

### Scenario Question
Describe how you would handle a requirement that creates unacceptable security, compliance, maintainability, or operational risk.

### STAR Answer

**Situation**  
A requested design would have introduced significant risk into the EC solution.

**Task**  
I needed to challenge the requirement professionally while still helping the stakeholder achieve the underlying business objective.

**Action**
1. Clarified the business outcome.
2. Identified the specific risk.
3. Explained the risk in business terms.
4. Distinguished the requested solution from the underlying requirement.
5. Proposed safer alternatives.
6. Compared the alternatives objectively.
7. Involved security, compliance, architecture, or governance stakeholders where appropriate.
8. Documented the decision and risk acceptance where required.
9. Obtained formal approval for the selected approach.
10. Ensured the final design remained supportable.

**Result**  
The stakeholder received an alternative path to the business outcome without silently accepting unacceptable risk.

### Follow-up Questions
- How do you say no without appearing obstructive?
- When should risk be formally accepted?
- What if the business insists?

---

# Rapid-Fire SME Probes

1. How do you handle conflicting requirements?
2. How do you distinguish a requirement from a solution?
3. How do you challenge a stakeholder professionally?
4. When should an SME recommend standard functionality?
5. When might local variation be justified?
6. How do you identify hidden requirements?
7. How do you manage late requirement changes?
8. How do you communicate technical constraints?
9. How do you handle executive pressure?
10. Who owns business risk?
11. Who makes the final design decision?
12. How do you document architecture/design decisions?
13. How do you manage scope creep?
14. How do you convert ambiguous requirements into acceptance criteria?
15. How can AI help analyze requirements without replacing stakeholder validation?

---

# Master Stakeholder Conflict Framework

Use this sequence:

**OUTCOME → FACTS → CONSTRAINTS → OPTIONS → TRADE-OFFS → DECISION → GOVERNANCE → COMMUNICATION**

### 1. OUTCOME
Ask:
> "What business outcome are we trying to achieve?"

Do not begin with configuration.

### 2. FACTS
Establish:
- Current process
- Current pain point
- User population
- Examples
- Existing configuration
- Data dependencies

### 3. CONSTRAINTS
Identify:
- Statutory requirements
- Policy
- Security
- Integration
- Timeline
- Budget
- Platform capabilities
- Supportability

### 4. OPTIONS
Usually compare:
- Standard functionality
- Configurable solution
- Process change
- Controlled extension/customization

### 5. TRADE-OFFS
Evaluate:
- User experience
- Maintainability
- Integration
- Security
- Release impact
- Data quality
- Delivery effort
- Operational support

### 6. DECISION
Make the decision criteria explicit.

### 7. GOVERNANCE
Define:
- Owner
- Approval
- Change control
- Risk acceptance
- Documentation

### 8. COMMUNICATION
Ensure every affected team understands:
- What was decided
- Why
- What changes
- What remains out of scope

---

# Requirement Classification Framework

| Requirement Type | SME Response |
|---|---|
| Statutory/legal | Validate and accommodate |
| Mandatory company policy | Confirm policy owner and implement |
| Business-critical | Assess solution options |
| Operational preference | Challenge and simplify where appropriate |
| User preference | Evaluate against business value |
| Technical constraint | Explain impact and alternatives |
| Security-sensitive | Involve security/governance |
| Integration-dependent | Perform end-to-end impact analysis |
| Future enhancement | Manage through roadmap/change process |

---

# Standard vs Custom Decision Framework

Before agreeing to customization, ask:

1. Is the requirement genuinely mandatory?
2. Can the business process be simplified?
3. Does standard EC functionality already support the outcome?
4. Can configuration solve it?
5. Does an approved extension pattern exist?
6. What integrations will be affected?
7. What is the security impact?
8. What is the release/upgrade impact?
9. What is the support burden?
10. Is the business willing to own the long-term consequence?

---

# Stakeholder Communication Pattern

A strong SME does not say:

> "That cannot be done."

Instead:

> **"The business outcome is achievable, but the requested approach introduces X risk. I see three options. Option A stays closest to standard capability, Option B changes the process, and Option C introduces additional complexity. Here are the trade-offs. Based on the stated priorities, we can take the decision through the appropriate governance path."**

This demonstrates advisory leadership rather than configuration-only thinking.

---

# Conflict Resolution Matrix

| Conflict | First Question | SME Focus |
|---|---|---|
| Global vs Local | Is the local variation mandatory? | Standardization |
| HR vs Payroll | What controls are non-negotiable? | End-to-end process |
| Business vs Technical | What causes the technical complexity? | Transparency |
| Executive vs Delivery | What risk is being accepted? | Readiness |
| User vs Security | What business outcome is required? | Controlled access |
| Current vs Future | Is the requirement temporary or strategic? | Roadmap |
| Standard vs Custom | Can the outcome be achieved without custom build? | Maintainability |

---

# AI-Assisted Requirement Analysis

AI can accelerate requirement work without becoming the decision-maker.

### Useful Applications
- Summarize stakeholder interviews.
- Identify conflicting statements.
- Extract functional requirements.
- Detect ambiguous requirements.
- Generate clarification questions.
- Map requirements to EC capabilities.
- Identify impacted objects and processes.
- Generate acceptance criteria.
- Suggest test scenarios.
- Compare requirement versions.
- Identify potential integration dependencies.
- Draft decision logs.

### Human Validation

The SME must validate:
- Business intent
- Legal/statutory interpretation
- Security implications
- Data privacy
- Solution feasibility
- Stakeholder acceptance
- Final design decision

A strong interview statement:

> **"I would use AI to accelerate requirement analysis and expose ambiguity or conflict, but the business owner and SME remain accountable for validating intent, feasibility, risk, and the final decision."**

---

# Common Anti-Patterns

Avoid:

- Accepting the most senior stakeholder's request without analysis.
- Treating stakeholder preference as a mandatory requirement.
- Saying "standard functionality" without demonstrating why.
- Saying "customization is impossible" without alternatives.
- Allowing technical teams to make business decisions.
- Allowing business teams to ignore security or integration constraints.
- Escalating every disagreement immediately.
- Hiding delivery risks to protect the timeline.
- Allowing requirements to change without impact analysis.
- Treating documentation as an administrative task.
- Making configuration decisions before clarifying the business outcome.

---

# Strong SME Answer Pattern

For any stakeholder conflict scenario:

1. **Listen and clarify.**
2. **Identify the business outcome.**
3. **Separate requirement from requested solution.**
4. **Identify facts and constraints.**
5. **Assess standard EC capability.**
6. **Identify solution alternatives.**
7. **Explain trade-offs.**
8. **Facilitate the decision.**
9. **Document governance and ownership.**
10. **Communicate the decision and consequences.**

---

# Category Success Criteria

The candidate is ready for this category when they can:

- Resolve global versus local requirements.
- Challenge custom requirements constructively.
- Manage HR versus Payroll priorities.
- Handle late requirement changes.
- Communicate technical constraints to business stakeholders.
- Handle executive pressure without hiding delivery risk.
- Convert ambiguous requests into testable requirements.
- Separate business requirements from proposed solutions.
- Explain standard versus custom trade-offs.
- Facilitate decisions without taking ownership away from the business.
- Use evidence, prototypes, and impact analysis effectively.
- Demonstrate trusted-advisor behavior.
- Use AI to accelerate requirement analysis while retaining human accountability.

---

## Interview Positioning

For a Tech Delivery SME interview, frame stakeholder leadership as:

**Business Outcome → Requirement Clarity → Constraints → Options → Trade-Offs → Decision → Governance → Delivery**

The strongest answers demonstrate that the SME is not merely a configurator. The SME acts as a **trusted technology advisor who converts competing stakeholder expectations into clear, governed, and sustainable Employee Central solutions**.
