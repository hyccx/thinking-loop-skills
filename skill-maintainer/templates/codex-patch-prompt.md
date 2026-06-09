# Codex Patch Prompt Template

Use this template to generate the final patch prompt. The prompt should be self-contained: Codex should be able to execute it without additional context.

---

## 问题描述

[1 sentence describing what went wrong]

## 根因

- Skill: [skill name]
- File: [file path relative to skill root]
- Line / Section: [specific location]

## 修改内容

**操作**: [edit / add / delete]
**目标文件**: [absolute or relative path]

**修改前** (如果是 edit):
```
[existing content]
```

**修改后**:
```
[new content]
```

## 验证方式

[1 sentence describing how to verify the fix works]

---

## Notes

- If the change is an add (new file), write "[new file]" in the "修改前" section.
- If the change is a delete, write "[delete entire file]" in the "修改后" section.
- Be specific about the file path so Codex can open it without searching.
