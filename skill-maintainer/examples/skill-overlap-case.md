# Example: Skill Overlap Between Idea-Expander and Skill-Maintainer

## Symptom

User asked: "帮我看看 need-extractor 的输出，我觉得方向不太对。"

Both idea-expander and skill-maintainer could handle this. Idea-expander would expand possibilities; skill-maintainer would diagnose the problem. The user got confused about which skill to invoke.

## Diagnosis

### 1. 是否跑偏
Yes — this is a boundary overlap, not a single skill output problem.

### 2. 跑偏类型
- 职责重叠 — both skills claim they can handle "skill output review"
- 触发不准 — the user's input matches two descriptions

### 3. 根因判断
- 根因文件: Both SKILL.md descriptions
- 根因说明: idea-expander description says "skill-system idea" as a trigger; skill-maintainer says "skill output is unsatisfactory" as a trigger. The phrase "skill output review" appears in both implicitly.

### 4. 最小修改建议
| 操作 | 文件 | 具体内容 |
|------|------|----------|
| edit | idea-expander SKILL.md ▸ "When Not to Use" | Add: "Diagnosing skill output problems — use skill-maintainer instead" |
| edit | skill-maintainer SKILL.md ▸ "When to Use" | Add: "When a skill output needs diagnosis — even if the user doesn't explicitly say 'diagnose'" |

### 5. 是否需要新增 skill
No.

### 6. 给 Codex 的修改 prompt

## 问题描述
User input about skill output quality triggers both idea-expander and skill-maintainer.

## 根因
- Skill: idea-expander
- File: SKILL.md
- Section: When Not to Use

## 修改内容
**操作**: edit
**目标文件**: C:\Users\86133\.codex\skills\idea-expander\SKILL.md

在 "When Not to Use" 中追加:
- Diagnosing skill output problems or suggesting fixes \u2014 use skill-maintainer instead

---

## 问题描述
Also add clarifying trigger to skill-maintainer.

## 根因
- Skill: skill-maintainer
- File: SKILL.md
- Section: When to Use

## 修改内容
**操作**: edit
**目标文件**: C:\Users\86133\.codex\skills\skill-maintainer\SKILL.md

在 "When to Use" 中追加:
- A skill's output needs diagnosis, even if the user phrase doesn't explicitly say "diagnose" or "fix"
