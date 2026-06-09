# Test: "Simple" Mode Limits Output

## Input
> 我想做个自动分类 Obsidian 笔记的插件。简单扩散一下就够了。

## Expected behavior
- Mode: small-expansion-mode
- Triggers triggered: exactly 1
- Total results: max 3
- Template: small-expansion-output.md
- No formal auditor handoff block — instead, brief "记录提示"

## Check
- [ ] Trigger count == 1
- [ ] Result count <= 3
- [ ] Uses small-expansion template structure
- [ ] Does NOT include full auditor handoff
- [ ] Includes "记录提示" marker
