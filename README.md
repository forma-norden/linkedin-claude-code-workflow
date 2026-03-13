# LinkedIn Claude Code Workflow

This repository packages a Claude Code workflow for turning LinkedIn signals into outbound execution. It includes reusable skills for engagement scraping and scoring, LinkedIn Ads campaign build, end-to-end outbound routing, and loop measurement for continuous iteration.

## What's Inside

| File | What it does |
|------|-------------|
| `.claude/skills/linkedin-engagement-routing.md` | Runs the engagement to lead-list workflow with enrichment, validation, scoring, and routing gates. |
| `.claude/skills/linkedin-ad-campaign-builder.md` | Builds LinkedIn campaigns from a config sheet and validates launch readiness before publish. |
| `.claude/skills/outbound-campaign-builder.md` | Converts a scored company list into a live sequencer campaign with tiered routing logic. |
| `.claude/skills/signal-loop-operator.md` | Closes the loop across content, outbound, and retargeting, then logs what improved. |
| `docs/playbook/` | Full markdown source of the linked playbook hub and child workflow pages. |
| `docs/templates/claude-starter-template.md` | Starter `CLAUDE.md` structure for project identity, tools, rules, and output standards. |
| `docs/templates/icp-scoring-criteria-template.md` | Hard-threshold scoring template for Tier 1, Tier 2, Tier 3, and disqualifiers. |
| `docs/templates/copy-framework-template.md` | Signal-triggered and automated sequence framework for email and ad copy. |
| `tests/` | Prompt-based tests and validation checklists for each skill file. |

## Prerequisites

- [ ] Claude Code installed and running
- [ ] Phantom Buster API access
- [ ] Apollo access for enrichment
- [ ] Million Verifier API key for validation
- [ ] LinkedIn Ads API access if using campaign automation
- [ ] Sequencer API access (Apollo, Smartlead, or Instantly)

## Installation

1. Clone the repo:
   ```bash
   git clone https://github.com/forma-norden/linkedin-claude-code-workflow.git
   ```
2. Copy the skill files into your project:
   ```bash
   cp -r linkedin-claude-code-workflow/.claude/skills your-project/.claude/
   ```
3. Copy template docs into your working `docs/` folder if needed:
   ```bash
   cp -r linkedin-claude-code-workflow/docs/templates your-project/docs/
   ```
4. Add tool credentials to your `.env` file before running the workflow.

## Usage

Load the workflow skill and run it against a target LinkedIn post:

```text
Read .claude/skills/linkedin-engagement-routing.md

Use docs/templates/icp-scoring-criteria-template.md as the scoring source.
Post URL: https://www.linkedin.com/posts/...
Output folder: /outputs
```

Expected output:

- Enriched and validated contact CSV with tier column
- Routing recommendation by tier
- Retargeting audience export list

## Who This Is For

GTM engineers, RevOps leads, VP Sales, and founders at B2B companies with 50 to 500 employees who are building or consolidating their
outbound infrastructure and want to reduce tool sprawl through
better-engineered GTM systems.

---

---

## From the Forma NÃ´rden GTM Library

This is a free resource from the Forma NÃ´rden open-source GTM library, built by 
[Yananai A. Chiwuta](https://yananaichiwuta.com/), GTM engineer and founder of 
[Forma NÃ´rden](https://formanorden.com/).

- [Open-source GTM systems](https://github.com/forma-norden): all repos in the library  
- [GTM engineering blog](https://formanorden.com/blog/): strategy, systems, and outbound deep-dives  
- [All resources](https://formanorden.com/resources/): guides, frameworks, and templates  

If this saves you time, star the repo and follow 
[Forma NÃ´rden on LinkedIn](https://www.linkedin.com/company/formanorden/).

Built by [Forma NÃ´rden](https://formanorden.com/): GTM engineering for B2B companies.
