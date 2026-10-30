---
template_id: TPL-API
artifact_type: spec
variant: api
version: 1.0.0
output_format: docx
depends_on: [brd]
policies: all            # policies.md is always applied in full
nomenclature: [NOM-GEN-*, NOM-DOC-*, NOM-ID-*, NOM-SPEC-*]
use_when: the specification is mainly about an API, an event or an integration
---
# API Specification – {{project_name}}

## Document Control
| Version | Date | Author | Reviewer | Status |
|---------|------|--------|----------|--------|

## 1. Purpose & References
<!-- astra:section id=purpose
query: "purpose scope linked BRD references integration" -->

## 2. Context & Participants
<!-- astra:section id=context
query: "components services BFF order service payment service gateway logistics"
prefer: project-data/architecture -->

## 3. Authentication & Authorization
<!-- astra:section id=auth
query: "authentication scopes roles access tokens webhook signature HMAC" -->
| Caller | Auth method | Scopes / role |
|--------|-------------|---------------|

## 4. Endpoints
<!-- astra:section id=endpoints
query: "API endpoint method path request response" -->
### API-<MODULE>-<NNN> <name>
- **Method and path:**
- **Traces to:** FR-...
- **Request (fields):**
- **Response (fields):**
- **Idempotency:**
- **Timeout:**
- **Error codes:** HTTP status + `ERR-<MOD>-<NNN>`

## 5. Events
<!-- astra:section id=events
query: "events kafka order.created payment.initiated order.paid order.failed payload"
prefer: project-data/architecture, project-data/jira-export -->
| Event | Producer | Consumers | Key attributes |
|-------|----------|-----------|----------------|

## 6. Data Model
<!-- astra:section id=data_model
query: "entities fields attributes order payment attempt refund" -->

## 7. Error Handling & Retries
<!-- astra:section id=errors
query: "error codes retry idempotent failure timeout fallback" -->

## 8. Non-Functional Requirements
<!-- astra:section id=nfr
query: "latency p95 throughput orders per minute availability" -->
| Category | Requirement | Target |
|----------|-------------|--------|

## 9. Open Questions
<!-- astra:section id=open_questions query: "open questions TBD" -->

## 10. Sources
<!-- astra:auto -->
