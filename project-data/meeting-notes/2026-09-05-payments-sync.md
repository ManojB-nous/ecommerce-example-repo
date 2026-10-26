# Payments Sync
**Date:** 2026-09-05 · **Attendees:** PO, Payments Lead, Security Architect, Finance, QA Lead
- Gateway: Razorpay primary, PayU fallback when primary error rate > 5% over 5 min.
- Security: hosted card fields only – confirmed SAQ A.
- Finance: refunds for failed-but-debited payments must auto-trigger within 24 h.
- Open: should COD limit be ₹10,000 or ₹7,500 for new customers? **Finance to decide.**
