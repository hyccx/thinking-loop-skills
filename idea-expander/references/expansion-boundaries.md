# Expansion Boundaries — What Idea Expander Does and Does Not Do

## What idea-expander IS responsible for

1. Opening possibilities from a vague starting point
2. Selecting and applying relevant expansion triggers
3. Producing bounded, structured output
4. Generating a handoff prompt for idea-auditor
5. Identifying directions that should not be explored further
6. Performing anti-system checks

## What idea-expander is NOT responsible for

### NOT responsible for final review
Expansion produces candidates, not conclusions. The review and judgment role belongs to idea-auditor. If idea-auditor does not exist yet, the output must still contain the audit prompt — another agent or the user can perform it manually.

### NOT responsible for route ranking
Idea-expander does not weigh options, rank directions, or assign priority scores. Ranking belongs to route-judge.

### NOT responsible for project execution
Idea-expander does not generate timelines, task lists, milestone plans, or resource estimates. Execution belongs to project-next-step.

### NOT responsible for Obsidian capture
Idea-expander does not write Obsidian notes, format markdown for a vault, or tag entries. Capture belongs to ob-capture-thought.

### NOT responsible for direct file modification
Idea-expander never creates, modifies, or deletes files in the user's workspace. It is a thinking tool only.

## Fractal Depth Rule

Idea-expander operates at one level of expansion depth per invocation:
- Each trigger produces at most 3 direct results.
- Those results are NOT recursively expanded.
- If the user wants deeper expansion, they must explicitly ask and the new invocation treats the previous output as a fresh input.

## Boundary Violation Detection

If the user's request crosses into any of the "not responsible" areas, idea-expander should:
1. Decline to perform the out-of-scope action.
2. Suggest the correct skill for that action.
3. Return to expansion.

Example:
- User: "帮我选一个方向" (help me pick one direction)
- Response: "Idea-expander 不负责选择方向。我帮你扩散了 3 个候选方向，下面你可以把输出交给 idea-auditor 做审查，然后由 route-judge 做排序。"
