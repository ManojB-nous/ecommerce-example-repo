---
template_id: TPL-TC
artifact_type: testcases
version: 1.1.0
output_format: xlsx
depends_on: [spec]
policies: all            # policies.md is always applied in full
nomenclature: [NOM-GEN-*, NOM-DOC-*, NOM-ID-*, NOM-TST-*]
---
# Test Cases – {{project_name}}

## Test Scope
<!-- astra:section id=test_scope
query: "scope features modules to test environments" -->

## Test Environment
<!-- astra:section id=test_env
query: "environment QA UAT feature flag checkout_v2 gateway sandbox test cards" -->

## Test Data Notes
<!-- astra:section id=test_data
query: "test data sample values limits boundaries valid invalid" -->

## Test Cases
<!-- astra:section id=cases
query: "functional requirements acceptance criteria validation rules error handling" -->
<!-- one row per case; xlsx sheet "TestCases" uses these columns -->
| TC ID | Traces To | Title | Type (Positive/Negative/Boundary/Security) | Preconditions | Steps | Test Data | Expected Result | Priority | Automatable |
|-------|-----------|-------|-------------------------------------------|---------------|-------|-----------|-----------------|----------|-------------|

## Coverage Summary
<!-- astra:auto  FR → count of TCs by type -->

## Open Questions
<!-- astra:section id=open_questions query: "open questions TBD decision pending" -->
