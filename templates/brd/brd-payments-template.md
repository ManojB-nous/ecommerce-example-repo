---
template_id: TPL-BRD-PAY
artifact_type: brd
variant: payments
version: 1.0.0
output_format: docx
policies: all            # policies.md is always applied in full
nomenclature: [NOM-GEN-*, NOM-DOC-*, NOM-ID-*, NOM-BRD-*]
use_when: the BRD is mainly about payments, refunds or gateway behaviour
---
# Business Requirements Document (Payments) – {{project_name}}

## Document Control
| Version | Date | Author | Reviewer | Status |
|---------|------|--------|----------|--------|
| {{version}} | {{date}} | Astra (draft) | {{reviewer}} | Draft |

## 1. Executive Summary
<!-- astra:section id=exec_summary
query: "payment problem objectives success rate conversion benefits"
prefer: project-data/charter, project-data/requirements -->

## 2. Business Objectives & Success Metrics
<!-- astra:section id=objectives
query: "payment success rate KPI target baseline conversion" -->

## 3. Stakeholders (RACI)
<!-- astra:section id=stakeholders
query: "payments lead finance controller security architect sponsor RACI" -->
| Name / Role | Responsibility | R | A | C | I |
|-------------|----------------|---|---|---|---|

## 4. Scope
<!-- astra:section id=scope
query: "payment methods in scope out of scope BNPL wallets UPI cards COD" -->
### 4.1 In Scope
### 4.2 Out of Scope

## 5. Payment Methods & Journeys
<!-- astra:section id=methods
query: "UPI intent QR saved cards new card wallets COD payment screen retry"
prefer: project-data/ux, project-data/requirements -->

## 6. Gateway, Failover & Resilience
<!-- astra:section id=gateway
query: "primary gateway fallback failover thresholds error rate latency switch back"
prefer: project-data/emails, project-data/architecture -->

## 7. Refunds, Reconciliation & Reporting
<!-- astra:section id=refunds
query: "failed but debited refund batch reconciliation gateway_txn_id attempt_no report finance"
prefer: project-data/meeting-notes, project-data/compliance -->

## 8. Business Requirements
<!-- astra:section id=requirements
query: "payment requirements must should shall rules limits"
prefer: project-data/requirements -->
| ID | Requirement | Priority (MoSCoW) | Acceptance Criteria | Source |
|----|-------------|-------------------|---------------------|--------|

## 9. Business Rules (COD, Coupons, Fees)
<!-- astra:section id=business_rules
query: "COD limit COD fee coupon rules eligibility exclusions" -->

## 10. Compliance & Security Considerations
<!-- astra:section id=compliance
query: "PCI-DSS SAQ A tokenization RBI NPCI consumer protection dark patterns" -->

## 11. Assumptions, Constraints & Dependencies
<!-- astra:section id=assumptions
query: "assumptions dependencies production keys gateway timeline sale freeze" -->

## 12. Open Questions
<!-- astra:section id=open_questions
query: "open questions TBD pending decision COD limit steering" -->

## 13. Sources
<!-- astra:auto  list of [S#] → path@commit -->
