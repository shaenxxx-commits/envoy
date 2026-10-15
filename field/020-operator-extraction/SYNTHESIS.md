# Lead Synthesis — Operator Extraction

## FACT — Run-Level

- Sender extraction done for all 262 disputes in
  courts 29, 32, 34.
- Total unique EOAs: 5.
- Dominant operator in courts 29 and 32:
  0xd0d5fad9380bcd518a2b387032583d700f570d0e.
- Dominant operator in court 34:
  0xe66f7f8abef94c22e02fdc075fd5da5a0c5ba225.
- No EOA appears in all three courts.
- Two minor EOAs (0x9e51bbd7, 0xf1c7c037) bridge
  pairs of courts.

## OBSERVATION

- The three court-level waves are not one program.
- Courts 29 and 32 share one operator.
- Court 34 has a different operator.
- Template reuse crosses operator boundaries.

## UNKNOWN

- Off-chain identity of each operator.
- Whether the minor EOAs are separate programs or
  helpers.
- Whether 0xd0d5fad9 and 0xe66f7f8a are related
  organizations.

## LEAD INTERPRETATION

Run 019 external review was correct. The Run 018
strong hypothesis was not supported by the evidence.

The corrected picture:

- The Kleros V2 field through DisputeResolver contains
  at least two independent operator programs (courts
  29/32 and court 34) plus minor participants.
- The shared consumer templates are evidence of
  template reuse, not program identity.

This closes the H1 question for on-chain analysis.
Further progress requires off-chain identification
of the operators or a shift to Resource Fit.

## Decision

Strong H1 refuted.
Weak H1 confirmed.
Field now characterized as multi-operator with
template reuse.

## Next Observation

Either off-chain operator identification or shift to
Resource Fit. Decision requires Architect.

## Provenance

Sender data per court preserved in raw-senders.json.
