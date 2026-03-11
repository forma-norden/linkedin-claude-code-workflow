# End-to-End Outbound Campaign Build

> **Best for:** teams that want the complete pipeline from company list to live campaign without switching between multiple tools and documents.

## Why this workflow matters

This is the full system: company list in, live campaign out.

No copy-pasting. No manual data handling. No separate scoring spreadsheet, enrichment workflow, and copy document living in different places.

## What Claude Code does in this workflow

1. Receives a company CSV with basic firmographic data
2. Scores and tiers every company against [ICP Scoring Criteria Template](09%20ICP%20Scoring%20Criteria%20Template.md)
3. Finds the right decision-makers at Tier 1 and Tier 2 companies via Apollo
4. Enriches contact emails through a waterfall
5. Validates all emails through Million Verifier
6. Writes personalized copy using [Copy Framework Template](10%20Copy%20Framework%20Template.md)
7. Creates the campaign in your sequencer and loads all contacts

## The prompt sequence

Run these in order.

### Prompt 1: Score the list

> "Here is my company list [attach CSV]. Tier every company using my scoring-criteria.md file. Disqualify companies that do not meet minimum criteria. Output a tiered CSV with score breakdown."

### Prompt 2: Find decision-makers

> "Find [job title/persona] at all Tier 1 and Tier 2 companies using Apollo. I need full name, title, LinkedIn URL, company, and work email where available."

### Prompt 3: Enrich missing emails

> "For all contacts without a verified work email, run the enrichment waterfall: Prospeo first, Findymail second, Datagma third. Stop when an email is found. Then validate the full list via Million Verifier."

### Prompt 4: Write copy

> "Using copy-framework.md, write a 3-step email sequence for this campaign. Target persona: [role] at [company type]. Signal to reference: [hiring event / funding round / tech change]. Apply conditional personalization based on industry."

### Prompt 5: Build the campaign

> "Create a new campaign in [sequencer] called [name]. Add all Tier 1 contacts to the ABM sequence. Add all Tier 2 contacts to the signal-triggered sequence. Use the copy from Prompt 4. Map all variables. Confirm before launching."

## Why scoring uses Python, not AI

When Claude Code scores the company list, it should generate a Python script that applies your thresholds as hard logic.

That creates three advantages:

- zero hallucination risk in scoring
- reliable operation at scale
- full auditability because you can inspect the logic line by line

## Building your company list

The fastest path is usually Apollo with basic filters such as industry, headcount, and funding stage, then export the CSV into Claude Code.

You can also build the list fully inside Claude Code using Apollo MCP if that is faster for your team.

The only rule that matters is speed to a clean, scoreable list.

## Connect it back to LinkedIn

Once the outbound workflow is live, route the same account set into [LinkedIn Ad Campaign Builder](03%20LinkedIn%20Ad%20Campaign%20Builder.md) and [The Signal Loop](05%20The%20Signal%20Loop.md) so outreach and impressions reinforce each other.
