# Handoff to Route Judge

当 2+ 路线通过审查时，生成以下 prompt 给 route-judge：

---
给 route-judge 的排序 prompt：

请对以下通过审计的候选路线进行排序。输入来自 idea-auditor。

[list routes with audit conclusions]

请输出：
1. 第一推荐
2. 第二推荐
3. 暂时不要碰
4. 未来再考虑
5. 最小验证实验
