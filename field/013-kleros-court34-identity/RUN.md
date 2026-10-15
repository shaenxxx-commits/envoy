# Field Run 013 — Court 34 Identity

FIELD: KLEROS
STAGE: COURT IDENTITY
STATUS: CLOSED
RESULT: court 34 is a general-purpose court

## Objective

Identify court 34, which drives 129 of 146 disputes in
2026-Q3 (Run 012). Run 002 External nodes had called
it "Agentic Commerce Court". Verify against MetaEvidence.

## Method

Sampled 10 of 135 court-34 disputes (evenly spaced).
For each: retrieve the DisputeTemplateRegistry event
from the creating transaction and decode the
MetaEvidence JSON.

## Result

| id  | category                  | title                                 |
|-----|---------------------------|---------------------------------------|
| 151 | Image Generation          | AI-Generated Painting                 |
| 166 | Agentic Commerce          | Spanish consumer claim                |
| 181 | Oracle                    | South Korea president prediction      |
| 196 | Services                  | Spanish consumer claim                |
| 211 | Services                  | Spanish consumer claim                |
| 228 | Services                  | Spanish consumer claim                |
| 243 | Services                  | Barnes v. Felix (legal case)          |
| 258 | Services                  | Spanish consumer compensation         |
| 275 | Services                  | Spanish consumer compensation         |
| 295 | prediction_market.mentions| Trump rally mention prediction        |

Court 34 carries heterogeneous dispute types.
No single product or category dominates.

## Observations

- "Services" appears in 6 of 10 samples, mostly
  Spanish-language consumer disputes.
- "Agentic Commerce" appears once.
- Other categories: Image Generation, Oracle,
  prediction_market.mentions.
- The category field is user-supplied. It describes
  the dispute, not the court.

## Discrepancy with Run 002

Run 002 External responses (Kimi, Grok) reported
court 34 as "Agentic Commerce Court" and connected it
to AI-agent dispute resolution demos in August 2026.
That identification is not supported by the sampled
MetaEvidence.

Possible explanations (none verified):
- Court 34 was originally used for an Agentic Commerce
  demo but continued in general use.
- The External nodes confused the court ID with a
  category used in some disputes.
- Court IDs were reassigned at some point.

## Decision

Court 34 is a general-purpose court accessed through
DisputeResolver. The "Agentic Commerce Court" label
is not confirmed for court 34 in this corpus.

## Next Observation

The overall picture of court 34 in 2026-Q3 is:
many heterogeneous disputes created in one quarter
through one public tool. This is likely a test or
early-use period. Confirming that would require
either MetaEvidence patterns (e.g. shared policyURI
or template) or external documentation.

## Provenance

Sampled from local corpus, RPC-verified.
No interpretation of why the spike occurred.

## REVISION NOTICE (2026-10-15)

The conclusion "court 34 is general-purpose, not
Agentic-specific" was revised by Run 015 following
independent external review.

Grok (MS8) pointed to official Kleros documentation
that names court 34 "Agentic Commerce Court".
A court can be officially named one thing and accept
heterogeneous disputes. The observed consumer content
does not refute the official name.

Revised statement:

"Court 34 is officially named Agentic Commerce Court
(per public Kleros docs). In the observed corpus,
Spanish consumer templates dominate its disputes."

This notice preserves the original Run 013 text and
records the correction, per no-silent-rewriting rule.
