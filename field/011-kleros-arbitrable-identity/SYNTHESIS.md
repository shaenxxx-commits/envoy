# Lead Synthesis — Kleros Arbitrable Identity

## FACT — Run-Level

- The single arbitrable emitting all 296 events is
  DisputeResolver:
  0xb5526d022962a1fff6ed32c93e8b714c901f4323.
- It is listed in the official Kleros V2 deployment
  addresses for Arbitrum One.
- It is not a token and not a proxy; it implements
  ERC-792 events (DisputeRequest, Ruling).
- 296 disputes are distributed across 7 courtIDs:
  1, 3, 24, 29, 31, 32, 34.
- Court 34 accounts for 135 disputes, court 29 for 87,
  court 32 for 36, court 31 for 21, court 3 for 8,
  court 1 for 6, court 24 for 3.
- A sampled MetaEvidence (dispute 289, court 31) is a
  user-supplied Spanish-language template.

## OBSERVATION

- The events emitted by DisputeResolver match the
  standard ERC-792 Arbitrable pattern, not a custom
  product event set.
- Courts 29 and 32 (Argentina consumer protection)
  together account for 123 of 296 disputes (~42%).
- Court 34 (Agentic Commerce) accounts for 135 of 296
  (~46%).
- The remaining ~12% are spread across general and
  technical courts.

## UNKNOWN

- Whether court 34 is truly "Agentic Commerce Court"
  or the ID has been reused.
- What fraction of the recent density spike belongs
  to each court.
- Whether all MetaEvidence templates through this
  gateway are user-created or mixed.

## LEAD INTERPRETATION

The identification changes the framing of the field:

- The corpus is not a single product's dispute log.
  It is the aggregate of disputes opened through a
  shared public Kleros tool.
- The arbitrable is generic: any user can create a
  dispute via DisputeResolver.
- The court distribution shows the field is spread
  across both general-purpose courts (1, 3) and
  specialized ones (29, 31, 32, 34).

This means the corpus describes Kleros V2 usage
through one public gateway, not a single integrator.

## Decision

Field identity established.
The corpus from Runs 006-010 is now attributable.

## Next Observation

Categorized summary: split the 296 disputes by court
and by time, and identify which court(s) drive the
recent density spike.

## Provenance

Raw commands preserved in COMMANDS.md.
Court map preserved in COURTS.md.
