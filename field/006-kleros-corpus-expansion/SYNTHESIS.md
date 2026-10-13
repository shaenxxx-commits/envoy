# Lead Synthesis — Kleros V2 Corpus Expansion

## FACT — Run-Level

- 178 unique DisputeCreation events retrieved from
  Arbitrum One via public RPC, from nova.
- Address: 0x991d2df165670b9cac3B022f4B68D65b664222ea.
- Topic0: 0x141dfc18aa6a56fc816f44f0e9e2f1ebc92b15ab167770e17db5b084c10ed995.
- Dispute ID range: 118 .. 295.
- Block range: 431 728 818 .. 514 090 528.
- All 178 events originate from a single arbitrable:
  0xb5526d022962a1fff6ed32c93e8b714c901f4323.
- Chunk 9 (blocks 414M..424M) returned zero events.

## OBSERVATION

- The distribution across chunks is uneven: chunks 0
  and 1 (last ~20M blocks) contain 147 of 178 events
  (~83%). Earlier chunks contain few or none.
- Multiple disputes share individual blocks
  (e.g. blocks 497987024, 499350169, 500355302).
  Consistent with batch or rapid creation.
- Lowest id observed is 118. No lower id appeared
  within the traversed range.

## UNKNOWN

- Whether V2 disputes with id < 118 exist.
- Whether V2 has other arbitrable contracts beyond
  0xb5526d...4323.
- Whether the queried court (single arbitrable) is
  the only court, or the only one visible through
  this arbitrable.
- Whether the V2 contract existed at blocks below
  414M.
- Whether dispute id 118 is genuinely the first
  V2 dispute, or merely the first within the
  traversed block range.

## LEAD INTERPRETATION

The corpus is now representative by volume — 178
events is far above the target of 10 and gives a
usable sample. But representativeness by volume
is not the same as completeness of the field.

Two structural facts stand out and are not yet
resolved:

1. All 178 disputes come from one arbitrable.
   This may mean the V2 field is dominated by one
   arbitrable in the observed period, or that other
   arbitrables exist outside the traversed range.
2. The lowest id is 118, and the traversed range
   returned zero events below block 431M. Two
   explanations: the V2 field started with id 118,
   or earlier ids exist outside the traversed range.

Neither fact should be treated as a conclusion
about the field. They are observations that
generate the two next steps.

## Decision

SENSOR STATUS = GREEN (extended corpus).
The Run 005 Next Observation is satisfied by volume.
Completeness remains undetermined.

## Next Observation

Two independent probes, each as a separate run:

1. Range probe: extend eth_getLogs below block 414M
   to determine whether ids < 118 exist.
2. Arbitrable probe: remove the arbitrable filter
   and query DisputeCreation over the same range
   to enumerate any additional arbitrable contracts.

Do not begin pattern analysis until both probes
complete.

## Provenance

This is Lead synthesis.
Raw RPC responses and exact commands are preserved
in COMMANDS.md.
