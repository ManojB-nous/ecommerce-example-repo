# Coupon & COD Business Rules (Finance + Marketing, v1.1, 2026-10-04)
## Coupons
- One coupon per order; auto-applied "best offer" can be replaced by a manual coupon.
- Coupon types: flat (INR), percentage (cap mandatory), free delivery.
- Invalid reasons shown to user: expired, minimum order value not met, category not eligible, usage limit reached, not valid for this account.
- Coupon value is re-validated server-side at payment and at order creation.
## COD
- Allowed only if order value ≤ INR 10,000 and pincode is COD-enabled.
- Not allowed for orders containing gift cards or electronics > INR 5,000 per item.
- COD fee: INR 49 per order.
- New-customer COD limit: **under discussion** (INR 7,500 proposed).
## Worked examples (for illustration only)
| Case | Input | Expected |
|------|-------|----------|
| Percentage coupon with cap | 20% coupon, cap INR 500, order INR 4,000 | Discount INR 500 (the cap applies; 20% would be INR 800) |
| Flat coupon | Flat INR 150, order INR 1,200 | Discount INR 150 |
| Coupon expires before payment | Coupon valid at cart, expired at payment | Server rejects it at payment; the user sees "expired" |
| COD at the limit | Order INR 10,000, COD-enabled pincode | COD offered |
| COD above the limit | Order INR 10,001 | COD not offered |
| COD with a gift card | Gift card in the cart | COD not offered |
## Edge cases
- A manual coupon replaces the auto-applied "best offer"; the replaced offer is shown as removed.
- A coupon never makes the payable amount negative.
## Open items
- Open: the new-customer COD limit (see above).
- Open: whether the INR 49 COD fee counts toward the COD order-value limit is not stated in any source.
