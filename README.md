# book-setup

A reusable template for writing a book with the help of GitHub Copilot agents in VS Code.

This repository ships with a small set of customization files that turn Copilot Chat into a coordinated writing room: a **Writer** drafts chapters, an **Editor** reviews style and consistency, a **FactChecker** audits plausibility and continuity, and a **Chapter-Pipeline** orchestrator chains them together.

The setup is genre-agnostic. Fill in the placeholders, point the agents at your worldbuilding files, and start writing.

## What's in here

```
.github/
  agents/
    chapter-pipeline.agent.md   # Orchestrator: Writer → (Editor ∥ FactChecker) → Writer (revision)
    writer.agent.md             # Drafts and revises chapters
    editor.agent.md             # Reviews style, voice, characters, clarity
    fact-checker.agent.md       # Audits plausibility, continuity, worldbuilding
  instructions/
    author-voice.instructions.md                # The "how" — tone, sentence rhythm, taboos
    chapter-writing-guidelines.instructions.md  # The craft constants — tense, POV, format
story-questions.md              # 99 questions to interrogate your story idea
```

## How to use this template

1. **Clone or copy** this repository as the root of your book project.
2. **Decide on your folder layout.** The agents reference these by default — rename them in the agent and instruction files if you prefer different names:
   - `chapters/` — the actual prose, one file per chapter
   - `book-guide.md` / `outline.md` — overall arc, beats, chapter list
   - `story/` — background, hook, conflict, timeline
   - `world/` — settings, technology, magic systems, locations
   - `characters/` — main cast and supporting characters
   - `factions/` — groups, organizations
   - `questions/` — your answers to the questions in `story-questions.md`, organized by theme
3. **Replace the placeholders.** Search the repo for `{{` and fill in:
   - `{{BOOK_TITLE}}` — your working title
   - `{{GENRE}}` — e.g. *Hard Science-Fiction*, *Cozy Fantasy*, *Literary Thriller*
   - `{{LANGUAGE}}` — the language you write in (e.g. *English*, *German*)
   - `{{POV}}` — e.g. *third person limited*, *first person*, *rotating POV*
   - `{{TENSE}}` — e.g. *past*, *present*
   - `{{TONE_REFERENCES}}` — authors or works whose voice you're calibrating against
   - `{{TABOOS}}` — devices, tropes, or phrases you want to avoid
   - `{{DOMAIN}}` — the specialist domain the FactChecker should police (e.g. *physics and astronomy*, *medieval warfare*, *legal procedure*)
4. **Answer the questions.** Work through `story-questions.md` and capture your answers in `questions/` (one file per topic cluster). The Writer and FactChecker treat these as the canonical statement of authorial intent.
5. **Seed your first chapter.** Write a prologue or opening scene by hand or with the Writer agent. Future chapters will be calibrated against it stylistically.
6. **Invoke the pipeline.** In Copilot Chat, ask the **Chapter-Pipeline** agent for a new chapter. It will delegate to Writer, then run Editor and FactChecker in parallel, then ask the Writer for one focused revision pass.

## Agent contract at a glance

| Agent | Writes prose? | Edits files? | Primary job |
|---|---|---|---|
| Writer | yes | yes (`chapters/`, canon files) | Draft and revise chapters |
| Editor | no | no | Style, voice, character, clarity feedback |
| FactChecker | no | no | Plausibility, continuity, worldbuilding audit |
| Chapter-Pipeline | no | no | Orchestrate the three above |

The two instruction files in `.github/instructions/` apply to every file under `chapters/` via their `applyTo` glob — they encode the craft constants and the author voice so every Copilot interaction in those files starts from the same foundation.

## Customizing further

- Edit `applyTo` globs in the instruction frontmatter if you change the chapters folder name.
- Add new agents (e.g. a *Researcher*, *Sensitivity Reader*, *Translator*) by dropping additional `.agent.md` files into `.github/agents/`.
- The agents are written for Copilot Chat in VS Code but the prompts translate cleanly to other agent runtimes.

WIP — feedback and pull requests welcome.
