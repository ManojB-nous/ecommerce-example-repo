# Payment Integration Design
- Checkout BFF (Node.js) → Order Service → Payment Service → Gateway
- Payment Service is idempotent on `order_id + attempt_no`
- Webhooks from gateway are verified by HMAC signature
- Events published to Kafka: `order.created`, `payment.initiated`, `order.paid`, `order.failed`
- NFR: checkout API p95 < 500 ms; 3,000 orders/min at sale peaks
## Components
| Component | Responsibility |
|-----------|----------------|
| Checkout BFF (Node.js) | Serves the checkout screens, calls the services below |
| Order Service | Creates and updates orders; publishes order events |
| Payment Service | Starts payments, handles retries and webhooks, applies idempotency |
| Gateway (Razorpay primary, PayU fallback) | Hosted card fields, UPI, wallets, refunds |
| Logistics API | Pincode serviceability and delivery estimate |
## Payment flow
1. The BFF asks the Order Service to create an order; `order.created` is published.
2. The BFF asks the Payment Service to start a payment for `order_id + attempt_no`; `payment.initiated` is published.
3. The customer pays in the gateway-hosted fields or UPI app; card data never reaches our systems.
4. The gateway sends a signed webhook; the Payment Service verifies the HMAC signature.
5. On success `order.paid` is published; on failure `order.failed` is published and the customer can retry.
## Failover
Thresholds and switch-back are in `emails/2026-10-02-gateway-failover.md`. The Payment Service reads the gateway health metrics and routes new attempts; attempts already in flight finish on the gateway that started them.
## Data entities (names)
| Entity | Key attributes |
|--------|----------------|
| order | order_id, status, total, payment_method |
| payment_attempt | order_id, attempt_no, gateway, gateway_txn_id, status |
| refund | refund_id, order_id, gateway_txn_id, status, triggered_at |
## Environments
DEV, QA, UAT and PROD. Gateway sandboxes are used outside PROD.
## Observability
Metrics kept per gateway: error rate over a rolling 5-minute window, p95 latency, success rate. These feed the failover rule and the payment success KPI.
