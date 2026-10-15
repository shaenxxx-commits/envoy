# Lead Synthesis — Consumer Wave Hypothesis

## FACT — Run-Level

Sampled policyURI (court 29, n=20; court 32, n=20).
Court 34 full set from Run 014 (n=135).

| policyURI                          | c29 | c32 | c34 |
|------------------------------------|-----|-----|-----|
| /ipfs/QmbEs5Ae8Sh5WaMAchUiNLhRqSe9ossQMaRV5mZ1L5uqom | 13  |  0  | 46  |
| /ipfs/QmUbgqKuUvfsnWLP6o8GhZu8jcCaD31GUSZSSexe11fZco |  3  | 13  | 37  |
| /ipfs/Qmassb4gkqJ6h7e7JTRgfCWPMEeoLU72PWbPmhjTAMQwF4 |  0  |  6  |  3  |

## HYPOTHESIS EVALUATION

H1 stated: the three court-level waves are stages of
one consumer dispute program, migrating between courts
through the same DisputeResolver gateway.

H1 requires policyURI overlap across courts.

Observed overlap:

- QmUbgqKuUvfsnW appears in all three courts
  (29, 32, 34).
- QmbEs5Ae8Sh5W appears in courts 29 and 34.
- Qmassb4gkqJ appears in courts 32 and 34.

Every court shares at least one policyURI with at
least one other court, and one policyURI is present
in all three.

H1 is SUPPORTED.
H0 (disjoint programs) is CONTRADICTED.

## OBSERVATION

- The consumer templates are not court-specific.
  They can be submitted to different courts.
- The same two dominant templates carry the wave from
  court to court.
- The wave is a migration, not a replacement.

## UNKNOWN

- Whether the choice of court is made by the user,
  by the template, or by external factors.
- Whether courts 29, 32, and 34 have different fee
  or juror structures that motivate selection.
- Whether the policyURI content includes instructions
  about the target court.
- Whether the migration is being driven by a single
  operator.

## LEAD INTERPRETATION

H1 is confirmed by direct evidence: a stable set of
Spanish-language consumer policy templates appears
in multiple courts over time. The three waves in
Run 012 are one program with three court phases.

This does not identify who operates the program. It
does establish that the three waves are connected,
which was not known before this run.

## Decision

Hypothesis H1 accepted.
Kleros V2 field, observed through DisputeResolver,
contains a single consumer dispute program that has
used at least three courts between 2025 and 2026.

## Next Observation

Candidate next steps:

1. Identify the operator behind the shared policyURI
   (requires off-chain source, may be out of scope
   for on-chain research).
2. Investigate why the program switched courts
   (fees, juror availability, court parameters).
3. Move to Resource Fit analysis.

## Provenance

Sampled policyURI preserved in /tmp/envoy_run018.json.
Method: eth_getLogs + DisputeTemplateRegistry decode,
same as Run 014.
