# Field Run 007 — Kleros Arbitrable Probe

FIELD: KLEROS
STAGE: ARBITRABLE PROBE
STATUS: CLOSED
RESULT: single arbitrable confirmed

## Objective

Complete the first of two probes defined in Run 006:
determine whether V2 DisputeCreation events originate
from more than one arbitrable contract.

Filter on arbitrable removed — only topic0 filter kept.

## Environment

- Machine: nova (local)
- Date: 2026-10-13
- RPC: https://arb1.arbitrum.io/rpc (public)
- Head block at run: 514 509 693

## Method

Same paginated eth_getLogs as Run 006, but without
filtering on a specific arbitrable.
Contract: 0x991d2df165670b9cac3B022f4B68D65b664222ea
Topic0:   0x141dfc18aa6a56fc816f44f0e9e2f1ebc92b15ab167770e17db5b084c10ed995

10 chunks of 10M blocks backwards.

## Result

Total events: 178
Unique arbitrable contracts: 1
Arbitrable: 0xb5526d022962a1fff6ed32c93e8b714c901f4323
Unique dispute IDs: 178
ID range: 118 .. 295

Chunk breakdown matches Run 006.

## Interpretation

Within the traversed block range 414M..514M, every
DisputeCreation event at KlerosCore V2 is emitted by
a single arbitrable contract.

This may reflect Kleros V2 beta whitelisting, or it
may indicate that other arbitrables exist outside the
traversed range. Not resolved by this run.

## Decision

Arbitrable probe complete.
Single arbitrable confirmed for the traversed range.
Second probe (range extension below 414M) proceeds
as Run 008.

## Next Observation

Run 008: extend the block range below 414M to test
whether earlier disputes or additional arbitrables
exist.
