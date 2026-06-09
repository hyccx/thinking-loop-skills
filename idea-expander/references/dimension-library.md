# Dimension Library — Scan Dimensions

Use these dimensions when performing a dimension-scan. Each represents a different analytical axis.

## Structural Dimensions
- **隐喻维度** (Metaphor): What system metaphor fits the concept? (car, body, city, game, etc.)
- **关系维度** (Relationship): How do parts connect? Who depends on whom?
- **边界维度** (Boundary): Where does this system end and the outside world begin?

## Process Dimensions
- **动作维度** (Action): What actions happen inside this system? Create, read, update, delete, notify, approve, reject?
- **流程维度** (Process): What is the flow? Linear, branching, looping, event-driven?
- **信息形态维度** (Information Form): Data, metadata, config, state, log, cache, index?

## Quality Dimensions
- **风险维度** (Risk): Where can it break? What fails silently?
- **时间维度** (Time): Real-time, batch, async, scheduled, on-demand?
- **确定性维度** (Certainty): Deterministic or probabilistic? Predictable or emergent?

## Human Dimensions
- **权限维度** (Authority): Who can do what? What are the permission boundaries?
- **体验维度** (Experience): What is the feel? The friction points? The delight moments?
- **身份维度** (Identity): Who is this for? What role does it assume?

## Judgment Dimensions
- **价值观维度** (Values): What values are embedded in this design? (privacy, speed, flexibility, simplicity)
- **目的维度** (Purpose): What is the actual goal? Does the design serve the goal or has it drifted?
- **反系统维度** (Anti-System): Should this even be a system? Or is it over-engineered?

## Evolution Dimensions
- **状态维度** (State): What states can this be in? Loading, empty, error, active, archived?
- **演化维度** (Evolution): How will it grow? What becomes tech debt? What gets rewritten?
- **反面维度** (Inverse): What is the opposite of this system? What are we excluding?

## Usage
- Default scan: pick 4-6 dimensions most relevant to the user's domain.
- If user asks for "full scan": pick up to 8.
- Always include 反系统维度 in scans for skill/system ideas — it prevents over-engineering.
