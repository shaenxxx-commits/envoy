# Field Run 011 — Kleros Arbitrable Identity

FIELD: KLEROS
STAGE: ARBITRABLE IDENTITY
STATUS: CLOSED
RESULT: arbitrable = DisputeResolver; 7 courts mapped

## Objective

Identify the single arbitrable contract that emits all
296 V2 DisputeCreation events, and map the courts it
uses.

## Environment

- Machine: nova (local)
- Date: 2026-10-13
- RPC: https://arb1.arbitrum.io/rpc (public)

## Method

1. eth_getCode on 0xb5526d...4323.
2. Standard ERC selectors via eth_call (name, symbol).
3. eth_getLogs on arbitrable address to identify its
   emitted events.
4. topic0 identification via keccak256.
5. Full transaction receipt decode.
6. MetaEvidence extraction from DisputeTemplateRegistry.
7. courts(uint256) on KlerosCore for each courtID used.

## Result

### Arbitrable identity

0xb5526d022962a1fff6ed32c93e8b714c901f4323 =
DisputeResolver (Kleros), per official Kleros
deployment list.

Not a token, not a proxy. ERC-792 Arbitrable.

Events emitted: DisputeRequest(address,uint256,uint256,uint256,string)
and Ruling(address,uint256,uint256).

### Court distribution

Across 296 disputes:

| courtID | name                              | count |
|---------|-----------------------------------|-------|
| 34      | Agentic Commerce (per Run 002)    | 135   |
| 29      | Corte de Disputas de Consumo y Vecindad | 87 |
| 32      | Corte de Defensores del Cliente   | 36    |
| 31      | Automated Curation                | 21    |
| 3       | Non-Technical                     | 8     |
| 1       | General Court                     | 6     |
| 24      | Humanity Court                    | 3     |

### Court parameters (from courts(uint256))

7 distinct courtIDs observed. Courts 29 and 32 share
identical parameters (minStake, feeForJuror, timing);
32 is parented to 29.

### MetaEvidence sample

A sampled dispute (id 289, court 31) carried
MetaEvidence in Spanish:

- title: "¿Es válido el reclamo?"
- category: "Junín"
- policyURI: /ipfs/Qmassb4gkqJ6h7e7JTRgfCWPMEeoLU72PWbPmhjTAMQwF4
- disputeKitData: type "gated", tokenGate 0x2a2f1fbb...
- arbitratorAddress: KlerosCore V2

This is a user-supplied template, not a product
signature.

## Interpretation

DisputeResolver is a generic Kleros tool: any user can
open a dispute through a web form. The 296 disputes
are therefore not one product's history but the
aggregate of disputes created through this shared
gateway across 7 courts over ~1.9 years.

## Decision

Arbitrable identity resolved.
Court map complete.
Run 006-010 corpus is now attributable:
296 disputes via DisputeResolver, 7 courts.

## Next Observation

With the field now identified, the next step is a
categorized summary: which courts correspond to which
periods, whether the recent density spike is court-
specific, and whether courts 29/32 (Argentina consumer)
drive the pattern.
