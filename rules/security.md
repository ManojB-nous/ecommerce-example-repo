---
rule_set: security
version: 1.2.0
owner: Security Architect
effective_date: 2026-11-01
---
# Security Rules – Checkout Revamp (CHK)

> Project-specific security rules. Company-wide behaviour rules are in `policies.md`; this file adds rules that come from this
> project's architecture and compliance sources. One rule per `##` heading, so each can be selected on its own.

## R-SEC-01 Card data stays in gateway-hosted fields
**Rule (MUST):** Card numbers, expiry dates and CVV are entered only in gateway-hosted fields. No artifact may describe merchant-side
storage, logging or transmission of card data. Merchant scope stays PCI-DSS v4.0 SAQ A.
**Why:** Keeping card data off our systems keeps the PCI scope at its smallest.
**Applies when:** any requirement, specification, API or test touches card entry, saved cards or payment screens.
**Check:** the artifact names the hosted fields and contains no field for PAN, expiry or CVV on our side.
**Source:** `project-data/compliance/pci-and-consumer-rules.md` (CMP-01); `project-data/meeting-notes/2026-09-05-payments-sync.md`.

## R-SEC-02 Gateway webhooks are verified before use
**Rule (MUST):** Every webhook from a payment gateway is verified by its HMAC signature before any state change. Unsigned or badly
signed calls are rejected and logged without the payload body.
**Why:** A forged "paid" webhook would let an order ship unpaid.
**Applies when:** specifications or tests cover payment callbacks, order status or refunds.
**Check:** the spec has a failure path for an invalid signature, and the test set has a negative case for it.
**Source:** `project-data/architecture/payment-integration.md`.

## R-SEC-03 Saved cards are tokens only, with consent
**Rule (MUST):** Card-on-file means network or gateway tokens only, stored after explicit customer consent. The consent control must
not be pre-ticked.
**Why:** Tokenization directions require consent, and dark-pattern guidelines forbid pre-ticked boxes.
**Applies when:** saved cards, one-tap payment or "remember this card" are in scope.
**Check:** the artifact shows the consent wording and where the consent is recorded.
**Source:** `project-data/compliance/pci-and-consumer-rules.md` (CMP-02, CMP-04).

## R-SEC-04 Money values are re-validated on the server
**Rule (MUST):** Prices, coupon values, delivery fees and COD eligibility are re-validated on the server at payment and again at order
creation. A value sent by the client is never trusted.
**Why:** The client can be tampered with; a coupon valid at the cart can expire before payment.
**Applies when:** coupons, totals, COD or any amount shown to the user is described.
**Check:** the spec states which service recalculates the amount and what happens on a mismatch.
**Source:** `project-data/requirements/coupon-and-cod-rules.md`.

## R-SEC-05 Order and refund changes are audit-logged
**Rule (MUST):** Creation, status change, cancellation and refund of an order each write an audit record with actor (user, system or
role), timestamp, old value, new value and `gateway_txn_id` where one exists.
**Why:** Finance reconciliation and dispute handling depend on an exact history.
**Applies when:** order, payment or refund behaviour is specified or tested.
**Check:** the audit fields are listed, and a test confirms a record exists after each change.
**Source:** `policies.md` (POL-SEC-003); `project-data/meeting-notes/2026-10-10-finance-sync.md`.

## R-SEC-06 Access is stated per role for every admin function
**Rule (MUST):** Each admin or support function (refund trigger, coupon create, COD limit change) names the role allowed to use it. If
the sources do not say, write `TBD – needs confirmation` and add an open question.
**Why:** Unstated access defaults to "everyone" in implementation.
**Applies when:** a specification or story describes a function used by staff rather than customers.
**Check:** a role column exists for every staff-facing function.
**Source:** `policies.md` (POL-SEC-001); `project-data/stakeholders/stakeholder-register.md`.
