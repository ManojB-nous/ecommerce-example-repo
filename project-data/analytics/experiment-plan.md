# Experiment Plan – checkout_v2
_Owner: Digital Commerce PO · 2026-10-20_

## Design
- Feature flag `checkout_v2` splits traffic between the current and the new checkout.
- Rollout: 10% of traffic from 2027-01-10, then 100% before the 2027-03 spring sale.
## Events
One event per step view and per drop-off (CHK-109): `step_viewed`, `step_completed`, `step_abandoned`, with `step`, `device` and `variant`.
## Metrics
Primary: cart to order conversion (baseline 41%, target 52%). Secondary: payment success rate (baseline 88%, target 94%), mobile steps (target 3 or fewer), checkout LCP p75 (target below 2.5 s).
## Guardrails
Payment success rate must not fall below the baseline in the variant group.
## Open items
- Open: minimum sample size and test duration are not set.
