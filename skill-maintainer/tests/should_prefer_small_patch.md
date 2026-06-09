# Test: Diagnosis Prefers Small Patches Over Full Rewrites

## Input
> need-extractor 的输出感觉太硬了，模板感太重。

## Expected behavior
- Diagnosis identifies the problem as tone/adaptation, not structural
- Patch recommendation is: edit templates/output.md to add tone adaptation guidance
- Does NOT recommend rewriting SKILL.md
- Does NOT recommend creating a new skill

## Check
- [ ] Root cause file is templates/, not SKILL.md
- [ ] Patch scale <= 2 (add example or edit template)
- [ ] Does NOT recommend rewriting the entire skill
- [ ] Patch prompt targets a specific file and line
