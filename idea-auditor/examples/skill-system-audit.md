# Example: Skill System Idea Audit

## Input (from idea-expander output)
Candidate routes:
1. Make thought-catcher a need-extractor mode
2. Make thought-catcher an independent skill
3. Use Obsidian daily note template instead

## Output

### 审查对象
thought-catcher 的三个候选处理方式。

### 它想解决的问题
在 Obsidian 中捕捉零散思考想法，不让它们丢失。

### 真需求判断
真需求。用户有捕捉习惯但缺乏结构。需要最低门槛的记录方式。

### 过度设计风险
路线2（独立 skill）过度设计。用户还没有验证"使用捕捉"这个习惯本身。

### 维护成本判断
路线1（作为 mode）维护成本低，复用 need-extractor 已有结构。
路线3（template）维护成本几乎为零。

### 审查结论
- 路线1: 保留
- 路线2: 暂时搁置
- 路线3: 保留

### Handoff
2条路线保留，生成给 route-judge 的 prompt。
