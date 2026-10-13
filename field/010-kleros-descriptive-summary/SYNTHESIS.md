# Lead Synthesis — Kleros Descriptive Summary

## FACT — Run-Level

- V2 field spans 2024-11-14 to 2026-10-12.
- 296 disputes in ~697 days.
- Average rate: 0.42 disputes/day.
- Block time observed: 0.251 sec.
- 11 blocks contain more than one dispute.
- Maximum disputes in a single block: 3.
- 142 of 296 disputes (48%) fall into the last
  20M-block window pair (490M..509M).

## OBSERVATION

- The distribution is not uniform over time.
- Early period (2024-11 .. 2025-08): slow but
  continuous accumulation, single disputes.
- Recent period (2026-09 .. 2026-10): sharply higher
  creation density, including many blocks with
  multiple disputes.
- The two windows around 420M..429M contain zero
  events.

## UNKNOWN

- Whether the recent density reflects real field
  activity, test-driven creation, or a new use case.
- Whether the corpus is complete up to a specific
  block, or whether it continues to grow at the
  same pace.
- Whether id 0 is the first real dispute or a test.
- Whether other arbitrables or older contracts
  exist outside the queried address.

## LEAD INTERPRETATION

This summary is descriptive. No hypothesis about
Kleros or about the field's meaning is proposed
here.

The most salient descriptive feature is the sharp
increase in dispute creation density in the last
few months, and the appearance of block-level
clusters.

## Decision

Descriptive summary complete.
Corpus description stable for the current snapshot.

## Next Observation

Interpretation direction requires Architect input.
Two candidate directions, not yet chosen:

1. Focus on the recent high-density period.
2. Focus on the whole corpus as a stable baseline.
