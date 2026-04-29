---
description: "Chapter writing guidelines for {{BOOK_TITLE}}: tense, POV, tone, style conventions."
applyTo: "chapters/**/*.md"
---

# Chapter writing guidelines — {{BOOK_TITLE}}

These guidelines apply to every file under `chapters/`. They define the craft constants of the book. Plot, worldbuilding, and character canon live in separate files (see *Sources of canon* below) and are out of scope here.

> **Replace the placeholders** (`{{...}}`) with your project's values before relying on this file. The structure is what matters; the specifics are yours.

## Sources of canon

When in doubt about plot, world, or character facts, consult — in this order:

1. `book-guide.md` / `outline.md` — overall arc, beats, chapter list, POV assignments per chapter
2. `story/` — background, hook, conflict, timeline
3. `world/` — settings, technologies, magic systems, locations
4. `characters/` — main cast
5. `factions/` — groups, organizations
6. `questions/` — your own answers about tone, theme, antagonist, intent (the author's stated vision)

If a fact is missing from canon, do **not** invent it silently. Either ask the author, or write provisionally and flag the assumption in the chat.

## Language

- Language: **{{LANGUAGE}}**.
- Use the current orthographic standard for that language.
- Quotation marks: the convention native to {{LANGUAGE}}.
- Numbers, units, decimal separator: native convention. Be consistent within a single chapter.
- Numerals as digits in technical/measured contexts; spell out only when the literary effect calls for it (rare).

## Narrative perspective

- **Perspective:** {{POV}}. Each chapter follows **exactly one** POV character unless `book-guide.md` explicitly authorizes a switch.
- **No headhopping** within a chapter. No omniscient interjections the POV character could not perceive or know.
- Sensory description matches the POV character's perception (their senses, their vocabulary, their blind spots).
- The reader may know things the POV character does not — but only if prior chapters established them. Never more than the cast collectively knows.
- **Prologue or framing exceptions:** allowed if marked as such in `book-guide.md` and consistently maintained for that single piece. From chapter 1 onward, strict POV.

## Tense

- **Narrative tense:** {{TENSE}}.
- Flashbacks, memories, exposition about the past: a clearly distinct tense, marked as a temporal shift.
- Hold tense consistent within a scene. Tense switches only at clean cuts (scene break, remembered episode).

## Tone & atmosphere

- Genre: **{{GENRE}}**. Stay inside it; cross-genre touches are welcome but should not derail the contract with the reader.
- Baseline mood: as defined in `questions/` (Tone, Genre & Atmosphere). Reread it before every chapter.
- **Humor** if it exists in this book is character-based and arises from the situation, not from the narrator winking at the reader. No slapstick, no quip-chasing, unless the genre explicitly calls for it.
- **Darker registers** (horror, grief, violence) only where the story earns them. No shock for shock's sake.
- No moralizing narrator commentary. Judgment happens through character perception.

## POV characters

- Characters are not interchangeable. Each one has a distinct vocabulary, sensory bias, rhythm of thought, and blind spots — see `characters/`.
- Inner life is shown sparingly and concretely: behavior, sensation, micro-decisions. Avoid abstract emotion labels in favor of the observable cause.
- If the book has non-human or unusual POVs (AI, animal, child, alien), their interiority must feel *other*, not human-in-disguise.

## Style conventions

- **Show, don't tell** — especially for emotion and threat. Concrete detail beats abstract claim.
- **No info-dumps.** Worldbuilding seeps in through action, perception, and conflict. A short clarifying aside is allowed only when the POV character is themselves working the term out.
- **Dialogue:** terse, functional, character-specific. Each major character should be identifiable by voice alone in a stripped line of dialogue.
- **Cut filler.** Adverb crutches replaced by stronger verbs. Repeated words flagged unless deliberate.
- **Vary sentence length.** Short and hard in action and shock; longer and dissecting in observation and reflection.

## Format & structure

- Chapter heading: `# Chapter <number> — <title>` (or `# Prologue`). Numbering follows `book-guide.md`.
- An optional `# Plan` block at the very top of a draft is allowed for working notes and is **not** part of the prose. Remove or move it before the chapter is considered finished.
- Scene breaks within a chapter: blank line + `---` + blank line.
- Diagnostic / inline-document blocks (logs, letters, transcripts) in fenced code blocks (```` ```text ````) with consistent column alignment if tabular.
- No footnotes, no bracketed narrator commentary inside the prose.

## Consistency

- Proper names — characters, places, factions, ships, organizations — exactly as written in `characters/`, `world/`, `factions/`. No spelling drift.
- Quantitative facts (distances, durations, dates, ages, capacities) must agree with `world/` and `story/timeline.md`. When unsure: look it up, do not guess.
- **Causal/temporal sequence must hold.** Events across multiple locations must be compatible with travel time, communication delay, and the established calendar. If a scene exposes a contradiction with `story/timeline.md`, fix one of them — never silently diverge.
- A character's knowledge cannot exceed what prior chapters and their senses have given them.

## What does not belong in chapter files

- Meta-commentary about the writing process (outside the optional `# Plan` block).
- Plot summaries or outline notes from `book-guide.md` — chapters **narrate**, they do not recap.
- Foreign-language terms without reason. Established terms-of-art are fine; flavor-borrowings need motivation.
