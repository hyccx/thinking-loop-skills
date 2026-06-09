---
name: idea-expander
description: Use when the user has a new idea, vague direction, project thought, Obsidian structure idea, Agent feature idea, skill-system idea, or asks to expand possibilities, discover missing angles, generate better questions, use analogies, reverse the framing, scan dimensions, or open up thinking. Produce limited idea expansion using trigger-based thinking. Do not use for final decision-making, strict auditing, route ranking, full project planning, Obsidian note writing, or direct file modification.
---

# Idea Expander

## Purpose

Expand a vague idea, project thought, Obsidian structure, Agent feature, or skill-system concept into multiple thinking dimensions. This skill opens possibilities only — it does not make final choices, rank routes, audit, or act. It works by selecting built-in "expansion triggers" that match the user's expressed intent, then producing a bounded, structured output.

## When to Use

Use when the user:
- Has a new idea and wants to explore what it could become
- Has a fuzzy direction and wants missing angles exposed
- Wants to see a problem from different perspectives or dimensions
- Wants better questions or generative prompts for further thinking
- Wants analogies to reframe a concept
- Wants reverse-thinking or minimal-version thinking
- Wants to check if an idea should become a skill, mode, reference, or example
- Wants a gap scan of an existing system

## When Not to Use

Do not use for:
- Final route ranking or decision-making
- Strict auditing or validation
- Full project planning or execution
- Obsidian note writing or capture
- Direct code repair or file modification
- Pure brainstorming with no bounds

## Core Principles

1. Default to limited expansion, not infinite divergence.
2. Default: trigger at most 2 expansion triggers.
3. User explicitly requests "big expansion" / "deep": at most 4 triggers.
4. User says "simple" / "small expansion" / "not too much": at most 1 trigger.
5. Each trigger outputs at most 3 results.
6. Every expansion output MUST include a handoff prompt for idea-auditor.
7. Do not make final choices.
8. Do not generate full project plans.
9. Do not list tools.
10. Do not inflate a small idea into a large system.
11. If the idea is not worth systematizing, say so explicitly — suggest recording as example/mode/reference only.

## Modes

### small-expansion-mode
Trigger: user says "\u7b80\u5355\u70b9 / \u5c0f\u5c0f\u6269\u6563 / \u522b\u592a\u591a / just a little"
Count: 1 trigger, max 3 total results across all triggered items
Template: templates/small-expansion-output.md

### deep-expansion-mode
Trigger: user says "\u5927\u6269\u6563 / \u6253\u5f00\u601d\u8def / \u5168\u9762\u60f3 / open it up"
Count: up to 4 triggers, each max 3 results
Template: templates/deep-expansion-output.md

### dimension-scan-mode
Trigger: user says "\u4ece\u4e0d\u540c\u7ef4\u5ea6\u770b / \u8fd8\u6709\u54ea\u4e9b\u89d2\u5ea6 / \u6211\u53ef\u80fd\u6f0f\u4e86\u4ec0\u4e48"
Behavior: Scan across dimension-library dimensions
Output: templates/dimension-scan-output.md

### perspective-shift-mode
Trigger: user says "\u6362\u4e2a\u89d2\u5ea6 / \u5982\u679c\u6211\u662f xxx / \u4ece\u4e0d\u540c\u89d2\u8272\u770b"
Behavior: Switch to a perspective from perspective-library
Output: templates/perspective-shift-output.md

### meta-question-mode
Trigger: user says "\u6211\u8be5\u600e\u4e48\u7ee7\u7eed\u95ee / \u600e\u4e48\u95ee\u624d\u80fd\u6253\u5f00\u601d\u8def / \u5e2e\u6211\u751f\u6210\u95ee\u9898"
Behavior: Generate open-ended questions using meta-question-patterns
Output: templates/meta-question-output.md

### triggered-expansion-mode (default)
Trigger: no explicit mode request; auto-detect from user phrasing
Behavior: Select 1-2 triggers from trigger-library based on implicit intent
Output: templates/triggered-expansion-output.md

## Trigger Selection

### Explicit trigger mapping

User phrase / expressed intent \u2192 Trigger(s):

- "\u5c0f\u5c0f\u6269\u6563 / \u7b80\u5355\u542f\u53d1 / just a hint" \u2192 small-expansion (1 trigger, fewer results)
- "\u5927\u6269\u6563 / \u6253\u5f00\u601d\u8def / \u5168\u9762\u5c55\u5f00" \u2192 deep-expansion (up to 4 triggers)
- "\u4e0d\u540c\u7ef4\u5ea6 / \u89d2\u5ea6 / scan" \u2192 dimension-scan
- "\u6362\u89c6\u89d2 / \u5982\u679c\u6211\u662f / from the perspective of" \u2192 perspective-shift
- "\u6211\u8be5\u600e\u4e48\u95ee / \u751f\u6210\u95ee\u9898 / better questions" \u2192 meta-question
- "\u53cd\u8fc7\u6765\u60f3 / \u9006\u7740\u6765 / \u4e0d\u505a\u4f1a\u600e\u6837" \u2192 reverse-thinking
- "\u7c7b\u6bd4 / \u50cf\u4ec0\u4e48 / analogy" \u2192 analogy-transfer
- "\u7f3a\u4ec0\u4e48 / \u6f0f\u4e86\u4ec0\u4e48 / gap / missing" \u2192 gap-scan
- "\u98ce\u9669 / \u4ee5\u540e\u4f1a\u4e0d\u4f1a\u590d\u6742 / worst case" \u2192 risk-preplay
- "\u4ee5\u540e\u600e\u4e48\u770b / \u4e09\u4e2a\u6708\u540e / future" \u2192 future-retrospective
- "\u6700\u5c0f\u7248\u672c / \u7b80\u5355\u70b9 / \u53ea\u4fdd\u7559\u6838\u5fc3" \u2192 minimal-version
- "\u65b0\u5efa skill / \u5408\u5e76 / \u653e\u54ea\u91cc / \u5f52\u7c7b" \u2192 recombination (+ anti-system-check)

### Implicit detection (no explicit mode)

When the user doesn't name a mode, scan their phrasing for implicit intent:
- If they describe a concept with no constraints \u2192 default: small-expansion
- If they describe a concept with "worried" / "concerned" / "\u6015" \u2192 risk-preplay
- If they describe a concept they've been thinking about for a while \u2192 future-retrospective + dimension-scan
- If they describe a concept that sounds like it could be a skill \u2192 recombination + anti-system-check
- If they say "\u662f\u4e0d\u662f\u60f3\u590d\u6742\u4e86" / "overthinking" \u2192 anti-system-check
- If they say nothing specific \u2192 triggered-expansion-mode with 2 triggers (prefer dimension-scan + perspective-shift)

## Output Rules

1. Output in the user's language (default Chinese).
2. Default to moderate length \u2014 not too short, not exhaustive.
3. First state the current default perspective.
4. Then state which triggers were invoked and why.
5. Each trigger outputs at most 3 lines.
6. MUST include "Directions not to explore further" section.
7. MUST include the handoff prompt for idea-auditor.
8. Never make a final choice.

## Stop Conditions

1. Stop when enough candidate angles or routes have been generated.
2. Default max: 5 candidate routes.
3. Dimension scan default max: 8 dimension results.
4. If user asked for simple: max 3 total results.
5. If expansion is adding confusion rather than clarity: stop and suggest handoff to idea-auditor.
6. If the idea is not worth systematizing: stop expanding, suggest recording only.

## Failure Signals

The output has gone wrong if it:
- Lists too many directions, making the user more confused
- Makes a final decision
- Generates a full project plan
- Only lists tools
- Does not include a handoff prompt for idea-auditor
- Does not include "directions not to explore further"
- Inflates a small idea into a large system
- Forgets the anti-system check

## Handoff

Every output must end with a handoff that adapts based on context:

---

审查 checklist（可自行判断；如果 idea-auditor 已创建，也可以直接交给它处理）：

请逐一回答：

1. 哪些是真需求？
2. 哪些只是概念上有趣但不值得落地？
3. 哪些会导致过度设计？
4. 哪些应该变成 skill？
5. 哪些只应该变成 mode / reference / example / test？
6. 哪些现在应该搁置？
7. 最小可行版本是什么？

注意：如果 idea-auditor 尚未创建，就先把这份 checklist 作为人工审查清单使用。等 idea-auditor 创建后，再把这段作为正式 handoff prompt 使用。

---

If the idea is small enough (user said "小小扩散"), omit the handoff block and instead write:

记录提示：这个想法比较小，暂时不需要 formal audit。如果后续深入，再交给 idea-auditor。

## Resources

### references/
- [trigger-library.md](references/trigger-library.md) \u2014 12 built-in expansion triggers with descriptions, use cases, and trigger phrases
- [dimension-library.md](references/dimension-library.md) \u2014 Scan dimensions for dimension-scan mode
- [perspective-library.md](references/perspective-library.md) \u2014 Perspectives for perspective-shift mode
- [meta-question-patterns.md](references/meta-question-patterns.md) \u2014 Question templates for meta-question mode
- [expansion-boundaries.md](references/expansion-boundaries.md) \u2014 Boundary definitions and skill scope
- [handoff-to-auditor.md](references/handoff-to-auditor.md) \u2014 Expanded handoff prompt template for complex expansions

### templates/
- [templates/triggered-expansion-output.md](templates/triggered-expansion-output.md) \u2014 Default auto-triggered expansion
- [templates/small-expansion-output.md](templates/small-expansion-output.md) \u2014 Minimal expansion
- [templates/deep-expansion-output.md](templates/deep-expansion-output.md) \u2014 Full expansion
- [templates/dimension-scan-output.md](templates/dimension-scan-output.md) \u2014 Dimension scan
- [templates/perspective-shift-output.md](templates/perspective-shift-output.md) \u2014 Perspective shift
- [templates/meta-question-output.md](templates/meta-question-output.md) \u2014 Meta-question generation

### examples/
- [examples/skill-system-expansion.md](examples/skill-system-expansion.md) \u2014 Expanding a skill-system idea
- [examples/obsidian-expansion.md](examples/obsidian-expansion.md) \u2014 Expanding an Obsidian workflow idea
- [examples/mobile-agent-expansion.md](examples/mobile-agent-expansion.md) \u2014 Expanding a mobile Agent project idea

### tests/
- [tests/should_not_trigger_all_expanders.md](tests/should_not_trigger_all_expanders.md) \u2014 Default mode should not trigger all 12 triggers
- [tests/should_limit_output_when_user_says_simple.md](tests/should_limit_output_when_user_says_simple.md) \u2014 "\u7b80\u5355\u70b9" limits output to 1 trigger
- [tests/should_generate_auditor_prompt.md](tests/should_generate_auditor_prompt.md) \u2014 Every expansion includes auditor handoff
- [tests/should_not_make_final_decision.md](tests/should_not_make_final_decision.md) \u2014 Expander never makes final decisions
- [tests/should_identify_when_not_to_systematize.md](tests/should_identify_when_not_to_systematize.md) \u2014 Anti-system check: not every idea needs a skill

Do NOT read any of these files automatically. Load only when the task or the user's input requires a specific resource.