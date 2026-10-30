# Non-Functional Requirements
_Owner: Back-end (BFF) Lead · 2026-10-08_

| Category | Requirement | Target | Source |
|----------|-------------|--------|--------|
| Performance | Checkout API response time | p95 below 500 ms | `architecture/payment-integration.md` |
| Performance | Mobile page load (LCP, p75) | below 2.5 s | `charter/project-charter.md` |
| Scalability | Orders at sale peaks | 3,000 orders per minute | `architecture/payment-integration.md` |
| Reliability | Payment success rate | 94% (baseline 88%) | `charter/project-charter.md` |
| Security | Card data scope | PCI-DSS v4.0 SAQ A | `compliance/pci-and-consumer-rules.md` |
| Accessibility | Checkout screens | WCAG 2.1 AA | `meeting-notes/2026-09-19-ux-review.md` |
## Open items
- Open: availability target for the checkout is not set in any source.
