# Example: Mobile Agent Audit

## Input (from idea-expander)
Focus on "summarize WeChat conversations" only, local processing.

## Output

### 审查对象
微信聊天总结功能，本地处理。

### 它想解决的问题
微信聊天记录过多，无法快速回顾。

### 真需求判断
真需求。但技术实现依赖 accessibility service，风险高。

### 维护成本判断
高。微信版本更新可能随时中断。

### 审查结论
- 修改后保留：先人工流程验证需求，再做自动化。
- 最小版本：每周手动复制一段重要对话到 GPT，看总结是否真的有用。

### Handoff
1 条路线保留，建议交给 project-next-step。
