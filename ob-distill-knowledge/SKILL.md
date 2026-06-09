---
name: ob-distill-knowledge
description: Use to distill multiple Raw notes or repeated themes into an Obsidian Knowledge stage snapshot with source links, current judgment, scope, and open questions. Do not use for single minor thoughts, raw capture, generic wiki writing, unsupported conclusions, or direct file modification.
---

# Ob Distill Knowledge

Distill multiple Raw notes or repeated themes into an Obsidian Knowledge stage snapshot. This is a snapshot, not a permanent truth — it must cite sources and state scope.

## When to Use

Only trigger when ALL conditions are met:
- A theme appears repeatedly across multiple conversations or Raw notes
- Multiple Raw notes point to the same judgment
- The judgment affects project decisions
- Raw notes are piling up and becoming hard to find
- A stable stage-level judgment has formed

Do NOT use for:
- Single minor thoughts (use ob-capture-thought instead)
- Raw capture
- Generic wiki writing
- Unsupported conclusions
- Direct file modification

## Core Tasks

1. Distill stage-level judgment.
2. Preserve source Raw references.
3. State scope of applicability.
4. State non-applicability.
5. State open questions.
6. Do not write encyclopedia entries.
7. Do not write temporary judgments as permanent truths.
8. Do not invent sources.

## Output Template

# {{title-as-road-sign}}

## 一句话结论
## 背景
## 核心判断（3-5条）
## 适用范围
## 不适用范围
## 来源 Raw
## 后续问题

## Stop Conditions

- Stop after producing one Knowledge note
- Do not create multiple variants

## Failure Signals

- No source Raw references
- Written as encyclopedia
- Invented conclusions the user never said
- Distills a single minor thought into Knowledge
- Writes temporary judgment as permanent principle
- Removes uncertainty

## Resources

### references/
- [knowledge-principles.md](references/knowledge-principles.md)
- [raw-to-knowledge-rules.md](references/raw-to-knowledge-rules.md)
- [source-linking-rules.md](references/source-linking-rules.md)
- [anti-wiki-writing.md](references/anti-wiki-writing.md)

### templates/
- [templates/knowledge-note-template.md](templates/knowledge-note-template.md)

### examples/
- [examples/skill-system-knowledge.md](examples/skill-system-knowledge.md)
- [examples/obsidian-ai-readable-knowledge.md](examples/obsidian-ai-readable-knowledge.md)
- [examples/mobile-agent-route-knowledge.md](examples/mobile-agent-route-knowledge.md)

### tests/
- [tests/should_cite_raw_source.md](tests/should_cite_raw_source.md)
- [tests/should_not_invent_conclusion.md](tests/should_not_invent_conclusion.md)
- [tests/should_be_stage_snapshot.md](tests/should_be_stage_snapshot.md)
- [tests/should_not_distill_single_minor_thought.md](tests/should_not_distill_single_minor_thought.md)
