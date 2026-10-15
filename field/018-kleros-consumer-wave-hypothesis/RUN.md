# Field Run 018 — Consumer Wave Hypothesis

FIELD: KLEROS
STAGE: INTERPRETATION (hypothesis test)
STATUS: OPEN
HYPOTHESIS: H1 (see below)

## Context

Runs 006-016 produced a full descriptive corpus of
300 Kleros V2 disputes accessed through DisputeResolver.
Run 012 identified three court-level activity waves:

- 2025 Q2-Q3 — court 29 (Consumo y Vecindad)
- 2026 Q2    — court 32 (Defensores del Cliente)
- 2026 Q3    — court 34 (Agentic Commerce Court label,
              Spanish consumer dominant)

Run 014 showed that two Spanish-language consumer
templates dominate court 34 in 2026-Q3.

## Hypothesis H1

The three waves observed in courts 29, 32 and 34 are
not independent events. They are stages of one
evolving real-world consumer dispute program, which
over time used different Kleros courts through the
same DisputeResolver gateway.

Operational form:

- MetaEvidence policyURI is a stable identifier of
  a dispute template;
- if the same policyURI appears across courts 29, 32
  and 34, H1 is supported;
- if the courts use disjoint policyURI sets, H1 is
  contradicted.

## Null Hypothesis H0

The three courts host unrelated dispute programs
that happen to share Spanish-language content and
the DisputeResolver gateway. policyURI sets are
disjoint.

## Method

1. Sample MetaEvidence policyURI for disputes in:
   - court 29 (consumo) — target 15 samples
   - court 32 (defensores) — target 15 samples
   (court 34 full set already available from Run 014).

2. Compute intersections of policyURI sets across
   courts 29, 32, 34.

3. Verify sample sufficiency:
   - if the three sets have no intersection and each
     set has internal diversity, H1 is contradicted;
   - if any policyURI is shared across two or more
     courts, H1 is supported.

## Evidence Rules

- FACT: policyURI observed for a dispute.
- OBSERVATION: overlap or non-overlap of sets.
- HYPOTHESIS: H1 as stated above.
- UNKNOWN: where a policyURI cannot be retrieved.

H1 is confirmed only if overlap is observed.
Absence of overlap is a legitimate result and
contradicts H1.

## Expected Outcome

Either H1 is supported (consumer program migrates
between courts) or H1 is contradicted (independent
programs). Both are valid outcomes.

## Next Observation

To be defined after the test.

## RESULT (2026-10-15)

Sampled policyURI (courts 29 and 32, n=20 each)
cross-referenced with court 34 full set from Run 014.

Observed overlaps:

- QmUbgqKuUvfsnW appears in all three courts.
- QmbEs5Ae8Sh5W appears in courts 29 and 34.
- Qmassb4gkqJ appears in courts 32 and 34.

H1 is SUPPORTED. H0 is CONTRADICTED.

## DECISION

H1 accepted.
The three court-level waves are stages of one consumer
dispute program migrating between courts through the
DisputeResolver gateway.

## NEXT OBSERVATION

- Identify the operator behind the shared policyURI
  (off-chain).
- Investigate why the program switched courts.
- Or move to Resource Fit analysis.

STATUS: CLOSED
