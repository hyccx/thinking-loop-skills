# Example: Idea-Expander Output Too Broad

## Symptom

User asked: "我想做个自动分类 Obsidian 笔记的插件。简单扩散一下就够了。"

Idea-expander output: Listed 4 triggers, 12 results, 3 pages of text. User complained it was too long.

## Diagnosis

### 1. 是否跑偏
Yes. The user explicitly said "简单扩散一下" (small expansion), but the output used deep-expansion mode.

### 2. 跑偏类型
- 太长 — output exceeded small-expansion limits
- 太泛 — included irrelevant dimensions
- 忘记停止条件 — ignored the "simple" request

### 3. 根因判断
- 根因文件: SKILL.md — Trigger Selection section
- 根因说明: The implicit detection logic does not scan for "简单" / "simple" / "just a little" phrases. It treated the generic input as "no explicit mode" and defaulted to triggered-expansion with 2 triggers, but actually selected 4.

### 4. 最小修改建议
| 操作 | 文件 | 具体内容 |
|------|------|----------|
| edit | SKILL.md ▸ Trigger Selection ▸ Implicit detection | Add: "If the user says '简单扩散' / '简单点' / '小小' / 'just a little' / 'not too much' → override to small-expansion-mode regardless of other signals." |

### 5. 是否需要新增 skill
No. A simple trigger rule addition fixes this.

### 6. 给 Codex 的修改 prompt

## 问题描述
User asks for "简单扩散" but idea-expander outputs deep-expansion.

## 根因
- Skill: idea-expander
- File: SKILL.md
- Section: Trigger Selection > Implicit detection

## 修改内容
**操作**: edit
**目标文件**: C:\Users\86133\.codex\skills\idea-expander\SKILL.md

**修改前**:
### Implicit detection (no explicit mode)
When the user doesn't name a mode, scan their phrasing for implicit intent:

**修改后**:
### Implicit detection (no explicit mode)
When the user doesn't name a mode, scan their phrasing for implicit intent:
- If the user says "简单扩散" / "简单点" / "小小扩散" / "just a little" / "not too much" → override to small-expansion-mode regardless of other signals
