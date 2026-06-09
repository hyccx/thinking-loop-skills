# Example: Skill System Idea Expansion

## Input

> 我想建一个叫 "thought-catcher" 的 skill，用来在 Obsidian 里捕捉零散的思考想法。但我不确定它应该是一个独立的 skill，还是 need-extractor 的一个 mode。帮我扩散一下这个想法。

## Expansion Output

### 1. 当前默认视角
你在以 skill-maintainer 的视角思考一个新 skill 的定位。

### 2. 本次触发的扩散器
- **recombination** — 因为你问的是"独立 skill 还是已有 skill 的 mode"
- **anti-system-check** — 因为新建 skill 需要先排除"不需要系统化"的情况

### 3. 扩散结果

#### recombination
1. **作为 need-extractor 的 mode**: thought-catcher 采集原始素材，need-extractor 分析需求，两者天然互补。可以考虑在 need-extractor 里新增一个 capture-mode。
2. **作为独立 skill**: 如果 thought-catcher 有自己的 workflow（不只是捕捉，还包括 tagging、linking、review-scheduling），独立 skill 更合理。
3. **作为 reference 文件**: 如果只是记录几个模板和 prompts，不需要 skill 结构，放进 references/ 即可。

#### anti-system-check
1. **不一定需要系统化**: 如果你只是想要一个随手记的地方，Obsidian daily note + 几个 template 就够了。
2. **如果只是模板问题**: 你可能不需要 skill，只需要一个 Obsidian template snippet。
3. **建议**: 先手工用一周，看是否真的需要自动化。不需要一开始就设计系统。

### 4. 最值得继续看的方向
- 先作为 need-extractor 的一个 mode 开始，而不是独立 skill
- 同时评估一周内的使用频率

### 5. 不建议继续展开的方向
- 现在就开始设计 thought-catcher 的完整架构
- 现在就想 tagging 和 linking 策略

### 6. 给 idea-auditor 的审查 prompt

请审查上面扩散出的方向，判断：
1. thought-catcher 是真实需求还是"建 skill 成瘾"？
2. 作为 need-extractor mode 和作为独立 skill 的边界在哪里？
3. 是否应该优先尝试 Obsidian template 方案？
