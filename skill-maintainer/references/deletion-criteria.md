# Deletion Criteria — When to Deprecate or Delete a Skill

## Signs a Skill Should Be Deleted

1. **Zero usage**: The skill has not been triggered in 30+ days.
2. **Replaced**: Another skill now covers its functionality with better results.
3. **Always patched**: Every use reveals a problem that requires patching. The skill is fundamentally wrong.
4. **Too narrow**: The skill was created for a one-time scenario and has no general applicability.
5. **Too broad**: The skill tries to do everything and succeeds at nothing. (Consider splitting first.)
6. **Confusing**: Users regularly trigger the wrong skill because the boundary is unclear.

## Deletion Process

### Step 1: Verify
Check if the skill has ever been used. If not used in 30 days, flag for deprecation.

### Step 2: Check dependencies
Does any other skill reference this skill by name in its handoff or workflow? If yes, those references must be updated first.

### Step 3: Notify
If this is a shared skill (in a team setting), notify before deleting.

### Step 4: Archive, do not delete immediately
Move the skill directory to an archive location (e.g., skills-archive/) instead of deleting. Keep for 90 days.

### Step 5: Update cross-references
Remove references to the deleted skill from other skills' handoff sections and "See also" notes.

## What NOT to Delete

- A skill that has ONE bad output but is otherwise useful (fix the output, not the skill)
- A skill that overlaps slightly with another (resolve the conflict, do not delete)
- A skill that the user likes but does not use often (personal taste is valid)
