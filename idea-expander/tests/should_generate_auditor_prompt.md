# Test: Every Expansion Includes Auditor Handoff

## Input
> 帮我扩散一下这个想法：我想建一个 habit-tracker skill。

## Expected behavior
- Mode: triggered-expansion-mode
- Output MUST include the auditor handoff prompt (7 questions from SKILL.md Handoff section)
- The handoff block must be present after the expansion results

## Check
- [ ] Contains "给 idea-auditor 的审查 prompt" header
- [ ] Contains all 7 judgment questions
- [ ] Auditor block appears AFTER expansion results, not before
