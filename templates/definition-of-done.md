# Definition of Done (Template)

> **Acceptance gate after verification.** A chapter only counts as "done" once every item is satisfied. Purpose (hard-won lesson): prevent **clarity debt** from accumulating across the book — C is checked hard here, not deferred to a late pass. Lives at `templates/definition-of-done.md`; run per chapter.

## Gate — Chapter {{N}}

- [ ] **Tension:** reader rating **T ≥ {{target}}** (default 4).
- [ ] **Clarity:** reader rating **C ≥ {{target}}** (default 4). *If this threshold breaks, that is an Important finding — targeted revision or an author decision, not a default wave-through.*
- [ ] **No open blocker** from Editor or FactChecker.
- [ ] **Canon updated:** new/changed cross-chapter values in `canon/facts-register.md`; decision-register status updated.
- [ ] **No new tic** left unremediated (checked against `style/tic-blocklist.md`); newly discovered tics added to the list.
- [ ] **Protected passages intact** (`open-points/diegesis-protection-register.md` not violated).
- [ ] **Complexity budget held** (no open over-layering with low C).
- [ ] **Bookkeeping updated** (open items added/removed).

## When the gate breaks

| Broken item | Standard response |
|---|---|
| C below target | Targeted clarity revision (affected passages only), then a reader re-check **of that passage only**. |
| Open blocker | Second, tightly focused revision round. |
| Canon not updated | Worldbuilder again, before closing. |
| New tic | Add to the list; on clustering, a micro-remediation. |

> Only once every box is ticked: chapter closed, item moved to `open-points/done.md`.
