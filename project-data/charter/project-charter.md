# Project Charter – Checkout Revamp
**Approved:** 2026-08-25 · **Sponsor:** Chief Digital Officer
## Goal
Raise cart-to-order conversion from 41% to ≥ 52% within two quarters of 100% rollout.
## KPIs
| KPI | Baseline (Aug 2026) | Target |
|-----|--------------------|--------|
| Cart → order conversion | 41% | 52% |
| Mobile checkout steps | 6 | ≤ 3 |
| Payment success rate | 88% | 94% |
| Checkout LCP (mobile p75) | 3.8 s | < 2.5 s |
## Timeline
Design freeze 2026-11-15 · 10% traffic 2027-01-10 · 100% traffic before the 2027-03 spring sale.
## Objectives
1. Reduce abandonment at the address and payment steps of the mobile checkout.
2. Raise the payment success rate by adding a fallback gateway and a retry that keeps the cart.
3. Meet the compliance constraints in `compliance/pci-and-consumer-rules.md` without widening PCI scope.
## Scope summary
In: guest checkout, address autocomplete with pincode validation, saved cards (tokens), UPI, wallets, COD, coupons, order summary, payment retry, A/B instrumentation.
Out (see the SOW): buy-now-pay-later, international shipping, loyalty-points redemption, changes to the order-management system beyond new events.
## Milestones
| Milestone | Date | Note |
|-----------|------|------|
| Charter approved | 2026-08-25 | Sponsor: Chief Digital Officer |
| Design freeze | 2026-11-15 | |
| 10% traffic on `checkout_v2` | 2027-01-10 | |
| Spring sale code freeze begins | 2027-02-20 | Risk RSK-001 |
| 100% traffic | before 2027-03 | Before the spring sale |
## Governance
- Steering committee meets fortnightly; its decisions are recorded in the meeting notes (next recorded item: COD new-customer limit, 2026-10-28).
- The Digital Commerce Product Owner owns the backlog and day-to-day scope calls.
- Scope changes above 5 person-days need approval from the Chief Digital Officer (see the SOW summary).
## Delivery team (roles)
Digital Commerce Product Owner, Payments Lead, Front-end Lead, Back-end (BFF) Lead, UX Lead, Accessibility Specialist, QA Lead, Security Architect (advisory), Logistics Integration Manager (advisory), Finance Controller (advisory).
## Launch criteria
- All Must-priority stories done and accepted by the Product Owner.
- No open S1 or S2 defects.
- Accessibility failures from the audit fixed (CHK-110).
- Payment success rate monitored from the first 10% of traffic.
