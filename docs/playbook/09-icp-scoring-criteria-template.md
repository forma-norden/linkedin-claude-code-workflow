# ICP Scoring Criteria Template

> **Use this page when:** you need the tiering model Claude Code should apply before prospecting, enrichment, or campaign creation.

## How to use this template

Claude Code reads this file when tiering any company list.

Scoring should execute as Python logic with hard thresholds, not AI interpretation.

Every company receives a numeric score and a tier based on that score.

## Scoring dimensions

### 1. Industry fit (0-25 points)

| Industry | Score |
| --- | --- |
| `[Primary vertical - e.g. B2B SaaS]` | 25 |
| `[Secondary vertical - e.g. RevTech / MarTech]` | 20 |
| `[Adjacent vertical - e.g. Professional Services]` | 10 |
| All other industries | 0 |

### 2. Company size - headcount (0-20 points)

| Headcount | Score |
| --- | --- |
| 50-200 | 20 |
| 20-49 | 15 |
| 201-500 | 10 |
| 10-19 | 5 |
| <10 or >500 | 0 |

### 3. Revenue or ARR signals (0-20 points)

| Signal | Score |
| --- | --- |
| ARR $1M-$20M confirmed | 20 |
| ARR $500K-$1M confirmed | 15 |
| Revenue signal present but unconfirmed | 8 |
| No revenue data available | 0 |

### 4. Funding stage (0-15 points)

| Stage | Score |
| --- | --- |
| Series A or Series B | 15 |
| Seed with revenue evident | 10 |
| Bootstrapped with revenue confirmed | 8 |
| Series C+ | 5 |
| Pre-seed or no funding data | 0 |

### 5. Tech stack signals (0-10 points)

| Signal | Score |
| --- | --- |
| CRM in stack such as HubSpot or Salesforce | 5 |
| Marketing automation active | 3 |
| Sales engagement tool active | 2 |
| No CRM or automation detected | 0 |

### 6. Hiring signals (0-10 points)

| Signal | Score |
| --- | --- |
| Open AE, SDR, or BDR role | 10 |
| Open VP Sales, CRO, or Head of Revenue role | 8 |
| Open marketing or demand gen role | 5 |
| No relevant open roles | 0 |

## Tier assignment

| Tier | Score range | Volume | Approach |
| --- | --- | --- | --- |
| **Tier 1** | 70-100 | 20-50 accounts | Full ABM with human review |
| **Tier 2** | 45-69 | 100-300 accounts | Sequenced outbound plus LinkedIn touchpoint |
| **Tier 3** | 25-44 | 500-2,000 accounts | Automated outbound only |
| **Disqualified** | <25 or hard disqualifier | Excluded | No outreach |

## Hard disqualifiers

Apply these before scoring:

- Headcount below your minimum threshold
- B2C company or mixed B2B/B2C without a clear B2B revenue motion
- No CRM in stack and no marketing automation
- ACV clearly below your service economics
- Competitor of an existing client
- Already in active pipeline or already closed-won

## Scoring prompt for Claude Code

> "Score every company in [filename.csv] using my scoring-criteria.md file. Apply hard disqualifiers first and remove any that match. For remaining companies, calculate a numeric score based on each dimension. Assign Tier 1, 2, or 3 based on the score ranges defined. Output a new CSV with columns: original data + `icp_score`, `icp_tier`, `disqualified`, `disqualify_reason`. Save to `/outputs/YYYY-MM-DD_scored-accounts.csv`."

## Calibration note

These thresholds are starter values, not final truth.

Replace them with values derived from your own closed-won CRM export.

Use this prompt when building the real version:

> "Analyse this CRM export [attach file]. Identify the firmographic patterns that cluster among closed-won accounts. Group by company size, industry, ARR, funding stage, tech stack, and hiring patterns at time of close. Suggest scoring dimensions and thresholds based on what you find."
