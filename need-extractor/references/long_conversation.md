# Long Conversation Analysis — Extracting Real Needs from Multi-Turn Dumps

Use this reference when the user pastes a long conversation (their own with others, or a back-and-forth with Codex) and asks for need extraction. Load when SKILL.md step 4 is triggered.

## Core Technique

A long conversation is not a single message — it is a trail of breadcrumbs. The user's real need is usually visible in:

1. What they keep circling back to
2. What they get frustrated by
3. What they dismiss too quickly
4. Where their energy shifts (excited vs. deflated)
5. What they say when they forget to self-edit

## Scanning Strategy

Do not read the conversation linearly. Instead:

### Pass 1: Skim for emotional markers
Scan for sentences that express:
- **Frustration** — "this is so annoying", "I hate that", "why is this so hard"
- **Excitement** — "that would be so cool", "this is exactly what I want"
- **Defensiveness** — "but I need it because...", "the reason is..."
- **Resignation** — "I guess it's fine", "maybe I don't need it"

Mark these sentences. The user's real need lives near their strong emotions, not their reasoned arguments.

### Pass 2: Map the contradiction
Look for two opposing statements the user has made at different points:

- "I want this to be simple" + "I need it to handle every edge case"
- "I just want to ship fast" + "I want it to be perfect"
- "I need a general solution" + "my use case is very specific"

The contradiction is the core of the analysis (facet 5).

### Pass 3: Identify orbiting assumptions
Find things the user is treating as non-negotiable but has not actually justified:

- "I need a database" — why? Do they need persistence, or just in-memory state?
- "I need an API" — why? Is there a client other than themselves?
- "I need authentication" — why? Do they have multiple users?

These are candidates for facet 6 (What Can Be Cut).

### Pass 4: Find the one unresolved question
At the end of the conversation, what single question remained unanswered? This is likely the core anxiety driving the whole thing. Make this the center of your analysis.

## Conversation History Abbreviation

When quoting from a long conversation, do not quote full paragraphs. Use abbreviated, cleaned-up quotes:

- Source: "yeah idk maybe I should just use something else like maybe not worth it because then I would have to..."
- Quote: "maybe I should just use something else"

Clean up filler words and repetition, but keep the user's voice. Do not paraphrase into your own language.

## The "What If Reverse" Test

After your analysis, mentally run this test:

- What if the user *stopped working on this entirely*? What would they actually lose?
- What if they shipped the jankiest possible version today? What would actually break?
- What if they solved the opposite problem? Would the real need still be met?

If the answer to any of these surprises you, your analysis has missed something.

## Pruning Strategy for Long Inputs

If the conversation is very long (>2000 words):
1. Only analyze the last 1/3 of the conversation — that is where the user has usually clarified themselves
2. Include the first message for context
3. Skip the middle unless it contains an emotional marker from Pass 1
