# Boundary Conflicts — Detecting and Resolving Skill Overlaps

## How to Detect an Overlap

Two skills overlap when a single user input could reasonably trigger both, and both would produce substantially similar output.

### Detection Methods

1. **Description overlap**: Compare the "description" fields of two SKILL.md frontmatter files. If more than 40% of the trigger phrases appear in both, there is an overlap risk.

2. **Output similarity**: Feed the same test input to both skills. If the outputs share more than 50% of their content or structure, the skills overlap.

3. **User confusion**: If the user has asked "should I use X or Y for this?" more than once, the boundary is unclear.

## Resolution Strategies

### Strategy 1: Delegate (Preferred)
One skill handles the shared scenario and explicitly delegates to the other for other scenarios.
- Add to Skill A's workflow: "If the user needs [thing], first run [skill], then produce output."
- Add to Skill B's "Do NOT use when": "Use skill-maintainer instead."

### Strategy 2: Merge
The overlapping functionality is core to both skills. Merge them into one skill with multiple modes.
- Create a new mode in the surviving skill.
- Deprecate the other skill (see deletion-criteria.md).

### Strategy 3: Differentiate
Both skills are worth keeping, but their entry points need to be more distinct.
- Tighten each skill's description frontmatter to exclude the other's domain.
- Add explicit exclusion phrases: "Do NOT use for [other skill's domain]."
- Add example inputs showing when to use which.

## Common Overlap Pairs

- **idea-expander vs skill-maintainer**: Both can analyze a skill. Differentiate: idea-expander opens possibilities; skill-maintainer diagnoses problems.
- **need-extractor vs idea-expander**: Both can handle vague inputs. Differentiate: need-extractor strips down to real need; idea-expander opens up into multiple angles.
- **skill-maintainer vs idea-auditor**: Both can review. Differentiate: skill-maintainer fixes skills; idea-auditor judges whether expanded directions are worth pursuing.

## Avoided Overlaps

Do NOT create skills with these overlapping purposes:
- Two skills that both "analyze requirements"
- Two skills that both "audit design decisions"
- Two skills that both "write Obsidian notes"
