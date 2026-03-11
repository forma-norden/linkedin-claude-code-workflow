# Test: signal-loop-operator

Load skill: `.claude/skills/signal-loop-operator.md`

Prompt:

```text
Use this skill with campaign reply data and pipeline outcomes.
Return scoring adjustment proposals and copy updates.
```

Must pass:

- [ ] Compares outcomes by signal and tier
- [ ] Updates copy framework based on evidence
- [ ] Proposes scoring changes only with data support
- [ ] Assigns owner and next-cycle action
- [ ] Produces all three output files

Failure indicators:

- Recommends scoring changes without evidence
- Returns high-level advice only
