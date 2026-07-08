# Status Block (Template)

> Only if the book uses diegetic diagnostic/status blocks (e.g. machine POV, logs, reports, readouts). Otherwise ignore this file.
>
> Always inside a ```text``` code block. Values consistent with the baseline (first block in the book) and with `canon/facts-register.md`.

## Format

```text
{{LABEL}} {{running number}} — {{timestamp}}
{{FIELD-1}}: {{VALUE}}
{{FIELD-2}}: {{VALUE}}
{{STATUS}}: {{nominal / deviation …}}
```

## Rules

- **Baseline is the calibration line:** the first status block in the book defines the norm values; later states are measured against it.
- Do not invent values that contradict the `canon/facts-register.md` bookkeeping.
- Deviations must follow causally from the plot (the FactChecker checks this).
- Keep the format **identical** across all chapters (conventions sheet).
