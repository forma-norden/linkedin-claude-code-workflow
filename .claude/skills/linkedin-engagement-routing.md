# linkedin-engagement-routing

## Purpose

Run a full LinkedIn engagement workflow from post URL to routed outbound list.

## Inputs Required

- LinkedIn post URL
- Scoring criteria file path
- Output folder
- Tool credentials in `.env`

## Workflow

1. Pull all likers and commenters from the target post.
2. Enrich records with title, company, industry, company size, and work email.
3. Validate every email and remove invalid or risky contacts.
4. Score all valid contacts against the provided scoring criteria.
5. Assign route by tier:
   - Tier 1 -> ABM sequence
   - Tier 2 -> signal-triggered sequence
   - Tier 3 -> automated sequence
6. Produce a retargeting audience export using Tier 1 and Tier 2.

## Output Format

Primary CSV columns:

- `first_name`
- `last_name`
- `title`
- `company`
- `industry`
- `company_size`
- `email`
- `email_status`
- `icp_score`
- `icp_tier`
- `route`
- `source_post_url`

## Quality Gates

- No contact with `email_status` equal to `invalid` or `risky`
- No missing `icp_tier` for valid contacts
- No routing without score

## Fail Conditions

Stop and request correction if:

- post scrape returns empty
- enrichment coverage is below 50%
- scoring criteria file is missing thresholds
