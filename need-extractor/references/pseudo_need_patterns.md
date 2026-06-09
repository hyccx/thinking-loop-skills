# Pseudo-Need Patterns — Common Signs of Overdesign

Use this reference when you suspect the user is over-engineering, misdiagnosing their problem, or cargo-culting a solution that does not fit. Load when SKILL.md instruction 4 (Call out pseudo-needs aggressively) needs sharper pattern-matching.

## Common Pseudo-Need Patterns

### 1. "I need an X to manage my Y"

Often means the user saw someone else use X and assumed they need it too — without diagnosing whether their Y actually creates pain.

**Red flags:**
- They cannot describe the last time Y caused a real problem
- They describe the tool's features before describing their own pain
- "Everyone uses X" / "Industry standard is X"

**What to check:** Ask what happens if they use the simplest possible alternative (spreadsheet, manual process, a single file).

### 2. "I should plan for future scale"

Premature scaling is the most expensive form of procrastination.

**Red flags:**
- No current users / a handful of users
- Cannot name a concrete bottleneck they have already hit
- "I don't want to rewrite later" — without evidence that rewriting is costly in *their* context

**What to check:** Ask what breaks first at 10x current usage, and how long it would actually take to fix it then.

### 3. "I need a unified platform"

The siren song of consolidation.

**Red flags:**
- The user has 2-3 separate tools that work fine
- "It's annoying to switch between them" — but cannot name how much time they lose
- Wants to build something custom rather than glue existing tools

**What to check:** Ask what concrete friction they hit daily. Often the answer is "nothing, I just prefer having one thing."

### 4. "I want to make it production-ready"

Often means "I am scared to ship something imperfect."

**Red flags:**
- The project has no users yet
- They are adding tests, CI/CD, monitoring, docs — before anyone has used it
- "I want to do it right from the start"

**What to check:** Ask what the worst outcome would be if they shipped the janky version. Usually the answer is "nothing bad, I just feel embarrassed."

### 5. "I need flexibility for future use cases"

Designing for unvalidated futures.

**Red flags:**
- Cannot name a specific future use case they have validated with a real person
- "What if someone wants to..." — fills in the blank with a scenario that has never come up
- Adding abstractions, plugin systems, or config files before hardcoding

**What to check:** Ask if they have ever actually been burned by lack of flexibility in a past project. Often the answer is "I over-engineered for flexibility last time too."

### 6. "I want to compare all options first"

Analysis paralysis dressed as due diligence.

**Red flags:**
- Has been researching for weeks without building
- The list of options keeps growing
- Each new option adds criteria, making the decision harder

**What to check:** Ask: "What is the cheapest option you could try in the next 2 hours that would tell you if this direction works?"

### 7. "I need to organize my X before I start"

Reordering deck chairs before checking if the ship floats.

**Red flags:**
- The user is sorting files, renaming things, setting up folder structures, writing documentation — before building the core thing
- "I need to clean up before I can focus"

**What to check:** Ask what is the scariest unknown about their project. Usually the answer is nothing to do with organization.

## How to Use This Reference

When you detect one of these patterns in the user's input:

1. Name the pattern by example, not by label — do not say "this is pattern #4." Instead, say something like: "You mentioned making it production-ready before anyone has used it. That reads like a fear of shipping, not a real requirement."
2. Quote the user's own words that triggered the pattern recognition.
3. Propose a minimal alternative — what would the simplest adequate version look like?
4. Do not frame this as "you are wrong." Frame it as "here is what I notice. Is this accurate?"
