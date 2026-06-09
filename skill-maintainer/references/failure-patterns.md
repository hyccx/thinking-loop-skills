# Failure Patterns — Expanded Reference

Each pattern includes: symptoms, root cause, and fix strategy.

## Pattern 1: Over-Generalization

**Symptoms**: The skill output could apply to anyone. No specific reference to the user's actual context. Reads like a Wikipedia article or a generic tutorial.

**Root cause**: SKILL.md output rules don't demand specificity. No example showing what "specific" means.

**Fix**: Add an output rule: "引用用户原话. If the user said X, say X, not 'the user's project'." Add an example showing the difference.

## Pattern 2: Verbose Cascade

**Symptoms**: The skill outputs 3 pages of text for a simple question. Each section expands recursively.

**Root cause**: No length limits. No stop conditions. Output rules don't set a ceiling.

**Fix**: Add explicit word/paragraph limits per mode. Add stop condition: "If output exceeds 300 words for small mode, stop and trim."

## Pattern 3: Mechanical Form-Filling

**Symptoms**: The skill rigidly follows the template but produces output that feels tone-deaf. The template structure is visible and distracting.

**Root cause**: Output rules emphasize structure over adaptation. No guidance on tone adaptation.

**Fix**: Add rule: "Adapt the template to the user's tone. If the user is casual, do not use formal section headers." Add example showing casual adaptation.

## Pattern 4: Trigger Drift

**Symptoms**: The skill activates for inputs that don't match its purpose. Or it fails to activate when it clearly should.

**Root cause**: Description in frontmatter is either too narrow (misses triggers) or too broad (catches wrong triggers).

**Fix**: Review the actual inputs that caused drift. Add/remove trigger phrases in description. Tighten "Do NOT use when" section.

## Pattern 5: Skill Sibling Rivalry

**Symptoms**: Two skills produce overlapping output for the same input. User gets confused about which skill to use.

**Root cause**: Skills were created independently without boundary negotiation. Their descriptions overlap.

**Fix**: Move the overlapping responsibility to one skill, add a handoff to the other. Add a note in one skill's "Do NOT use when" section referencing the other skill.

## Pattern 6: Missing Handoff

**Symptoms**: Skill output ends without telling the user what to do next. The user is left with options but no direction.

**Root cause**: SKILL.md workflow does not include a handoff step. No downstream skill is referenced.

**Fix**: Add a Handoff section to the workflow. Reference the downstream skill(s) by name.

## Pattern 7: Over-Systematization

**Symptoms**: A simple question gets a full system architecture as answer. The user asked for a tip and got a platform.

**Root cause**: Skill lacks anti-system-check trigger. No proportion-awareness in output rules.

**Fix**: Add anti-system-check as a required step. Add rule: "If the answer can fit in 3 bullet points, do not output a system design."

## Pattern 8: Scope Creep

**Symptoms**: Skill outputs include analysis, recommendations, next-actions, and code — things that belong in separate skills.

**Root cause**: SKILL.md boundaries are not clearly defined. No "Do NOT" section, or the "Do NOT" section is too short.

**Fix**: Explicitly list what the skill does NOT do. Add boundary check as first step of workflow.
