# Field Run 009 — Kleros Full Corpus Extraction

FIELD: KLEROS
STAGE: FULL CORPUS EXTRACTION
STATUS: CLOSED
RESULT: complete V2 corpus, 296 disputes, ID -> block map

## Objective

Following the boundary identified in Run 008:
- extract the exact block for each of the 296 V2 disputes;
- locate the precise V2 field start block.

## Environment

- Machine: nova (local)
- Date: 2026-10-13
- RPC: https://arb1.arbitrum.io/rpc (public)
- Head block at run: 514 511 288

## Method

Single paginated eth_getLogs pass over 30 chunks of
10M blocks, from head backwards to block 214M.

Same contract and topic0 as Runs 005-008.

## Result

- Unique disputes: 296
- ID range: 0 .. 295, contiguous, no missing IDs
- Arbitrable: single, 0xb5526d022962a1fff6ed32c93e8b714c901f4323
- Lowest block with event: 274 289 504 (id = 0)
- Highest block with event: 514 090 528 (id = 295)
- Chunks below block 274M: 0 events
- Chunk 414M..424M: 0 events

## Interpretation

The V2 field starts at block 274 289 504 (dispute id 0)
and continues to the current head. No V2 dispute exists
below that block within the traversed range.

The dispute ID sequence is contiguous from 0 to 295.

## Decision

Full V2 corpus extracted. ID -> block map preserved
in DISPUTES.md and /tmp/envoy_run009.json.

## Next Observation

Descriptive summary of the corpus: distribution over
time, creation density, cluster analysis.
