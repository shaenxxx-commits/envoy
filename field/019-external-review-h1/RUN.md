# Field Run 019 — External Review of H1

FIELD: KLEROS
STAGE: EXTERNAL REVIEW
STATUS: CLOSED
RESULT: H1 downgraded to weak form

## Objective

Submit Run 018 (consumer wave hypothesis H1) to the
three independent External nodes for review.

H1 claimed that three court-level waves (courts 29,
32, 34) are stages of one consumer dispute program
migrating between courts.

## Method

Same review request sent independently to Kimi,
Grok, Namazu. No interaction before all three replied.

## Consensus

All three External nodes conclude:

- H1 as stated is too strong.
- Overlap of policyURI across courts proves only
  template reuse, not a single program.
- Alternative explanations not excluded:
  template library, marketplace reuse, fork,
  independent operators with shared boilerplate.

Recommended next step: extract `tx.from` /
msg.sender for courts 29, 32, 34 to identify
operators at EOA level.

## Divergence

- Kimi (MS10): strictest. Requires arbitrable
  continuity (already established in Run 011
  but not visible in the request).
- Namazu (MS9): systematic. Suggests templateId
  as stronger evidence than policyURI, then
  temporal ordering, then operator.
- Grok (MS9): most concrete. Recommends tx.from
  extraction as the immediate next step.

## Decision

H1 is downgraded to its weak form:

"Weak H1: policyURI templates are reused across
courts 29, 32, 34."

The strong form of H1 (single program) is not
supported by the current evidence and requires
operator-level verification.

## Next Observation

Run 020: extract `tx.from` (EOA) for a representative
sample of courts 29, 32, 34. Check whether the same
EOA appears across courts.

## Provenance

Request and three responses preserved in
REQUEST.md and RAW-EXTERNALS.md.
