# Epic: Checkout Revamp
_Owner: Digital Commerce PO · 2026-08-28_

## Why
Checkout conversion is 41% (industry benchmark ~55%). Mobile checkout takes 6 steps; 27% of abandonment happens at the address step.

## Target
- Conversion from cart to order ≥ 52% within 2 quarters.
- Mobile checkout in ≤ 3 steps.

## Scope
- Guest checkout (email + phone only)
- Address autocomplete with pincode validation
- Saved cards via gateway tokenization, UPI intent, wallets, COD (order value ≤ ₹10,000)
- Coupon field with real-time validation; one coupon per order
- Order summary with delivery date estimate
- Retry payment on failure without re-entering details

## Not in scope
- Buy-now-pay-later
- International shipping
## Epic breakdown
| Capability | Jira key |
|------------|----------|
| Guest checkout | CHK-101 |
| Address autocomplete and pincode check | CHK-102 |
| UPI intent / QR payment | CHK-103 |
| COD eligibility | CHK-104 |
| Coupon validation | CHK-105 |
| Payment retry | CHK-106 |
| Order events | CHK-107 |
| Delivery estimate | CHK-108 |
| A/B instrumentation | CHK-109 |
| Accessibility fixes | CHK-110 |
| Saved cards (tokens) | CHK-111 |
| Order confirmation messages | CHK-112 |
| Automatic refund for failed-but-debited payments | CHK-113 |
| Gateway failover | CHK-114 |
## Dependencies
- Logistics serviceability API (p95 900 ms today, see RSK-002).
- PayU production keys for the fallback gateway (DEP-001).
- Google Places API quota for address autocomplete (ASM-001, still to verify).
- Feature flag `checkout_v2` for the gradual rollout (CHK-109).
## Related documents
Business rules: `coupon-and-cod-rules.md`. Retry and failure handling: `payment-retry-and-failure-handling.md`. Address and delivery: `guest-checkout-and-address.md`. Non-functional targets: `non-functional-requirements.md`.
## Open items
- Open: COD limit for new customers (INR 7,500 or INR 10,000), see ISS-001.
