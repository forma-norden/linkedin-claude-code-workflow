# LinkedIn Engagement to Qualified Lead List

> **Best for:** teams already publishing on LinkedIn and wanting each post to become a scored, routeable source of qualified contacts.

## Why this workflow matters

This is the highest-leverage workflow in the playbook.

It converts content you are already producing into a live pipeline feed with no extra manual work after setup.

## How it works

```text
LinkedIn Post Published
        ↓
Claude Code triggers Phantom Buster scrape
        ↓
Scraped profiles -> Apollo enrichment
        ↓
Million Verifier email validation
        ↓
ICP scoring against your scoring criteria
        ↓
ICP-fit contacts -> routed to outbound
Non-fit contacts -> discarded
        ↓
Same ICP-fit list -> uploaded to LinkedIn as custom audience
```

## Step-by-step build

### Step 1: Set up Phantom Buster as your scraper

Phantom Buster's LinkedIn Post Commenters and Likers extractors are the standard pattern for this workflow.

Prompt:

> "Set up a Phantom Buster skill that takes a LinkedIn post URL and returns all engagers as a CSV. Save as `.claude/skills/phantombuster.md`."

### Step 2: Connect Apollo for enrichment

Apollo handles title, company, and firmographic enrichment after the scrape.

Prompt:

> "Take this list of LinkedIn profiles and enrich them using Apollo. I need full name, title, company, company size, industry, employee count, and work email."

### Step 3: Validate every email

Run every email list through Million Verifier before any send. Invalid and risky emails degrade deliverability fast.

Prompt:

> "Validate all emails in this CSV using my Million Verifier API key. Remove invalid and risky emails. Save the clean list to `/outputs`."

### Step 4: Score the list against your ICP

Use hard thresholds from [ICP Scoring Criteria Template](09%20ICP%20Scoring%20Criteria%20Template.md), not loose AI judgment.

Prompt:

> "Score each contact against my scoring-criteria.md file. Assign Tier 1, Tier 2, or Tier 3. Discard anyone who does not meet minimum criteria. Output a clean CSV with a tier column added."

### Step 5: Route to outbound

Use [Copy Framework Template](10%20Copy%20Framework%20Template.md) as the writing source once the scored list is ready.

- Tier 1 contacts -> escalate to ABM sequence
- Tier 2 contacts -> add to signal-triggered email sequence
- Tier 3 contacts -> add to automated outbound

Prompt:

> "Push all Tier 1 and Tier 2 contacts to my [sequencer] campaign using the API. Flag Tier 1 contacts in a Slack message to the SDR channel."

### Step 6: Upload the same list to LinkedIn Ads

The same enriched, ICP-scored list that feeds outbound also becomes your retargeting audience on LinkedIn Ads.

That is where email outreach and ad impressions start reinforcing each other instead of operating as separate motions.

## Automate it on Railway

Once the workflow runs cleanly end to end, deploy it on Railway so it runs every week without a terminal open.

1. Prompt Claude Code to write the Railway deployment script.
2. Push the workflow to Railway.
3. Run it on a fixed schedule or trigger it manually from Slack.

Example prompt:

> "Write a deployment script for this workflow to run on Railway every Monday at 7am UTC. It should scrape the last 7 days of posts from my LinkedIn company page and personal profile."

## Why the starter files matter here

| File | What it controls in this workflow |
| --- | --- |
| [CLAUDE.md Starter Template](08%20CLAUDE%20Starter%20Template.md) | Tool library, output rules, and execution safeguards |
| [ICP Scoring Criteria Template](09%20ICP%20Scoring%20Criteria%20Template.md) | Tier logic and disqualifiers |
| [Copy Framework Template](10%20Copy%20Framework%20Template.md) | The sequence language used once contacts are routed |
