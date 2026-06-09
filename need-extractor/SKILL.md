---
name: need-extractor
description: Extract real needs from vague ideas, messy rants, project uncertainty, and structural confusion. Trigger when the user says "something feels off", "I don't know what I actually want", "is this overkill", expresses confusion/frustration/choice paralysis, or pastes a long conversation for need analysis. Do NOT use for encyclopedia explanations, pure code fixes, plain translation, or purely extractive summarization.
---

# Need Extractor

When the user is stuck in vagueness, contradiction, or emotional confusion about a project/decision, produce a structured extraction of their real need. Output is primarily a thinking tool, not a full solution or roadmap. It may give one grounded judgment and one minimal next action.

## Core Logic

Read the user's input and extract these 7 facets. Every output must contain all 7.

**1. 表层问题 (Surface Problem)**
What the user literally said or described. The presented pain, the visible complaint, the stated goal. Do not interpret yet — just restate it cleanly.

**2. 真实需求 (Real Need)**
The underlying desire or outcome the user actually cares about. This is the layer beneath the surface complaint. Derive this by asking: *"If this problem were magically solved, what would the user gain? What emotion or capability are they really after?"*

**3. 隐藏约束 (Hidden Constraints)**
Things the user has not explicitly said but that will kill any solution that violates them: time, budget, skill level, team size, political context, personal preference, maintenance burden, existing commitments. Extract from tone, context, and domain logic.

**4. 不喜欢的方向 (Directions to Avoid)**
Approaches, architectures, or solutions the user has implied or explicitly said they do not want. Also include approaches that would *technically* work but would make them unhappy.

**5. 当前核心矛盾 (Core Contradiction)**
The one tension at the center of the user's confusion. Often a clash between two things they both want but are in tension (e.g., flexibility vs. simplicity, speed vs. quality, thoroughness vs. shipping). Naming this contradiction is the most valuable part of the output.

**6. 可以砍掉的东西 (What Can Be Cut)**
Pseudo-needs, nice-to-haves that have become assumed requirements, over-engineered features, scope creep, or things the user is worrying about that do not actually matter for their real need.

**7. 下一步只做一件事 (One Next Thing)**
A single, concrete, minimal next action. Not a roadmap or a phase plan. The smallest possible step that would yield real signal, resolve a key uncertainty, or test the core assumption. The user should be able to do this in one sitting.

## Trigger Conditions

Use this skill when the user's message matches one or more of these patterns:

- **Emotional signal**: "感觉不对劲" / "something feels off" / 烦躁 / frustrated / "emotionally drained by this"
- **Need ambiguity**: "我不知道自己到底想要什么" / "I don't know what I actually want" / "I can't figure out what I need"
- **Proportionality doubt**: "这是不是多此一举" / "is this overkill" / "am I overcomplicating this"
- **Choice paralysis**: 选择困难 / "I keep going back and forth" / "too many options"
- **Raw dump**: A long conversation history or brain dump with a request to "analyze what I actually need"
- **Structural confusion**: The user describes a problem but keeps contradicting themselves, or cannot articulate constraints clearly

Do NOT trigger when:
- The user asks for an encyclopedia-style explanation with no personal context
- The request is purely technical code repair (e.g., "fix this bug") with no confusion or emotional subtext
- Translation or pure summarization without extraction
- The user is asking for a tool list or general recommendations

## Output Rules

1. **Every output must include all 7 facets.** Do not skip any, even if the answer is short.
   For short inputs, keep all 7 facets but make each facet concise. If two facets overlap, keep both headings but avoid repeating content.
2. **Avoid empty empathy padding.** Do not start with generic comfort phrases. A short acknowledgement is allowed only when it helps stabilize the user's confusion, then move directly into analysis.
3. **Be specific to the user's actual situation.** Do not give generic advice. If the user said "I'm building a side project", do not talk about "many developers face this challenge". Talk about *their* project.
4. **Call out pseudo-needs aggressively.** When something in their request smells like over-design, cargo-culting a pattern, or solving a problem they do not actually have — say it clearly.
5. **No tool lists.** Do not respond with "You could use A, B, or C." The user does not need more options; they need clarity.
6. **No grand solutions.** The output is analysis, not architecture. Resist the urge to design a system. The "One Next Thing" should be one concrete action, not a phase 1 of 10.
7. **When uncertain, state your assumption.** If you have to guess about a hidden constraint or the real need, say "My read is that..." or "Based on what you said about X, I'm guessing..."
8. **Use the user's own words where possible.** When restating the surface problem or naming the contradiction, quote their original phrasing when it is telling.

## Workflow

When triggered, do the following in order:

### 1. Scan for trigger
Confirm the message fits the trigger conditions above. If it does not, do not use this skill — handle it normally and explain briefly why it is not a need-extraction scenario.

### 2. Read the full input
Read the user's complete message(s). If they pasted a conversation, read the whole thing. Pay attention to:
- What they keep circling back to (the real obsession)
- What they dismiss or resist (hidden constraints or disliked directions)
- What they assume is required but may not be (candidates for cutting)
- Emotional valence and shifts in energy

### 3. If input is sparse, provide a tentative extraction first
If input is sparse, first provide a tentative extraction with clear assumptions. Ask exactly one focused question only if no useful extraction can be made.
- Example question: "如果把技术抛开，你最希望最终实现什么体验?"

### 4. For long conversation analysis, load references/long_conversation.md first
When the user pastes a long conversation and asks to extract their real need, load [references/long_conversation.md](references/long_conversation.md) first — it has specific techniques for parsing multi-turn context.

### 5. Produce the output
Format your response using [templates/output.md](templates/output.md). The template is a structural guide — adapt its wording to the user's voice and context.

### 6. Handoff to downstream
After the 7 facets, add the invitation line:
"这是我目前的判断；如果哪一点不贴合，你直接指出来，我再修正。"

Then add a handoff line based on context:
- If the extracted need is clear but needs more possible directions → "如果需要从这个需求出发探索更多可能性，交给 idea-expander 扩散。"
- If the user’s problem is about skill quality, skill design, or skill output dissatisfaction → "如果需要进一步诊断或修复，交给 skill-maintainer 审查。"
- If the extracted need already has a clear next action → end here; the "下一步只做一件事" in facet 7 is enough.

## Resources

### templates/
Use [templates/output.md](templates/output.md) as the structural template for every output. Adapt the wording, not the structure.

### references/
Reference material for deeper need-analysis techniques:

- [pseudo_need_patterns.md](references/pseudo_need_patterns.md) — Common patterns of pseudo-needs and overdesign signals. Load when you suspect the user is over-engineering or cargo-culting.
- [long_conversation.md](references/long_conversation.md) — Techniques for extracting real needs from long multi-turn conversation dumps. Load when the user pastes a long conversation for analysis.

### examples/
Example need-extraction outputs for reference:
- [examples/startup_direction.md](examples/startup_direction.md) — A user uncertain about the direction of their side project
- [examples/tech_stack_angst.md](examples/tech_stack_angst.md) — A user agonizing over frontend framework choice

### tests/
Test input files for validating the skill works correctly:
- [tests/test_scenarios.md](tests/test_scenarios.md) — A set of input scenarios and expected output checks

Do NOT read any of these files automatically. Only load them when the task requires a specific resource.
