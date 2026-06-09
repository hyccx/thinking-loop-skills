# Handoff to Idea-Auditor — Expanded Audit Prompt Template

Use this template for complex expansions (deep-expansion-mode or any expansion with 3+ triggers). For small expansions, use the abbreviated handoff in SKILL.md.

---

给 idea-auditor 的审查 prompt：

## 扩展上下文

本次扩展触发了以下触发器：[list triggers used]
原始输入：[user's original idea or question]
扩散输出摘要：[1-2 sentence summary of what was produced]

## 审查要点

请逐一判断：

1. **需求真实性**
   - 哪些扩散方向反映的是真实 user need？
   - 哪些只是看起来有趣但与用户实际场景无关？

2. **落地可行性**
   - 哪些方向值得做成 skill / mode / reference / example / test？
   - 哪些方向应该放在现有系统中，而不是新建？

3. **过度设计检查**
   - 哪些方向有过度设计的风险？
   - 哪些方向现阶段不应该落地？

4. **反系统检查**
   - 本次扩散是否默认假设了"需要系统化"？这个假设成立吗？
   - 这个思路有没有更好的非系统化处理方式（一次记录、一个example、一个小script）？

5. **优先级建议**
   - 最值得投入的 1-2 个方向是什么？
   - 哪些方向应该立刻搁置？

6. **最小可行版本**
   - 基于扩散结果，最小可行版本应该包含什么？
   - 最小可行版本不应该包含什么？

---

Return the audit results as structured output with clear judgments. Include a recommendation for next step (expand further, build MVP, or abandon).
