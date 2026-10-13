# Lead Synthesis — Kleros Arbitrable Probe

## FACT — Run-Level

- 178 DisputeCreation events retrieved.
- All 178 from one arbitrable:
  0xb5526d022962a1fff6ed32c93e8b714c901f4323.
- Unique dispute IDs: 178. Range 118 .. 295.
- Head block at run: 514 509 693.
- Chunk breakdown identical to Run 006.

## OBSERVATION

- Removing the arbitrable filter did not change the
  result. No second arbitrable appeared.
- The single-arbitrable picture is stable across two
  independent runs over the same block range.

## UNKNOWN

- Whether other arbitrables exist outside 414M..514M.
- Whether the single arbitrable is a whitelisting
  artifact of V2 beta.
- Whether disputes below id 118 exist.

## LEAD INTERPRETATION

The single-arbitrable result is now confirmed by two
runs, but only within the same traversed range.
This is a property of the observed range, not yet
of the field.

The absence of a second arbitrable within a ~100M
block range is not strong evidence of absence in the
field as a whole — but it is a real observation.

## Decision

Probe complete. Single arbitrable confirmed in range.

## Next Observation

Run 008: range probe below 414M.
