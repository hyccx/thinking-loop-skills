# Test: Diagnosis Detects Boundary Overlap

## Input
> 我问了 need-extractor "帮我分析这个 idea"，结果 idea-expander 也出来了一个类似的回答。这两个是不是重复了？

## Expected behavior
- Diagnosis identifies this as "职责重叠" (role overlap)
- Compares descriptions of need-extractor and idea-expander
- Suggests: add exclusion phrase to one or both descriptions
- Does NOT recommend merging or deleting either skill
- Does NOT recommend creating a new skill

## Check
- [ ] Identifies the overlap type correctly
- [ ] Compares SKILL.md descriptions
- [ ] Fix is smaller than merging or deleting
- [ ] No new skill recommended
