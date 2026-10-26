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
