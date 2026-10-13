# Field Run 012 — Kleros Court x Time

FIELD: KLEROS
STAGE: CATEGORIZED SUMMARY (court x time)
STATUS: CLOSED
RESULT: three product waves identified

## Objective

Split the 296-dispute corpus by court and by quarter to
identify which court(s) drive the recent density spike.

## Method

Local joins of:
- /tmp/envoy_run009.json (id -> block)
- /tmp/envoy_run011_courtids.json (id -> courtID)
- /tmp/envoy_run010.json (11 timestamp samples)

Timestamps for intermediate blocks derived by linear
interpolation between known sample points.

## Court distribution

| courtID | name                       | total |
|---------|----------------------------|-------|
| 1       | General                    |   6   |
| 3       | Non-Technical              |   8   |
| 24      | Humanity                   |   3   |
| 29      | Consumo y Vecindad         |  87   |
| 31      | Automated Curation         |  21   |
| 32      | Defensores del Cliente     |  36   |
| 34      | Court 34                   | 135   |

## Court x quarter

| court | 24Q4 | 25Q1 | 25Q2 | 25Q3 | 25Q4 | 26Q1 | 26Q2 | 26Q3 | 26Q4 |
|-------|------|------|------|------|------|------|------|------|------|
|   1   |  0   |  1   |  0   |  5   |  0   |  0   |  0   |  0   |  0   |
|   3   |  4   |  4   |  0   |  0   |  0   |  0   |  0   |  0   |  0   |
|  24   |  0   |  0   |  0   |  3   |  0   |  0   |  0   |  0   |  0   |
|  29   |  5   |  6   | 37   | 22   | 10   |  0   |  1   |  6   |  0   |
|  31   |  0   |  7   | 13   |  1   |  0   |  0   |  0   |  0   |  0   |
|  32   |  0   |  0   |  0   |  0   |  0   |  4   | 20   | 11   |  1   |
|  34   |  0   |  0   |  0   |  0   |  0   |  0   |  0   |129   |  6   |

## Quarterly totals

| quarter | disputes |
|---------|----------|
| 2024-Q4 |    9     |
| 2025-Q1 |   18     |
| 2025-Q2 |   50     |
| 2025-Q3 |   31     |
| 2025-Q4 |   10     |
| 2026-Q1 |    4     |
| 2026-Q2 |   21     |
| 2026-Q3 |  146     |
| 2026-Q4 |    7     |

## Observations

Three distinct court-driven waves:

1. 2025 Q2-Q3 — court 29 (Consumo y Vecindad).
   Peak 37 in 2025-Q2.
2. 2026 Q2 — court 32 (Defensores del Cliente).
   Peak 20 in 2026-Q2, continuing 11 in 2026-Q3.
3. 2026 Q3 — court 34. 129 disputes in a single
   quarter. This is the recent density spike.

The recent spike is almost entirely one court.
129 of 146 disputes in 2026-Q3 belong to court 34.

## Unknown

- What court 34 is officially named.
- Whether court 34 is the "Agentic Commerce Court"
  identified in Run 002.
- What caused the sharp rise and fall of court 29
  (peak 2025-Q2, decay by 2025-Q4).
- Whether court 32 is a continuation or successor
  of court 29.

## Decision

Categorized summary complete.
Recent spike is court-34-driven.
Field has three distinct court-level activity waves.

## Next Observation

Identity of court 34. If Run 002 External claim is
correct, court 34 = Agentic Commerce Court. This can
be verified through the Kleros documentation or by
decoding MetaEvidence for several court-34 disputes.
