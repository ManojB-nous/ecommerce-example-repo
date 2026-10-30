# Payment Retry and Failure Handling
_Owner: Payments Lead · 2026-10-05_

## Rules
- When a payment fails, the cart and the address are kept (CHK-106).
- The customer can retry or switch method, up to 3 retries in 30 minutes.
- UPI intent and QR payments time out after 5 minutes (CHK-103).
- Each attempt has an `attempt_no`; the payment service is idempotent on `order_id + attempt_no`.
## Failed but debited
The payment is refunded automatically; the batch runs at T+0 23:00 and Finance receives a daily report. For UPI the refund completes within T+1 (CMP-05).
## Failover
If the primary gateway breaches the thresholds in `emails/2026-10-02-gateway-failover.md`, new attempts go to the fallback gateway. Wallets have no fallback.
## Customer messages
See the error-state messages in `ux/screen-inventory.md`.
## Open items
- Open: behaviour of a retry that starts on the fallback gateway after the primary recovers is not described in any source.
