# Field Run 003 — Kleros Baseline Sensor

FIELD: KLEROS
STAGE: BASELINE SENSOR TEST
STATUS: CLOSED
SENSOR STATUS: YELLOW

## Objective

Determine whether Envoy can construct a reproducible minimum sensor for 10 real Kleros V2 disputes, preferably resolved Arbitrum cases.

## Target Dataset

Minimum 10 real V2 disputes with, where available:

- dispute ID
- chain
- court
- type
- date / block
- status
- ruling
- rounds
- dispute kit
- evidence reference
- evidence availability
- juror / vote availability
- reproducible source

## External Runs

- Kimi — MS5
- Namazu — MS5
- Grok 4.5 — MS4

Raw responses are preserved separately.

## Combined Result

No External node produced a complete structured dataset of 10 V2 disputes.

### Kimi

Three Lemon cases were found in Kleros research documentation.

Their mapping to on-chain Kleros V2 dispute IDs remained UNKNOWN.

A UDRP section also appeared unexpectedly in the response and is treated as contamination / deviation, not Kleros V2 evidence.

### Namazu

0 V2 disputes obtained in structured form.

V1 cases were successfully observed through Klerosboard, demonstrating that structured observation works for parts of the V1 environment.

### Grok

2 specific resolved V2 cases were documented from official Kleros materials.

A complete 10-case structured dataset was not obtained.

## Common Access Boundary

The three External runs independently encountered:

1. The Graph V2 Core subgraph requires authorization.
2. Kleros V2 UI is a SPA and static extraction does not expose case data.
3. No reproducible public bulk list of 10 resolved V2 disputes was obtained.
4. Evidence content was not independently verified for the documented cases.

## Interpretation

The field is publicly documented and individual V2 cases can be identified.

However, public documentation / individual observability does not currently equal a machine-reproducible dataset through the tested access paths.

V1 provides a useful contrast because structured cases were accessible there.

This result is an observation about Envoy's current sensor capability, not yet a hypothesis about Kleros itself.

## Decision

SENSOR STATUS = YELLOW.

Do not begin pattern analysis.

Do not treat the access barrier as evidence of intentional restriction without further observation.

## Next Observation

Test an independent on-chain route:

Arbitrum
→ KlerosCore events
→ DisputeCreation
→ dispute IDs
→ V2 metadata
→ minimum reproducible sample.

The purpose is to determine whether a V2 sensor can be constructed without dependence on The Graph API key.
