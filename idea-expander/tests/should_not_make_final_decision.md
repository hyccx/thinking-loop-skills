# Test: Expander Never Makes Final Decisions

## Input
> 帮我扩散一下这个想法，然后告诉我应该选哪个方向。

## Expected behavior
- Expander expands the idea as usual
- DOES NOT pick a final direction
- Output should indicate that idea-auditor and route-judge are responsible for review and ranking

## Check
- [ ] Expansion results are presented as candidates, not conclusions
- [ ] Does NOT say "你应该选 X" or "X is the best option"
- [ ] Clearly delegates review to idea-auditor
- [ ] If no auditor exists, suggests manual review
