# Lead Synthesis — External Review of H1

## FACT — Run-Level

- Three independent reviews received.
- All three agree: H1 is too strong.
- All three agree: policyURI overlap is necessary
  but not sufficient for "single program".
- All three recommend operator-level extraction
  (tx.from / msg.sender) as next step.
- Kimi notes arbitrable continuity (already
  established in Run 011: one DisputeResolver).
- Namazu adds: templateId is stronger than
  policyURI.
- Grok adds: check for other arbitrable contracts
  writing into courts 29/32/34.

## OBSERVATION

- The Run 018 claim was a synthesis leap:
  from "shared templates" to "single program".
- Run 015 and Run 019 together show a stable
  pattern: External adversarial review catches
  Lead overclaims reliably.

## LEAD INTERPRETATION

H1 must be split into two levels:

- Weak H1 (SUPPORTED): templates are reused
  across courts 29, 32, 34.
- Strong H1 (NOT SUPPORTED): the three waves
  are one program.

The strong form requires an operator-level signal
(tx.from, templateId continuity, or off-chain
identity) that we have not yet extracted.

This is a corrective observation. Run 018's
conclusion is not retracted as a record — it is
downgraded in scope.

## Decision

- Strong H1 not accepted.
- Weak H1 accepted.
- Next run: operator extraction via tx.from.

## Next Observation

Run 020: tx.from extraction for courts 29, 32, 34.

## Provenance

Review request and three responses preserved
in REQUEST.md and RAW-EXTERNALS.md.
