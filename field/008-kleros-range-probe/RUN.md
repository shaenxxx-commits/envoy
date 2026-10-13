# Field Run 008 — Kleros Range Probe

FIELD: KLEROS
STAGE: RANGE PROBE
STATUS: CLOSED
RESULT: full V2 field boundary identified

## Objective

Complete the second probe from Run 006:
extend the block range below 414M to determine whether
earlier disputes or additional arbitrables exist.

## Environment

- Machine: nova (local)
- Date: 2026-10-13
- RPC: https://arb1.arbitrum.io/rpc (public)

## Method

Paginated eth_getLogs, same topic0 and contract as
Runs 006-007. Traversed four windows of 10 chunks each,
going backwards from block 414 509 694 to 164 509 694.

## Result

Below 214M (five chunks, 50M blocks): 0 events.

Combined picture across three successful traversal zones:

| Block range       | Events | IDs     |
|-------------------|--------|---------|
| 164M..214M        | 0      | none    |
| 214M..314M        | 24     | 0..23   |
| 314M..414M        | 94     | 24..117 |
| 414M..514M        | 178    | 118..295|

Total: 296 events, IDs 0..295, no gaps.
Single arbitrable: 0xb5526d022962a1fff6ed32c93e8b714c901f4323.

## Interpretation

- The V2 field begins between block 214M and 254M.
  At least 50M blocks below 214M are empty.
- IDs 0..295 form a contiguous sequence with no gaps.
  Each ID appears exactly once in the sample.
- All 296 events originate from one arbitrable.
- The single-arbitrable picture is stable across
  three independent traversal zones.

## Decision

Range probe complete.
V2 field boundary identified.
Corpus: 296 disputes, IDs 0..295.

## Next Observation

If deeper completeness is required, traverse below
164M to confirm the field start block. Otherwise
proceed to a first descriptive summary of the corpus.
