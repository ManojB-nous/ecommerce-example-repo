---
rule_set: governance
version: 1.0.0
owner: PMO & Quality Office
effective_date: 2026-11-01
---
# Delivery Governance Rules – Checkout Revamp (CHK)

## R-GOV-01 Work outside the SOW is a change request
**Rule (MUST):** Anything not covered by SOW-CHK-2026-021 is marked "Subject to change request" and is never promised. A change
request above 5 person-days needs approval from the Chief Digital Officer. Use the change-request impact template.
**Applies when:** a new feature, scope increase or extra deliverable appears in a request or source.
**Source:** `project-data/contracts/sow-summary.md`; `policies.md` (POL-LEG-001).

## R-GOV-02 Known SOW exclusions
**Rule (MUST NOT):** Do not plan or specify buy-now-pay-later, international shipping, loyalty-points redemption, or changes to the
order-management system beyond the new events. Mention them only under Out of Scope.
**Applies when:** scope sections of a BRD, stories or specs are written.
**Source:** `project-data/contracts/sow-summary.md`; `project-data/requirements/checkout-epic.md`.

## R-GOV-03 Rollout dates and the sale code freeze
**Rule (MUST):** Use the dates as sourced: design freeze 2026-11-15, 10% traffic 2027-01-10, 100% traffic before the 2027-03 spring
sale. The spring-sale code freeze from 2027-02-20 is an open risk (RSK-001), so plans that need changes after that date say so.
**Applies when:** timelines, release plans or risks are described.
**Source:** `project-data/charter/project-charter.md`; `project-data/raid/raid-log.csv` (RSK-001).

## R-GOV-04 Open decisions are listed, not resolved
**Rule (MUST):** An item that a source marks as open or "under discussion" stays open in the artifact. List it under Open Questions
with each source. When sources conflict, the most recent dated decision wins (POL-ACC-004), and an undecided item has no winner.
**Applies when:** the sources contain "Open:", "to decide", "under discussion" or two different values for one rule.
**Source:** `policies.md` (POL-ACC-002, POL-ACC-004).

## R-GOV-05 Deferred requests stay out of scope
**Rule (MUST):** A change request with status Deferred or Rejected is not added to scope. State its status and ID wherever the
topic appears.
**Applies when:** a deferred idea (for example save-for-later) is mentioned.
**Source:** `project-data/change-requests/`.
