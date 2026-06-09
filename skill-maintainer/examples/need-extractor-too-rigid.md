# Example: Need-Extractor Output Too Rigid

## Symptom

User asked: "我感觉最近写代码越来越没动力，不知道是不是方向错了，还是单纯累了。"

Need-extractor output: Produced all 7 facets mechanically. Started with "表层问题: 你感觉写代码没动力" and went through each heading. The user said it felt like a template fill-in rather than a real conversation.

## Diagnosis

### 1. 是否跑偏
Partially. The output followed the 7-facet structure correctly, but the delivery felt rigid. The problem is in tone adaptation, not structure.

### 2. 跑偏类型
- 太硬 — output was mechanically structured
- 太泛 — didn't use the user's specific words enough

### 3. 根因判断
- 根因文件: templates/output.md
- 根因说明: The template says "write the 7 facet labels in Chinese" but doesn't instruct to adapt the tone or hide the template structure. The template structure is visible in the output, making it feel like a form.

### 4. 最小修改建议
| 操作 | 文件 | 具体内容 |
|------|------|----------|
| edit | templates/output.md | Add a "Tone Adaptation" section: "Do not output the facet numbers as headings. Integrate the 7 points into flowing prose. The structure should be invisible to the reader." |
| add | examples/ | Add an example showing the adapted version vs the mechanical version |

### 5. 是否需要新增 skill
No.

### 6. 给 Codex 的修改 prompt

## 问题描述
Need-extractor output feels like a fill-in-the-blank form instead of natural analysis.

## 根因
- Skill: need-extractor
- File: templates/output.md
- Section: Adaptation Rules

## 修改内容
**操作**: edit
**目标文件**: C:\Users\86133\.codex\skills\need-extractor\templates\output.md

在 Adaptation Rules 末尾追加:
- The output structure (7 facets) should be invisible to the reader. Do not output "1. 表层问题" as a heading. Integrate the facets into flowing paragraphs. Use the user's own phrasing throughout.
