# Perspective Library — Common Viewpoints

Use these perspectives when performing a perspective-shift. Each represents a different stakeholder or observer.

## Common Perspectives

### 用户视角 (User Perspective)
What does the end-user experience? What do they see, feel, stumble on? This is usually the most important perspective but the most often skipped during design.

### 维护者视角 (Maintainer Perspective)
How does this system feel to maintain? Is the cognitive load sustainable? Will the maintainer understand it in 6 months?

### 反对者视角 (Critic / Opponent Perspective)
Why should this NOT be built? What arguments would kill it in a design review? What is its weakest structural point?

### 未来自己视角 (Future-Self Perspective)
Three months from now, would you thank yourself for building this? Or curse yourself?

### Codex 视角 (Codex / Agent Perspective)
How does this appear to an AI agent? Is the system legible? Are the rules explicit? Can the agent make safe and correct decisions without ambiguity?

### Obsidian 视角 (Obsidian / Knowledge-Base Perspective)
How does this fit into an existing knowledge management system? Does it add structure without adding friction? Is it retrievable?

### skill-maintainer 视角 (Skill Maintainer Perspective)
If this becomes a skill, how hard is it to maintain? Does it introduce versioning complexity? Does it need its own scripts and tests?

### 初学者视角 (Beginner Perspective)
How would someone with no context encounter this? What is the first impression? What is the onboarding cost?

### 执行者视角 (Doer / Executor Perspective)
Who actually does the work? What is the effort-to-value ratio? Is this actionable?

### 旁观者视角 (Bystander / Neutral Observer Perspective)
Does this system look healthy from the outside? Is it elegant or over-constructed? What would an impartial third party notice?

## Usage
- Default shift: pick 2-3 contrasting perspectives (e.g., user + critic, or beginner + future-self).
- If user asks for "full shift": pick up to 5.
- The most valuable pair is usually 用户视角 + 反对者视角 — they reveal both the desire and the risk.
