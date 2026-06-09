---
name: need-extractor
description: Extract real needs from vague ideas, messy rants, project uncertainty, and structural confusion. Trigger when the user says "something feels off", "I don't know what I actually want", "is this overkill", expresses confusion/frustration/choice paralysis, or pastes a long conversation for need analysis. Do NOT use for encyclopedia explanations, pure code fixes, plain translation, or purely extractive summarization. Three modes: Mini (short input), Normal (default), Full (deep/long-conversation).
---

# Need Extractor

When the user is stuck in vagueness, contradiction, or emotional confusion about a project/decision, produce a structured extraction of their real need. Output is primarily a thinking tool, not a full solution or roadmap. It may give one grounded judgment and one minimal next action.

## When to Use

Use this skill when the user's message matches one or more of these patterns:

- **Emotional signal**: "感觉不对劲" / "something feels off" / 烦躁 / frustrated / "emotionally drained by this"
- **Need ambiguity**: "我不知道自己到底想要什么" / "I don't know what I actually want" / "I can't figure out what I need"
- **Proportionality doubt**: "这是不是多此一举" / "is this overkill" / "am I overcomplicating this"
- **Choice paralysis**: 选择困难 / "I keep going back and forth" / "too many options"
- **Raw dump**: A long conversation history or brain dump with a request to "analyze what I actually need"
- **Structural confusion**: The user describes a problem but keeps contradicting themselves, or cannot articulate constraints clearly

Do NOT trigger when:
- The user asks for an encyclopedia-style explanation with no personal context
- The request is purely technical code repair with no confusion or emotional subtext
- Translation or pure summarization without extraction
- The user is asking for a tool list or general recommendations

## Mode Selection

The skill auto-selects a mode based on input length and complexity. The user can also override by mentioning the mode name explicitly.

**Auto-selection rules:**
- **Mini**: input < 100 words / < 3 sentences, no strong emotional or contradiction signal, or user says "brief" / "简单" / "快速". For short, straightforward inputs.
- **Normal** (default): standard need-extraction scenario, moderate-length input, no explicit mode request. For most cases.
- **Full**: user explicitly pastes a long conversation / chat history / retrospective material; or user explicitly requests deep analysis ("全面分析" / "deep review"); or user provides multiple documents or requests batch analysis.

### Mini Mode
Triggered for short inputs. Executes compressed extraction:
- All 7 facets present, each compressed to 1-2 sentences
- Does NOT read any references, templates, examples, or tests
- Output ≤500 Chinese characters
- No handoff to downstream skills unless the user explicitly asks

### Normal Mode (Default)
Standard extraction for moderate-length inputs:
- Standard 7 facets with moderate depth
- Does NOT read references by default
- Output ≤900 Chinese characters
- Handoff per standard rules

### Full Mode
Deep analysis triggered by long conversations or explicit request:
- Full 7 facets with detailed analysis (each facet 1-3 paragraphs)
- Loads references per Resource Reading Policy below
- Loads templates/output.md for structural reference
- Output ≤1500 Chinese characters, unless explicitly asked for a complete report
- Standard handoff to downstream skills

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

## Resource Reading Policy

Default: Do NOT read any files from references/, examples/, templates/, or tests/ automatically.

Only load a reference file when ALL of these are true:
- The current mode allows it (Mini: never; Normal: never; Full: yes)
- AND the specific condition for that file is met (see below)

**Per-file conditions:**
- `references/long_conversation.md`: Load only in Full Mode AND when user explicitly pastes a long conversation / chat history / Codex process / retrospective material
- `references/pseudo_need_patterns.md`: Load only when overdesign signals are clearly present AND mode permits (Normal if stalled, Full always)
- `templates/output.md`: Load only when user explicitly asks for strict format calibration (Full only).
- `examples/`: Only for style calibration or testing, never default
- `tests/`: Only for validation, never default

## Output Budget

- **Mini Mode**: ≤500 Chinese characters (7-facet body; invitation line excluded)
- **Normal Mode**: ≤900 Chinese characters (7-facet body; invitation line excluded)
- **Full Mode**: ≤1500 Chinese characters (unless explicitly asked for a complete report)

These apply to the analysis body only. Handoff lines, resource citations, and the invitation line are excluded from the count.

## Early Stop Rules

Stop expanding and output when any of these conditions is met:

1. **Sparse input**: Input < 3 sentences with no clear emotional signal → output Mini Mode with "my read is..." framing. Optionally ask exactly one focused question, but only if no useful extraction is possible without it.
2. **Core contradiction already clear**: If the central tension is obvious from the first reading → do not re-read the full input. Trust the first read and proceed.
3. **User agreement**: If the user responds with "正确" / "差不多" / "就是这样" / "this is right" → stop analysis. Do not add depth or expansion unless explicitly asked.
4. **Clear next action**: If Facet 7 is obvious and directly actionable → skip handoff to downstream skills unless context explicitly requires it.

## Workflow

Execute depending on the active mode. In all modes, start here:

### Common to all modes

1. **Scan for trigger**: Confirm the message fits Trigger Conditions above. If not, handle normally and explain briefly.
2. **Read input**: Read the user's complete message(s). Pay attention to:
   - What they keep circling back to (real obsession)
   - What they dismiss or resist (hidden constraints / disliked directions)
   - What they assume is required but may not be (cut candidates)
   - Emotional valence and energy shifts
3. **Select mode**: Auto-select per Mode Selection rules. Respect explicit user override.

### Mini Mode Workflow

4a. Extract compressed 7 facets (1-2 sentences each). Do not load any reference files.
5a. Output within Mini Budget. Add the standard invitation line (see Handoff below).
6a. End here. No downstream handoff unless user explicitly requests it.

### Normal Mode Workflow

4b. Extract standard 7 facets. Apply the output structure from memory; do not read templates/output.md unless user explicitly requests format calibration.
5b. If pseudo-need signals are present, use knowledge of pseudo_need_patterns.md patterns in memory. Do not load the file unless analysis stalls.
6b. Output within Normal Budget. Add the standard invitation line.
7b. Handoff per Handoff rules below.

### Full Mode Workflow

4c. Load templates/output.md for structural reference.
5c. If the user pasted a long conversation, load references/long_conversation.md. Use its multi-pass scanning strategy:
   - Pass 1: Skim for emotional markers
   - Pass 2: Map the contradiction
   - Pass 3: Identify orbiting assumptions
   - Pass 4: Find the one unresolved question
6c. If overdesign signals are present, load references/pseudo_need_patterns.md for sharper pattern-matching.
7c. Extract full 7 facets with depth. Each facet may be 1-3 paragraphs.
8c. Output within Full Budget (or full report if explicitly requested). Add the standard invitation line.
9c. Handoff per Handoff rules below.

### Handoff (all modes)

After the 7 facets, add:
"这是我目前的判断；如果哪一点不贴合，你直接指出来，我再修正。"

Then context-dependent handoff:
- Clear need but needs exploration → "如果需要从这个需求出发探索更多可能性，交给 idea-expander 扩散。"
- Skill quality / design / dissatisfaction → "如果需要进一步诊断或修复，交给 skill-maintainer 审查。"
- Clear next action already → end here; Facet 7 is enough.

## Output Rules

1. **Every output must include all 7 facets.** Do not skip any. Keep all 7 headings even if a facet is short.
2. **Avoid empty empathy padding.** A short acknowledgement is allowed only to stabilize confusion, then move directly into analysis.
3. **Be specific to the user's actual situation.** Do not give generic advice. Talk about *their* project.
4. **Call out pseudo-needs aggressively.** Quote the user's own words; frame as observation, not accusation.
5. **No tool lists.** Do not respond with "You could use A, B, or C."
6. **No grand solutions.** Output is analysis, not architecture. Facet 7 must be one concrete action.
7. **When uncertain, state your assumption.** Use "My read is that..." or "Based on what you said about X, I'm guessing..."
8. **Use the user's own words where possible.** Quote their original phrasing when it is telling.

## Resources

### templates/
[templates/output.md](templates/output.md) — Structural template for 7-facet output. Load only per Resource Reading Policy.

### references/
Reference material for deeper need-analysis techniques:

- [pseudo_need_patterns.md](references/pseudo_need_patterns.md) — Common patterns of pseudo-needs and overdesign signals. Load when you suspect the user is over-engineering or cargo-culting.
- [long_conversation.md](references/long_conversation.md) — Techniques for extracting real needs from long multi-turn conversation dumps. Load when the user pastes a long conversation for analysis.

### examples/
Example need-extraction outputs:
- [examples/startup_direction.md](examples/startup_direction.md) — Side project direction uncertainty
- [examples/tech_stack_angst.md](examples/tech_stack_angst.md) — Frontend framework choice anxiety

### tests/
Test input files for validation:
- [tests/test_scenarios.md](tests/test_scenarios.md) — Input scenarios and expected output checks
