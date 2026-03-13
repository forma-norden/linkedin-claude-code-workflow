# Ecosystem: linkedin-claude-code-workflow

How this repo connects to the rest of the Forma Norden GTM library.

## Works With

| Repo | Relationship | When to use together |
|------|-------------|---------------------|
| `linkedin-profile-dm-conversion-playbook` | Parallel | This repo handles ads and signal processing, that repo handles organic/DM |
| `cold-email-copy-playbook` | Downstream | Multi-channel: ads build awareness, email converts |
| `clay-claude-code-skill-pack` | Upstream | Enriched data feeds LinkedIn ad audience targeting |
| `buying-window-signal-workflow` | Upstream | Signal scoring determines ad campaign prioritization |
| `n8n-gtm-workflow-pack` | Parallel | n8n automates ad-to-outbound sync workflows |

## Suggested Skill Chains

1. Ad program: ad-audiences > linkedin-ad-campaign-builder > ad-creative-copy > ad-bidding-optimization > ad-measurement
2. Signal to outbound: engagement-routing > outbound-campaign-builder > signal-loop-operator
