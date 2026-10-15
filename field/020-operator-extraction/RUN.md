# Field Run 020 — Operator Extraction

FIELD: KLEROS
STAGE: OPERATOR IDENTIFICATION (on-chain)
STATUS: CLOSED
RESULT: Strong H1 refuted; three independent operators

## Objective

Test Strong H1 from Run 018 as recommended by Run 019
external review: identify EOA operators per court and
check for cross-court identity.

## Method

For every dispute in courts 29, 32, 34:
- retrieve creation transaction hash via eth_getLogs;
- fetch tx.from via eth_getTransactionByHash;
- count unique senders per court;
- intersect sets across courts.

## Result

### Senders per court

| court | disputes | unique senders |
|-------|----------|----------------|
| 29    | 87       | 2              |
| 32    | 36       | 2              |
| 34    | 139      | 4              |

### Dominant sender per court

| court | dominant sender                            | share |
|-------|--------------------------------------------|-------|
| 29    | 0xd0d5fad9380bcd518a2b387032583d700f570d0e | 86/87 |
| 32    | 0xd0d5fad9380bcd518a2b387032583d700f570d0e | 35/36 |
| 34    | 0xe66f7f8abef94c22e02fdc075fd5da5a0c5ba225 | 106/139 |

### Intersection sets

- 29 ∩ 32 = {0xd0d5fad9...}
- 29 ∩ 34 = {0x9e51bbd7...} (minor sender)
- 32 ∩ 34 = {0xf1c7c037...} (minor sender)
- 29 ∩ 32 ∩ 34 = {} (empty)

### Sender inventory

- 0xd0d5fad9380bcd518a2b387032583d700f570d0e
  primary in courts 29 and 32
- 0xe66f7f8abef94c22e02fdc075fd5da5a0c5ba225
  primary in court 34
- 0x9e51bbd7584afd0fb2e4bddab37f23a9f192d30a
  minor; appears in 29 and 34
- 0xf1c7c037891525e360c59f708739ac09a7670c59
  minor; appears in 32 and 34
- 0x401378723bdece4aa54949f1d7458fa2c601332a
  minor; appears only in 34

## Interpretation

Strong H1 (one program across three courts) is
REFUTED. No single EOA created disputes in all three
courts.

The observed pattern:

- courts 29 and 32 are dominated by the same operator
  (0xd0d5fad9); one program with two court phases.
- court 34 is dominated by a different operator
  (0xe66f7f8a); a separate program.
- Two minor EOAs (0x9e51bbd7, 0xf1c7c037) each bridge
  two courts but belong to neither dominant program.

Weak H1 (template reuse across courts) remains
supported: the shared policyURI templates cross
operator boundaries. The dominant court-34 operator
uses templates that were originally created by the
courts 29/32 operator or a shared library.

## Decision

- Strong H1 refuted.
- Weak H1 confirmed.
- Court 29 + 32: one operator (0xd0d5fad9).
- Court 34: separate operator (0xe66f7f8a).
- Cross-court template reuse is real but does not
  imply a single program.

## Next Observation

Candidate directions:

1. Recover identity of 0xd0d5fad9 and 0xe66f7f8a
   (off-chain, via IPFS policy content or public
   sources).
2. Examine why court 34 uses templates created
   earlier in courts 29/32 (shared library?).
3. Move to Resource Fit analysis.

## Provenance

Full sender data preserved in raw-senders.json.
