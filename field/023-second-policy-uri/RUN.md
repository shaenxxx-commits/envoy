# Field Run 023 — Second Policy URI

FIELD: KLEROS
STAGE: SOURCE VERIFICATION
STATUS: CLOSED
RESULT: second policy is a general consumer dispute
        template, not Lemon-specific

## Objective

Fetch and inspect the second dominant policyURI
(QmUbgqKuUvfsnWLP6o8GhZu8jcCaD31GUSZSSexe11fZco)
in court 34. Determine whether it is also a Lemon
document or a different operator's policy.

## Method

HTTP GET via cdn.kleros.link. PDF metadata extract.
Text extract via pdftotext -layout.

## Result

Type: application/pdf, 7 pages, 916 374 bytes.

PDF Title: "Política General de Disputas de Consumo
v2.1.0"

Body content: general Argentine consumer dispute
policy, listing seven Argentine consumer protection
principles, with explicit references to:
- Ley Argentina de Defensa del Consumidor
- Marco Regulatorio de Medicina Prepaga
- Ley de Tarjetas de Crédito

Version marker inside the document: v2.1.0.

Key difference from policyURI #1: this document is
not Lemon-specific. It is a generic Argentine
consumer dispute policy applicable to any consumer
claim submitted through Kleros V2.

## Comparison

| URI                                   | Title                                            | Operator-specific |
|---------------------------------------|--------------------------------------------------|-------------------|
| QmbEs5Ae8Sh5W...                      | Política de Interpretación de Disputas Lemon    | YES (Lemon)       |
| QmUbgqKuUvfsnW...                     | Política General de Disputas de Consumo v2.1.0  | NO (generic)      |

## Observations

- The two dominant templates are not variants of
  one document. One is Lemon's own policy; the
  other is a general consumer policy with a version
  history (v2.1.0 implies earlier revisions).
- The general policy existed before Lemon? Or was
  created for the program? Not answered here.
- The general policy references Argentine law
  directly, including sector-specific regulations
  (prepaid medicine, credit cards). This suggests it
  is maintained by someone familiar with Argentine
  consumer law.

## Decision

The second policyURI is not Lemon-specific.
The corpus contains at least two distinct policy
templates:
- one operator-branded (Lemon);
- one generic Argentine consumer protection policy.

This rules out a simple "one operator, one template"
model. Either multiple operators share a general
policy, or the same operator uses both.

## Next Observation

1. Determine who maintains the generic policy
   (v2.1.0). Possibly Kleros Enterprise,
   a legal association, or a consortium.
2. Check other disputes in courts 29/32 for this
   policyURI to see whether Lemon also uses it.
3. Update KLEROS-CONTEXT to v0.2.

## Provenance

Second policy PDF preserved at
field/023-second-policy-uri/general-consumer-policy.pdf.
