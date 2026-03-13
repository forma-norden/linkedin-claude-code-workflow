# linkedin-ad-audiences

Use this skill to build targeting strategies for LinkedIn Ads campaigns
including ICP audiences, exclusions, ABM account lists, and remarketing.

## Required Inputs

- ICP definition (titles, seniority, company size, industry)
- campaign objective (awareness, consideration, conversion)
- ABM account list if available
- first-party audience data if available

## Audience Building Principles

1. Start narrow, expand after 2 weeks of data.
2. Company list targeting matches at 95-100%. Contact list matches at 30-70%.
3. Exclude current customers, competitors, and existing pipeline from cold campaigns.
4. Minimum audience size for reliable delivery: 5,000 members.
5. Layer targeting dimensions, do not stack too many on one campaign.

## Audience Types

### Saved Audiences (Attribute Targeting)
Targeting by: job title, seniority, function, company size, industry, geography.
Best for: broad awareness and list expansion.

### Matched Audiences (Account Lists)
Upload company list (by name or domain) or contact list (by email).
Best for: ABM Tier 1-2, account-specific campaigns.
Match rate: company lists 95-100%, contact lists 30-70%.

### Retargeting Audiences
Website visitors (Insight Tag), video viewers, lead gen form openers, company page visitors.
Best for: mid-funnel and conversion campaigns.

### Lookalike Audiences
Based on matched or retargeting audiences.
Best for: expanding TAM with similar profiles.

## ABM Audience Tiers

| Tier | Account Count | Targeting | Content |
|------|--------------|-----------|---------|
| Tier 1 | 10-50 | 1:1 by company name | Custom by account |
| Tier 2 | 50-200 | Cluster by vertical/size | Cluster-specific |
| Tier 3 | 200-1000 | Programmatic by attributes | Segment-specific |

## Exclusion Strategy

Always exclude:
- Current customers
- Active pipeline (CRM sync)
- Competitors and their employees
- Team members and company employees
- Previous converters (move to different funnel stage)

## Execution Sequence

1. Define ICP attributes for targeting.
2. Build saved audience with attribute targeting.
3. Upload ABM company list for matched audience.
4. Create retargeting audiences from Insight Tag data.
5. Set exclusions across all active campaigns.
6. Validate audience size meets 5,000 minimum.

## Output Contract

Return:

- audience configuration with targeting criteria
- exclusion list specifications
- ABM tier assignment with audience sizing
- retargeting audience setup steps
- audience refresh cadence recommendation
