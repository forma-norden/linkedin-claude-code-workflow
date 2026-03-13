# linkedin-ad-campaign-builder

## Purpose

Create LinkedIn Ads campaigns from a structured configuration sheet.

## Inputs Required

- Sheet URL or structured CSV
- Campaign status flag column (for example `Ready to Launch`)
- Ad asset folder path

## Required Fields

- campaign group
- campaign name
- targeting type
- audience
- cta
- destination url
- daily budget
- start date

## Workflow

1. Read campaign rows marked for launch.
2. Validate required fields and formats.
3. Build campaign payloads per row.
4. Generate a pre-launch summary.
5. Wait for explicit confirmation.
6. Create campaigns and attach ad creatives.

## Output

- `launch-plan.md` with each campaign and validation status
- `created-campaigns.csv` with campaign IDs and metadata

## Quality Gates

- no launch if any required field is missing
- no launch if destination URL is invalid
- no launch without human confirmation
