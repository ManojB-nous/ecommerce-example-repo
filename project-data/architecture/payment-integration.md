# Payment Integration Design
- Checkout BFF (Node.js) → Order Service → Payment Service → Gateway
- Payment Service is idempotent on `order_id + attempt_no`
- Webhooks from gateway are verified by HMAC signature
- Events published to Kafka: `order.created`, `payment.initiated`, `order.paid`, `order.failed`
- NFR: checkout API p95 < 500 ms; 3,000 orders/min at sale peaks
