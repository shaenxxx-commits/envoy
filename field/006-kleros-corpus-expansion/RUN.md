# Field Run 006 — Kleros V2 Corpus Expansion

FIELD: KLEROS
STAGE: ON-CHAIN CORPUS EXPANSION
STATUS: CLOSED
SENSOR STATUS: GREEN (extended corpus)

## Objective

Complete the Next Observation from Run 005:
expand the on-chain sample from 6 disputes to a
representative corpus of V2 dispute-creation events.

Target: at least 10 V2 dispute IDs.

## Environment

- Machine: nova (local)
- Date: 2026-10-13
- RPC: https://arb1.arbitrum.io/rpc (public)
- Tooling: python3 via /tmp/envoy-keccak venv (urllib/curl)

## Method

Paginated eth_getLogs by canonical topic0:
0x141dfc18aa6a56fc816f44f0e9e2f1ebc92b15ab167770e17db5b084c10ed995
address: 0x991d2df165670b9cac3B022f4B68D65b664222ea

RPC limit: 10 000 000 blocks per request.
Traversed 10 chunks of 10M blocks backwards from head
block at 514 507 160.

## Result

Total unique V2 disputes found: 178
Dispute ID range: 118 .. 295
Block range: 431 728 818 .. 514 090 528
Arbitrable: all 178 from a single contract:
0xb5526d022962a1fff6ed32c93e8b714c901f4323

Chunk breakdown:
- chunk 0 (504M..514M): 54 events
- chunk 1 (494M..504M): 93 events
- chunk 2 (484M..494M): 4 events
- chunk 3 (474M..484M): 3 events
- chunk 4 (464M..474M): 2 events
- chunk 5 (454M..464M): 9 events
- chunk 6 (444M..454M): 9 events
- chunk 7 (434M..444M): 3 events
- chunk 8 (424M..434M): 1 event (id 118)
- chunk 9 (414M..424M): 0 events

## Observations

- All 178 disputes originate from one arbitrable
  contract. No second arbitrable observed in this
  sample.
- Several disputes share a single block — batch
  creation pattern.
- Lowest observed id is 118. Below block 431M no
  events were found within the traversed range.

## Unknown

- Whether disputes with id < 118 exist.
- Whether V2 has other arbitrable contracts beyond
  0xb5526d...4323.
- Whether all V2 courts are represented, or only
  the court served by this arbitrable.
- Whether the V2 launch predates block 414M.

## Decision

Corpus expanded. Sensor remains GREEN.
Sample is representative by volume (178 >> 10) but
not demonstrated as complete for the V2 field.

## Next Observation

Two independent directions, each as a separate run:

1. Extend block range below 414M to determine
   whether ids < 118 exist.
2. Remove the arbitrable filter and query
   DisputeCreation over the same range to identify
   any additional arbitrable contracts.
