# Field Run 026 — Temporal Dynamics

FIELD: KLEROS
STAGE: TEMPORAL ANALYSIS
STATUS: CLOSED
RESULT: growth driven by one operator; retail layer
        is historical, not growing

## Objective

Answer the Next Observation from Run 025: when did
the 42 new disputes arrive, and is the retail layer
growing smoothly or in bursts?

Without this, we could not distinguish "active
field" from "one-month spike" or "retail transition"
from "single-operator campaign".

## Method

Local join of /tmp/envoy_run025.json (already
contains block per dispute). Sampled 44 timestamps
across the full block range 274289504..522734131
via eth_getBlockByNumber. Interpolated timestamps
for intermediate blocks. Aggregated by month and
by operator per month.

## Result

### Disputes per month (full history)

| Month    | Disputes |
|----------|----------|
| 2024-11  |    5     |
| 2024-12  |    4     |
| 2025-01  |    3     |
| 2025-02  |    7     |
| 2025-03  |    8     |
| 2025-04  |    8     |
| 2025-05  |   28     |
| 2025-06  |   14     |
| 2025-07  |    7     |
| 2025-08  |   16     |
| 2025-09  |    8     |
| 2025-10  |    5     |
| 2025-11  |    4     |
| 2025-12  |    1     |
| 2026-02  |    1     |
| 2026-03  |    3     |
| 2026-04  |   13     |
| 2026-05  |    6     |
| 2026-06  |    2     |
| 2026-07  |    4     |
| 2026-08  |   46     |
| 2026-09  |   96     |
| 2026-10  |   40     |
| 2026-11  |   13     |

### Last three months by operator

| Month    | 0xe66f7f8a | 0xd0d5fad9 | Others |
|----------|------------|------------|--------|
| 2026-09  |     84     |      9     |   3    |
| 2026-10  |     35     |      3     |   2    |
| 2026-11  |     12     |      1     |   0    |

## Observations

1. The field is not in steady retail growth. It has
   two burst periods:
   - 2025-05: 28 disputes (peak);
   - 2026-08-09: 46 + 96 (much larger peak).

2. The 2026-08-09 peak is dominated by one operator
   (0xe66f7f8a: 84 of 96 in September).

3. The other large operator (0xd0d5fad9) is
   declining: 9 -> 3 -> 1 across September-November.

4. The retail layer identified in Run 025 (51%
   unique templates overall) is a historical
   accumulation, not recent growth. Recent months
   are dominated by 0xe66f7f8a.

5. Monthly average (24 months): ~14 disputes.
   Median: ~7. The field is small.

## Revision to Run 025

Run 025 said the field is "two large operators
plus a growing retail tail". Run 026 shows:
- retail is historical, not growing;
- one operator dominates recent months;
- the other operator is declining.

The "three-layer" model of Run 025 stands
structurally, but the "growing retail" part is
retracted.

## Unknown

- Identity of 0xe66f7f8a (dominant operator).
- What triggered the 2025-05 burst (28 disputes).
- What triggered the 2026-08 burst (Agentic launch?
  Mendoza expansion? Lemon scaling?).
- Whether the decline of 0xd0d5fad9 is a real
  shift or a temporary pause.

## Decision

Run 026 answers the temporal question: growth is
burst-driven and concentrated in one operator.
Retail layer is not growing.

Resource-assessment impact: field is smaller than
Run 025 impression suggested. Recent growth is one
operator's campaign, not market-wide.

## Next Observation

External search for identity of 0xe66f7f8a.
Without knowing who this operator is, the resource
assessment cannot distinguish:
- "Lemon scaling their own program";
- "a partner scaling";
- "test campaign";
- "something else".

Run 027: external search.

## Provenance

Raw data from /tmp/envoy_run025.json.
Timestamps sampled and interpolated; see COMMANDS.md.
