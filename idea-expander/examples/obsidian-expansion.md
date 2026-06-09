# Example: Obsidian Workflow Idea Expansion

## Input

> 我想在 Obsidian 里建立一个"决策日记"系统——每次做重要决策时，记录当时的想法、依据、预期结果，以后回顾时可以知道自己当初为什么这样选。但我不确定这是不是一个好主意，也不知道应该怎么做。

## Expansion Output

### 1. 当前默认视角
你在以一个 Obsidian power-user 的视角设计一个个人知识管理工作流。

### 2. 本次触发的扩散器
- **perspective-shift** — 因为你提到了"以后回顾"，需要切换到未来视角
- **minimal-version** — 因为你不确定这是不是好主意，说明需要验证核心假设

### 3. 扩散结果

#### perspective-shift
1. **未来自己视角**: 三个月后回顾一个决策，你最希望看到什么？很可能不是格式，而是上下文——当时你的情绪、时间压力、可选方案。如果日记只记录了理性决策树，丢失了情绪上下文，三个月后你会觉得"这个记录不够用"。
2. **反对者视角**: "你现在想建系统而不是做决策，这是不是又一种拖延？" 决策日记的收益取决于你做决策的频率。如果一个月才一个重大决策，这个系统 hardly justifies 自己。

#### minimal-version
1. **核心假设**: 你需要的其实不是系统，而是一个 template——每次做决策时复制一个 markdown 模板，填 4 个字段 (Decision / Context / Expected / Actual) 就够了。
2. **最小版本**: 一个 Obsidian template 文件，包含：**# Decision** | **Context** | **Expected Outcome** | **Actual Outcome (填于回顾时)**。不需要 dataview，不需要 graph，不需要链接。
3. **验证方式**: 用这个 template 记录 3 次决策，看它是否有价值。如果有价值，再考虑要不要加 metadata。

### 4. 最值得继续看的方向
- 先做一个最简单的 template，不要建系统
- 用 3 次决策来验证是否真的需要这个习惯

### 5. 不建议继续展开的方向
- Dataview 查询、dashboard、统计面板——还不到时候
- 和已有 Obsidian 系统整合——先验证核心价值
- 分类体系、标签策略——会变成拖延

### 6. 给 idea-auditor 的审查 prompt

请审查上面扩散出的方向，判断：
1. "决策日记"是真实长期需求还是临时冲动？
2. template 方案足够吗？还是需要更结构化的支持？
3. 这个 idea 值得做成 skill 吗？还是应该留在 Obsidian 内部使用？
