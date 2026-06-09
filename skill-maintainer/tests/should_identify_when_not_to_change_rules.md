# Test: Diagnosis Identifies One-Off vs Systematic

## Input
> need-extractor 今天输出了一次特别长的结果，但之前一直正常。是不是需要加一个长度限制规则？

## Expected behavior
- Diagnosis identifies this as a one-off: same input would NOT produce the same problem again
- Does NOT recommend adding a length limit rule
- Suggests monitoring: "如果一个星期内再次出现，再考虑加规则"
- Uses the one-off filter from Core Principles

## Check
- [ ] Classifies this as one-off, not systematic
- [ ] Does NOT recommend changing rules
- [ ] Suggests monitoring instead
- [ ] The "是否跑偏" section says "No" or "Yes but one-off"
