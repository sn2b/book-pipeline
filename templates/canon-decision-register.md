# Canon Decision Register (Template)

> **Purpose (hard-won lesson):** Late or reversed canon rulings forced expensive rewrites. This register makes every **gating decision** visible and locks it *before* dependent chapters are written. Lives at `canon/canon-decision-register.md`.
>
> **Rule:** No chapter that depends on a decision with status `🔴 open` gets written. The pipeline checks this in the **pre-flight gate**.

## Status Legend

- 🔴 **open** — not yet decided; blocks dependent chapters.
- 🟡 **tentative** — working assumption, may still flip; dependent chapters at your own risk.
- 🟢 **decided** — settled, propagated.
- 🔒 **locked** — decided AND built into chapters; change only via a deliberate rewrite decision.

## Register

| ID | Decision / question | Status | Ruling | Dependent chapters | Source/date |
|---|---|---|---|---|---|
| CD-01 | {{e.g. does character X survive the showdown?}} | 🔴 open | — | {{Ch28–Ch32}} | {{Author, YYYY-MM-DD}} |
| CD-02 | {{e.g. which key value applies?}} | 🟢 decided | {{VALUE + unit}} | {{Ch14, Ch17, Ch28}} | {{YYYY-MM-DD}} |
| CD-03 | {{…}} | 🟡 tentative | {{…}} | {{…}} | {{…}} |

## How to Work

1. As soon as a decision affects **more than one chapter** → enter it here (not just in your head).
2. Before writing a chapter: check all entries whose "dependent chapters" name the current one. If any is 🔴 → **have it decided first**.
3. On `🟢 decided`: also put the value into `canon/facts-register.md` and into the relevant world file.
4. Once built into chapters: raise to `🔒 locked`. A change after that is a deliberate rewrite, not a silent edit.
