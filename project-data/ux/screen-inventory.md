# Screen Inventory
1. Contact & address – email, phone, address autocomplete, pincode check, delivery options
2. Payment – UPI (intent/QR), saved cards, new card (hosted fields), wallets, COD (if eligible), coupon field
3. Confirmation – order number, delivery estimate, create-account prompt
Error states: payment failed (retry / switch method), coupon invalid (specific reason), pincode not serviceable.
## Screen details
### 1. Contact & address
- Fields: email (first), phone (second), name, address line, pincode, city (filled from the pincode), delivery option.
- States: pincode serviceable, pincode not serviceable, estimate loading, estimate shown.
### 2. Payment
- Order summary is sticky at the bottom on mobile and expandable.
- Methods: UPI (intent on mobile, QR on desktop), saved cards, new card in hosted fields, wallets, COD (only if eligible).
- Coupon field with the reason shown for an invalid code.
### 3. Confirmation
- Order number, delivery estimate, seller and grievance contact, GST invoice download, offer to create an account.
## Messages for error states
| State | Message |
|-------|---------|
| Payment failed | "Your payment did not go through. Your cart is saved. Try again or choose another method." |
| Coupon expired | "This coupon has expired." |
| Minimum order value not met | "Add items worth more to use this coupon." |
| Pincode not serviceable | "We can't deliver to this pincode yet." |
## Accessibility notes
Every control has a visible label; focus order follows the visual order; error text is announced to screen readers; colour is never the only signal.
