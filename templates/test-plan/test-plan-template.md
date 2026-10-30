---
template_id: TPL-TP
artifact_type: test-plan
version: 1.0.0
output_format: docx
depends_on: [spec]
policies: all            # policies.md is always applied in full
nomenclature: [NOM-GEN-*, NOM-DOC-*, NOM-ID-*, NOM-TST-*, NOM-REL-*, NOM-TPL-*]
---
# Test Plan – {{project_name}}

## Document Control
| Version | Date | Author | Reviewer | Status |
|---------|------|--------|----------|--------|

## 1. Objectives
<!-- astra:section id=objectives
query: "test objectives quality goals KPIs payment success conversion" -->

## 2. Scope
<!-- astra:section id=scope
query: "features in scope out of scope modules to test exclusions" -->
### 2.1 In Scope
### 2.2 Out of Scope

## 3. Test Types & Approach
<!-- astra:section id=approach
query: "functional regression performance security accessibility boundary negative automation" -->

## 4. Test Environments & Data
<!-- astra:section id=environments
query: "environments DEV QA UAT PROD test data gateway test cards feature flag checkout_v2" -->

## 5. Entry & Exit Criteria
<!-- astra:section id=criteria
query: "entry exit criteria defects severity S1 S2 coverage" -->

## 6. Schedule & Milestones
<!-- astra:section id=schedule
query: "design freeze rollout 10% 100% code freeze timeline milestones"
prefer: project-data/charter, project-data/raid -->

## 7. Risks & Mitigations
<!-- astra:section id=risks
query: "risks dependencies issues assumptions mitigation"
prefer: project-data/raid -->
| ID | Risk | Impact | Mitigation | Owner |
|----|------|--------|------------|-------|

## 8. Roles & Responsibilities
<!-- astra:section id=roles
query: "QA lead product owner payments lead roles responsibilities" -->

## 9. Open Questions
<!-- astra:section id=open_questions query: "open questions TBD decision" -->

## 10. Sources
<!-- astra:auto -->
