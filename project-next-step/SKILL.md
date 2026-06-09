---
name: project-next-step
description: Use when a direction or route has been selected and the user needs the next 1-3 concrete actions, a Codex-ready task prompt, and acceptance criteria. Do not use for broad idea expansion, route ranking, raw need extraction, Obsidian knowledge writing, or direct file modification.
---

# Project Next Step

Cut the selected direction into 1-3 concrete next actions with Codex-ready prompts and acceptance criteria. No roadmaps, no long-term plans.

## Core Tasks

1. Identify current stage.
2. Find the biggest blocker.
3. State what NOT to do now.
4. Output the next 1-3 actions.
5. Generate Codex-executable prompt.
6. Provide acceptance criteria.
7. If review needed after execution, enter result-review-mode.
8. If major judgment shift occurs, handoff to ob-capture-thought.

## When to Use

- After route-judge has selected a direction
- When user needs a concrete next action
- When a project is stuck

Do NOT use for:
- Broad idea expansion
- Route ranking
- Raw need extraction
- Obsidian knowledge writing
- Direct file modification

## Output Format

### 1. 当前阶段
### 2. 最堵的点
### 3. 现在不该做什么
### 4. 下一步 1-3 件事
### 5. 给 Codex 的任务 prompt
### 6. 验收标准
### 7. 完成后怎么复盘
### 8. 是否需要交给 ob-capture-thought

## Stop Conditions

- Stop at 3 actions max
- Do not create a roadmap
- Do not expand into future phases

## Failure Signals

- Outputs a big plan
- Outputs a long-term roadmap
- More than 3 actions
- No Codex prompt
- No acceptance criteria
- Re-starts route expansion
- Writes Obsidian knowledge

## Resources

### references/
- [next-action-rubric.md](references/next-action-rubric.md)
- [mvp-cutting-rules.md](references/mvp-cutting-rules.md)
- [codex-task-prompt-rules.md](references/codex-task-prompt-rules.md)
- [acceptance-criteria.md](references/acceptance-criteria.md)
- [result-review-mode.md](references/result-review-mode.md)

### templates/
- [templates/next-step-output.md](templates/next-step-output.md)
- [templates/codex-task-prompt.md](templates/codex-task-prompt.md)

### examples/
- [examples/skill-system-next-step.md](examples/skill-system-next-step.md)
- [examples/obsidian-next-step.md](examples/obsidian-next-step.md)
- [examples/mobile-agent-next-step.md](examples/mobile-agent-next-step.md)

### tests/
- [tests/should_not_create_big_roadmap.md](tests/should_not_create_big_roadmap.md)
- [tests/should_output_1_to_3_actions.md](tests/should_output_1_to_3_actions.md)
- [tests/should_include_acceptance_criteria.md](tests/should_include_acceptance_criteria.md)
- [tests/should_generate_codex_prompt.md](tests/should_generate_codex_prompt.md)
