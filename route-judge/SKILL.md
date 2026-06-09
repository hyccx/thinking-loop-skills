---
name: route-judge
description: Use when there are two or more audited candidate routes and the user needs ranking, prioritization, sequencing, or a first recommendation. Do not use for idea expansion, raw auditing, full project planning, Obsidian note writing, or direct file modification.
---

# Route Judge

Rank 2+ audited candidate routes by user constraints. Output first choice, second choice, not-now, later-consider, with rationale and minimal validation experiment.

## Core Tasks

1. Accept 2+ audited candidate routes.
2. Rank by user constraints.
3. Output: first recommendation, second recommendation, do not touch now, consider later.
4. Provide ranking rationale.
5. Provide minimal validation experiment.
6. Generate handoff prompt for project-next-step.

## When to Use

- After idea-auditor has produced 2+ routes worth pursuing
- When user needs to decide which direction to start with

Do NOT use for:
- Idea expansion or new direction generation
- Raw auditing
- Full project planning
- Obsidian note writing
- Direct file modification

## Ranking Criteria

- Fits real need
- Low maintenance
- Quickly verifiable
- Fits current stage
- Does not increase complexity
- Reversible
- Can serve as foundation for next steps

## Output Format

### 1. 候选路线
### 2. 排序标准
### 3. 第一推荐
### 4. 第二推荐
### 5. 暂时不要碰
### 6. 未来再考虑
### 7. 最小验证实验
### 8. 给 project-next-step 的 prompt

## Stop Conditions

- Stop after producing ranked output
- Do not expand or generate new ideas

## Failure Signals

- Lists pros/cons without ranking
- No first recommendation
- No "do not touch now" section
- No minimal validation experiment
- Expands new routes
- Generates full project plan
- Writes Obsidian notes

## Resources

### references/
- [ranking-rubric.md](references/ranking-rubric.md)
- [hard-constraints.md](references/hard-constraints.md)
- [tie-breaker-rules.md](references/tie-breaker-rules.md)
- [handoff-to-project-next-step.md](references/handoff-to-project-next-step.md)

### templates/
- [templates/route-ranking-output.md](templates/route-ranking-output.md)

### examples/
- [examples/skill-route-judge.md](examples/skill-route-judge.md)
- [examples/obsidian-route-judge.md](examples/obsidian-route-judge.md)
- [examples/mobile-agent-route-judge.md](examples/mobile-agent-route-judge.md)

### tests/
- [tests/should_rank_not_list.md](tests/should_rank_not_list.md)
- [tests/should_mark_not_now.md](tests/should_mark_not_now.md)
- [tests/should_include_minimal_experiment.md](tests/should_include_minimal_experiment.md)
- [tests/should_generate_project_next_step_prompt.md](tests/should_generate_project_next_step_prompt.md)
