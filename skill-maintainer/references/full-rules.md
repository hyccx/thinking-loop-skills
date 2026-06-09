# Skill Maintainer — Full Diagnostic Rules

This file contains detailed diagnostic rules referenced by Full Mode (and occasionally Normal Mode) of SKILL.md. Load only when needed.

## Full Core Tasks

1. Determine whether the skill output deviated from its intended behavior.
2. Classify the deviation type.
3. Identify root cause file: SKILL.md, description, references, examples, templates, or tests.
4. Determine remediation type: small edit, add example, add test, revise reference, revise template, add mode, or adjust boundary.
5. Default: do NOT create a new skill. Prioritize fixing the existing one.
6. Default: do NOT rewrite the entire skill. Prioritize the smallest possible change.
7. Determine if this is a one-off glitch. If it happened only once and is not recurring, do not modify rules.
8. Output a copy-paste-ready modification prompt for Codex.

## Full Diagnosis Steps

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
Map the failure to one or more types from the Full Deviation Types section below.

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

## Full Deviation Types

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

## Core Principles (Full)

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

## Failure Signals (Full)

The diagnosis is wrong if:
- It recommends creating a new skill when an existing one could be patched
- It recommends rewriting the entire SKILL.md when a small edit would suffice
- It recommends changing rules for a one-off glitch
- The patch prompt is vague or requires the engineer to make design decisions
- The diagnosis describes the problem but does not name the specific file and line to change
- It makes the skill more complex instead of more stable
