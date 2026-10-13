# Scenario Category 17 — Stakeholder & Requirement Conflict

## Interview Practice Guide — 20 Scenario-Based Questions, STAR Answers & SME Probes

**Track:** SCALE — School of Career Acceleration  
**Target Role:** Tech Delivery Subject Matter Expert — SAP SuccessFactors Employee Central  
**Question IDs:** SCALE-EC-17-Q01 through SCALE-EC-17-Q20

## Learning outcome

Resolve ambiguous, competing, or changing Employee Central requirements using structured discovery, evidence, decision rights, option analysis, stakeholder communication, and traceable acceptance.

> **Answer integrity:** These are illustrative STAR models, not claims of personal achievement. Replace them with genuine examples and evidence. Where requirements involve product capabilities, security, or local policy, validate the specifics in the target tenant and with accountable specialists.

---

## Q01 — Vague Requirement at Discovery

### Interview Question
A stakeholder says, “Make the transfer process easier,” but cannot explain the required change. How do you structure discovery?

### STAR Model Answer
- **Situation:** The request expresses dissatisfaction but lacks a defined problem, scope, and measurable outcome.
- **Task:** Turn the request into an actionable, testable requirement.
- **Action:** I would ask users to walk through the current process, identify pain points and exceptions, define affected populations and roles, and clarify the desired future state. I would distinguish business outcomes from proposed technical solutions, document assumptions, and agree acceptance criteria and decision owners before design begins.
- **Result:** Stakeholders would have a shared problem statement, scope, and evidence of what success means.

### SAP SuccessFactors Employee Central Example
Map a representative transfer journey, including data, effective date, approvals, permissions, and downstream consumers as applicable.

### SME Probe
What would make you stop discovery from becoming an open-ended workshop with no decision?

---

## Q02 — Conflicting Business and Technical Requirements

### Interview Question
HR wants fewer mandatory fields, while downstream systems require those values. How do you resolve the conflict?

### STAR Model Answer
- **Situation:** A user-experience request conflicts with data requirements of connected processes.
- **Task:** Make the trade-offs explicit and agree a design that protects data integrity without unnecessary friction.
- **Action:** I would identify which fields are truly mandatory for which populations and processes, trace the downstream contracts, and confirm whether defaults, conditional validation, or an alternative data source are supported and appropriate. I would evaluate options with business and integration owners, test valid/invalid cases, and document the decision and exception handling.
- **Result:** The requirement would be reconciled through a governed decision rather than weakening controls without understanding consequences.

### SAP SuccessFactors Employee Central Example
Trace the field from EC entry to the actual target consumers and validate the mandatory/conditional rules in the tenant.

### SME Probe
What evidence would justify making a field optional for one population but mandatory for another?

---

## Q03 — Standard Versus Custom Disagreement

### Interview Question
A stakeholder insists on customization, while the technical team recommends standard Employee Central capabilities. How do you facilitate a decision?

### STAR Model Answer
- **Situation:** Stakeholders disagree based on business preference and technical maintainability concerns.
- **Task:** Create a decision framework that focuses on the business requirement and lifecycle impact.
- **Action:** I would define the mandatory requirement and exceptions, demonstrate standard capability in the target tenant, and document any functional gap. I would compare options on fit, supportability, security, integration, release impact, implementation effort, and total lifecycle cost. I would recommend an option with evidence and ensure the accountable owner makes the decision.
- **Result:** The choice would be traceable to business criteria and documented trade-offs.

### SAP SuccessFactors Employee Central Example
Compare standard configuration and any proposed extension using a controlled scenario; do not assume feature support without verifying it.

### SME Probe
How do you respond if a stakeholder labels a preference as a mandatory requirement?

---

## Q04 — Global Versus Local Requirements

### Interview Question
Global HR wants one standard process, while a country team asks for a different EC process. How do you assess the exception?

### STAR Model Answer
- **Situation:** A local variation may be justified by policy, operations, or preference but its basis is unclear.
- **Task:** Maintain global consistency where appropriate while meeting verified local requirements.
- **Action:** I would document the common global requirement and local delta, seek evidence for mandatory constraints with qualified local owners, and classify the difference as data, process, security, reporting, or integration. I would compare supported options, assess maintainability and downstream impacts, and record the decision owner, exception rationale, tests, and review date.
- **Result:** Any variation would be bounded, justified, and governed rather than becoming an undocumented fork.

### SAP SuccessFactors Employee Central Example
Use representative global/local populations and verify exact tenant configuration before recommending a variation.

### SME Probe
What would you do when the local team cannot evidence a claimed legal constraint?

---

## Q05 — Requirements Change After Sign-Off

### Interview Question
A business sponsor changes an acceptance criterion after the solution has been approved and built. How do you respond?

### STAR Model Answer
- **Situation:** A late requirement change affects delivered configuration, tests, timeline, and potentially connected systems.
- **Task:** Incorporate the change through governance and protect delivery quality.
- **Action:** I would document the new requirement and reason, assess scope/configuration/data/workflow/RBP/integration/testing impacts, estimate effort and risk with owners, and obtain the required decision. I would update the baseline, acceptance criteria, and traceability, then test both the change and regressions.
- **Result:** The change would be controlled and visible rather than introduced informally into the build.

### SAP SuccessFactors Employee Central Example
Assess the effect of a changed transfer approval requirement on EC rules/workflow and downstream interfaces.

### SME Probe
How do you respond if the sponsor says the change is “just one small field” and should not require impact assessment?

---

## Q06 — Unclear Decision Rights

### Interview Question
HR, HRIS, and Security each believe the other team should approve a sensitive access requirement. Delivery is blocked. How do you move forward?

### STAR Model Answer
- **Situation:** Decision authority is not assigned, and teams cannot progress safely.
- **Task:** Clarify accountability without making an unauthorized decision.
- **Action:** I would identify the business outcome, policy owner, data owner, technical approver, security/risk authority, and impacted parties. I would propose a responsibility matrix and decision date, elevate unresolved accountability through governance, and document assumptions and the impact of delay. I would not approve access or accept residual risk outside my authority.
- **Result:** The issue would have a named decision owner and a traceable path to resolution.

### SAP SuccessFactors Employee Central Example
Assign responsibilities for the access model, workflow policy, implementation, and security validation for the actual EC process.

### SME Probe
What should you do if the person with the most technical knowledge does not have the authority to accept the business risk?

---

## Q07 — Requirement Cannot Be Met Exactly

### Interview Question
The requested experience is not supported exactly by the current EC configuration or product scope. How do you handle the gap?

### STAR Model Answer
- **Situation:** The business expects behaviour that may not be available or suitable in the target environment.
- **Task:** Establish the actual gap and propose viable alternatives.
- **Action:** I would verify the requirement and supported product behaviour, identify which parts are essential, and test standard options. I would evaluate process changes, supported configuration, integration options, or a documented workaround as appropriate, comparing risk, maintenance and user impact. I would explain unsupported assumptions clearly and seek an authorized decision.
- **Result:** The organization would choose among verified options rather than build to an unconfirmed promise.

### SAP SuccessFactors Employee Central Example
Validate the exact requirement in the target tenant and current product documentation before proposing implementation commitments.

### SME Probe
How do you prevent a workaround from being mistaken for a fully supported standard capability?

---

## Q08 — Acceptance Criteria Are Subjective

### Interview Question
A stakeholder says the solution is “not user-friendly” but cannot specify why. UAT sign-off is blocked. What do you do?

### STAR Model Answer
- **Situation:** Acceptance feedback is valid as a concern but too subjective to resolve consistently.
- **Task:** Translate the feedback into observable usability or process criteria.
- **Action:** I would observe representative users performing key tasks, identify points of confusion or rework, and ask what outcome they expected. I would convert findings into specific criteria such as steps, clarity, error recovery, time, or task completion, validate them with the stakeholder, and run a focused test with agreed evidence.
- **Result:** The concern would become actionable and sign-off could be based on observable behaviour.

### SAP SuccessFactors Employee Central Example
Observe a transfer/change task with representative users and document expected versus actual user actions and results.

### SME Probe
How do you distinguish a genuine usability defect from resistance to a newly standardized process?

---

## Q09 — Requirement Conflicts with Data Governance

### Interview Question
A business user wants to store a new value in an existing field because it is convenient, but the field has a defined meaning and downstream use. How do you respond?

### STAR Model Answer
- **Situation:** A short-term workaround would overload an existing data element and undermine its meaning.
- **Task:** Preserve data semantics while meeting the real business need.
- **Action:** I would clarify what information is actually required, identify the existing field definition and consumers, and explain the reporting/integration risk of repurposing it. I would assess supported data-model alternatives and maintenance implications, then agree a governed design with the data owner.
- **Result:** The solution would retain a trustworthy data model and avoid hidden semantic conflicts.

### SAP SuccessFactors Employee Central Example
Trace the existing field's purpose through EC, reports, and integrations before recommending a new representation.

### SME Probe
What downstream defects can arise when one field contains values with two different meanings?

---

## Q10 — Scope Creep During Delivery

### Interview Question
During implementation, stakeholders repeatedly add new scenarios without changing timeline or resources. How do you manage scope?

### STAR Model Answer
- **Situation:** New asks accumulate and the team risks losing focus on the agreed outcome.
- **Task:** Preserve delivery commitments while ensuring important requirements are evaluated fairly.
- **Action:** I would log each request, distinguish defects from scope changes and enhancements, assess value/risk/dependencies/effort, and present options such as trade-off, phased release, or schedule/resource adjustment. I would get the authorized decision and update the backlog and acceptance baseline.
- **Result:** Priorities and delivery consequences would remain visible, and the team would avoid ungoverned additions.

### SAP SuccessFactors Employee Central Example
Classify a new transfer variant as a defect, policy clarification, enhancement, or new scope using the approved requirement baseline.

### SME Probe
How do you decide whether a newly discovered case is a defect or a legitimate new requirement?

---

## Q11 — Stakeholder Pushes for Production Shortcut

### Interview Question
A senior leader asks for a quick configuration change in production to satisfy an urgent request, bypassing testing and change control. What is your response?

### STAR Model Answer
- **Situation:** Urgency creates pressure to bypass controls around a potentially impactful change.
- **Task:** Protect production and the business while enabling an authorized urgent response.
- **Action:** I would assess impact and urgency, identify a safe containment/workaround, explain risks and minimum necessary validation, and use the approved emergency change process if warranted. I would seek authorized approval, test the affected and adjacent paths, document the change, and validate outcomes after deployment.
- **Result:** The business would have a governed response rather than an undocumented production modification.

### SAP SuccessFactors Employee Central Example
Use the actual release and emergency change process for the relevant EC configuration.

### SME Probe
What distinguishes an emergency change from an unauthorized change justified after the fact?

---

## Q12 — Evidence-Based Requirements Prioritization

### Interview Question
There are more EC requirements than the team can deliver in the current release. How do you prioritize?

### STAR Model Answer
- **Situation:** Multiple requirements compete for limited delivery capacity.
- **Task:** Recommend an order that maximizes business value and controls material risk.
- **Action:** I would assess business outcome, mandatory policy/compliance constraints, employee impact, operational risk, dependencies, effort, reversibility, and timing. I would distinguish release blockers from valuable enhancements, document assumptions and scoring rationale, and present options to the authorized decision owner.
- **Result:** Priorities would be transparent and linked to business outcomes and risk.

### SAP SuccessFactors Employee Central Example
Prioritize requirements affecting data integrity, access controls, critical integrations, and user process based on evidenced business impact.

### SME Probe
How do you prevent the loudest stakeholder from dominating prioritization?

---

## Q13 — Business and Technical Teams Disagree on Root Cause

### Interview Question
HR says the EC solution is wrong, while the technical team says the requirement was misunderstood. How do you resolve the dispute?

### STAR Model Answer
- **Situation:** Competing explanations prevent the team from fixing the actual problem.
- **Task:** Establish the agreed expected behaviour and identify the failed requirement/configuration boundary.
- **Action:** I would retrieve the approved requirement and acceptance criteria, reproduce the scenario, compare expected and actual outputs, and inspect the design and test evidence. I would classify the finding as requirement ambiguity, design defect, implementation defect, data issue, or environment behaviour based on evidence. I would assign remediation and update documentation where the baseline itself was incomplete.
- **Result:** The dispute would move from opinion to an evidence-backed decision and correction plan.

### SAP SuccessFactors Employee Central Example
Use the approved EC test case and configuration/design artifacts to trace the expected and actual transaction outcomes.

### SME Probe
What if the original requirement was ambiguous and both teams made reasonable but incompatible assumptions?

---

## Q14 — Stakeholder Rejects Risk Explanation

### Interview Question
You document an architectural risk, but leadership insists on proceeding and argues the risk is theoretical. How do you respond?

### STAR Model Answer
- **Situation:** Decision-makers discount a risk because impact or likelihood is not fully quantified.
- **Task:** Clearly distinguish evidence, uncertainty, recommendation, and decision authority.
- **Action:** I would explain the failure mode, assumptions, dependencies, evidence available, plausible business impact, and confidence level. I would identify what test or data could reduce uncertainty, propose mitigations and residual risk options, and record the accountable decision. I would not state an unproven root cause as fact or conceal a material risk.
- **Result:** Leadership would make an informed decision with residual risk visible and owned.

### SAP SuccessFactors Employee Central Example
Present a risk record for the real EC dependency, including evidence, uncertainty, mitigation, and decision owner.

### SME Probe
How do you distinguish a recommendation based on incomplete evidence from a formal risk warning?

---

## Q15 — Global Template Versus User Experience

### Interview Question
A global HR template creates extra effort for a specific user population, but a local variation would add maintenance. How do you decide?

### STAR Model Answer
- **Situation:** Consistency and local usability are in tension.
- **Task:** Evaluate whether the variation provides enough business value to justify its lifecycle cost.
- **Action:** I would observe the affected workflow, quantify friction where possible, confirm mandatory policy needs, and compare template, training/process, configuration, and supported extension options. I would assess security, integration, supportability, and regression impacts, then record the decision and success measures.
- **Result:** The choice would be evidence-based and reviewed after rollout rather than driven by a universal preference for either standardization or customization.

### SAP SuccessFactors Employee Central Example
Pilot the process with representative global/local users and validate supported configuration options in the tenant.

### SME Probe
What measures would show that the local variation justifies its additional complexity?

---

## Q16 — Requirements Traceability and Change Control

### Interview Question
A defect is found in UAT, but the team cannot identify which requirement or design decision the configuration was meant to satisfy. What do you do?

### STAR Model Answer
- **Situation:** Traceability gaps make it hard to assess intended behaviour and decide what to fix.
- **Task:** Reconstruct the rationale and restore the chain from requirement through design, configuration, and tests.
- **Action:** I would gather approved business process, tickets, decisions, configuration history, and test artifacts, and interview relevant owners. I would avoid inventing missing rationale, mark gaps explicitly, and obtain business confirmation of the intended behaviour. I would update traceability and change governance before implementing the correction.
- **Result:** The team would have a clearer basis for the fix and a plan to prevent similar traceability gaps.

### SAP SuccessFactors Employee Central Example
Link the relevant EC requirement to rule/workflow/RBP/data design, configuration items, and UAT scenarios.

### SME Probe
What do you do if no accountable stakeholder can confirm the intended business behaviour?

---

## Q17 — Negotiate Acceptance and Residual Risk

### Interview Question
UAT reveals a low-frequency edge-case defect. The sponsor wants to accept it, but support believes the workaround is unclear. How do you facilitate the decision?

### STAR Model Answer
- **Situation:** A defect may be acceptable to business under certain conditions, but support and operational risks remain.
- **Task:** Ensure acceptance is informed, authorized, and operationally manageable.
- **Action:** I would define the affected population, frequency/evidence, business impact, workaround, detection, recoverability, and likely recurrence. I would seek input from business, support, security/integration owners as relevant, define acceptance/expiry criteria, and record the authorized risk decision. I would not treat a verbal acceptance as sufficient for a material production risk.
- **Result:** The decision would have explicit ownership, mitigation, and a route to reassessment.

### SAP SuccessFactors Employee Central Example
Document a UAT defect with affected EC transaction, workaround steps, control implications, and operational owner.

### SME Probe
What makes a workaround unacceptable even when the business agrees to accept the defect?

---

## Q18 — Facilitate an Architecture Decision Workshop

### Interview Question
A complex EC design decision requires agreement across HR, integration, security, data, and operations. How do you run the workshop to reach a decision?

### STAR Model Answer
- **Situation:** Each discipline sees a different part of the problem and discussion risks becoming circular.
- **Task:** Produce an actionable decision with recorded rationale and ownership.
- **Action:** I would circulate the problem statement, requirements, options, decision criteria, known evidence, and open questions ahead of the session. I would confirm decision authority, hear constraints from each discipline, compare options and trade-offs, separate facts from assumptions, and close with decisions, owners, actions, and due dates. Unresolved items would be escalated rather than disguised as consensus.
- **Result:** The group would have a traceable decision or a clear path to the missing evidence/authority.

### SAP SuccessFactors Employee Central Example
Use an option matrix covering data model, workflow, access, integration, testing, and support for the EC design at hand.

### SME Probe
How do you prevent a workshop from ending with agreement on discussion but no accountable decision?

---

## Q19 — Communicate Design Trade-Offs to Non-Technical Stakeholders

### Interview Question
A business leader cannot follow technical architecture details but must choose between two EC designs. How do you explain the decision?

### STAR Model Answer
- **Situation:** The decision is important, but the current explanation is too technical for the accountable business owner.
- **Task:** Present choices in terms of business outcomes, risks, cost, and operational consequences.
- **Action:** I would summarize the required outcome, show two or three viable options, and compare user impact, control, lifecycle cost, integration dependency, maintainability, and residual risk. I would use a simple process/model diagram and explain the assumptions and evidence required. I would ask the stakeholder to restate the trade-off before recording the decision.
- **Result:** The decision-maker could make an informed choice without needing to understand every technical detail.

### SAP SuccessFactors Employee Central Example
Present standard configuration, process adjustment, and any justified supported extension in business language with explicit trade-offs.

### SME Probe
How do you explain a risk that cannot yet be assigned a reliable probability?

---

## Q20 — Defend a Difficult Requirement Decision

### Interview Question
You must defend a contested EC requirement/solution decision before a panel of business, technical, security, and operations stakeholders. What is your approach?

### STAR Model Answer
- **Situation:** The solution involves competing priorities and consequences across multiple disciplines.
- **Task:** Show that the decision satisfies the requirement, considers viable alternatives, and leaves risks explicitly managed.
- **Action:** I would present the validated problem statement, acceptance criteria, relevant EC capability/tenant constraints, options considered, decision criteria, impact assessment, security/integration/testing plan, and evidence. I would distinguish known facts from assumptions, identify rejected alternatives and why, and name the residual-risk owner and success metrics.
- **Result:** The panel could assess the decision on evidence, business value, supportability, and accountable governance.

### SAP SuccessFactors Employee Central Example
Use an actual or controlled EC design case and trace the decision from requirement through data/workflow/RBP/integration and acceptance evidence.

### SME Probe
What missing evidence would make you recommend deferring the decision rather than forcing consensus?

---

# Rapid-Fire SME Probe Bank

1. How do you convert a vague request to a testable requirement?
2. How do you resolve mandatory-field conflicts?
3. What evidence separates standard from custom fit?
4. How do you govern local variation?
5. How do you control late requirement changes?
6. Who owns the final decision and risk?
7. How do you verify a product capability claim?
8. How do you define subjective acceptance?
9. Why preserve data semantics?
10. How do you control scope creep?
11. How do you respond to a production shortcut request?
12. How should competing requirements be prioritized?
13. How do you resolve competing root-cause hypotheses?
14. How do you communicate uncertain risk?
15. When does an accepted defect still require mitigation?

# STAR Answer Quality Rubric

Score each dimension from 0 to 4 as a coaching aid, not a validated hiring assessment.

| Dimension | Strong evidence |
|---|---|
| Situation | Defines the conflict, affected process, and business context. |
| Task / ownership | Clarifies role, authority, and stakeholder responsibilities. |
| Action / reasoning | Uses discovery, option analysis, evidence, and change governance. |
| EC relevance | Connects the decision to relevant data, workflow, RBP, integration, and testing concerns. |
| Result / evidence | Records a decision, acceptance criteria, or verification plan without fabricated metrics. |
| SME insight | Explains trade-offs, risk, alternatives, and escalation. |
| Integrity | Labels assumptions and does not claim authority or product behaviour without evidence. |

# Common Stakeholder/Requirement Anti-Patterns

- Jumping into configuration before clarifying the problem.
- Treating stakeholder preference as a mandatory requirement.
- Allowing scope changes without impact assessment.
- Making a decision outside assigned authority.
- Forcing agreement when key evidence is missing.
- Claiming a product capability without verification.
- Treating a risk warning as a proven root cause.
- Recording acceptance without mitigation, owner, or exit criteria.

# Master Framework — Conflict to Traceable Decision

**Clarify outcome → Establish facts and constraints → Identify decision owner → Generate viable options → Compare impacts and risks → Validate assumptions → Decide/govern → Update traceability → Test acceptance → Measure and revisit.**

# Success Criteria

The candidate can answer all 20 scenarios in STAR format, convert ambiguity into acceptance criteria, facilitate trade-off decisions, manage scope and residual risk, and communicate evidence accurately to both technical and non-technical stakeholders.

## Source and Verification Guidance

This is a coaching blueprint. Verify product-specific capabilities in the target EC tenant and current official SAP documentation. For security, country policy, and legal constraints, involve authorized specialists. Record assumptions, decision authority, and review status before using a recommendation in a live implementation.
