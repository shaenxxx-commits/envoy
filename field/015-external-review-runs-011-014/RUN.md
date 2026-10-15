# Field Run 015 — External Review of Runs 011-014

FIELD: KLEROS
STAGE: EXTERNAL REVIEW
STATUS: CLOSED
RESULT: three reviews; court 34 identity requires revision

## Objective

Submit the factual results of Runs 011-014 to the three
independent External nodes for review. Identify
methodological gaps before proceeding to interpretation
or resource analysis.

## Method

Same review request sent independently to Kimi, Grok,
Namazu. No interaction between nodes before all three
replied.

Request contained:
- factual summary of Runs 011-014;
- four questions: correctness, court-34 identification,
  missing material, next step.

## Reviews received

- Kimi K2 Thinking — MS9
- Namazu — MS8
- Grok 4.5 — MS8

## Consensus

All three recommend option (c): close methodological
debts before interpretation or resource analysis.

All three agree:
- Descriptive results of Runs 011-014 are broadly
  correct as an on-chain corpus.
- The single-arbitrable finding is correct within the
  traversed range.
- Classification is reproducible.
- Methodology has gaps that should be closed.

## Divergence

Kimi and Namazu: court 34 is not the Agentic Commerce
Court; the label is a user category.

Grok: the official Kleros documentation (changelog
2026-08-17, blog, X, v2.kleros.builders/#/courts/34)
explicitly names court 34 the Agentic Commerce Court.
The observed consumer content does not refute this.
A court can be named one thing and accept heterogeneous
disputes.

Grok's argument is verifiable against an external
source. Kimi and Namazu did not check external
documentation.

## Convergent methodological gaps

All three raise:

- Parent court and dispute hierarchy for court 34.
- DisputeKit ID used in court 34.
- PolicyRegistry / official court policy.
- Complete log-scan confirmation (no gap, no range
  truncation).
- Arbitrable completeness below block 164M.
- Resolved vs ongoing status of disputes.
- Who actually creates disputes through
  DisputeResolver (platform identities).
- Fees / token used per dispute.

## Decision

The internal classification of court 34 as
"general-purpose" is revised to a weaker form:

"Court 34 is officially named Agentic Commerce Court
(per public Kleros documentation) and accepts
heterogeneous disputes through DisputeResolver;
in the observed corpus, Spanish consumer templates
dominate."

This preserves both the official name and the observed
content. It does not adopt either "Agentic-specific"
or "general-purpose" as an exclusive label.

## Next Observation

Methodological debt closure before interpretation:

1. Verify official court 34 name from Kleros docs
   (external source check).
2. Query courts(34) for parent, disputeKit, and
   related parameters.
3. Full log-scan completeness check below block 164M.
4. Check whether any court > 34 exists and whether
   it is Agentic-specific.

## Provenance

Review request text and three responses preserved
in RAW-EXTERNALS.md.
