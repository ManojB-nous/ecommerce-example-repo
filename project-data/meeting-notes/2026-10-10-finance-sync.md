# Finance Sync
**Date:** 2026-10-10
- Reconciliation needs `gateway_txn_id` and `attempt_no` on every payment event.
- Refund for failed-but-debited: auto-trigger at T+0 23:00 batch; report to Finance daily.
- COD new-customer limit: Finance prefers INR 7,500; PO prefers INR 10,000 → decision at steering 2026-10-28.
