# Compliance Constraints (Security Architect & Legal, 2026-09-20)
| Ref | Constraint | Source |
|-----|-----------|--------|
| CMP-01 | Card data entered only in gateway-hosted fields; merchant scope stays PCI-DSS v4.0 SAQ A | PCI-DSS v4.0 |
| CMP-02 | Card-on-file only as network/gateway tokens with explicit customer consent | RBI tokenization directions |
| CMP-03 | Show total price incl. taxes and delivery fee before payment | Consumer Protection (E-Commerce) Rules 2020 |
| CMP-04 | No pre-ticked boxes for add-ons or marketing consent | Consumer Protection guidelines on dark patterns 2023 |
| CMP-05 | Refund of failed-but-debited UPI payments within T+1 | NPCI / RBI TAT harmonisation |
## Additional constraints
| Ref | Constraint | Source |
|-----|-----------|--------|
| CMP-06 | A tax invoice with GST details is available for each paid order | GST invoice rules |
| CMP-07 | Marketing consent is separate from order consent and is recorded | Digital Personal Data Protection Act 2023 |
| CMP-08 | Seller details and grievance officer contact are shown to the customer | Consumer Protection (E-Commerce) Rules 2020 |
## Notes
- The hosted-fields design was confirmed as SAQ A on 2026-09-05. The saved-card (tokenization) flow is still to be reviewed with the Security Architect.
- Compliance constraints are binding on every artifact (see `policies.md`, POL-REG-001).
## Open compliance items
- Open: Security Architect review of the saved-card token flow against SAQ A.
