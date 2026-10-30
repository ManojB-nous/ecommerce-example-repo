# Golden Repository – Ecommerce Checkout Revamp (CHK)

This repository is the single source of truth Astra uses to generate delivery artifacts (BRD, specification, user stories,
test cases, test plan, change-request impact) for the **Checkout Revamp** project. It holds the rules, the templates and the
project evidence. It does not hold generated documents.

## Layout
| Path | Purpose | Who changes it |
|------|---------|----------------|
| `policies.md` | Company-wide behaviour rules for every Astra response | Office of the CTO, Legal, Information Security |
| `nomenclature.md` | Naming, ID formats and document structure | PMO & Quality Office |
| `golden.yaml` | Manifest: which rule sections always apply, which apply to a doc type, stage or tag, and each template's default | PMO & Quality Office |
| `rules/` | Project rules, one rule per `##` heading (security, payments, commerce, UX and accessibility, quality and testing, governance, API and events) | The owner named in each file |
| `templates/` | Document templates, one folder per document type, optional variants | PMO & Quality Office |
| `project-data/` | Evidence: requirements, decisions, contracts, compliance, backlog, risks, analytics | The project team |

The four items `policies.md`, `nomenclature.md`, `templates/` and `project-data/` are required at the repository root.
`golden.yaml` and `rules/` are optional, but without `golden.yaml` no rule is guaranteed to apply.

## How rules are chosen
`golden.yaml` assigns every rule section one of three levels:
1. **always** – included in every response (for example the company policies and rule R-GOV-04).
2. **applies_to** – included when the request's document type, stage and tags match (for example the COD rules apply to a
   BRD, spec, user stories or test cases about `cod`).
3. **not listed** – chosen by how well the section matches the request text.

## Rule format
One rule per `##` heading, titled `R-<AREA>-<NN> <short name>`, followed by **Rule** (MUST, MUST NOT or SHOULD), optionally
**Why**, **Applies when**, **Check** and **Source**. Keep each rule short and self-contained, because it may be shown on its own.

## Templates
Folder name = document type, file name = variant.
| Document type | Variants |
|---------------|----------|
| `brd` | `brd-template` (default), `brd-payments-template` |
| `spec` | `functional-spec-template` (default), `api-spec-template` |
| `testcases` | `test-case-template` |
| `user-stories` | `user-story-template` |
| `test-plan` | `test-plan-template` |
| `change-request` | `cr-impact-template` |

Each template section carries an `astra:section` comment with a search query and the folders to prefer.

## Project data conventions
- Dated sources name the date in the file name or the first lines (`2026-10-02-gateway-failover.md`).
- Emails start with `From`, `To`, `Date`, `Subject`. Meeting notes start with `Date` and `Attendees`.
- Mark undecided items with `Open:` so they are not mistaken for decisions.
- Use roles, never personal names.
- Terms are defined in `project-data/glossary.md`.

## Changing this repository
1. Branch, change, open a pull request.
2. Rule or policy changes are reviewed by the file owner; changes to `golden.yaml` also by the PMO.
3. A rule heading that `golden.yaml` points to must not be renamed without updating `golden.yaml` (Astra shows a warning if they drift).
4. Update `CHANGELOG.md`.
