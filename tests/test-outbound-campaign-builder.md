# Test: outbound-campaign-builder

Load skill: `.claude/skills/outbound-campaign-builder.md`

Prompt:

```text
Use this skill with a scored company CSV.
Target persona is VP Sales.
Build a tiered launch plan for Smartlead.
```

Must pass:

- [ ] Filters by tier before contact pull
- [ ] Includes enrichment waterfall and validation step
- [ ] Produces copy by tier and route
- [ ] Includes variable mapping checks
- [ ] Requires confirmation before launch

Failure indicators:

- Contacts routed without validation
- No tier-based sequence split
