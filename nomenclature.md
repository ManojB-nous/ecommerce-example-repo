---
nomenclature_version: 2.0.0
owner: PMO & Quality Office
effective_date: 2026-11-01
---
# Nomenclature & Document Standards

> How we **name, number and structure** delivery artifacts. Astra applies the sections whose `applies_to` matches the artifact being generated.
> Rule IDs: `NOM-<AREA>-<NNN>`.

## 1. General Conventions
<!-- applies_to: all -->
- **NOM-GEN-001** Dates: ISO 8601 `YYYY-MM-DD`. Times: 24-hour with zone, e.g. `14:30 IST`.
- **NOM-GEN-002** Currency: ISO code + amount, e.g. `INR 50,000`, `USD 1,200.00`. Use the source's number grouping.
- **NOM-GEN-003** Use glossary terms from `project-data/glossary.md` exactly; do not create synonyms.
- **NOM-GEN-004** Module codes: use only the codes in *Project Module Codes* at the end of this file.

## 2. Document Control & Versioning
<!-- applies_to: all -->
- **NOM-DOC-001** Every artifact starts with a Document Control table: `Version | Date | Author | Reviewer | Status`.
- **NOM-DOC-002** Versions: `0.x` = draft, `1.0` = first approved, minor bump for edits, major bump for scope change.
- **NOM-DOC-003** Status values only: `Draft`, `In Review`, `Approved`, `Superseded`.
- **NOM-DOC-004** File names: `<PROJECTCODE>_<ARTIFACT>_v<version>.<ext>`, e.g. `LOS_BRD_v0.3.docx`.

## 3. Identifiers
<!-- applies_to: all -->
| Item | Format | Example |
|------|--------|---------|
| Business requirement | `BR-<MOD>-<NNN>` | BR-ELG-001 |
| Functional requirement | `FR-<MOD>-<NNN>` | FR-ELG-004 |
| Non-functional requirement | `NFR-<CAT>-<NNN>` (PERF, AVL, SEC, SCL, ACC) | NFR-PERF-002 |
| User story | `US-<MOD>-<NNN>` | US-PAY-012 |
| Business rule | `RULE-<MOD>-<NNN>` | RULE-DEC-003 |
| API | `API-<MOD>-<NNN>` | API-APP-001 |
| Test case | `TC-<MOD>-<NNN>` | TC-ELG-017 |
| Defect | `DEF-<NNNN>` | DEF-0042 |
| Open question | `OQ-<NNN>` | OQ-007 |
| Assumption / Risk | `ASM-<NNN>` / `RSK-<NNN>` | RSK-004 |

- **NOM-ID-001** IDs are never reused, even after a requirement is deleted (mark it `Withdrawn`).

## 4. Business Requirements Document (BRD)
<!-- applies_to: brd -->
- **NOM-BRD-001** Priority uses MoSCoW: `Must`, `Should`, `Could`, `Won't (this phase)`.
- **NOM-BRD-002** Every BR has at least one testable acceptance criterion.
- **NOM-BRD-003** Separate sections for In Scope, Out of Scope, Assumptions, Constraints, Dependencies, Open Questions.
- **NOM-BRD-004** Stakeholders listed with role and RACI.

## 5. Specifications (Functional / API)
<!-- applies_to: spec, api-spec -->
- **NOM-SPEC-001** Every FR states `Traces to: BR-…`.
- **NOM-SPEC-002** Field validation table columns: `Field | Type | Length | Mandatory | Format / Rule | Error message`.
- **NOM-SPEC-003** APIs documented as: method, path, auth/scopes, request, response, error codes (HTTP + business code `ERR-<MOD>-<NNN>`).
- **NOM-SPEC-004** NFR table covers PERF, AVL, SEC, SCL, ACC (WCAG 2.1 AA for UI).

## 6. User Stories
<!-- applies_to: user-stories -->
- **NOM-US-001** Format: *As a <role>, I want <capability>, so that <benefit>.*
- **NOM-US-002** Acceptance criteria in Given / When / Then.

## 7. Test Cases
<!-- applies_to: testcases -->
- **NOM-TST-001** Each TC states `Traces to: FR-… / BR-…`.
- **NOM-TST-002** Type values: `Positive`, `Negative`, `Boundary`, `Security`, `Performance`.
- **NOM-TST-003** Priority values: `P1` (blocker path), `P2`, `P3`.
- **NOM-TST-004** Every FR has at least one Positive, one Negative and one Boundary test.
- **NOM-TST-005** Columns: `TC ID | Traces To | Title | Type | Preconditions | Steps | Test Data | Expected Result | Priority | Automatable (Y/N)`.

## 8. Severity (defects and risks)
<!-- applies_to: all -->
`S1 Critical` · `S2 Major` · `S3 Minor` · `S4 Cosmetic`

## 9. Project Module Codes – ecommerce-checkout-revamp (project code `CHK`)
<!-- applies_to: all -->
| Code | Module |
|------|--------|
| CRT | Cart |
| GST | Guest checkout |
| ADR | Address & serviceability |
| PAY | Payments |
| COD | Cash on delivery |
| CPN | Coupons & offers |
| ORD | Order creation & events |
| RFD | Refunds |
| NTF | Notifications |
| ANL | Analytics & experiments |
