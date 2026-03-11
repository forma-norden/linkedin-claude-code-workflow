# Set Up the Project Folder

> **Best for:** teams building the Claude Code operating layer before they automate LinkedIn, outbound, or retargeting workflows.

## Why this page matters

Everything Claude Code does is governed by files in a local folder.

Get the structure right once and every workflow you build inherits the same ICP logic, tool library, output standards, and copy rules.

## What Claude Code actually is

Claude Code is not a SaaS tool. There is no dashboard. There is no subscription UI.

It is a terminal-based AI agent that runs on your local machine, reads and writes files in your project folders, calls external APIs, and executes code through natural-language prompts.

The mental model shift that matters:

| Old workflow | Claude Code workflow |
| --- | --- |
| Open Clay, configure columns, run enrichment | Prompt: "Enrich these contacts using my scoring criteria" |
| Open LinkedIn Ads, manually create campaign | Prompt: "Create this campaign from my Google Sheet" |
| Write copy in Google Docs, paste into sequencer | Prompt: "Write copy for Tier 1 accounts referencing their hiring signal" |
| Scrape engagers with a separate tool, export CSV | Prompt: "Scrape this post and route ICP-fit engagers to outbound" |

The data, the logic, and the actions all live in one place.

## The required files

| File or folder | What it does | Included page |
| --- | --- | --- |
| `CLAUDE.md` | Master context file Claude Code reads first every time it runs | [CLAUDE.md Starter Template](08%20CLAUDE%20Starter%20Template.md) |
| `scoring-criteria.md` | ICP tier model built from closed-won CRM data | [ICP Scoring Criteria Template](09%20ICP%20Scoring%20Criteria%20Template.md) |
| `copy-framework.md` | Working email and LinkedIn copy structures | [Copy Framework Template](10%20Copy%20Framework%20Template.md) |
| `.claude/skills/` | Saved API scripts and integration patterns | Covered in `The API skill pattern` below |
| `/templates/` | Example outputs for scored CSVs, campaign configs, and formatted records | Create after the first successful run |

## The full folder structure

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

## Build your scoring criteria from CRM data

Do not guess at this. Build it empirically:

1. Export your CRM with closed-won deals only.
2. Prompt Claude Code to analyze the firmographic patterns across those wins.
3. Define your tier thresholds from that output.
4. If closed-won volume is thin, use your best current clients as the proxy.

The goal is a scoring file that reflects who actually buys from you, not who you think should buy from you.

## The API skill pattern

For any new platform integration:

1. Open Plan Mode in Claude Code.
2. Prompt: "I want to connect to [platform] API. Here is the documentation: [URL or paste]. Walk me through authentication and test a basic API call."
3. Let Claude Code test, error, and retry until it has a working call.
4. Save that working pattern into `.claude/skills/[platform].md`.
5. Reuse that skill across future workflows instead of re-solving it from scratch.

## Checkpoint rule

> After any successful skill build, run your checkpoint command to lock the working state. Future sessions should inherit the working integration without rebuilding it.

## Where to go next

If your structure is ready, move in this order:

1. [LinkedIn Engagement to Qualified Lead List](02%20LinkedIn%20Engagement%20to%20Qualified%20Lead%20List.md)
2. [LinkedIn Ad Campaign Builder](03%20LinkedIn%20Ad%20Campaign%20Builder.md)
3. [End-to-End Outbound Campaign Build](04%20End-to-End%20Outbound%20Campaign%20Build.md)
