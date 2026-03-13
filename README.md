# LinkedIn Claude Code Workflow

This repository packages a Claude Code workflow for turning LinkedIn signals into outbound execution. It includes reusable skills for engagement scraping and scoring, LinkedIn Ads campaign build, end-to-end outbound routing, and loop measurement for continuous iteration.

## What's Inside

| File | What it does |
|------|-------------|
| `.agents/skills/SKILL.md` | Orchestrator and routing logic |
| `.agents/skills/linkedin-engagement-routing.md` | Runs the engagement to lead-list workflow with enrichment, validation, scoring, and routing gates. |
| `.agents/skills/linkedin-ad-campaign-builder.md` | Builds LinkedIn campaigns from a config sheet and validates launch. |
| `.agents/skills/outbound-campaign-builder.md` | Converts a scored company list into a live sequencer campaign. |
| `.agents/skills/signal-loop-operator.md` | Closes the loop across content, outbound, and retargeting, logging improvements. |
| `.agents/skills/linkedin-ad-audiences.md` | Architecting high-intent ABM ad audiences using matched lists and exclusions. |
| `.agents/skills/linkedin-ad-bidding-optimization.md` | Setting manual bidding floors, caps, and managing pacing based on performance. |
| `.agents/skills/linkedin-ad-measurement.md` | Connecting Insight Tag data to downstream pipeline creation metrics. |
| `.agents/skills/linkedin-ad-creative-copy.md` | Frameworks for structuring high-performing ad copy by funnel stage. |

## Prerequisites

- [ ] Claude Code installed and running
- [ ] Phantom Buster API access
- [ ] Apollo access for enrichment
- [ ] Million Verifier API key for validation
- [ ] LinkedIn Ads API access if using campaign automation
- [ ] Sequencer API access (Apollo, Smartlead, or Instantly)

## Installation

### Cursor, Windsurf, or Generic AI IDE
1. Clone the repo: `git clone https://github.com/forma-norden/linkedin-claude-code-workflow`
2. Copy the `.agents/skills/` directory into your project's `.agents/skills/` folder.

### Claude Code
1. Clone the repo: `git clone https://github.com/forma-norden/linkedin-claude-code-workflow`
2. Copy the `.agents/skills/` directory into your project's `.claude/skills/` folder.

## Usage

Load the workflow skill and run it against a target LinkedIn post:

```text
Read .agents/skills/linkedin-engagement-routing.md

Use docs/templates/icp-scoring-criteria-template.md as the scoring source.
Post URL: https://www.linkedin.com/posts/...
Output folder: /outputs
```

Expected output:

- Enriched and validated contact CSV with tier column
- Routing recommendation by tier
- Retargeting audience export list

## Who This Is For

GTM engineers, RevOps leads, VP Sales, and founders at B2B companies with 50 to
500 employees who are building or consolidating their outbound infrastructure and
want to reduce tool sprawl through better-engineered GTM systems.

---

## From the Forma Nôrden GTM Library

This is a free resource from the Forma Nôrden open-source GTM library, built by
[Yananai A. Chiwuta](https://yananaichiwuta.com/), GTM engineer and founder of
[Forma Nôrden](https://formanorden.com/).

- [Open-source GTM systems](https://github.com/forma-norden) - all repos in the library  
- [GTM engineering blog](https://formanorden.com/blog/) - strategy, systems, and outbound deep-dives  
- [All resources](https://formanorden.com/resources/) - guides, frameworks, and templates  

If this saves you time, star the repo and follow
[Forma Nôrden on LinkedIn](https://www.linkedin.com/company/formanorden/).

Built by [Forma Nôrden](https://formanorden.com/) - GTM engineering for B2B companies.



