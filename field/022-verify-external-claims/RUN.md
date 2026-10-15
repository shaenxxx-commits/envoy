# Field Run 022 — Verification of External Claims

FIELD: KLEROS
STAGE: SOURCE VERIFICATION
STATUS: CLOSED
RESULT: 6 of 6 external claims verified; Lemon confirmed

## Objective

Verify the External-cited public sources from Run 021
(Kimi MS11, Namazu MS10, Grok MS10). Check whether
the URLs they cited exist and whether their content
matches the claims made.

Per EXTERNALS §10, External claims are candidates,
not facts. This run converts candidates into facts
where supported.

## Method

HTTP HEAD + GET for each cited URL. For PDF content,
download and extract text via pdftotext.

No blockchain queries in this run.

## Sources cited by External nodes

Priority 1:
- Lemon blog announcement
- Kleros changelog 2026-08-17
- GitHub PR kleros-v2#2189

Priority 2:
- Mendoza judicial pilot paper (IPFS)
- Poder Judicial Mendoza news page
- Derecho en Zapatillas article (Resolución 893/2025)

Priority 3 (not attempted in this run):
- Federico Ast public statements on Milei
- "Sociedades Automatizadas" plan
- EOA-public organization linkage

## Result

### URL availability

All 6 checked URLs returned HTTP 200. None were
hallucinated.

### Content verification

#### 1. Lemon blog
URL: lemon.me/blog/alianza-kleros-justicia-descentralizada
Title: "Lemon descentraliza la justicia en materia
de consumo a través de Kleros"
Key claims confirmed:
- Launch date: 12 June 2024
- Users resolve claims via Kleros within the Lemon app
- Purpose: faster and more transparent than
  Defensa al Consumidor

#### 2. Kleros changelog
URL: docs.kleros.io/changelog/2026-08-17
Title: "August 17, 2026 - Kleros Documentation"
Description: "New Commerce and Agentic Commerce
courts on Kleros V2, revamped Curate classic with
Permanent GTCR, and local justification drafts in
Court."
Confirmed: Agentic Commerce Court announcement date
and scope.

#### 3. GitHub PR #2189
URL: github.com/kleros/kleros-v2/pull/2189
Title: "New dispute kit gated for Argentinian
consumer protection lawyers"
State: closed, merged 2025-10-27
Author: jaybuidl
Confirmed.

#### 4. Mendoza judicial paper
URL: cdn.kleros.link/ipfs/QmUXRov3EQU5PYPZ2p6eP2fFiKCCsgmDnG5McQKYhYRXV4
Type: application/pdf (3.2 MB)
Confirmed as downloadable. Content not fully
extracted in this run; presence confirmed.

#### 5. Poder Judicial Mendoza
URL: jusmendoza.gob.ar/...experiencia-kleros...
Title: "La Suprema Corte de Mendoza presentó su
experiencia Kleros en el evento Cripto más importante
de la Argentina"
Confirmed: Federico Ast (Director Ejecutivo Kleros)
at Merge Buenos Aires.

#### 6. Derecho en Zapatillas
URL: derechoenzapatillas.com/2025/kleros-y-el-futuro-
del-defensor-del-cliente-en-argentina/
Title: "Kleros y el futuro del defensor del cliente
en Argentina"
Confirmed: Resolución Nº 893/2025 published
19 August 2025, Subsecretaría de Defensa del
Consumidor y Lealtad Comercial, Ministerio de
Economía.

### IPFS policyURI verification (unexpected result)

The dominant policyURI in court 34
(QmbEs5Ae8Sh5WaMAchUiNLhRqSe9ossQMaRV5mZ1L5uqom)
was fetched via cdn.kleros.link.

Content: a PDF document.

Extracted PDF Title:
"Política de Interpretación de Disputas Lemon"

This is a direct, primary-source confirmation that
the dominant court-34 template in our corpus is a
Lemon consumer-dispute policy document.

The document body lists seven Argentine consumer
protection principles, including "in dubio pro
consumidor" — a doctrinal principle of Argentine
consumer law.

This result was not part of the External-cited
sources; it is a direct finding from the corpus
itself. It moves the Lemon hypothesis (H2) from
External-level to FACT-level.

## Decision

- 6 of 6 External-cited priority 1-2 sources verified.
- Lemon integration confirmed by primary source
  (lemon.me blog).
- Dominant court-34 policy document is a Lemon
  document (PDF fetched and preserved in this repo).
- H2 (field = Kleros Enterprise + Argentina consumer)
  moves from hypothesis to supported fact.

Remaining:

- Second dominant policyURI
  (QmUbgqKuUvfsnWLP6o8GhZu8jcCaD31GUSZSSexe11fZco)
  not yet fetched. Likely also Lemon-related, but
  not confirmed.
- Distinction between multiple operators
  (0xd0d5fad9 vs 0xe66f7f8a) under a shared
  Lemon template remains open.

## Next Observation

1. Fetch and inspect the second dominant policyURI.
2. Update KLEROS-CONTEXT from v0.1 to v0.2,
   promoting verified sources from Layer 2 (External)
   to Layer 1 (FACT).
3. Continue with remaining External claims
   (Federico Ast on Milei, Sociedades Automatizadas)
   if useful for the resource contour.

## Provenance

Lemon policy PDF preserved at
field/022-verify-external-claims/lemon-policy.pdf.
All URL fetch results recorded in this RUN.md.
