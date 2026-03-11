# CLAUDE.md - linkedin-claude-code-workflow

This repo contains four Claude Code workflow skills for LinkedIn-led pipeline
execution. Load the correct skill before running any workflow.

## Skills in This Repo

| Skill | When to use it |
|-------|---------------|
| `linkedin-engagement-routing` | Converting LinkedIn engagers into scored and routeable contacts |
| `linkedin-ad-campaign-builder` | Creating LinkedIn Ads campaigns from a configuration sheet |
| `outbound-campaign-builder` | Building tiered outbound campaigns from scored company data |
| `signal-loop-operator` | Feeding response data back into routing and copy logic |

## Templates in This Repo

| Template | Purpose |
|----------|---------|
| `docs/templates/claude-starter-template.md` | Base project operating file |
| `docs/templates/icp-scoring-criteria-template.md` | Scoring thresholds and disqualifiers |
| `docs/templates/copy-framework-template.md` | Signal-driven copy system |

## Playbook Source

The full page tree from the original playbook package is available in:

- `docs/playbook/`

## How to Load a Skill

Say: `Read .claude/skills/linkedin-engagement-routing.md` before describing your task.

## Output Rule

Workflow output must be operational:

- exact tables or CSV columns
- routing decisions with explicit thresholds
- no generic strategy summary

## Testing

Run tests from the `tests/` folder before production use.
