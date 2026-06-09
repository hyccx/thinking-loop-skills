# Test: Anti-System Check — Not Every Idea Needs a Skill

## Input
> 我想建一个 skill 来记录我每天做了什么事情。就是简单的 daily log。

## Expected behavior
- Combination of recombination + anti-system-check triggers
- Output should explicitly question whether a skill is needed
- Suggest alternative: Obsidian daily note template, or a reference file, or just a markdown file
- Should NOT default to "yes, build a skill"
- If the idea is too small for automation, should say so directly

## Check
- [ ] Includes anti-system-check trigger
- [ ] Questions whether a skill is needed at all
- [ ] Suggests non-skill alternatives (template, reference, mode)
- [ ] Does NOT default to building a new skill
- [ ] May suggest "先手工记录一周" (try manually first)
