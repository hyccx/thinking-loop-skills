---
name: skill-maintainer
description: |
  Diagnose skill failures and produce minimal, targeted modifications.
  Use when a skill output is unsatisfactory: too generic, too long, too rigid,
  too complex, wrong trigger, overlap, boundary violation, no next action,
  or skill structure repair.
  Do not use for idea expansion, project planning, note writing, or brainstorming.
  Default behavior: review first, read only the target SKILL.md unless needed,
  and prefer the smallest viable fix.
---

# Skill Maintainer

## 1. Purpose

Diagnose skill failures and produce minimal, targeted modifications. This is a meta-skill for maintaining the Codex skills system itself.

It does NOT solve the user's original problem. It fixes the skill that was supposed to help with that problem.

Execution depth adapts to task complexity: Mini (review only), Normal (review + modify one skill), Full (batch/deep maintenance).

## 2. Lean Mode

Lean Mode is the default execution posture. It means:

- Default: do only the maintenance task the user explicitly asked for
- Default: read only the target skill's SKILL.md
- Do NOT automatically read references/, examples/, or tests/
- Do NOT default to batch modifications
- Do NOT default to long reports
- Do NOT default to proposing many alternatives
- Default to the smallest viable modification

Lean Mode applies across all execution modes. Each mode (Mini/Normal/Full) specifies how strictly Lean is applied.

## 3. Compact Rules

These rules override all other guidance when they apply:

1. **Default to existing.** Fix the current skill. Do NOT create a new one.
2. **Default to small.** Prioritize adding examples, tests, or references over rewriting SKILL.md.
3. **One-off filter.** If the issue happened once and is not recurring, do NOT change rules.
4. **One target at a time.** Do NOT process multiple skills unless explicitly asked.
5. **Resource discipline.** Default: only the target SKILL.md. See Resource Reading Policy below.
6. **Detailed diagnostic rules** are in `references/full-rules.md`. Load only when needed (Full Mode, or when SKILL.md alone is insufficient).

## 4. When to Use

Use when:
- A skill output was too generic, too long, too rigid, or too complex
- A skill triggered when it should not have, or did not trigger when it should have
- Two skills overlap in responsibility or violate boundaries
- A skill output lacks a next-action, handoff, or stop condition
- A skill inflated a small idea into a whole system
- A skill forgot to check anti-system conditions
- You are deciding: modify existing skill, add mode/reference/example/test, or create new skill

Do NOT use for:
- Normal idea expansion (use idea-expander)
- Project planning (use project-next-step)
- Obsidian note writing (use ob-capture-thought)
- General brainstorming
- Final route ranking

## 5. Mini Mode

Trigger: User says "看看这个 skill 怎么样", "要不要优化一下", or similar low-commitment review request.

Behavior:
- Review only. Do NOT modify any files.
- Read the target skill's SKILL.md (Lean Mode).
- Output: current issues, whether a fix is needed, and the minimal change scope.
- Output Budget: ≤500 中文字.
- Do NOT generate a patch prompt. Only describe what would need to change and why.

## 6. Normal Mode

Trigger: User names a specific skill and asks for a fix, optimization, or structure repair. This is the default when Mini Mode criteria are not met.

Behavior:
- Review the target skill and output a modification plan.
- Only modify when the user explicitly asks for modification, or the current request already clearly requires it.
- Only change necessary files. Default priority: SKILL.md > references/ > examples/ > tests/.
- If detailed rules need to be migrated, create or update `references/full-rules.md`.
- Read additional resources only when needed to verify the fix.
- Output Budget: ≤1000 中文字 (plan + changes + outcome).
- After modification, output: which files changed, new file structure, whether original capability is preserved, behavioral changes.

## 7. Full Mode

Trigger: Only enabled when the user explicitly asks for "批量处理", "全量审查", "深度修复", "迁移多个 skill", or similar batch/deep maintenance.

Behavior:
- Can read multiple skills.
- Can read references/, examples/, tests/.
- Still output scope and plan before starting.
- Output Budget: ≤1500 中文字 unless the user explicitly asks for a full report.
- After modification, output the same summary as Normal Mode, plus cross-skill impact notes.

## 8. Resource Reading Policy

Default (Lean): read only the target skill's SKILL.md.

Read additional resources ONLY when:
- The user explicitly asks
- SKILL.md alone is insufficient to determine original capability
- Examples/tests need verification
- Detailed rules need to be migrated to references/
- A reference file's usage needs to be confirmed

Do NOT proactively read all references/, examples/, or tests/ for "safety". Read on demand.

### references/

- `references/full-rules.md` — Detailed diagnostic rules: full diagnosis steps, full deviation types, core principles, failure signals
- `references/patch-strategy.md` — Patch decision tree
- `references/anti-bloat-principles.md` — Principles to prevent skill bloat
- `references/failure-patterns.md` — Expanded failure patterns with examples
- `references/boundary-conflicts.md` — Boundary overlap detection and resolution
- `references/deletion-criteria.md` — Skill deprecation and deletion criteria

### templates/

- `templates/diagnosis-output.md` — Output structure template
- `templates/codex-patch-prompt.md` — Modification prompt template

## 9. Output Budget

| Mode | Budget |
|---|---|
| Mini | ≤500 中文字 |
| Normal | ≤1000 中文字 |
| Full | ≤1500 中文字 (unless user explicitly asks for full report) |

"Budget" counts the diagnostic/maintenance output, not the user's original question or the SKILL.md content being referenced.

## 10. Early Stop Rules

Stop when:
- The smallest viable modification has been identified and applied.
- Do NOT make a simple skill complex.
- Do NOT add useless fields just to follow a template.
- Do NOT process multiple skills unless explicitly asked.
- Do NOT mistake "optimizing execution control" for "removing detailed capability".
- If the target skill is already correct for Lean Mode, output "No change needed" and stop.
- If the issue is a one-off, output "One-off — no rule changes needed" and stop.

## 11. Output Format

Select relevant sections based on mode and whether modification was performed.

### Mode
[Which mode was used: Mini / Normal / Full. Reason for choosing this mode.]

### Diagnosis
[Is the skill off-track? Yes/No with brief justification. Applicable deviation types. Root cause and file.]

### Modification Plan (Mini: optional when fix needed. Normal/Full: required.)
[What would need to change, in which file, why.]

### Changes Applied (Only when files were actually modified)
[Which files changed, new file structure, whether original capability preserved.]

### Behavioral Changes (Only when files were actually modified)
[How behavior changes before vs after. What stays the same.]

### Next Steps
[Optional. What the user should verify or try next.]
