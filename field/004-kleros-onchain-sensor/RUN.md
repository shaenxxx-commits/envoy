# Field Run 004 — Kleros On-Chain Sensor

FIELD: KLEROS
STAGE: ON-CHAIN SENSOR TEST v0.1
STATUS: CLOSED
SENSOR STATUS: YELLOW

## Objective

Test whether Envoy can obtain real Kleros V2 dispute-creation logs directly from Arbitrum One without relying on The Graph API.

Target dataset: at least 5 real V2 disputes, preferably 10.

## External Runs

- Grok 4.5 — MS5
- Namazu — MS6
- Kimi K2 Thinking — MS6

Raw responses are preserved separately in this directory.

## Combined Result

No External node retrieved an actual on-chain DisputeCreation log during this run.
No real V2 dispute ID was extracted from a primary on-chain log.
Minimum dataset reached: 0 records.

## Commonly Reported Technical Details

All three External nodes reported the same KlerosCore V2 proxy address on Arbitrum One:

0x991d2df165670b9cac3B022f4B68D65b664222ea

All three identified the documented event signature:

DisputeCreation(uint256,address)

These are recorded as claims reported by the External nodes, not as independently verified on-chain observations from this run.

Namazu reported a topic0 value. Kimi explicitly did not compute or confirm it. Grok did not extract it from a verified ABI or on-chain log. The topic0 value was not independently verified in this run.

## Access Failures Reported

- Grok: explorer extraction failed; the tested Arbiscan API endpoints reported deprecation; no direct RPC log query was completed.
- Namazu: three public RPC endpoints returned empty response bodies in its execution environment.
- Kimi: Arbiscan and public RPC attempts timed out.

These are observations about the External nodes execution environments. They do not prove that public RPC access is generally unavailable.

## Interpretation

The architectural path is documented but the practical sensor remains unproven because zero real logs were extracted.

Do not proceed to pattern analysis.
Do not treat secondary-source case IDs as on-chain-confirmed IDs.

## Decision

SENSOR STATUS = YELLOW.

## Next Observation

On the local machine nova, independently validate the contract address and compute the canonical topic0 from the event signature. Then perform one small JSON-RPC request to a public Arbitrum endpoint (eth_blockNumber first, then a narrowly scoped eth_getLogs test).

Preserve the exact request and raw response. Do not begin bulk extraction until at least one log has been independently verified.
