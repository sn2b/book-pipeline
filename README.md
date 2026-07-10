# book-pipeline

A reusable template for writing a book with the help of GitHub Copilot agents in VS Code.

> **Consider this a playground — a test, a brainwave.** It exists to see whether you can wire up a suite of coordinated Copilot agents to actually run a book-writing workflow end to end. Treat it as an experiment to poke at, not a finished product.

This repository ships with a small set of customization files that turn Copilot Chat into a coordinated writing room: a **Writer** drafts chapters, an **Editor** reviews style and consistency, a **FactChecker** audits plausibility and continuity, a **Reader** gives beta-reader feedback, a **Worldbuilder** keeps canon clean, and a **Chapter-Pipeline** orchestrator chains them together behind two hard quality gates.

The setup is genre-agnostic and built to work **preventively, not reactively**: decisions, voices, and conventions are locked down *before Chapter 1*, and per-chapter gates keep clarity or canon debt from accumulating. Fill in the placeholders, answer the questions, plan the arc, and start writing.

> **Where the "preventive" design comes from:** an earlier novel only held together because repeated remediation passes caught problems after the fact. This template shifts those fixes forward — every recurring failure mode has a dedicated register, tracker, or gate that catches it before it reaches the page. See *How the lessons are built in* below.

## What's in here

```
.github/
  agents/
    chapter-pipeline.agent.md   # Conductor: pre-flight → Writer → (Editor ∥ FactChecker ∥ Reader)
                                #   → synthesis → revision → verification → Definition-of-Done → Worldbuilder
    writer.agent.md             # Drafts and revises chapters; the only one who edits chapters/
    editor.agent.md             # Style, voice, tics, form-variance, clarity, consistency
    fact-checker.agent.md       # Plausibility, continuity, numbers, knowledge-reveal, worldbuilding
    reader.agent.md             # Beta-reader perspective + mandatory tension/clarity (T/C) rating
    worldbuilder.agent.md       # Maintains world/character/plot canon + the canon registers
  instructions/
    author-voice.instructions.md                # The "how" — tone, sentence rhythm, taboos
    chapter-writing-guidelines.instructions.md  # The craft constants — tense, POV, format
templates/                      # Fill-in scaffolds for every canon file, tracker, gate, and report
                                #   (incl. questions-vision.md — the 99-question vision interrogation)
open-points.md                  # (created on first pipeline run) pipeline bookkeeping
```

### The `templates/` folder

Copy each template to its working location and fill in the `{{...}}` placeholders.

| Template | Working location | What it prevents |
|---|---|---|
| `book-guide.md` | `book-guide.md` (root) | no shared map of acts / clocks / POV plan |
| `story-arc-plan.md` | `story/story-arc-plan.md` | discovering the ending mid-draft → rewrites |
| `canon-decision-register.md` | `canon/canon-decision-register.md` | late/reversed canon rulings → rewrites |
| `conventions.md` | `canon/conventions.md` | notation drift across chapters |
| `facts-register.md` | `canon/facts-register.md` | manual grep for cross-chapter numbers |
| `chapter-synopsis-register.md` | `canon/chapter-synopsis-register.md` | full reread to spot contradictions |
| `tension-curve-tracker.md` | `canon/tension-curve-tracker.md` | an act sagging while each chapter "passes" |
| `setup-payoff-register.md` | `canon/setup-payoff-register.md` | orphaned seeds / unprepared payoffs |
| `knowledge-reveal-tracker.md` | `canon/knowledge-reveal-tracker.md` | info leaks / premature twists |
| `voice-signature.md` | `style/voice-signature.md` | character voices blurring together |
| `tic-blocklist.md` | `style/tic-blocklist.md` | the same style tics recurring |
| `complexity-budget.md` | `style/complexity-budget.md` | over-layering that lowers clarity |
| `diegesis-protection-register.md` | `open-points/diegesis-protection-register.md` | remediation passes breaking canonical forms |
| `pre-flight-checklist.md` | run per chapter | writing on an unresolved gating decision |
| `definition-of-done.md` | run per chapter | clarity debt accumulating across the book |
| `chapter.md` | `chapters/<file>.md` | chapters missing POV/tense/T-C/form metadata |
| `status-block.md` | inside chapters | inconsistent diegetic status/log blocks |
| `review-report.md` | reviewer output | non-mechanical synthesis of feedback |
| `open-items.md` | `open-points/` dashboard | bookkeeping outgrowing a single file |
| `done.md` | `open-points/done.md` | active lists growing unbounded |
| `worldbuilding-entry.md` | `world/`,`factions/`,`characters/` | inconsistent world-file structure |
| `questions-vision.md` | `questions/` | starting to write without a fixed vision (holds the 99-question interrogation) |

## Folder layout (target)

The agents reference these by default — rename them in the agent and instruction files if you prefer different names.

```
chapters/     # the actual prose, one file per chapter
book-guide.md # overall arc, beats, chapter list, POV plan
story/        # background, hook, conflict, timeline, story-arc-plan.md
world/        # settings, technology, magic systems, locations
characters/   # main cast and supporting characters
factions/     # groups, organizations
questions/    # your answers to the questions-vision interrogation, organized by theme (highest authority)
canon/        # decision register, conventions, facts register, synopsis + pacing + seed + reveal trackers
style/        # voice signature, tic blocklist, complexity budget
open-points/  # diegesis protection register, done archive, dashboard (or single open-points.md at root)
```

## How to use this template

1. **Clone or copy** this repository as the root of your book project.
2. **Replace the placeholders.** Search the repo for `{{` and fill in:
   - `{{BOOK_TITLE}}`, `{{GENRE}}`, `{{LANGUAGE}}`, `{{POV}}`, `{{TENSE}}`
   - `{{TONE_REFERENCES}}`, `{{TABOOS}}`, `{{DOMAIN}}` (the specialist domain the FactChecker polices)
3. **Set the vision first.** Work through `templates/questions-vision.md` (its appendix holds the 99-question interrogation); capture your answers in `questions/`, one file per topic cluster. This is the highest authority — every agent defers to it.
4. **Lock the foundation + style before any chapter exists.** Fill in `book-guide.md`, `canon/canon-decision-register.md`, `canon/conventions.md`, `style/voice-signature.md`, an empty `style/tic-blocklist.md`, and `style/complexity-budget.md`.
5. **Plan the whole arc.** Fill `story/story-arc-plan.md`: **decide the ending first**, start the owed-payoff ledger, and get every load-bearing decision to at least 🟡 in the Canon Decision Register. Sign off *before Chapter 1*.
6. **Build the world.** World / character / faction entries (`templates/worldbuilding-entry.md`) + `canon/facts-register.md`. Create the trackers: synopsis, tension-curve, setup-payoff, knowledge-reveal.
7. **Write chapters via the pipeline.** In Copilot Chat, ask the **Chapter-Pipeline** agent for a new chapter. It runs the **pre-flight gate**, delegates to the Writer, runs Editor + FactChecker + Reader in parallel, synthesizes a revision list, has the Writer revise, runs a verification pass, checks the **Definition of Done**, then has the Worldbuilder propagate canon.
8. **Keep the books.** Maintain `open-points.md` (or the `open-points/` dashboard) after every run.

## Setup order (mandatory)

The order is the value. Do not skip it.

```
questions/  →  foundation + style  →  story-arc-plan (ending-first)  →  world + trackers  →  chapters (pipeline)  →  bookkeeping
```

## The pipeline at a glance

```
Pre-flight gate
   → Writer (draft)
   → Editor ∥ FactChecker ∥ Reader (parallel review; Reader gives mandatory T/C)
   → Synthesis & author-escalation (prioritized revision list)
   → Writer (one targeted revision)
   → Verification pass (Editor ∥ FactChecker: did the fixes land?)
   → Definition-of-Done gate (T/C thresholds, no blockers, canon updated, no tics)
   → Worldbuilder (propagate canon + update registers)
   → Bookkeeping update
```

## Agent contract

| Agent | Writes prose? | Edits files? | Primary job |
|---|---|---|---|
| Writer | yes | yes (`chapters/`, canon files) | Draft and revise chapters |
| Editor | no | no | Style, voice, tics, form-variance, clarity |
| FactChecker | no | no | Plausibility, continuity, numbers, knowledge-reveal |
| Reader | no | no | Beta-reader feedback + mandatory T/C rating |
| Worldbuilder | no | yes (canon files only, never `chapters/` or `questions/`) | Keep canon consistent; maintain the registers |
| Chapter-Pipeline | no | no (except bookkeeping) | Orchestrate the gates and the review loop |

The two instruction files in `.github/instructions/` apply to every file under `chapters/` via their `applyTo` glob — they encode the craft constants and the author voice so every Copilot interaction in those files starts from the same foundation.

## How the lessons are built in

| Hard-won lesson | Preventive asset |
|---|---|
| Style tics recur | `style/voice-signature.md` + `style/tic-blocklist.md`, from day 1 |
| Late canon reversals → rewrites | `canon/canon-decision-register.md` + pre-flight gate |
| Arc/ending discovered mid-draft → rewrites | `story/story-arc-plan.md` + one-time Story-Level Pre-Flight (ending-first) |
| Clarity (C) lags behind tension (T) | mandatory reader T/C + C threshold in the Definition of Done |
| Concept over-layering | `style/complexity-budget.md` + a "does this earn itself?" test in the agents |
| Diegesis protection was reactive | `open-points/diegesis-protection-register.md`, passages tagged at creation |
| Manual cross-consistency grep | `canon/facts-register.md` + `canon/conventions.md` as the central source |
| Full reread to catch contradictions | `canon/chapter-synopsis-register.md` (first reading source) |
| An act sags though each chapter "passes" | `canon/tension-curve-tracker.md` (macro T/C arc) |
| Planted seeds orphaned / payoff unprepared | `canon/setup-payoff-register.md` |
| Info leak / premature twist | `canon/knowledge-reveal-tracker.md` |
| Chapters structurally monotonous | `form_*` tags in the chapter frontmatter + Editor/Reader form-variance check |

## Customizing further

- Edit `applyTo` globs in the instruction frontmatter if you change the `chapters/` folder name.
- Add new agents (e.g. a *Researcher*, *Sensitivity Reader*, *Translator*) by dropping additional `.agent.md` files into `.github/agents/`.
- Small projects can keep a single `open-points.md`; larger ones graduate to the `open-points/` dashboard (`templates/open-items.md`).
- The agents are written for Copilot Chat in VS Code but the prompts translate cleanly to other agent runtimes.

WIP — feedback and pull requests welcome.
