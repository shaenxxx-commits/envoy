# Field Run 010 — Kleros Descriptive Summary

FIELD: KLEROS
STAGE: DESCRIPTIVE SUMMARY
STATUS: CLOSED
RESULT: time distribution and density of V2 corpus

## Objective

Produce a descriptive summary of the 296-dispute V2
corpus identified in Run 009. Description only — no
interpretation, no hypothesis, no pattern analysis.

## Environment

- Machine: nova (local)
- Date: 2026-10-13
- RPC: https://arb1.arbitrum.io/rpc (public)

## Method

- ID -> block map from Run 009 (/tmp/envoy_run009.json).
- Sample timestamps: every 30th dispute, 11 samples.
- eth_getBlockByNumber for timestamp.
- Cluster detection: blocks with more than one dispute.
- Density buckets: 10M-block windows.

## Result

### Time span

- Start: 2024-11-14 06:14:53 UTC (id 0, block 274 289 504)
- End:   2026-10-12 10:50:59 UTC (id 295, block 514 090 528)
- Span:  239 801 024 blocks, ~697 days.
- Average block time observed: 0.251 sec.
- Average dispute rate: 0.42 per day.

### Timestamp samples

| id  | block       | timestamp (UTC)         |
|-----|-------------|--------------------------|
| 0   | 274289504   | 2024-11-14 06:14:53      |
| 30  | 325094694   | 2025-04-11 01:46:37      |
| 60  | 341166013   | 2025-05-27 19:24:50      |
| 90  | 367330771   | 2025-08-11 14:52:52      |
| 120 | 440052924   | 2026-03-09 17:51:22      |
| 150 | 495894648   | 2026-08-18 17:18:57      |
| 180 | 498315651   | 2026-08-25 18:07:34      |
| 210 | 503017746   | 2026-09-08 12:12:04      |
| 240 | 504040281   | 2026-09-11 11:50:03      |
| 270 | 506420250   | 2026-09-18 11:22:28      |
| 295 | 514090528   | 2026-10-12 10:50:59      |

### Clusters

Blocks containing more than one dispute:

- 11 blocks total.
- 29 disputes inside clusters (~10% of corpus).
- Maximum in one block: 3.

Top clustered blocks:

- 497987024 (3)
- 498202543 (3)
- 500355302 (3)
- 367768005 (3)
- 348418917 (3)

### Density per 10M-block window

| window (blocks)        | disputes |
|------------------------|----------|
| 270M..279M             |   5      |
| 280M..289M             |   4      |
| 290M..299M             |   3      |
| 300M..309M             |   6      |
| 310M..319M             |   9      |
| 320M..329M             |   8      |
| 330M..339M             |  18      |
| 340M..349M             |  23      |
| 350M..359M             |   7      |
| 360M..369M             |  11      |
| 370M..379M             |  13      |
| 380M..389M             |   1      |
| 390M..399M             |   8      |
| 400M..409M             |   1      |
| 410M..419M             |   1      |
| 420M..429M             |   0      |
| 430M..439M             |   1      |
| 440M..449M             |   6      |
| 450M..459M             |  12      |
| 460M..469M             |   4      |
| 470M..479M             |   2      |
| 480M..489M             |   4      |
| 490M..499M             |  43      |
| 500M..509M             |  99      |
| 510M..519M             |   7      |

## Observations

- The corpus spans ~1.9 years.
- 48% of all disputes (142/296) fall into the last
  two 10M-block windows (490M..509M).
- The highest-density window is 500M..509M (99 events).
- Two windows (420M..429M) contain zero events.
- Cluster events are small and rare.

## Decision

Descriptive summary complete.
No pattern interpretation performed.

## Next Observation

The next step is not yet defined by the field.
A first pass at interpretation or a targeted
question can now be formulated, but only after
Architect input on direction.
