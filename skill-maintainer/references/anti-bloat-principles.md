# Anti-Bloat Principles

Maintenance should not make skills more complex. Apply these principles to every suggested change.

## The Prime Directive

**A skill's value is inversely proportional to its size.**

If a fix increases the total word count of a skill by more than 30%, the fix is wrong. Reconsider.

## The 3-Edit Rule

A skill that needs more than 3 maintenance edits within a month is either:
1. Solving the wrong problem
2. Overlapping with another skill
3. Trying to do too much

Do not apply a 4th fix. Instead, step back and restructure or split.

## The New-Skill Filter

Before recommending a new skill, ask:
- Can this be a mode of an existing skill? (most common answer)
- Can this be a reference file in an existing skill?
- Can this be an example file?
- Can this be a test file?
- Is this actually a one-time thought that doesn't need systematizing?

Only if all answers are "no" should a new skill be considered.

## The Compliment Trap

"The user said they like this feature, let's expand it" is the most common path to bloat.
- User likes a specific output → add an example, not a feature.
- User asks for a variant → add a mode, not a skill.
- User wants more detail → add a reference, not a rule.

## Anti-Pattern: The Swiss Army Knife

A skill that tries to handle every edge case becomes useless for every specific case.
- If a skill has more than 5 modes, it has too many.
- If a skill has more than 10 output rules, it has too many.
- If a skill references more than 5 files, the references should be consolidated.

## Maintenance Burden Budget

Every file added to a skill increases its maintenance burden:
- SKILL.md: high (always loaded)
- templates/: medium (loaded on use)
- references/: medium (loaded on use)
- examples/: low (loaded only during diagnosis)
- tests/: low (loaded only during validation)
- scripts/: high (must be maintained across environments)

Prefer low-burden additions (examples, tests) over high-burden ones (SKILL.md rules, scripts).
