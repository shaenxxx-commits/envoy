# Lead Synthesis — Verification of External Claims

## FACT — Run-Level

- Six External-cited priority 1-2 sources verified
  via HTTP. All returned HTTP 200.
- Five of six verified by content (title / metadata
  matched the claim).
- One (Mendoza IPFS PDF) verified by existence;
  content not extracted in this run.
- One additional fetch outside the External citation
  list: the dominant court-34 policyURI was retrieved
  via cdn.kleros.link and decoded as a PDF.
- PDF Title: "Política de Interpretación de Disputas
  Lemon".
- PDF body: seven Argentine consumer protection
  principles including "in dubio pro consumidor".

## OBSERVATION

- No hallucinated URLs. The External nodes cited
  real, checkable sources and their descriptions
  matched.
- The Lemon integration is now a primary-source
  fact, not an External claim.
- The dominant court-34 template is a Lemon policy
  document. This was not part of any External
  citation; it came from our own corpus.

## UNKNOWN

- Second dominant policyURI
  (QmUbgqKuUvfsnWLP6o8GhZu8jcCaD31GUSZSSexe11fZco)
  content not fetched.
- The Mendoza paper's full text not extracted.
- Whether the five operators in the corpus all
  belong to Lemon or include others using the same
  Lemon template.
- Whether the court-34 operator (0xe66f7f8a) is a
  Lemon-affiliated EOA or an independent one
  reusing Lemon's template.

## LEAD INTERPRETATION

Run 022 substantially closes the External-claims
question. The Run 021 external reviewers did not
hallucinate and their statements are now verified
where possible.

The H2 hypothesis ("field = Kleros Enterprise +
Argentina consumer") is now at FACT-level for the
Lemon integration, and STRONGLY SUPPORTED for the
corpus-level identification of the dominant
template as Lemon.

Two important consequences:

1. The corpus is not anonymous Kleros V2 usage.
   It is at minimum a Lemon Enterprise integration
   with a specific legal policy document in Spanish.

2. The presence of a second dominant policyURI plus
   five distinct operators suggests either a broader
   Argentina consumer protection program or multiple
   operators sharing the same templates. This requires
   one more step (fetch second policyURI) before the
   picture is fully clarified.

## Decision

- KLEROS-CONTEXT to be updated: Layer 2 items that
  verified are promoted to Layer 1; new IPFS result
  added to Layer 1.
- The remaining Layer 2 claims (Federico Ast on
  Milei, Sociedades Automatizadas) remain
  unverified.
- Run 023 will fetch the second policyURI and
  resolve the multi-operator question.

## Next Observation

Run 023:
1. Fetch second dominant policyURI PDF.
2. Check whether it is also a Lemon document or
   another operator's.
3. Update KLEROS-CONTEXT to v0.2.

## Provenance

Lemon PDF preserved at
field/022-verify-external-claims/lemon-policy.pdf.
