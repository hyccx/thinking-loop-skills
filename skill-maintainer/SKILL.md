---
name: skill-maintainer
description: Use when a Codex skill output is unsatisfactory, too generic, too long, too rigid, too complex, triggers incorrectly, overlaps with another skill, violates its boundary, lacks next action, or when deciding whether to modify an existing skill, add a mode/reference/example/test, or create a new skill. Diagnose the failure and produce a minimal patch prompt. Do not use for normal idea expansion, project planning, Obsidian note writing, or general brainstorming.
---

# Skill Maintainer

## Purpose

Diagnose skill failures and produce minimal, targeted modifications. This is a meta-skill for maintaining the Codex skills system itself.

It does NOT solve the user's original problem. It fixes the skill that was supposed to help with that problem.

## Core Tasks

1. Determine whether the skill output deviated from its intended behavior.
2. Classify the deviation type.
3. Identify root cause file: SKILL.md, description, references, examples, templates, or tests.
4. Determine remediation type: small edit, add example, add test, revise reference, revise template, add mode, or adjust boundary.
5. Default: do NOT create a new skill. Prioritize fixing the existing one.
6. Default: do NOT rewrite the entire skill. Prioritize the smallest possible change.
7. Determine if this is a one-off glitch. If it happened only once and is not recurring, do not modify rules.
8. Output a copy-paste-ready modification prompt for Codex.

## When to Use

Use when:
- A skill's output was too generic, too long, too rigid, or too complex
- A skill triggered when it should not have, or did not trigger when it should have
- Two skills overlap in responsibility or violate each other's boundaries
- A skill output lacks a next-action, handoff, or stop condition
- A skill inflated a small idea into a whole system
- A skill forgot to check anti-system conditions
- You are deciding: modify existing skill, add mode/reference/example/test, or create new skill

Do NOT use for:
- Normal idea expansion (use idea-expander)
- Project planning (use project-next-step)
- Obsidian note writing (use ob-capture-thought)
- General brainstorming
- Final route ranking

## Diagnosis Steps

### Step 1: Collect evidence
Read the skill output that was unsatisfactory. Quote specific lines or omissions. Do not rely on vague memory — read the actual output.

### Step 2: Read the skill's SKILL.md
Open the relevant skill's SKILL.md. Check:
- Description: does it accurately describe what happened?
- Trigger conditions: did the user's input match the trigger?
- Output rules: did the output follow the rules?
- Stop conditions: did the output stop when it should have?
- Boundaries: did the output stay within scope?

### Step 3: Classify deviation type
Map the failure to one or more types from the list below.

### Step 4: Find root cause file
Determine which file in the skill directory caused the problem.

### Step 5: Determine fix scope
Choose the smallest fix that prevents recurrence:
1. Add example (if the skill was vague on a specific scenario)
2. Add test (if a check is missing)
3. Add reference (if details belong in a separate file)
4. Add mode (if a new use case needs different behavior)
5. Edit SKILL.md rule (if a rule is wrong or missing)
6. Edit description (if the trigger is wrong)
7. Adjust boundary / merge skills (if overlap)

### Step 6: Check one-off filter
Would this fix matter if the same input was given again? If not, it's a one-off. Do not change rules for one-offs.

## Deviation Types

- **太泛** (Too Generic): Output applies to any situation, not the user's specific context.
- **太长** (Too Long): Output exceeds reasonable length for the mode.
- **太硬** (Too Rigid): Output follows rules mechanically without adapting to tone or actual intent.
- **太复杂** (Too Complex): Output introduces unnecessary structure, jargon, or abstractions.
- **触发不准** (Wrong Trigger): Skill activated when it shouldn't, or failed to activate when it should.
- **职责重叠** (Overlap): Two skills produce similar outputs for the same input.
- **输出越界** (Boundary Violation): Output did something outside the skill's stated scope.
- **没有下一步** (No Next Action): Output ends without telling the user what to do next.
- **没有 handoff** (No Handoff): Output does not pass to the downstream skill.
- **把简单问题系统化** (Over-Systematize): A simple, one-shot question was answered with a full system design.
- **skill 膨胀** (Skill Bloat): The skill has grown too large or covers too many unrelated scenarios.
- **忘记停止条件** (Ignored Stop): Output continues past the stop condition.

## Core Principles

1. Do not default to creating a new skill. Fix the existing one first.
2. Do not default to rewriting SKILL.md. Prioritize adding examples, tests, or references.
3. Each fix addresses exactly one recurring problem.
4. One-off output dissatisfaction does not warrant rule changes.
5. SKILL.md holds only: trigger conditions, boundaries, core workflow, output format, and handoff.
6. Long rules go in references. Real cases go in examples. Anti-deviation checks go in tests.
7. If a skill becomes too long, split out references first, do not keep stuffing SKILL.md.
8. The maintenance goal is stability and conciseness, not complexity.
9. Can be a mode? Do not create a new skill.
10. Can be a reference? Do not edit SKILL.md.
11. Can be an example or test? Do not write it as a hard rule.

## Output Format

Every diagnosis must follow this structure:

### 1. 是否跑偏
[Yes / No with brief justification]

### 2. 跑偏类型
[List applicable deviation types from the Deviation Types section]

### 3. 根因判断
[Which file(s) caused the problem, and why]

### 4. 最小修改建议
[Specific, minimal modification: which file, what to change, what to add or remove]

### 5. 是否需要新增 skill
[Yes / No. If yes, justify why existing skills cannot be modified to cover it. Default: No.]

### 6. 给 Codex 的修改 prompt
[A single, copy-paste-ready prompt block that can be sent directly to Codex to perform the fix]

## Failure Signals

The diagnosis is wrong if:
- It recommends creating a new skill when an existing one could be patched
- It recommends rewriting the entire SKILL.md when a small edit would suffice
- It recommends changing rules for a one-off glitch
- The patch prompt is vague or requires the engineer to make design decisions
- The diagnosis describes the problem but does not name the specific file and line to change
- It makes the skill more complex instead of more stable

## Resources

### references/
- [patch-strategy.md](references/patch-strategy.md) \u2014 Patch decision tree: when to edit, add, split, or delete
- [anti-bloat-principles.md](references/anti-bloat-principles.md) \u2014 Principles to prevent skill bloat during maintenance
- [failure-patterns.md](references/failure-patterns.md) \u2014 Expanded failure patterns with examples
- [boundary-conflicts.md](references/boundary-conflicts.md) \u2014 How to detect and resolve skill boundary overlaps
- [deletion-criteria.md](references/deletion-criteria.md) \u2014 When to deprecate or delete a skill entirely

### templates/
- [templates/diagnosis-output.md](templates/diagnosis-output.md) \u2014 Output structure template
- [templates/codex-patch-prompt.md](templates/codex-patch-prompt.md) \u2014 Template for the modification prompt

### examples/
- [examples/idea-expander-too-broad.md](examples/idea-expander-too-broad.md) \u2014 Diagnosing an overly broad idea-expander output
- [examples/need-extractor-too-rigid.md](examples/need-extractor-too-rigid.md) \u2014 Diagnosing an overly rigid need-extractor output
- [examples/skill-overlap-case.md](examples/skill-overlap-case.md) \u2014 Diagnosing boundary overlap between two skills

### tests/
- [tests/should_prefer_small_patch.md](tests/should_prefer_small_patch.md) \u2014 Verify diagnosis prefers small patches over full rewrites
- [tests/should_not_create_new_skill_by_default.md](tests/should_not_create_new_skill_by_default.md) \u2014 Verify default answer for new skill is "no"
- [tests/should_detect_boundary_overlap.md](tests/should_detect_boundary_overlap.md) \u2014 Verify overlap detection works
- [tests/should_identify_when_not_to_change_rules.md](tests/should_identify_when_not_to_change_rules.md) \u2014 Verify one-off filter works

Do NOT read any of these files automatically. Load only when the task requires a specific resource.
