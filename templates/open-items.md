# Open Items — Dashboard (Template)

> Pipeline bookkeeping index. Use this dashboard model when a single `open-points.md` at the root grows too large; contents then live in detail files under `open-points/`. Maintained by the conductor.
>
> **Small projects:** keep the single `open-points.md` at the root (sectioned as `## Open author questions`, `## Deferred review findings`, `## Verification remainders`, `## Worldbuilder follow-ups`, `## Done`). **Larger projects:** graduate to this dashboard + the detail files below.

## Sorting System

**ID scheme:** `CAT-Chapter-NN`
- `AQ` author question · `RF` review finding (deliberately kept) · `SF` structure finding (cross-cutting) · `WB` Worldbuilder follow-up · `FC` FactChecker residual finding · `FIX` remediation

**Status symbols:** 🔴 active · 🟡 waiting (bound to later chapters) · 🟢 watch (check at the character's next POV) · ⚪ follow-up (documentary)

**Severity:** Blocker | Important | Optional | Follow-up

## Detail Files

| File | Content |
|---|---|
| `open-points/author-questions.md` | Items only the author can decide |
| `open-points/review-findings.md` | Deliberately kept Editor/Reader notes |
| `open-points/structure-findings.md` | Cross-cutting reader/structure findings |
| `open-points/worldbuilder-followups.md` | Canon gaps and plot seeds |
| `open-points/factchecker-residual-findings.md` | Residual plausibility findings |
| `open-points/diegesis-protection-register.md` | Protected passages (before remediation passes) |
| `open-points/done.md` | Archive (chronological) |

## 🔴 Active

| ID | Title | Severity |
|---|---|---|
| {{AQ-Ch?-01}} | {{…}} | {{Important}} |

## 🟡 Waiting

| ID | Title | Resolution |
|---|---|---|
| {{WB-Seed-01}} | {{…}} | {{Act 2/3}} |

## 🟢 Watch

| ID | Title | At next POV of |
|---|---|---|
| {{…}} | {{…}} | {{character}} |

## ⚪ Follow-ups / Resolved

- {{…}}

## Maintenance Workflow

1. **Run start:** review the dashboard, pull relevant items into the brief.
2. **During:** enter new items in the matching detail file (`### ID — title · status · severity` + block with date/source/context/action).
3. **Run end:** move closed items to `done.md` (newest first). Update the dashboard.
4. **Conventions:** never reuse an ID; status symbol at the end of the title; detail in the detail file, never in the dashboard.
