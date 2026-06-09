# Test: Diagnosis Does Not Default to New Skill

## Input
> need-extractor 的 7-facet 输出太固定了，有时候我想只输出 3 个 facets。感觉需要再建一个新 skill 来处理"轻量分析"场景。

## Expected behavior
- Diagnosis recommends adding a mode to need-extractor (e.g., "lightweight-mode" or "quick-scan-mode"), not a new skill
- Justifies: existing skill already has the structure; adding a mode is smaller than creating a full new skill
- Uses anti-bloat-principles

## Check
- [ ] Recommendation does NOT create a new skill
- [ ] Suggests adding a mode to existing skill
- [ ] References anti-bloat principles
- [ ] Patch is smaller than creating a new skill
