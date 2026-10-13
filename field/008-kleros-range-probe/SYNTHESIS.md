# Lead Synthesis — Kleros Range Probe

## FACT — Run-Level

- 296 unique DisputeCreation events identified across
  the full traversed range 164M..514M.
- IDs: 0..295, contiguous, no gaps.
- Single arbitrable for all 296:
  0xb5526d022962a1fff6ed32c93e8b714c901f4323.
- Block range: 164M..514M traversed (50M blocks
  below 214M returned zero).
- ID 0 confirmed present.
- Below 214M: 50M blocks with zero events.

## OBSERVATION

- The distribution of events is uneven across the
  traversal: recent chunks contain more events.
  Total per earlier window:
    214M..314M: 24 events
    314M..414M: 94 events
    414M..514M: 178 events
- The single-arbitrable result is confirmed across
  three independent traversal zones and both Run 006
  and Run 007.

## UNKNOWN

- Whether the field starts exactly at some block
  between 214M and 254M (not yet located).
- Whether the field has ever had another arbitrable
  in its history.
- Whether id 0 is the true first dispute.

## LEAD INTERPRETATION

The V2 field is now bounded in two directions:

- top: current head block
- bottom: somewhere between 214M and 254M

Total size in the observed range: 296 disputes.

The even distribution of IDs (no gaps 0..295) is
notable. Either the dispute counter starts at 0 and
increments without gaps, or the sample did not miss
any events in the traversed range.

## Decision

Range probe complete.
V2 field boundary identified.
First real corpus: 296 disputes, IDs 0..295.

## Next Observation

This is the first point at which Envoy has a
complete V2 dispute corpus for a bounded range.
The next step is not another probe but a first
descriptive summary of this corpus: block timing,
creation density, and whether clusters exist.

## Provenance

Raw commands and per-chunk results are preserved in
COMMANDS.md.
The full list of dispute IDs and blocks is preserved
in DISPUTES.md.
