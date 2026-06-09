# Thinking Loop Skills

一套个人思维闭环 Skills。

目标是把模糊想法处理成：

```text
真实需求 → 想法扩散 → 想法审查 → 路线排序 → 下一步行动 → Obsidian 记录
```

---

## Skills

```text
thinking-loop-skills/
├── need-extractor          # 还原真实需求
├── idea-expander           # 扩散想法、维度和视角
├── idea-auditor            # 审查想法是否过度设计
├── route-judge             # 多路线排序
├── project-next-step       # 裁剪下一步行动
├── ob-capture-thought      # 保存 Obsidian Raw
├── ob-distill-knowledge    # 提炼 Knowledge 阶段快照
└── skill-maintainer        # 维护和修复 skills 系统
```

---

## Workflow

完整链路：

```text
need-extractor
→ idea-expander
→ idea-auditor
→ route-judge
→ project-next-step
→ ob-capture-thought
→ ob-distill-knowledge
```

旁路维护：

```text
任意 skill 输出跑偏
→ skill-maintainer
```

注意：这不是每次都必须完整跑一遍。
普通问题只用一个 skill，复杂问题才接力。

---

## Usage

还原真实需求：

```text
$need-extractor

我现在的问题是：
……
```

扩散想法：

```text
$idea-expander

基于这个想法，小小扩散一下：
……
```

审查想法：

```text
$idea-auditor

请审查这个想法是否是真需求、是否过度设计：
……
```

路线排序：

```text
$route-judge

请在下面几个路线里排序：
……
```

下一步行动：

```text
$project-next-step

请把这个方向裁剪成下一步 1-3 个动作：
……
```

保存到 Obsidian Raw：

```text
$ob-capture-thought

请把这次思维变化整理成 Obsidian Raw：
……
```

维护 skill：

```text
$skill-maintainer

这个 skill 的输出让我感觉太长 / 太泛 / 太复杂，请诊断是否需要修改：
```

---

## Status

当前版本：`v1.0.0`
