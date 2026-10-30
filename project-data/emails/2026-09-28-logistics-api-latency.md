From: Logistics Integration Manager
To: Checkout Squad
Date: 2026-09-28
Subject: Serviceability API latency

The serviceability API p95 is 900 ms. Step 1 of the new checkout calls it once per pincode entry.
We can offer a bulk-refresh of COD-enabled pincodes every night. Reusing a serviceability result for part of a day is a proposal only; it needs agreement from the Product Owner and Finance before it is used.
