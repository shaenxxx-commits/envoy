# Lead Synthesis — Kleros Full Corpus Extraction

## FACT — Run-Level

- 296 unique V2 disputes, IDs 0..295, no gaps.
- All from a single arbitrable:
  0xb5526d022962a1fff6ed32c93e8b714c901f4323.
- Start block (id 0): 274 289 504.
- End block (id 295): 514 090 528.
- Below block 274M: 0 events across 60M traversed.
- Between 274M and 514M: 296 events.
- Head block at run: 514 511 288.

## OBSERVATION

- The corpus spans approximately 240M blocks, from
  V2 launch to head. At ~0.25s per block, this is
  roughly 1.5-2 years of field history.
- The ID sequence is contiguous with no gaps.
  Either Kleros V2 increments its dispute counter
  strictly and no dispute failed to emit, or the
  traversal missed nothing.

## UNKNOWN

- Whether any V2 dispute ever came from another
  arbitrable. None seen in the corpus.
- Whether V2 dispute creation is currently paused
  or ongoing.
- Whether the ID 0 block is also the block of V2
  contract deployment. The contract may have been
  deployed earlier than its first dispute.

## LEAD INTERPRETATION

The V2 field, as observed through on-chain
DisputeCreation events, is:

- bounded: block 274 289 504 .. 514 090 528
- contiguous: 296 disputes, no gaps
- single-arbitrable: one contract creates all disputes

These three properties are now established for the
traversed range and stable across Runs 005-009.

This is the first point at which Envoy holds a
complete field corpus for a bounded range.

## Decision

Corpus extraction complete.
ID -> block map preserved.

## Next Observation

Proceed to a descriptive summary: time distribution,
creation density per period, existence of clusters.
No interpretation yet — description only.

## Provenance

Raw commands preserved in COMMANDS.md.
Full ID -> block map in DISPUTES.md.
