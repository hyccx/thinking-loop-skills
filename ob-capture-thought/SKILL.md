---
name: ob-capture-thought
description: Use to convert an important thought shift, decision, conversation result, project judgment, or skill-system insight into an Obsidian Raw-style markdown note. Preserve context and turning points. Do not use for polished wiki articles, final Knowledge notes, broad summarization, or direct file modification.
---

# Ob Capture Thought

Save important thought shifts, decisions, and project judgments as Obsidian Raw notes. Preserve the original context and turning point — do not polish into wiki articles.

## Core Tasks

1. Preserve original thought.
2. Preserve turning point.
3. Preserve current judgment.
4. Preserve key original phrasing and context.
5. Preserve follow-up actions.
6. Do not write encyclopedia entries.
7. Do not force-distill into permanent principles.
8. If multiple Raw notes form a stable judgment, suggest handoff to ob-distill-knowledge.

## When to Use

- After a major thought shift during a conversation
- After a project decision
- After a route judgment
- After discovering a pattern worth remembering

Do NOT use for:
- Polished wiki articles
- Final Knowledge notes
- Broad summarization
- Direct file modification

## Output Template

# {{title-as-road-sign}}

## 一句话记录
## 原始想法
## 转折点
## 当前判断
## 关键原话 / 原始上下文
## 后续动作
## 来源

## Stop Conditions

- Stop after producing one Raw note
- Do not create multiple variants

## Failure Signals

- Writes encyclopedia-style
- Removes original turning point
- Writes temporary judgment as permanent principle
- Auto-generates complex tags
- Invents sources
- Directly distills into Knowledge

## Resources

### references/
- [raw-principles.md](references/raw-principles.md)
- [title-as-road-sign.md](references/title-as-road-sign.md)
- [preserve-turning-point.md](references/preserve-turning-point.md)
- [what-not-to-polish.md](references/what-not-to-polish.md)

### templates/
- [templates/raw-note-template.md](templates/raw-note-template.md)

### examples/
- [examples/skill-system-raw.md](examples/skill-system-raw.md)
- [examples/obsidian-direction-change-raw.md](examples/obsidian-direction-change-raw.md)
- [examples/mobile-agent-route-change-raw.md](examples/mobile-agent-route-change-raw.md)

### tests/
- [tests/should_preserve_original_context.md](tests/should_preserve_original_context.md)
- [tests/should_not_wikify.md](tests/should_not_wikify.md)
- [tests/should_keep_turning_point.md](tests/should_keep_turning_point.md)
- [tests/should_not_create_knowledge.md](tests/should_not_create_knowledge.md)
