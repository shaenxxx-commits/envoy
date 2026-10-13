# Field Run 005 — Kleros On-Chain Sensor Verification

FIELD: KLEROS
STAGE: ON-CHAIN SENSOR VERIFICATION (local)
STATUS: CLOSED
SENSOR STATUS: GREEN

## Objective

Complete the Next Observation defined in Run 004:
verify the on-chain path from the local machine nova.
Run 004 External nodes failed in their sandboxed
environments.

Target: at least 5 real Kleros V2 dispute-creation
events retrieved directly from Arbitrum.

## Environment

- Machine: nova (local)
- Date: 2026-10-13
- RPC: https://arb1.arbitrum.io/rpc (public)
- Tooling: curl, python3 (keccak via /tmp venv)

## Method

1. Compute canonical topic0 for
   DisputeCreation(uint256,address) locally.
2. Verify contract bytecode exists at the reported
   KlerosCore proxy address.
3. Query eth_getLogs by topic0 over a bounded block
   range.
4. Decode event fields (dispute ID, arbitrable, block).
5. Verify dispute 295 via eth_call to disputes(uint256).

## Result

- Public RPC reachable from nova.
- Contract code present at
  0x991d2df165670b9cac3B022f4B68D65b664222ea (proxy).
- 6 DisputeCreation events retrieved over block range
  0x1ea00000..0x1eaab53f (~700 000 blocks).
- Dispute IDs: 290, 291, 292, 293, 294, 295.
- All six from arbitrable
  0xb5526d022962a1fff6ed32c93e8b714c901f4323.
- eth_call to disputes(295) returned:
  courtID = 34, period = 4, ruled = true.
- Court 34 corresponds to Agentic Commerce Court per
  Kleros documentation.

## Sensor Status

GREEN.

- A. CONTRACT DISCOVERY — GREEN
- B. EVENT DISCOVERY — GREEN (topic0 verified locally)
- C. ON-CHAIN EXTRACTION — GREEN
- D. DISPUTE IDENTIFICATION — GREEN
- E. MINIMUM DATASET — GREEN (6 >= 5)

## Discrepancy Recorded

Namazu (Run 004, MS6) reported topic0:

0x62e78dda5c29aa08e1998c76f3164f8f0a9eda8a7d3a9d3d7a70c20e6e9e5d7c

Locally computed canonical topic0:

0x141dfc18aa6a56fc816f44f0e9e2f1ebc92b15ab167770e17db5b084c10ed995

These do not match. The Namazu value is recorded as
an unverified External claim and is not used.

## Interpretation

The access barrier recorded in Run 004 was a property
of the External execution environments, not of the
Kleros field itself. Public Arbitrum RPC is reachable
and usable from nova.

## Decision

On-chain sensor is operational. Sensor status raised
from YELLOW (Run 004) to GREEN (Run 005).

## Next Observation

Extend the sample: expand eth_getLogs to cover a wider
block range and collect at least 10 V2 dispute IDs.
Preserve exact commands and raw responses.
