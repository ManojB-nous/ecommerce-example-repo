---
rule_set: quality-and-testing
version: 1.0.0
owner: QA Lead
effective_date: 2026-11-01
---
# Quality and Testing Rules – Checkout Revamp (CHK)

> Adds project rules on top of the test-case standards in `nomenclature.md` (NOM-TST-001 to NOM-TST-005).

## R-QA-01 Limits are tested on the boundary
**Rule (MUST):** For every numeric limit in the sources (COD value, per-item electronics value, coupon cap, retry count, timeout), the
test set has a case exactly at the limit and one just beyond it, typed `Boundary`.
**Applies when:** test cases or a test plan are written for rules that contain a number.
**Check:** each limit named in `rules/commerce.md` and `rules/payments.md` appears in at least one Boundary case.

## R-QA-02 Test data is synthetic and gateway-provided
**Rule (MUST):** Cards, UPI handles, emails and addresses in test data are synthetic. Card tests use only the gateway's published test
cards; nothing resembling a real card number appears (POL-PRIV-001).
**Applies when:** test data, examples or sample payloads are written.

## R-QA-03 Performance tests use the stated targets
**Rule (MUST):** Performance cases use the figures in the architecture source: checkout API p95 below 500 ms, and 3,000 orders per
minute at sale peaks. The page target is LCP below 2.5 s on mobile (p75). Do not invent other thresholds.
**Applies when:** performance, load or non-functional tests are described.
**Source:** `project-data/architecture/payment-integration.md`; `project-data/charter/project-charter.md`.

## R-QA-04 Both states of the checkout_v2 flag are covered
**Rule (MUST):** Regression and acceptance sets run with the `checkout_v2` feature flag on and off, because the rollout is gradual
(10% of traffic first).
**Applies when:** test plans, regression sets or release checks are written.
**Source:** `project-data/jira-export/stories.csv` (CHK-109); `project-data/charter/project-charter.md`.

## R-QA-05 Each error message is tested by its text
**Rule (SHOULD):** For every error state in the sources (payment failed, coupon invalid with a specific reason, pincode not
serviceable), a Negative case checks the message text, not only that an error appeared.
**Applies when:** negative cases are written.
**Source:** `project-data/ux/screen-inventory.md`.
