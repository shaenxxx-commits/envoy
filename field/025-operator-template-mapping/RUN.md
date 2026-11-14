# Field Run 025 — Operator × Template Mapping

FIELD: KLEROS
STAGE: OPERATOR-TEMPLATE MAPPING
STATUS: CLOSED
RESULT: field is multi-layer; +14% growth in one month

## Objective

Answer the question left open since Run 020: which
EOA operator uses which policy template. Specifically,
whether the two dominant templates (Lemon-branded
and generic v2.1.0) are used by different operators
or shared by all.

## Method

Full re-extraction of the corpus (local /tmp was
cleared during the month-long gap). One pass:

1. All DisputeCreation events via eth_getLogs
   (30 chunks of 10M blocks).
2. For each dispute: courtID (disputes view),
   tx.from, tx.to, and the
   DisputeTemplateRegistry policyURI.
3. Join sender × policyURI.

## Corpus state at run time

- Head block: 524 179 022
- Total disputes: 342 (was 300 on 2026-10-15)
- Growth: +42 disputes in 30 days (+14%)
- Unique senders: 11 (was 5)
- Dominant templates unchanged:
  - LEMON: QmbEs5Ae8Sh5W... (95 disputes)
  - GENERIC v2.1.0: QmUbgqKuUvfsnW... (74 disputes)

## Sender × policy matrix

### Large operators (274 of 342 = 80%)

| Sender                                          | Total | LEMON | GENERIC | OTHER |
|-------------------------------------------------|-------|-------|---------|-------|
| 0xe66f7f8abef94c22e02fdc075fd5da5a0c5ba225      | 143   | 42    | 29      | 72    |
| 0xd0d5fad9380bcd518a2b387032583d700f570d0e      | 131   | 47    | 36      | 48    |

Both large operators use BOTH dominant templates
in parallel. Neither is "the Lemon operator" or
"the generic operator".

### Medium operator (new since October)

| Sender                                          | Total | LEMON | GENERIC | OTHER |
|-------------------------------------------------|-------|-------|---------|-------|
| 0x9e51bbd7584afd0fb2e4bddab37f23a9f192d30a      | 30    | 4     | 8       | 18    |
| 0x6687c671980e65ebd722b9146fc61e2471558dd6      | 21    | 0     | 0       | 21    |
| 0xf1c7c037891525e360c59f708739ac09a7670c59      | 6     | 0     | 1       | 5     |

0x6687c671 is new: 21 disputes in the last month,
all with unique OTHER templates, no LEMON or
GENERIC usage.

### Minor senders (1-4 disputes)

0xdde30f65, 0x40137872, 0x8d8501a6, 0x5ae31b43,
0x87770be0, 0x4b0a9983 — six small operators,
most of them new during the gap.

## Policy distribution overall

| Template                       | Count |
|--------------------------------|-------|
| LEMON (QmbEs5Ae8Sh5W...)       | 95    |
| GENERIC v2.1.0 (QmUbgqKuUv...) | 74    |
| OTHER (unique per dispute)     | 173   |

173 of 342 disputes (51%) use unique one-off
templates with 1-2 disputes each. This is not
enterprise — this is retail usage through the
DisputeResolver web form.

## Observations

1. The two dominant templates are not split by
   operator. Both large operators use both. So
   the earlier hypothesis (Lemon on Lemon-template,
   everyone else on generic) is not supported.

2. New layer: retail users with unique templates.
   Half the corpus is now single-use policy
   documents. This is a structural change relative
   to Run 014 (where 61% was on the two dominant
   templates and 39% was spread over 44 unique
   URIs). The "other" share grew from 39% to 51%.

3. New medium operator 0x6687c671 appeared during
   the month with 21 disputes, all unique templates.
   Identity UNKNOWN.

4. Growth continues but at low absolute numbers.
   342 disputes = 0.47 per day over ~2 years.

## Unknown

- Identity of 0x6687c671 and its 21 disputes.
- What Qmassb4g is (16 disputes — third most
  frequent template).
- What the 72 OTHER templates at 0xe66f7f8a
  represent: tests, one-off retail users, or
  something else.
- Whether the retail-layer growth is a trend or
  a single-month spike.

## Decision

Run 025 answers the operator-template question:
operators are NOT split by template. Both dominant
templates run in parallel at both dominant operators.

New finding: half the corpus is now retail users
with unique templates. This layer was not visible
in October.

Resource-assessment impact: field remains small in
absolute terms, but has a new layer. Growth
trajectory needs one more data point (Run 026).

## Next Observation

Run 026: temporal dynamics. When did the 42 new
disputes arrive? Is the retail layer growing
smoothly or in bursts? Without this, we cannot
distinguish "active field" from "one-month spike".

## Provenance

Raw mapping at raw-mapping.json.
All data from public RPC Arbitrum.
