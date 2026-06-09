# Patch Strategy — Decision Tree

When you identify a problem in a skill, use this decision tree to determine the fix type.

## Decision Tree

### Q1: Is this a rule problem or a scope problem?

**Rule problem**: The SKILL.md has a rule that caused bad output.
→ Fix: Edit SKILL.md rule.

**Scope problem**: The skill was applied to something it shouldn't have been.
→ Fix: Adjust description or trigger conditions in SKILL.md frontmatter.

**Execution problem**: The output followed the rules but the result was still wrong.
→ Fix: Add example or test to clarify intent.

### Q2: Is the fix content-specific or structural?

**Content-specific**: The problem is about what the skill outputs (too vague, too verbose).
→ Fix: Add an example showing the right output, or tighten the output rules.

**Structural**: The problem is about how the skill is organized (overlap with another skill, missing mode).
→ Fix: Adjust boundaries, add mode, or merge skills.

### Q3: Can the fix be an example / test / reference instead of a SKILL.md change?

- If the skill's rules are correct but the executor needs guidance → add example
- If the skill's rules are correct but a check is missing → add test
- If the skill's SKILL.md is too long → move detail to references
- Only edit SKILL.md if the rules themselves are wrong

### Q4: Is this a one-off?

Ask: "If I feed the same input again with no changes, will the same problem occur?"
- Yes → it is systematic. Fix the skill.
- No → it is a one-off. Do not change rules.

## Patch Scale

| Scale | What | When |
|-------|------|------|
| 1 | Add example/test | Rule is correct, but executor needs guidance |
| 2 | Add reference | SKILL.md too long, details belong elsewhere |
| 3 | Add mode | Skill lacks a variant for a common scenario |
| 4 | Edit rule in SKILL.md | Rule is wrong or missing |
| 5 | Adjust description/trigger | Skill triggers incorrectly |
| 6 | Merge/restructure | Skills overlap |
| 7 | Delete skill | Skill is unused or replaced |

Always start at the smallest possible scale. Only move up if the smaller scale would not fix the problem.
