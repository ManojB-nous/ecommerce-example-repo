From: Payments Lead
To: Checkout Squad
Date: 2026-10-02
Subject: Gateway failover thresholds – final

Primary: Razorpay. Fallback: PayU.
Switch to fallback when primary error rate > 5% over a rolling 5-minute window OR p95 latency > 4 s.
Switch back after 15 minutes of healthy primary metrics. Card and UPI only; wallets have no fallback.
