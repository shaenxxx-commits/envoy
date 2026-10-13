# Lead Synthesis — Kleros On-Chain Sensor Verification

## FACT — Run-Level

- Public Arbitrum RPC (https://arb1.arbitrum.io/rpc) was
  reachable from nova on 2026-10-13.
- Contract bytecode exists at
  0x991d2df165670b9cac3B022f4B68D65b664222ea.
- The canonical topic0 for DisputeCreation(uint256,address)
  was computed locally:
  0x141dfc18aa6a56fc816f44f0e9e2f1ebc92b15ab167770e17db5b084c10ed995
- eth_getLogs returned 6 matching DisputeCreation events
  over block range 0x1ea00000..0x1eaab53f.
- Dispute IDs: 290, 291, 292, 293, 294, 295.
- All six from one arbitrable:
  0xb5526d022962a1fff6ed32c93e8b714c901f4323.
- eth_call to disputes(295) returned courtID = 34,
  period = 4, ruled = true.

## OBSERVATION

- The blocker recorded in Run 004 was environmental,
  not field-level. Three External nodes failed inside
  their sandboxes; the same operations succeeded from
  nova.
- Court 34 is consistent with Agentic Commerce Court
  as described in Run 002 by External nodes.

## UNKNOWN

- Full V2 dispute population size.
- Whether all V2 disputes are from the same arbitrable
  or a wider set.
- Whether dispute 290 predates 291-295 (same arbitrable,
  clustered in ~20 000 blocks).
- Whether the sample is representative of the V2 field
  or only of one court.
- Whether public RPC rate-limits apply over wider
  block ranges.

## LEAD INTERPRETATION

The on-chain sensor is operational from nova. The
YELLOW status in Run 004 reflected External sandbox
limitations, not the Kleros field.

The topic0 reported by Namazu (Run 004, MS6) is not
confirmed and is superseded by the locally computed
canonical value. This is a corrective observation,
not a criticism of the External node — the value was
already marked unverified in Run 004.

## Decision

SENSOR STATUS = GREEN.

The Next Observation from Run 004 is satisfied.

## Next Observation

Extend the sample to >= 10 V2 dispute IDs across a
wider block range. Preserve exact request and raw
response for each extraction. Verify each dispute ID
via eth_call to confirm courtID and ruled status.

Do not begin pattern analysis until the sample is
stabilized and reproduced.

## Provenance

This is Lead synthesis. Raw RPC responses and exact
commands are preserved in COMMANDS.md.
