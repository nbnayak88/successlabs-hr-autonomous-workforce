# AWF1 — 440 Scenario Metadata Manifest

## Applied SAP SuccessFactors Employee Central

**Status:** Baseline machine-readable manifest  
**Coverage:** 22 themes × 20 scenarios = 440 records  
**Primary product:** SAP SuccessFactors Employee Central

### Transformation spine

**Employee → HR Foundation → Person & Employment Data → Organization → Job & Position → HR Process → Experience → Integration → Insight → Automation → Intelligent HR Outcome**

### Boundary

AWF1 owns Employee Central and the digital HR foundation.

Other HR academies remain separate:
- ATA2a — Recruiting / SmartRecruiters
- ATA2b — Onboarding / SAP SuccessFactors Onboarding
- AGL4 — Succession & Development
- APH3 — Performance & Goals
- ARP5 — Compensation & Variable Pay
- ALM6 — Learning
- APE7 — Employee Central Payroll
- AWT8 — Time Tracking
- AWI9 — Workforce Analytics & Planning
- ADX0 — Employee Experience Suite
- AAI1-HR — Business AI / Joule / AI Agents for HR
- AIG2-HR — Integration Suite for HR

### Progression

**KNOW → DESIGN → DELIVER → SOLVE → INFLUENCE → TRANSFORM**

### Stable ID

**HR-AWF1-B[THEME]-Q[01–20]**

### Record schema

| Field | Meaning |
|---|---|
| scenario_id | Stable scenario ID |
| academy | AWF1 |
| stream | Applied SAP SuccessFactors Employee Central |
| theme_id | 01–22 |
| theme | Canonical interview theme |
| progression | KNOW/DESIGN/DELIVER/SOLVE/INFLUENCE/TRANSFORM |
| source_path | Owning STAR pack |
| capability_tags | Initial capability mapping |
| business_outcome_tags | Initial value mapping |
| difficulty_band | Theme-level initial band |
| question_index | 01–20 |
| difficulty | Scenario-level validation pending |
| probe_type | Scenario-level validation pending |
| architecture_signals | Scenario-level validation pending |
| metadata_status | BASELINE |

### Canonical 22-theme pool

1. Domain Foundation
2. Product / Technology Knowledge
3. Process & Business Context
4. Data & Information Model
5. Requirement Analysis
6. Solution Design
7. Configuration / Development
8. Integration & Architecture
9. Testing & Quality Assurance
10. Deployment & Release
11. Migration & Cutover
12. Operations & Support
13. Troubleshooting & Root Cause Analysis
14. Scenario-Based Problem Solving
15. Risk, Controls & Security
16. Performance & Optimization
17. Stakeholder Management
18. Communication & Consulting
19. Presales / Leadership / Decision Making
20. Transformation & Roadmap
21. Innovation & Emerging Technology
22. Enterprise Architecture & Business Value

Each theme owns exactly 20 scenario IDs.

### Baseline metadata policy

The manifest establishes the **440-record canonical scenario pool**, stable taxonomy and source ownership.

Scenario-level difficulty, SME probe type and architecture signals must be validated against the actual STAR packs. They are not fabricated.

### Validation gate

1. Extract exact scenario title.
2. Validate difficulty.
3. Classify SME probe.
4. Tag architecture signals.
5. Tag measurable business outcomes.
6. Check cross-theme duplication.
7. Mark **VALIDATED**.

**Integrity rule: evidence before metadata.**
