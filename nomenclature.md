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
- **NOM-GEN-004** Module codes: use only the codes in *Project Module Codes* below.
- **NOM-GEN-005** Percentages are written with the percent sign and no space (`94%`); durations with a unit (`15 minutes`, `4 s`).
- **NOM-GEN-006** Spell out "Cash on delivery (COD)" and "Unified Payments Interface (UPI)" on first use in every artifact.

## 2. Document Control & Versioning
<!-- applies_to: all -->
- **NOM-DOC-001** Every artifact starts with a Document Control table: `Version | Date | Author | Reviewer | Status`.
- **NOM-DOC-002** Versions: `0.x` = draft, `1.0` = first approved, minor bump for edits, major bump for scope change.
- **NOM-DOC-003** Status values only: `Draft`, `In Review`, `Approved`, `Superseded`.
- **NOM-DOC-004** File names: `<PROJECTCODE>_<ARTIFACT>_v<version>.<ext>`, e.g. `CHK_BRD_v0.3.docx`.
- **NOM-DOC-005** Every artifact has a Sources section that lists each cited file by path.

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
| Issue / Dependency | `ISS-<NNN>` / `DEP-<NNN>` | ISS-001 |
| Change request | `CR-<NNN>` | CR-003 |
| Jira story | `CHK-<NNN>` | CHK-104 |
| Compliance constraint | `CMP-<NN>` | CMP-01 |

- **NOM-ID-001** IDs are never reused, even after a requirement is deleted (mark it `Withdrawn`).

## 4. Business Requirements Document (BRD)
<!-- applies_to: brd -->
- **NOM-BRD-001** Priority uses MoSCoW: `Must`, `Should`, `Could`, `Won't (this phase)`.
- **NOM-BRD-002** Every BR has at least one testable acceptance criterion.
- **NOM-BRD-003** Separate sections for In Scope, Out of Scope, Assumptions, Constraints, Dependencies, Open Questions.
- **NOM-BRD-004** Stakeholders listed with role and RACI.
- **NOM-BRD-005** Every BR names its source file, so a reviewer can find the origin of the requirement.
- **NOM-BRD-006** A BR is one testable statement; split a sentence that holds two obligations.

## 5. Specifications (Functional / API)
<!-- applies_to: spec, api-spec -->
- **NOM-SPEC-001** Every FR states `Traces to: BR-…`.
- **NOM-SPEC-002** Field validation table columns: `Field | Type | Length | Mandatory | Format / Rule | Error message`.
- **NOM-SPEC-003** APIs documented as: method, path, auth/scopes, request, response, error codes (HTTP + business code `ERR-<MOD>-<NNN>`).
- **NOM-SPEC-004** NFR table covers PERF, AVL, SEC, SCL, ACC (WCAG 2.1 AA for UI).
- **NOM-SPEC-005** Data fields and event attributes use `snake_case`; endpoints use lower-case, hyphenated path segments.
- **NOM-SPEC-006** Every API lists its idempotency behaviour and its timeout.

## 6. User Stories
<!-- applies_to: user-stories -->
- **NOM-US-001** Format: *As a <role>, I want <capability>, so that <benefit>.*
- **NOM-US-002** Acceptance criteria in Given / When / Then.
- **NOM-US-003** A story is small enough for one sprint; larger work is an epic. Story points stay `TBD` until the team estimates.
- **NOM-US-004** A story keeps the Jira key as given in the export (`CHK-<NNN>`) and adds the `US-<MOD>-<NNN>` ID.

## 7. Test Cases
<!-- applies_to: testcases -->
- **NOM-TST-001** Each TC states `Traces to: FR-… / BR-…`.
- **NOM-TST-002** Type values: `Positive`, `Negative`, `Boundary`, `Security`, `Performance`.
- **NOM-TST-003** Priority values: `P1` (blocker path), `P2`, `P3`.
- **NOM-TST-004** Every FR has at least one Positive, one Negative and one Boundary test.
- **NOM-TST-005** Columns: `TC ID | Traces To | Title | Type | Preconditions | Steps | Test Data | Expected Result | Priority | Automatable (Y/N)`.
- **NOM-TST-006** Test case numbers run per module (`TC-PAY-001`, `TC-PAY-002`) and are never renumbered.
- **NOM-TST-007** Expected results quote the exact message or value from the source.

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

## 10. Jira Keys, Feature Flags and Release Names
<!-- applies_to: user-stories, testcases, test-plan, change-request -->
- **NOM-REL-001** Jira keys keep the form `CHK-<number>`; do not rewrite or renumber them.
- **NOM-REL-002** Feature flags are lower-case `snake_case`, for example `checkout_v2`.
- **NOM-REL-003** Releases are named `CHK-R<year>.<nn>`, for example `CHK-R2027.01`, with the traffic share in the description (10%, 100%).
- **NOM-REL-004** Environments are written `DEV`, `QA`, `UAT`, `PROD`.

## 11. Test Plans
<!-- applies_to: test-plan -->
- **NOM-TPL-001** A test plan has: objectives, scope in and out, test types, environments, entry and exit criteria, schedule, risks and roles.
- **NOM-TPL-002** Entry and exit criteria are measurable (for example "no open S1 or S2 defects").
- **NOM-TPL-003** Schedule dates come from the charter and RAID log; do not invent dates.

## 12. Change Requests
<!-- applies_to: change-request -->
- **NOM-CR-001** A change request ID is `CR-<NNN>`; the number is never reused.
- **NOM-CR-002** Status values only: `Proposed`, `Approved`, `Deferred`, `Rejected`.
- **NOM-CR-003** Effort is stated in person-days; anything above 5 person-days needs approval from the Chief Digital Officer.
- **NOM-CR-004** The impact section covers scope, effort, timeline, risk, compliance and test impact.
