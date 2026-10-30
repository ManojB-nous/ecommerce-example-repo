---
rule_set: payments
version: 1.1.0
owner: Payments Lead
effective_date: 2026-11-01
---
# Payment Rules – Checkout Revamp (CHK)

> Rules that decide how payments behave. Numbers are copied exactly from the project sources (POL-ACC-005): never round or restate them.

## R-PAY-01 Gateway failover thresholds
**Rule (MUST):** Razorpay is the primary gateway and PayU the fallback. Switch to the fallback when the primary error rate is above
5% over a rolling 5-minute window, or p95 latency is above 4 s. Switch back after 15 minutes of healthy primary metrics.
**Scope:** card and UPI only.
**Why:** Payment success rate must rise from 88% to 94% (charter KPI).
**Applies when:** gateway selection, resilience or monitoring is described.
**Source:** `project-data/emails/2026-10-02-gateway-failover.md` (final thresholds); `project-data/meeting-notes/2026-09-05-payments-sync.md`.

## R-PAY-02 Payment operations are idempotent
**Rule (MUST):** The payment service is idempotent on `order_id + attempt_no`. Repeating a request with the same pair returns the
first result and never creates a second charge.
**Applies when:** payment APIs, retries or duplicate-click behaviour are specified or tested.
**Check:** the spec states the key, and a test sends the same request twice.
**Source:** `project-data/architecture/payment-integration.md`.

## R-PAY-03 Payment retry keeps the cart
**Rule (MUST):** When a payment fails, the cart and the address are kept. The customer may retry or switch payment method, up to 3
retries in 30 minutes.
**Why:** The legacy flow loses the cart on 2 of 5 gateways after a failure.
**Applies when:** failure handling, error states or retry limits are described.
**Source:** `project-data/jira-export/stories.csv` (CHK-106); `project-data/legacy/current-checkout-flow.md`.

## R-PAY-04 Failed-but-debited payments are refunded automatically
**Rule (MUST):** A payment that failed but was debited is refunded without a customer request. The refund is triggered in the
T+0 23:00 batch, reported to Finance daily, and UPI refunds complete within T+1.
**Why:** Compliance sets T+1 for UPI; Finance set the batch time; the 2026-09-05 target of 24 h is the earlier, looser wording.
**Applies when:** refunds, reconciliation or failed-payment complaints are in scope.
**Check:** the artifact cites all three sources and does not state a single number without them.
**Source:** `project-data/compliance/pci-and-consumer-rules.md` (CMP-05); `project-data/meeting-notes/2026-10-10-finance-sync.md`;
`project-data/meeting-notes/2026-09-05-payments-sync.md`.

## R-PAY-05 Payment events carry reconciliation keys
**Rule (MUST):** Every payment event carries `gateway_txn_id` and `attempt_no`. Events published are `order.created`,
`payment.initiated`, `order.paid` and `order.failed`.
**Why:** Finance reconciles on those two fields.
**Applies when:** events, reporting or reconciliation are described.
**Source:** `project-data/jira-export/stories.csv` (CHK-107); `project-data/meeting-notes/2026-10-10-finance-sync.md`.

## R-PAY-06 UPI intent and QR time out after five minutes
**Rule (MUST):** UPI intent (mobile) and QR (desktop) payments time out after 5 minutes. On timeout the customer sees the retry and
switch-method options from R-PAY-03.
**Applies when:** UPI behaviour or timeouts are specified or tested.
**Source:** `project-data/jira-export/stories.csv` (CHK-103).

## R-PAY-07 Wallets have no fallback gateway
**Rule (MUST):** Wallet payments are not covered by the gateway fallback. If the primary gateway is unavailable, wallets are shown as
temporarily unavailable and the customer is offered card or UPI.
**Applies when:** wallet payments or failover behaviour are described.
**Source:** `project-data/emails/2026-10-02-gateway-failover.md`.
