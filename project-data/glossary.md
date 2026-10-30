# Glossary
_Owner: PMO · 2026-09-01_

Terms used across the project. Use these words exactly (NOM-GEN-003).

| Term | Meaning |
|------|---------|
| BFF | Backend for frontend: the Node.js service that serves the checkout screens |
| BR / FR / NFR | Business requirement / functional requirement / non-functional requirement |
| COD | Cash on delivery |
| Checkout squad | The delivery team for this project |
| `checkout_v2` | Feature flag for the new checkout |
| CMP | Compliance constraint, see `compliance/pci-and-consumer-rules.md` |
| CR | Change request |
| Failed-but-debited | A payment the gateway reports as failed but where the customer's account was charged |
| Failover | Switching new payment attempts from the primary to the fallback gateway |
| Gateway token | A network or gateway-issued substitute for a card number |
| Guest checkout | Buying without creating an account first |
| Hosted fields | Card input fields served by the gateway so card data never reaches our systems |
| Idempotent | Repeating a request gives the first result and never a second charge |
| LCP | Largest Contentful Paint, a page-load measure |
| MoSCoW | Must, Should, Could, Won't (this phase) priority scale |
| p95 / p75 | The value below which 95% / 75% of measurements fall |
| Pincode | Six-digit postal code used for delivery and serviceability checks |
| RACI | Responsible, Accountable, Consulted, Informed |
| SAQ A | The lightest PCI-DSS self-assessment questionnaire, for merchants that never handle card data |
| Serviceability | Whether we can deliver to a pincode, and whether COD is available there |
| SOW | Statement of work, here SOW-CHK-2026-021 |
| T+0 / T+1 | The same business day / the next business day |
| UPI | Unified Payments Interface |
| WCAG | Web Content Accessibility Guidelines |
