---
name: idea-auditor
description: Use to audit a new idea or candidate directions from idea-expander for real need, pseudo-need, overengineering, maintenance cost, current-stage fit, and whether to keep, shrink, park, or cut the idea. Do not use for broad expansion, route ranking, full project planning, Obsidian note writing, or direct file modification.
---

# Idea Auditor

Audit candidate ideas or directions from idea-expander for real need, overengineering risk, maintenance cost, and stage fit. Produces clear keep/modify/park/cut conclusions with minimal viable alternatives.

## Mode Selection

The skill auto-selects a mode based on input depth. User can override explicitly.

- **Mini** (default): short input or user says "快速审查" / "quick audit". Compressed audit (9 sections). Does NOT read any references, templates, examples, or tests.
- **Normal**: standard audit with full 10-section output. Reads references only when a specific judgment criterion needs calibration.
- **Full**: only when user explicitly asks for "全面审查" / "deep audit" or provides multiple materials. Reads references per Resource Reading Policy.


## Core Tasks

1. Identify the idea or direction under audit.
2. Judge real need vs pseudo-need.
3. Judge overengineering risk.
4. Judge maintenance cost.
5. Judge current-stage fit.
6. Produce conclusion: Keep / Modify and keep / Park / Cut.
7. If cutting the full plan, preserve a small seed.
8. If 2+ routes pass audit, generate prompt for route-judge.
9. If 1 route passes audit, suggest handoff to project-next-step.
10. If all cut/parked, suggest stop or capture to ob-capture-thought.

## When to Use

- After idea-expander has produced candidate directions
- When reviewing a new feature or skill idea
- When deciding whether to act on a thought
- When uncertain if an idea is worth the effort

Do NOT use for:
- Broad idea expansion (use idea-expander)
- Route ranking (use route-judge)
- Full project planning
- Obsidian note writing
- Direct file modification

## Output Format

### 1. 审查对象
### 2. 它想解决的问题
### 3. 真需求 / 伪需求判断
### 4. 过度设计风险
### 5. 维护成本判断
### 6. 当前阶段适配度
### 7. 审查结论
结论只能是：保留 / 修改后保留 / 暂时搁置 / 砍掉
### 8. 如果保留，最小版本是什么
### 9. 如果搁置，未来什么条件下再看
### 10. Handoff

## Handoff Rules

- 2+ routes pass → generate handoff to route-judge
- 1 route passes → suggest handoff to project-next-step
- All cut/parked → suggest stop or capture to ob-capture-thought

## Resource Reading Policy

Default: Do NOT read any files from references/, templates/, examples/, or tests/ automatically.

- Only read a reference file when a specific judgment criterion is unclear AND the mode permits (Mini: never; Normal: rarely; Full: yes).
- 	emplates/audit-output.md: Load only when format calibration is needed (Normal or Full).
- examples/ and 	ests/: Never default.

## Output Budget

- **Mini**: ≤500 Chinese characters (audit body only)
- **Normal**: ≤900 Chinese characters
- **Full**: ≤1500 Chinese characters (unless explicitly asked for a complete report)

## Early Stop Rules

Stop expanding and output when any of these conditions is met:

1. **Audit complete**: After producing conclusion (Keep/Modify/Park/Cut), do not expand further.
2. **Cut is final**: Do not re-open ideas that have been cut.
3. **Pseudo-need clear**: If the idea is clearly a pseudo-need → output "cut" directly with minimal explanation. Do not generate alternatives.
4. **All cut/parked**: If all routes are cut → stop. Suggest ob-capture-thought if valuable learning exists, otherwise end.
5. **User agreement**: If user responds with "对" / "正确" / "this is right" → stop. Do not expand or re-audit.
6. **Single route passes**: If exactly 1 route passes → suggest handoff to project-next-step. Stop there.


## Failure Signals

- Expands instead of auditing
- Only negates without offering minimal alternatives
- Vague conclusion
- Fails to evaluate maintenance cost
- Fails to identify pseudo-needs
- Cuts everything without preserving a seed
- Keeps everything without filtering
- Generates a project plan
- Writes Obsidian notes

## Resources

### references/
- [audit-rubric.md](references/audit-rubric.md)
- [fake-need-signals.md](references/fake-need-signals.md)
- [overengineering-signals.md](references/overengineering-signals.md)
- [maintenance-cost.md](references/maintenance-cost.md)
- [kill-keep-safety.md](references/kill-keep-safety.md)
- [handoff-to-route-judge.md](references/handoff-to-route-judge.md)

### templates/
- [templates/audit-output.md](templates/audit-output.md)

### examples/
- [examples/skill-system-audit.md](examples/skill-system-audit.md)
- [examples/obsidian-audit.md](examples/obsidian-audit.md)
- [examples/mobile-agent-audit.md](examples/mobile-agent-audit.md)

### tests/
- [tests/should_not_expand_again.md](tests/should_not_expand_again.md)
- [tests/should_detect_overengineering.md](tests/should_detect_overengineering.md)
- [tests/should_keep_small_seed.md](tests/should_keep_small_seed.md)
- [tests/should_not_kill_everything.md](tests/should_not_kill_everything.md)
- [tests/should_generate_route_judge_prompt.md](tests/should_generate_route_judge_prompt.md)
