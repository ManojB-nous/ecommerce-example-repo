---
template_id: TPL-CR
artifact_type: change-request
version: 1.0.0
output_format: docx
policies: all            # policies.md is always applied in full
nomenclature: [NOM-GEN-*, NOM-DOC-*, NOM-ID-*, NOM-REL-*, NOM-CR-*]
---
# Change Request Impact Assessment – {{cr_id}}

## Document Control
| Version | Date | Author | Reviewer | Status |
|---------|------|--------|----------|--------|

## 1. Request Summary
<!-- astra:section id=summary
query: "change request raised by requested feature reason"
prefer: project-data/change-requests -->
| Field | Value |
|-------|-------|
| CR ID | |
| Raised by | |
| Raised on | |
| Status | Proposed |

## 2. Scope Impact
<!-- astra:section id=scope_impact
query: "scope in scope out of scope SOW exclusions epic"
prefer: project-data/contracts, project-data/requirements -->

## 3. Effort and Approval
<!-- astra:section id=effort
query: "person-days estimate approval CDO threshold change control"
prefer: project-data/contracts -->

## 4. Timeline and Release Impact
<!-- astra:section id=timeline
query: "design freeze rollout code freeze spring sale timeline"
prefer: project-data/charter, project-data/raid -->

## 5. Risk, Compliance and Test Impact
<!-- astra:section id=risk
query: "risks compliance PCI consent testing regression impact"
prefer: project-data/compliance, project-data/raid -->

## 6. Recommendation
<!-- astra:section id=recommendation
query: "recommendation defer approve reject backlog" -->
Label every line "Recommendation". The decision belongs to the named approver (POL-HRV-002).

## 7. Open Questions
<!-- astra:section id=open_questions query: "open questions TBD" -->

## 8. Sources
<!-- astra:auto -->
