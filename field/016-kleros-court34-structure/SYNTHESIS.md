# Lead Synthesis — Court 34 Structural Parameters

## FACT — Run-Level

- Court 34 parent = 33. Court 33 parent = 1 (General).
- Courts 35..45 do not exist. Court 34 is the top.
- All 300 disputes: period=4, ruled=true.
- Ruling distribution: 0:18, 1:138, 2:137, 3:6, 4:1.
- DisputeResolver calls KlerosCore with courtID as
  argument (selector 0xdc653511, dispute 295 tx).
- Corpus grew 296 -> 300 during the session.

## OBSERVATION

- The "no court above 34" result weakens the hypothesis
  that a dedicated Agentic-specific court exists above
  court 34. Court 34 is the last court in this
  deployment.
- Rulings 3 and 4 suggest at least some disputes use
  a multi-option dispute kit, not Classic.
- The field is actively producing new disputes
  (4 during a single session).

## UNKNOWN

- PolicyRegistry URI for court 34 (not returned by
  courts(34); may require a separate PolicyRegistry
  contract).
- disputeKitId per dispute.
- Whether court 34 is currently still accepting new
  disputes, or the 4 new ones were already in flight.

## LEAD INTERPRETATION

The structural questions raised by External review
are largely answered:

- Court 34 is officially named Agentic Commerce Court
  per external docs (Run 015), has parent 33, is the
  top court of the deployment, and currently accepts
  heterogeneous dispute types through DisputeResolver.
- All observed disputes are resolved.
- The corpus is not frozen; it grows.

Combining Run 015 and Run 016: court 34 is a named,
top-level, general-use court that accepts the
DisputeResolver gateway.

## Decision

Structural stage closed except PolicyRegistry URI.
Next: Phase 4 filter assessment and ROLES status.

## Next Observation

Run 017: Phase 4 — filter assessment (per ROADMAP).
