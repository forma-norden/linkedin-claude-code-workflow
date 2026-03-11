# Test: linkedin-engagement-routing

Load skill: `.claude/skills/linkedin-engagement-routing.md`

Prompt:

```text
Use this skill for a LinkedIn post at [POST_URL].
Scoring file: docs/templates/icp-scoring-criteria-template.md.
Return a validated CSV plan and routing summary.
```

Must pass:

- [ ] Includes scrape, enrichment, validation, scoring, and routing stages
- [ ] Defines tier-based routing logic
- [ ] Includes required output columns
- [ ] Blocks invalid and risky emails
- [ ] Includes fail conditions

Failure indicators:

- Missing email validation gate
- Generic strategy output without operational fields
