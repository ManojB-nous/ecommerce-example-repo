---
template_id: TPL-BRD
artifact_type: brd
version: 2.0.0
output_format: docx
policies: all            # policies.md is always applied in full
nomenclature: [NOM-GEN-*, NOM-DOC-*, NOM-ID-*, NOM-BRD-*]
---
# Business Requirements Document – {{project_name}}

## Document Control
| Version | Date | Author | Reviewer | Status |
|---------|------|--------|----------|--------|
| {{version}} | {{date}} | Astra (draft) | {{reviewer}} | Draft |

## 1. Executive Summary
<!-- astra:section id=exec_summary
query: "business problem, objectives, expected benefits, success metrics"
prefer: project-data/requirements, project-data/meeting-notes -->

## 2. Business Objectives & Success Metrics
<!-- astra:section id=objectives
query: "goals KPIs targets success metrics" -->

## 3. Stakeholders (RACI)
<!-- astra:section id=stakeholders
query: "stakeholders owners roles sponsor attendees" -->
| Name / Role | Responsibility | R | A | C | I |
|-------------|----------------|---|---|---|---|

## 4. Scope
<!-- astra:section id=scope
query: "in scope out of scope phase 1 MVP excluded" -->
### 4.1 In Scope
### 4.2 Out of Scope

## 5. Current State (As-Is)
<!-- astra:section id=as_is
query: "current process legacy system pain points manual" -->

## 6. Business Requirements
<!-- astra:section id=requirements
query: "requirements must should shall user needs rules"
prefer: project-data/requirements -->
| ID | Requirement | Priority (MoSCoW) | Acceptance Criteria | Source |
|----|-------------|-------------------|---------------------|--------|

## 7. Business Rules
<!-- astra:section id=business_rules
query: "business rules limits eligibility calculation validation" -->

## 8. Assumptions, Constraints & Dependencies
<!-- astra:section id=assumptions
query: "assumptions constraints dependencies integration third party timeline budget" -->

## 9. Compliance & Security Considerations
<!-- astra:section id=compliance
query: "compliance regulatory security privacy audit" -->

## 10. Open Questions
<!-- astra:section id=open_questions
query: "open questions TBD pending decision action items" -->

## 11. Glossary
<!-- astra:section id=glossary
query: "glossary terms definitions acronyms"
prefer: project-data/glossary.md -->

## 12. Sources
<!-- astra:auto  list of [S#] → path@commit -->
