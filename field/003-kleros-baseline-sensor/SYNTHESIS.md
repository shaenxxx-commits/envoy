# Lead Synthesis — Kleros Baseline Sensor

## FACT

Three independent External runs failed to produce the requested 10-case structured V2 dataset.

Two specific V2 cases were independently documented through public Kleros materials.

V1 structured cases were obtainable through Klerosboard.

The documented V2 Core subgraph requires authenticated access through the tested endpoint.

The tested V2 web interfaces are client-rendered applications whose data was not exposed by static extraction.

## OBSERVATION

The tested public access layer is insufficient for Envoy's current minimum sensor requirement.

The limitation appears specific to the V2 observation path rather than to Kleros as a whole.

## UNKNOWN

- Whether a valid The Graph API key is sufficient.
- Whether another public V2 data endpoint exists.
- Whether direct Arbitrum event extraction can produce the required sample.
- Whether V2 evidence references can be independently resolved.
- The exact size of the currently observable V2 dispute population.
- Whether the V2 UI has an undocumented usable data endpoint.

## LEAD INTERPRETATION

Current state:

DOCUMENTED
→ INDIVIDUALLY OBSERVABLE
→ NOT YET MACHINE-REPRODUCIBLE

This boundary is recorded as an observation, not a research hypothesis.

## Decision

Proceed with an on-chain sensor test.

## Provenance

This synthesis is Lead interpretation.

It must not be treated as an External statement.
