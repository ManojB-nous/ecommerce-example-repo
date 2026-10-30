---
rule_set: ux-and-accessibility
version: 1.0.0
owner: UX Lead
effective_date: 2026-11-01
---
# UX and Accessibility Rules – Checkout Revamp (CHK)

## R-ACC-01 WCAG 2.1 AA for every checkout screen
**Rule (MUST):** Every checkout screen meets WCAG 2.1 AA. A specification states the accessibility requirement per screen, and test
sets include keyboard-only and screen-reader checks.
**Why:** The audit of the current checkout found 14 WCAG failures, mainly colour contrast and missing labels.
**Applies when:** any screen, form or error state is described or tested.
**Source:** `project-data/meeting-notes/2026-09-19-ux-review.md`; CHK-110; `nomenclature.md` (NOM-SPEC-004).

## R-ACC-02 Every control has a programmatic label
**Rule (MUST):** Every input and radio button, including each payment-method option, has a label that assistive technology can read.
Placeholders do not count as labels.
**Applies when:** forms, payment selection or test cases for form controls are described.
**Source:** `project-data/meeting-notes/2026-09-19-ux-review.md`; CHK-110.

## R-UX-01 Checkout takes at most three steps on mobile
**Rule (MUST):** The mobile flow is three steps: (1) Contact and address, with the delivery option inline, (2) Payment,
(3) Confirmation. Any proposal that adds a step needs a stated reason and a Product Owner decision.
**Why:** The legacy flow has 6 steps; the charter target is 3 or fewer.
**Applies when:** flows, screens, journeys or step counts are described.
**Source:** `project-data/ux/screen-inventory.md`; `project-data/charter/project-charter.md`; `project-data/meeting-notes/2026-09-19-ux-review.md`.

## R-UX-02 No pre-ticked boxes or dark patterns
**Rule (MUST NOT):** No pre-ticked boxes for add-ons or marketing consent, and no countdowns, hidden costs or confirm-shaming text.
**Applies when:** consent, add-ons, upsell or promotional text is described.
**Source:** `project-data/compliance/pci-and-consumer-rules.md` (CMP-04).

## R-UX-03 Total price is shown before payment
**Rule (MUST):** The total, including taxes and the delivery fee, is shown before the customer pays. Order summary is sticky at the
bottom on mobile and expandable.
**Applies when:** the order summary, pricing or payment screen is described.
**Source:** `project-data/compliance/pci-and-consumer-rules.md` (CMP-03); `project-data/meeting-notes/2026-09-19-ux-review.md`.

## R-UX-04 Guest checkout asks for email first, then phone
**Rule (MUST):** Guest checkout asks for email first and phone second. Account creation is offered on the confirmation page, never
before payment.
**Why:** Forced login caused a 19% drop in the legacy flow.
**Applies when:** guest checkout, login or registration is described.
**Source:** `project-data/meeting-notes/2026-09-19-ux-review.md`; `project-data/legacy/current-checkout-flow.md`; CHK-101.
