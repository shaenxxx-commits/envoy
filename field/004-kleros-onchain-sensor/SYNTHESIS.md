# Lead Synthesis — Kleros On-Chain Sensor

## FACT — Run-Level

- Three independent External runs completed.
- None returned an actual on-chain DisputeCreation log.
- No V2 dispute ID was extracted from a primary on-chain log.
- Minimum dataset target was not reached: 0 records.

## EXTERNAL CLAIMS — NOT INDEPENDENTLY VERIFIED HERE

- All three nodes reported the same KlerosCore V2 proxy address on Arbitrum One:
  0x991d2df165670b9cac3B022f4B68D65b664222ea
- All three identified the event as DisputeCreation(uint256,address).
- Namazu supplied a topic0 value. No chain log was obtained to validate it.
  Kimi could not compute or confirm the hash.
  Grok did not independently extract it from a verified ABI or on-chain log.

These claims must not be promoted to direct on-chain FACT solely because they recur across External responses.

## OBSERVATION

All three nodes failed at the extraction stage, but through different reported execution constraints:
- deprecated API endpoints;
- page extraction failure;
- empty RPC response bodies;
- request timeouts.

This supports the narrow conclusion that the tested External environments did not provide a usable on-chain extraction path during this run.

It does not establish that public Arbitrum RPC is generally unavailable, nor that Kleros V2 logs cannot be retrieved elsewhere.

## UNKNOWN

- Whether the reported proxy address is the correct active V2 contract at the current block.
- The independently computed canonical topic0.
- Whether a public RPC works from the local machine nova.
- Whether eth_getLogs can retrieve the contract historical creation events.
- Whether dispute IDs and court metadata can be mapped reproducibly from returned logs.
- Whether a minimum sample of 5-10 V2 disputes can be assembled.

## LEAD INTERPRETATION

Current state:

DOCUMENTED PATH
-> ARCHITECTURALLY PLAUSIBLE
-> NOT YET OPERATIONALLY DEMONSTRATED

This is a statement about the state of the sensor, not about Kleros itself.

## Decision

SENSOR STATUS = YELLOW.

The documented architecture suggests a plausible route, but the sensor has not been demonstrated operationally. No pattern analysis is authorized on the basis of this run.

## Next Observation

On nova, independently verify the contract and event signature.
First query eth_blockNumber. Only if the response is valid, issue a narrowly scoped eth_getLogs request.
Preserve the exact request and raw response.
Continue to bulk extraction only after at least one log is independently verified.

## Provenance

This is Lead synthesis, not an External statement.
The raw External responses are preserved in separate files.
