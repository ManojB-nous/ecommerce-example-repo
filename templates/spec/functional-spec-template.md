---
template_id: TPL-FSD
artifact_type: spec
version: 1.3.0
output_format: docx
depends_on: [brd]
policies: all            # policies.md is always applied in full
nomenclature: [NOM-GEN-*, NOM-DOC-*, NOM-ID-*, NOM-SPEC-*]
---
# Functional Specification – {{project_name}}

## Document Control
| Version | Date | Author | Reviewer | Status |
|---------|------|--------|----------|--------|

## 1. Purpose & References
<!-- astra:section id=purpose
query: "purpose overview linked BRD references" -->

## 2. System Context
<!-- astra:section id=context
query: "architecture system context components integrations"
prefer: project-data/architecture -->

## 3. User Roles & Permissions
<!-- astra:section id=roles
query: "user roles permissions access admin" -->
| Role | Functions allowed | Policy |
|------|-------------------|--------|

## 4. Functional Requirements
<!-- astra:section id=functional
query: "functional behaviour screens workflow steps rules" -->
### FR-<MODULE>-<NNN> <title>
- **Traces to:** BR-...
- **Description:**
- **Preconditions:**
- **Main flow:**
- **Alternate / exception flows:**
- **Validation rules:** (field, type, length, mandatory, format)

## 5. Interfaces / APIs
<!-- astra:section id=apis
query: "API endpoint integration request response payload error codes" -->

## 6. Data Model
<!-- astra:section id=data_model
query: "entities fields data model tables attributes" -->

## 7. Non-Functional Requirements
<!-- astra:section id=nfr
query: "performance availability response time concurrent users SLA security accessibility" -->
| Category | Requirement | Target |
|----------|-------------|--------|

## 8. Error Handling & Messages
<!-- astra:section id=errors
query: "error states messages payment failed coupon invalid pincode not serviceable retry" -->
| Error state | Message shown | Recovery | Error code |
|-------------|---------------|----------|------------|

## 9. Traceability Matrix
<!-- astra:auto  BR → FR -->

## 10. Open Questions
<!-- astra:section id=open_questions query: "open questions TBD" -->

## 11. Sources
<!-- astra:auto -->
