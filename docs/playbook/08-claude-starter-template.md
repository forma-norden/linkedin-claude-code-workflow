# CLAUDE.md Starter Template

> **Use this page when:** you need the master routing file Claude Code should read first in a LinkedIn-led GTM project.

## How to use this template

Keep this file under 200 lines.

Put detailed scoring logic in [ICP Scoring Criteria Template](09%20ICP%20Scoring%20Criteria%20Template.md) and detailed outbound language in [Copy Framework Template](10%20Copy%20Framework%20Template.md).

## Project identity

This is a GTM execution project for `[COMPANY NAME]`.

Goal: convert LinkedIn activity and ICP account lists into qualified pipeline using automated outbound workflows.

## ICP definition

- **Industries:** `[e.g. B2B SaaS / Professional Services / RevTech]`
- **Company size:** `[e.g. 10-200 employees]`
- **ARR range:** `[e.g. $500K-$20M]`
- **Geography:** `[e.g. North America / EMEA]`
- **Decision-maker titles:** `[e.g. CEO, CRO, VP Sales, Head of Revenue]`
- **Tech signals:** `[e.g. HubSpot or Salesforce in stack, marketing automation active]`
- **Hiring signals:** `[e.g. open AE, SDR, or BDR roles = active revenue motion]`
- **Funding signals:** `[e.g. Series A-B = expansion budget available]`
- **Disqualifiers:** `[e.g. <10 employees, B2C, no CRM, <$5K ACV]`

Read the full tiering rules before scoring any list:

- [ICP Scoring Criteria Template](09%20ICP%20Scoring%20Criteria%20Template.md)

## Tool library

All API keys belong in `.env`. Never hardcode credentials.

| Tool | Purpose | Skill file |
| --- | --- | --- |
| Phantom Buster | LinkedIn post engagement scraping | `.claude/skills/phantombuster.md` |
| Apollo | Prospect finding and enrichment | `.claude/skills/apollo.md` |
| Million Verifier | Email validation before every send | `.claude/skills/million-verifier.md` |
| Prospeo | Primary email enrichment | `.claude/skills/prospeo.md` |
| Findymail | Secondary email enrichment | `.claude/skills/findymail.md` |
| Datagma | Tertiary email enrichment | `.claude/skills/datagma.md` |
| LinkedIn Ads API | Campaign creation and audience management | `.claude/skills/linkedin-ads.md` |
| `[Sequencer]` | Campaign creation and contact loading | `.claude/skills/sequencer.md` |

## Output standards

- Save all contact lists as CSV files inside `/outputs/` using `YYYY-MM-DD_[description].csv`
- Required CSV columns: `first_name`, `last_name`, `title`, `company`, `company_size`, `industry`, `email`, `email_status`, `icp_tier`, `signal_type`, `source`
- Email status values: `valid`, `risky`, `invalid`
- Never send to `risky` or `invalid`
- Confirm before executing any write, send, or publish action

## Tone and voice

Read this before writing emails, LinkedIn messages, ad copy, or any outbound-facing content:

- [Copy Framework Template](10%20Copy%20Framework%20Template.md)

## Workflow rules

1. Always score before prospecting.
2. Always validate emails before loading any sequencer.
3. Always checkpoint after a successful skill build or API connection.
4. Never send to disqualified contacts.
5. Tier 1 actions require human review before execution.
6. Tier 2 and Tier 3 actions can run autonomously after setup is confirmed.

## Folder structure

```text
/project-root
├── CLAUDE.md
├── .env
├── .claude/
│   ├── skills/
│   └── rules/
├── docs/
│   ├── scoring-criteria.md
│   └── copy-framework.md
├── inputs/
├── outputs/
└── campaigns/
```

## Checkpoint command

After any successful API skill build, run:

`/checkpoint [skill-name] - working as of [date]`
