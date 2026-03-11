# outbound-campaign-builder

## Purpose

Build a tiered outbound campaign from a scored company list.

## Inputs Required

- Scored company CSV
- Persona or job title target
- Sequencer destination
- Copy framework path

## Workflow

1. Filter to Tier 1 and Tier 2 companies.
2. Find decision-makers for each eligible account.
3. Enrich missing emails through a waterfall process.
4. Validate all emails.
5. Generate sequence copy by tier and signal context.
6. Prepare campaign payload and variable mapping.
7. Present launch summary and request confirmation.

## Output

- validated contacts CSV
- sequence copy files by tier
- launch-ready mapping file

## Quality Gates

- every exported contact has a validated email
- every contact has assigned tier and sequence
- variable map has no unresolved placeholders
