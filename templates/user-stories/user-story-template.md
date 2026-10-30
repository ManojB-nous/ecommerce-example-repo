---
template_id: TPL-US
artifact_type: user-stories
version: 1.0.0
output_format: md
depends_on: [brd]
policies: all            # policies.md is always applied in full
nomenclature: [NOM-GEN-*, NOM-DOC-*, NOM-ID-*, NOM-US-*]
---
# User Stories – {{project_name}}

## Epics
<!-- astra:section id=epics query: "epic feature area checkout" prefer: project-data/jira-export -->

## Stories
<!-- astra:section id=stories query: "as a user I want so that acceptance criteria" -->
### US-<NNN> <title>
- **As a** … **I want** … **so that** …
- **Traces to:** BR-...
- **Acceptance criteria (Given/When/Then):**
- **Story points:** TBD

## Definition of Ready
- Source cited, acceptance criteria written in Given / When / Then, dependencies named, open questions listed.

## Definition of Done
- Acceptance criteria tested, accessibility checked (WCAG 2.1 AA), audit logging confirmed where records change, and the story traces to a BR.
