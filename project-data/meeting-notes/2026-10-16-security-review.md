# Security Review
**Date:** 2026-10-16 · **Attendees:** Security Architect, Payments Lead, Back-end (BFF) Lead
- Hosted card fields only; SAQ A scope reconfirmed for new cards.
- Gateway webhooks are verified by HMAC signature before any state change.
- Saved cards are tokens only, stored after explicit consent that is not pre-ticked.
- Open: review of the saved-card token flow against SAQ A. **Security Architect to complete.**
