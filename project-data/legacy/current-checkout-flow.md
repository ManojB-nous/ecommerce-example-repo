# As-Is Checkout (mobile)
1. Cart → 2. Login / register (mandatory) → 3. Address (manual entry, no validation) → 4. Delivery options → 5. Payment method → 6. Review & place order.
Issues: forced login (19% drop), no pincode validation (3.1% orders undeliverable), payment failure loses cart on 2 of 5 gateways, coupon errors are generic ("Invalid coupon").
## Metrics (August 2026)
Cart to order conversion 41%. Biggest drops: address step 27%, payment step 23%, login or guest step 19% (see `analytics/funnel-aug-2026.csv`).
## Behaviour by step
| Step | What happens today | Pain point |
|------|--------------------|------------|
| Login / register | Mandatory before address | Forced login causes the 19% drop |
| Address | Free text, no pincode validation | 3.1% of orders are undeliverable |
| Delivery options | Separate screen | Extra step on mobile |
| Payment method | Five gateways, mixed behaviour | Cart lost after a failure on 2 of 5 gateways |
| Review and place order | Totals shown late | Delivery fee appears only here |
## Support themes
Customers report debited-but-failed payments, generic coupon errors and orders that cannot be delivered to the entered pincode.
