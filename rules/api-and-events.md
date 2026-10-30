---
rule_set: api-and-events
version: 1.0.0
owner: Office of the CTO (Architecture Board)
effective_date: 2026-11-01
---
# API and Event Rules – Checkout Revamp (CHK)

## R-API-01 Error codes follow ERR-<MOD>-<NNN>
**Rule (MUST):** Every API error returns an HTTP status and a business code `ERR-<MOD>-<NNN>`, using the module codes from
`nomenclature.md` (for example `ERR-PAY-003`). Error messages are safe to show to a customer.
**Applies when:** an API, error response or validation message is specified.
**Source:** `nomenclature.md` (NOM-SPEC-003).

## R-API-02 Mutating calls accept an idempotency key
**Rule (MUST):** Calls that create or change an order or a payment accept an idempotency key and return the first result for a
repeated key. For payments the key is `order_id + attempt_no` (see R-PAY-02).
**Applies when:** POST, PUT or PATCH endpoints are specified.

## R-API-03 Events use dotted lower-case names and a common envelope
**Rule (MUST):** Events are named `<entity>.<state>` in lower case (`order.created`, `payment.initiated`, `order.paid`,
`order.failed`) and carry an envelope: `event_id`, `event_type`, `occurred_at` (ISO 8601 with zone), `order_id`, and the payload.
**Applies when:** events, queues or message schemas are specified.
**Source:** `project-data/architecture/payment-integration.md`; CHK-107.

## R-API-04 Public paths are versioned
**Rule (SHOULD):** Public endpoints use a version prefix such as `/v1/`. A breaking change adds a new version; it never changes
an existing one.
**Applies when:** endpoint paths are listed in a specification.
