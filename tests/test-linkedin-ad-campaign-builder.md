# Test: linkedin-ad-campaign-builder

Load skill: `.claude/skills/linkedin-ad-campaign-builder.md`

Prompt:

```text
Use this skill to process a campaign sheet with 3 rows marked Ready to Launch.
Return the validation summary and launch plan.
```

Must pass:

- [ ] Lists required campaign fields
- [ ] Validates launch readiness before creation
- [ ] Includes explicit confirmation step
- [ ] Produces launch-plan and created-campaign outputs
- [ ] Blocks launch when required data is missing

Failure indicators:

- Publishes without confirmation
- Skips field validation
