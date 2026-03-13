# linkedin-ad-measurement

Use this skill to set up LinkedIn Ads tracking, attribution, and reporting
for B2B pipeline measurement.

## Tracking Infrastructure

### LinkedIn Insight Tag (Required)
JavaScript pixel installed on all website pages.
Tracks: page views, conversions, audience building.
Install via: Google Tag Manager, direct code, or platform integration.

### Conversions API (CAPI)
Server-side event tracking for accurate conversion data.
Handles: iOS privacy restrictions, ad blockers, cross-device attribution.
Setup: via webhook integration or CRM event forwarding.

### Conversion Events to Track

| Event | Setup | Attribution Window |
|-------|-------|--------------------|
| Website visit | Insight Tag auto-track | 90 days |
| Form submission | Insight Tag event rule | 90 days |
| Demo booked | CAPI or CRM sync | 90 days |
| Pipeline created | CRM to CAPI | 180 days |
| Revenue won | CRM to CAPI | 180 days |

## KPI Framework

### Awareness KPIs
- Impressions
- Reach (unique members)
- Frequency (impressions per member)

### Engagement KPIs
- Click-through rate (CTR)
- Social engagement rate (likes, comments, shares)
- Video completion rate

### Conversion KPIs
- Cost per lead (CPL)
- Lead-to-MQL conversion rate
- Cost per MQL
- Pipeline generated (CRM attribution)

### Revenue KPIs
- Pipeline sourced (first touch from LinkedIn Ads)
- Pipeline influenced (any touch from LinkedIn Ads)
- Revenue attributed
- ROAS (return on ad spend)

## Reporting Cadence

| Frequency | What to Report | Who Sees It |
|-----------|---------------|-------------|
| Weekly | Spend, impressions, CTR, leads | Campaign manager |
| Monthly | CPL, MQL rate, pipeline influenced | Marketing lead |
| Quarterly | Revenue attributed, ROAS, pipeline velocity | VP/C-Level |

## Execution Sequence

1. Install Insight Tag on all website pages.
2. Configure conversion events for each funnel stage.
3. Set up CAPI for server-side tracking (if available).
4. Build reporting dashboard with KPIs by funnel level.
5. Establish reporting cadence and stakeholder distribution.

## Output Contract

Return:

- tracking infrastructure setup plan
- conversion event configuration
- KPI framework matched to campaign objectives
- reporting template with cadence
- attribution model recommendation
