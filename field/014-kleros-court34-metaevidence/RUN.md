# Field Run 014 — Court 34 Full MetaEvidence Classification

FIELD: KLEROS
STAGE: FULL METAEDIDENCE CLASSIFICATION
STATUS: CLOSED
RESULT: two Spanish consumer templates dominate

## Objective

Classify all 135 court-34 disputes by MetaEvidence
policyURI and category. Determine whether one product
or many independent users drive the 2026-Q3 spike.

## Method

For each of 135 disputes:
1. eth_getLogs filtered by dispute ID at creation block.
2. eth_getTransactionReceipt for the tx.
3. Decode the DisputeTemplateRegistry event.
4. Extract policyURI, category, title.

## Result

Classified: 135 of 135.
Unique policyURI: 46.

Dominant URIs:

| policyURI                            | count | Services | Agentic Commerce |
|--------------------------------------|-------|----------|------------------|
| /ipfs/QmbEs5Ae8Sh5WaMAchUiNLhRqSe9ossQMaRV5mZ1L5uqom | 46 | 42 | 3 |
| /ipfs/QmUbgqKuUvfsnWLP6o8GhZu8jcCaD31GUSZSSexe11fZco | 37 | 30 | 7 |
| 44 others                            | 52    | 15       | 14               |

Category distribution:

| category                      | count |
|-------------------------------|-------|
| Services                      |  87   |
| Agentic Commerce              |  24   |
| Oracle                        |  11   |
| Image Generation              |   2   |
| prediction_market.*           |   5   |
| IP                            |   1   |
| Escrow                        |   1   |
| Ticket — automated enforcement|   1   |
| (empty)                       |   1   |
| Agentic Finance               |   1   |

## Observations

- Two Spanish-language consumer templates account for
  83 of 135 court-34 disputes (61%).
- Both templates use the same question family:
  "¿Es válido el reclamo?" and
  "¿Debería la empresa pagar la compensación...".
- The category field is user-supplied. Within a single
  policyURI the same template is labeled both
  "Services" and "Agentic Commerce".
- "Agentic Commerce" as a category is not tied to a
  unique template and appears in 24 disputes across
  multiple policyURIs.

## Discrepancy with Run 002

Run 002 (External Kimi, Grok) identified court 34 as
"Agentic Commerce Court". Full classification of the
court's MetaEvidence shows this is not accurate:

- court 34 is general-purpose;
- its 2026-Q3 spike is driven by Spanish consumer
  disputes;
- "Agentic Commerce" is a user-supplied category used
  inconsistently, not a court-level property.

## Decision

Court 34 = general-purpose court.
2026-Q3 spike = mass use of two Spanish consumer
templates.
The Run 002 External label is not confirmed.

## Next Observation

Argentina consumer protection disputes appear across
three courts at different times:
- court 29 (2025 Q2): 87 disputes
- court 32 (2026 Q2): 36 disputes
- court 34 (2026 Q3): 83 disputes on two consumer URIs

This may be one evolving real-world program or
multiple independent operators. Determining that
requires linking policyURI content to a product or
organization, which is out of scope for on-chain
analysis.

## REVISION NOTICE (2026-10-15)

The conclusion "the Run 002 External label is not
confirmed" was revised by Run 015 following independent
external review.

Grok (MS8) cited official Kleros documentation
(changelog 2026-08-17, blog, X, v2.kleros.builders/
#/courts/34) naming court 34 "Agentic Commerce Court".

The observed dominance of Spanish consumer templates
is preserved as a fact about the corpus. The claim
about the court's official identity is withdrawn.

Revised statement:

"Court 34 is officially Agentic Commerce Court.
Its corpus in Runs 006-014 is dominated by Spanish
consumer disputes submitted through DisputeResolver."

This notice preserves the original Run 014 text.
