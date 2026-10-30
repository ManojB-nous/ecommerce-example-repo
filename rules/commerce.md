---
rule_set: commerce
version: 1.1.0
owner: Digital Commerce Product Owner (with Finance and Marketing)
effective_date: 2026-11-01
---
# Commerce Rules – Coupons, COD and Delivery (CHK)

> Business rules agreed by Finance and Marketing. Limits and fees are quoted exactly as in the source (POL-ACC-005).

## R-CPN-01 One coupon per order
**Rule (MUST):** An order carries at most one coupon. An auto-applied "best offer" can be replaced by a coupon the customer types.
**Applies when:** coupons, offers or the order summary are described or tested.
**Source:** `project-data/requirements/coupon-and-cod-rules.md`; `project-data/requirements/checkout-epic.md`.

## R-CPN-02 Coupon types and the percentage cap
**Rule (MUST):** Coupon types are flat (INR), percentage and free delivery. A percentage coupon must have a maximum discount cap;
a percentage coupon without a cap is invalid configuration.
**Applies when:** coupon configuration, validation or boundary tests are described.
**Check:** at least one boundary test sits exactly on the cap.
**Source:** `project-data/requirements/coupon-and-cod-rules.md`.

## R-CPN-03 Invalid coupons show a specific reason
**Rule (MUST):** The customer sees the exact reason: expired, minimum order value not met, category not eligible, usage limit reached,
or not valid for this account. A generic "Invalid coupon" is not acceptable.
**Why:** Generic errors are a known pain point in the current checkout.
**Applies when:** coupon error states, copy or negative tests are described.
**Source:** `project-data/requirements/coupon-and-cod-rules.md`; `project-data/legacy/current-checkout-flow.md`; CHK-105.

## R-COD-01 COD eligibility
**Rule (MUST):** Cash on delivery is offered only when the order value is at or below INR 10,000 and the delivery pincode is
COD-enabled.
**Applies when:** payment-method selection, COD or pincode checks are described or tested.
**Check:** boundary tests at INR 10,000 and at the first value above it.
**Source:** `project-data/requirements/coupon-and-cod-rules.md`; `project-data/requirements/checkout-epic.md`; CHK-104.

## R-COD-02 COD exclusions and fee
**Rule (MUST):** COD is not allowed for orders that contain gift cards, or electronics priced above INR 5,000 per item. The COD fee
is INR 49 per order.
**Applies when:** COD eligibility, order totals or fees are described.
**Source:** `project-data/requirements/coupon-and-cod-rules.md`.

## R-COD-03 New-customer COD limit is undecided
**Rule (MUST):** The COD limit for new customers is an open decision: Finance prefers INR 7,500 and the Product Owner prefers
INR 10,000, with the decision planned at the steering meeting on 2026-10-28. Until a later source records the decision, an artifact
states both figures, marks the item `TBD – needs confirmation`, and lists it under Open Questions. It must not pick one.
**Why:** Picking a side would present a guess as a requirement (POL-ACC-002).
**Applies when:** COD, new customers or COD limits are mentioned.
**Source:** `project-data/meeting-notes/2026-10-10-finance-sync.md`; `project-data/meeting-notes/2026-09-05-payments-sync.md`;
`project-data/raid/raid-log.csv` (ISS-001).

## R-DLV-01 Pincode serviceability and delivery estimate
**Rule (MUST):** The pincode is validated for serviceability through the logistics API during address entry, and an estimated delivery
date is shown in step 1 and again on the confirmation screen.
**Why:** 3.1% of orders in the legacy flow were undeliverable because the pincode was never validated.
**Applies when:** address entry, delivery options or the confirmation screen are described.
**Source:** `project-data/jira-export/stories.csv` (CHK-102, CHK-108); `project-data/legacy/current-checkout-flow.md`; RSK-002.
