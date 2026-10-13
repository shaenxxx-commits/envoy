# Run 011 — Court Map

7 courts observed across the 296-dispute corpus.

Source: docs.kleros.io Court Hierarchy, cross-checked
against on-chain courts(uint256) calls.

| ID | Name                                 | Parent | feeForJuror | disputes |
|----|--------------------------------------|--------|-------------|----------|
| 1  | General Court                        | 1      | 0.005       | 6        |
| 3  | Non-Technical                        | 2      | 0.003       | 8        |
| 24 | Humanity Court                       | 1      | 0.0024      | 3        |
| 29 | Corte de Disputas de Consumo y Vecindad | 23  | 0.0054      | 87       |
| 31 | Automated Curation                   | 10     | 0.00017     | 21       |
| 32 | Corte de Defensores del Cliente      | 29     | 0.0054      | 36       |
| 34 | (see note)                           | —      | —           | 135      |

Note on court 34:
Court 34 is not listed in the current Kleros docs
court hierarchy table. Run 002 External reconnaissance
(Kimi, Grok) identified court 34 as "Agentic Commerce
Court". That identification is External-level and not
re-verified in this run.

Argentina consumer protection courts (29, 32) use
DisputeKitGated and require SBT eligibility tokens.
