# Guest Checkout and Address
_Owner: Digital Commerce PO · 2026-09-24_

## Guest checkout (CHK-101)
- A customer can buy with email and phone only. Email is asked first, then phone.
- Account creation is offered on the confirmation page, never before payment.
## Address (CHK-102)
- Address autocomplete uses the Google Places API; the pincode is validated for serviceability through the logistics API.
- The serviceability API p95 is 900 ms today (RSK-002), so step 1 must show a loading state.
- A pincode that is not serviceable shows "We can't deliver to this pincode yet."
## Delivery estimate (CHK-108)
The estimated delivery date comes from the logistics API and is shown in step 1 and on the confirmation screen.
## Open items
- Open: how long a serviceability result may be reused is not agreed (CHK-115).
