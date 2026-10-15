# Field Run 017 — Filter Assessment (Phase 4)

FIELD: KLEROS
STAGE: METHOD ASSESSMENT
STATUS: CLOSED
RESULT: filter passed with revisions noted

## Objective

Per ROADMAP Phase 4 and FIELD-SELECTION-v0.1 §8:
evaluate the field-selection filter itself after
real application (Runs 001-016).

The filter was declared provisional in v0.1. Runs
001-016 are the first test.

## Questions (from ROADMAP Phase 4)

1. Did the gates distinguish candidates?
2. Did the scores add useful discrimination?
3. Did UNKNOWN remain usable?
4. Did Research Fit remain separate from Resource Fit?
5. Did Ability to Test expose hidden methodological
   constraints?
6. Did the filter create ambiguity or confounds?

## Method

Compare the filter's intended behaviour against
what actually happened in Runs 001-016.

Not modifying the filter — only assessing it.

## Assessment

### Q1. Did the gates distinguish candidates?

PARTIAL.

The filter distinguished UDRP from Kleros on
"Existing Synthesis" (UDRP high, Kleros low) and
"Ability to Test" (UDRP high, Kleros lower).

But the actual selection was made by the Architect,
not by the filter. The Architect chose Kleros for
lower cluster size and developmental state — two
criteria not in the filter.

Observation: the filter ranks candidates, but the
final selection introduced criteria from outside
the filter (observation cost, cluster size,
maturity preference).

### Q2. Did the scores add useful discrimination?

WEAK.

The 0-2 scoring was applied inconsistently across
the four candidates. In practice, the useful output
was not the scores but the comparison itself:
UDRP = mature/saturated; Kleros = young/open.

Observation: qualitative "saturated vs open" was
more decision-relevant than numeric scores.

### Q3. Did UNKNOWN remain usable?

YES.

UNKNOWN states appeared frequently (ability to
build sensor, corpus size, mapping of ids, etc.).
None were silently promoted to positives or
negatives. The Run 004 -> Run 016 arc is a record
of gradual UNKNOWN -> FACT conversion, each step
documented.

Observation: UNKNOWN worked as intended. It held
place for information without forcing a choice.

### Q4. Did Research Fit remain separate from Resource Fit?

YES at the filter level, PARTIAL in practice.

The filter explicitly separates Research Fit and
Resource Fit. In Runs 001-016, all work was on
the research side. Resource Fit was never evaluated
in the field.

Observation: the distinction survived but Resource
Fit was never tested. It remains an untested filter
axis.

### Q5. Did Ability to Test expose hidden methodological
constraints?

YES.

The filter's separation of technical vs
methodological accessibility was decisive:

- technical: could we reach the corpus?
- methodological: could we actually test something?

Runs 003-005 are the concrete case: External sandboxes
failed technically (C. ON-CHAIN EXTRACTION = FAILED),
but nova succeeded. The filter's distinction allowed
this to be seen without conflating "no data" with
"unreachable data".

Observation: this was the filter's strongest design
choice.

### Q6. Did the filter create ambiguity or confounds?

MINOR.

Two ambiguities appeared:

1. The filter did not model "operator cost" or
   "observation cost". The Architect supplied this
   decision outside the filter. FIELD-SELECTION v0.1
   §3 mentions cost, but no gate captured it.

2. "Existing Synthesis" is ambiguous when a field
   has high synthesis in some dimensions and low in
   others (UDRP: high synthesis in doctrine, low in
   quantitative patterns). The filter scores
   synthesis as a single value.

## Decision

The filter is retained for future use with the
following observations recorded as candidate
amendments for a future revision:

A1. Add an explicit gate or field for "observation
    cost" / "operator cost" — a variable that
    influenced the actual selection.

A2. Revise "Existing Synthesis" to allow
    per-dimension scoring, not a single value.

A3. Add a note that Research Fit and Resource Fit
    must both be exercised in at least one field
    cycle before the filter is considered validated.

These are recorded as observations.
FIELD-SELECTION-v0.1 is not modified by this run.
A v0.2 revision is deferred until a second field
selection exercise provides comparison data.

## Next Observation

No further field action required for this phase.
The filter assessment is complete for the first
application.

## Provenance

This assessment relies on the run records of
001-016, preserved in the repository.
