MS2  
[EXTERNAL]  
Model: Grok 4.5  

**Independent Field-Selection Reconnaissance**  

This assessment applies the provisional filter defined in docs/FIELD-SELECTION-v0.1.md to the four listed candidates. All statements are grounded solely in publicly available material inspected for this task and the Envoy repository documents. No conclusions from other External nodes are used. Research Fit and Resource Fit are kept distinct. Scoring follows the document’s 0–2 scale where evidence permits; UNKNOWN is recorded without conversion to a positive or negative value.

### 1. UDRP

**PUBLIC TRACE**  
FACT: WIPO and other ICANN-accredited providers publish the large majority of UDRP decisions in full text. WIPO alone has administered over 80 000 UDRP-based cases since 1999; recent annual filings exceed 6 000. Searchable indexes, legal indices, and statistics are maintained on wipo.int.  
OBSERVATION: The public record is continuous, dated, and structured by case number, parties, domain, outcome, and panel reasoning.  
GATE: PASS. SCORE: 2.

**CORPUS BOUNDARY**  
FACT: Decisions can be filtered by year, provider, TLD, outcome, or legal issue via existing indexes. Subsets (e.g., single year, single provider, or specific legal questions) are routinely extracted for academic and practitioner analysis.  
OBSERVATION: Full historical volume exceeds 80 000 decisions, yet workable bounded subsets (recent years or thematic samples) are demonstrably feasible.  
GATE: PASS. SCORE: 2.

**SOURCE ACCESS**  
FACT: Primary decisions are freely downloadable from WIPO, Forum, and other provider sites. Secondary statistics and digests (e.g., GigaLaw quarterly reports) are also public.  
OBSERVATION: No paywall or registration barrier obstructs bulk access for research purposes.  
GATE: PASS. SCORE: 2.

**EXISTING SYNTHESIS**  
FACT: WIPO Overview 3.1 systematically summarises panel consensus on more than 100 recurring questions, citing over 1 400 representative decisions. Multiple independent empirical studies and practitioner digests exist.  
OBSERVATION: Core doctrinal structure is already highly synthesised.  
GATE: PASS (but high synthesis reduces novelty). SCORE: 1 (for residual open questions).

**UNRESOLVED STRUCTURAL QUESTION**  
OBSERVATION: Despite extensive synthesis, empirical questions remain about panel consistency across providers, the practical effect of reverse-domain-name-hijacking findings, the distribution of outcomes in multi-domain cases, and the interaction of UDRP with national court challenges.  
HYPOTHESIS: Systematic quantitative analysis of outcome patterns by complainant type, TLD, or panel composition could still surface non-obvious structural regularities.  
UNKNOWN: Whether any of these residual questions is sufficiently unresolved to justify a dedicated Envoy cycle.  
GATE: PASS (provisional). SCORE: 1.

**ABILITY TO TEST**  
Technical: High (public corpus, downloadable texts, existing scrapers and structured datasets already demonstrated).  
Methodological: Moderate (legal reasoning is accessible without specialised advocacy credentials; verification against published decisions does not require court access).  
GATE: PASS. SCORE: 2 (technical) / 1–2 (methodological).

**PRACTICAL VALUE (Resource Fit)**  
OBSERVATION: Brand-protection services, domain-monitoring tools, and legal-support niches already operate around UDRP.  
HYPOTHESIS: A refined empirical map of outcome patterns or predictive signals could support specialised advisory or tooling niches.  
UNKNOWN: Whether any such niche remains underserved relative to existing commercial offerings.  
SCORE: 1.

**Supported**  
Large, continuously updated public decision corpus; high technical accessibility; clear doctrinal baseline.

**Unknown**  
Precise residual research novelty after WIPO Overview 3.1; magnitude of any remaining practical niche.

**Main structural research opportunity**  
Quantitative mapping of outcome variation and reverse-hijacking patterns across the full public record.

**Main practical/resource opportunity**  
Specialised empirical intelligence for brand owners or domain investors.

**Main obstacle or uncertainty**  
High existing synthesis may leave limited open structural questions of sufficient depth.

### 2. Specific types of domain disputes

**PUBLIC TRACE**  
FACT: Subtypes (typosquatting, combosquatting, brand-jacking, personal-name squatting, gripe sites) appear inside UDRP decisions and in secondary literature. No separate dedicated public corpus exists solely for any single subtype.  
OBSERVATION: Identification of a subtype requires classification of existing UDRP (or court) records.  
GATE: Conditional PASS (dependent on UDRP corpus). SCORE: 1.

**CORPUS BOUNDARY**  
OBSERVATION: A bounded subset can be created by filtering UDRP decisions for linguistic or structural markers of a chosen subtype.  
UNKNOWN: The precise size and purity of any such filtered corpus without manual or model-assisted classification effort.  
GATE: PASS (with effort). SCORE: 1.

**SOURCE ACCESS**  
FACT: Same primary sources as UDRP.  
GATE: PASS. SCORE: 2.

**EXISTING SYNTHESIS**  
OBSERVATION: Practitioner and academic literature discusses subtypes, yet no authoritative, regularly updated overview equivalent to the WIPO Overview exists for any single subtype.  
GATE: PASS. SCORE: 1–2.

**UNRESOLVED STRUCTURAL QUESTION**  
HYPOTHESIS: Differences in panel treatment, success rates, or evidentiary thresholds across subtypes may remain incompletely mapped.  
UNKNOWN: Whether systematic differences are large enough to constitute a distinct structural question.  
GATE: PASS (provisional). SCORE: 1.

**ABILITY TO TEST**  
Technical: Feasible via classification of the UDRP corpus.  
Methodological: Requires reliable operational definitions of each subtype; classification error is a potential confound.  
GATE: PASS with caveat. SCORE: 1.

**PRACTICAL VALUE**  
OBSERVATION: Detection and defensive registration services already target these subtypes commercially.  
UNKNOWN: Whether a deeper structural analysis would open a distinct resource niche.  
SCORE: 1.

**Supported**  
Subtypes are publicly attested inside the UDRP record.

**Unknown**  
Size, purity, and discriminatory power of any subtype-specific corpus; depth of residual structural questions.

**Main structural research opportunity**  
Comparative outcome analysis across carefully defined subtypes.

**Main practical/resource opportunity**  
Improved detection heuristics or specialised advisory products.

**Main obstacle or uncertainty**  
Definitional boundary work and classification cost; risk that the field collapses into the broader UDRP analysis.

### 3. New TLD domain disputes

**PUBLIC TRACE**  
FACT: New-gTLD registrations are publicly countable (tens of millions across >1 000 strings). UDRP decisions involving new gTLDs form a visible subset of the overall UDRP corpus. ICANN and registry reports supply volume statistics.  
OBSERVATION: Dispute density relative to registration volume varies by TLD and is only partially documented.  
GATE: PASS. SCORE: 1–2.

**CORPUS BOUNDARY**  
FACT: New-gTLD cases can be filtered from the WIPO and other provider indexes by TLD string.  
OBSERVATION: Absolute numbers are smaller than legacy-gTLD cases, improving manageability.  
GATE: PASS. SCORE: 2.

**SOURCE ACCESS**  
FACT: Same public decision repositories as UDRP; zone-file and registry reports are also public.  
GATE: PASS. SCORE: 2.

**EXISTING SYNTHESIS**  
OBSERVATION: Aggregate statistics exist; detailed comparative jurisprudence focused solely on new gTLDs is thinner than the general UDRP Overview.  
GATE: PASS. SCORE: 1–2.

**UNRESOLVED STRUCTURAL QUESTION**  
HYPOTHESIS: Whether panel application of the three UDRP elements differs systematically for new-gTLD strings, or whether certain new gTLDs generate atypical dispute patterns, remains incompletely tested.  
UNKNOWN: Magnitude of any such difference.  
GATE: PASS (provisional). SCORE: 1–2.

**ABILITY TO TEST**  
Technical: High (subset of existing public corpus).  
Methodological: Requires only standard UDRP literacy plus TLD classification.  
GATE: PASS. SCORE: 2.

**PRACTICAL VALUE**  
OBSERVATION: Brand-protection demand exists for new gTLDs; registry and registrar services already address registration and monitoring.  
UNKNOWN: Whether dispute-specific intelligence constitutes a distinct underserved niche.  
SCORE: 1.

**Supported**  
Public decision subset and registration-volume data.

**Unknown**  
Precise scale of differential treatment or atypical patterns; commercial saturation of related services.

**Main structural research opportunity**  
Comparative analysis of UDRP outcomes and evidentiary patterns in new-gTLD versus legacy-gTLD cases.

**Main practical/resource opportunity**  
Targeted monitoring or advisory services for high-dispute new gTLDs.

**Main obstacle or uncertainty**  
Smaller absolute case volume may limit statistical power; risk of overlap with general UDRP work.

### 4. Kleros / crypto arbitration

**PUBLIC TRACE**  
FACT: Kleros Court (V1 and V2) publishes case interfaces, selected case studies, and on-chain dispute data. Subgraphs and explorer tools expose dispute metadata, juror stakes, and outcomes. A limited number of “famous cases” and research papers exist.  
OBSERVATION: The public record is thinner, more fragmented, and more recent than the UDRP corpus; many disputes are low-value or specialised (token curation, prediction-market resolution, consumer claims).  
GATE: PASS (qualified). SCORE: 1.

**CORPUS BOUNDARY**  
FACT: On-chain and subgraph data allow filtering by court, period, or dispute type. Absolute numbers remain far smaller than UDRP.  
OBSERVATION: A manageable corpus is obtainable, yet completeness depends on which chains and versions are included.  
GATE: PASS. SCORE: 1–2.

**SOURCE ACCESS**  
FACT: Court UI, subgraphs, and documentation are public. Full evidence packets and juror reasoning are not uniformly archived in a single searchable textual corpus comparable to WIPO decisions.  
OBSERVATION: Technical access is high for metadata; narrative depth varies.  
GATE: PASS with limitation. SCORE: 1.

**EXISTING SYNTHESIS**  
OBSERVATION: Protocol documentation, a small number of academic case studies, and blog retrospectives exist. No equivalent to the WIPO Overview of panel consensus has been identified.  
GATE: PASS. SCORE: 2 (low synthesis leaves more open ground).

**UNRESOLVED STRUCTURAL QUESTION**  
HYPOTHESIS: Questions concerning juror coherence, appeal dynamics, incentive alignment, evidence quality thresholds, and cross-court consistency remain largely open.  
OBSERVATION: The field is younger and less doctrinally stabilised than UDRP.  
GATE: PASS. SCORE: 2.

**ABILITY TO TEST**  
Technical: High for on-chain metadata; moderate for full evidence reconstruction.  
Methodological: Requires familiarity with blockchain interfaces and, for deeper analysis, understanding of crypto-economic incentives; specialist legal or economic expertise may become a confound for certain questions.  
GATE: PASS with caveat. SCORE: 1–2.

**PRACTICAL VALUE**  
OBSERVATION: Decentralised dispute resolution is an active development area; tooling, insurance, and integration niches are discussed in the ecosystem.  
UNKNOWN: Whether a quiet empirical reconnaissance can identify a concrete, currently underserved practical niche.  
SCORE: 1–2.

**Supported**  
Public on-chain and interface data; younger field with thinner doctrinal synthesis.

**Unknown**  
Completeness and narrative depth of the evidence corpus; exact scale of residual structural openness; practical saturation of related services.

**Main structural research opportunity**  
Empirical mapping of juror behaviour, outcome coherence, and incentive effects across specialised courts.

**Main practical/resource opportunity**  
Intelligence or tooling layers for participants in decentralised arbitration.

**Main obstacle or uncertainty**  
Smaller and more fragmented public narrative record; potential methodological barrier of domain-specific technical literacy.

### Comparative Assessment

| Criterion                  | UDRP | Specific types | New TLD | Kleros |
|----------------------------|------|----------------|---------|--------|
| Public Trace               | 2    | 1              | 1–2     | 1      |
| Corpus Boundary            | 2    | 1              | 2       | 1–2    |
| Source Access              | 2    | 2              | 2       | 1      |
| Existing Synthesis         | 1    | 1–2            | 1–2     | 2      |
| Unresolved Structural Q.   | 1    | 1              | 1–2     | 2      |
| Ability to Test (tech/meth)| 2/1–2| 1              | 2       | 1–2    |
| Practical Value            | 1    | 1              | 1       | 1–2    |

UDRP offers the strongest public trace, largest and most accessible corpus, and highest technical testability, but the lowest residual structural novelty because of extensive existing synthesis.  
Specific types inherit the UDRP corpus yet introduce definitional and classification overhead; they risk collapsing into a sub-analysis of UDRP.  
New TLD disputes form a cleanly filterable subset with moderate residual questions and high accessibility.  
Kleros presents the highest residual structural openness and the lowest existing synthesis, but a thinner and more fragmented narrative corpus together with potential methodological confounds.

No candidate fails an early gate outright. Discrimination is visible primarily on the axes of corpus depth versus residual structural openness.

### Candidate(s) to Investigate First

First priority: UDRP (or its cleanly bounded new-TLD subset).  
Reason: Highest technical accessibility and public-trace reliability permit an immediate, low-cost test of the Envoy method itself (observation → mapping → bounded hypothesis) before committing resources to fields with greater access or literacy barriers. The large, structured corpus maximises the chance of producing distinguishable, verifiable observations in the first cycle.

Second priority (parallel or immediate follow-on): Kleros.  
Reason: Greatest residual structural openness and lowest existing synthesis offer higher research novelty once the method has been stress-tested on a high-trace field.

Specific types and pure new-TLD analysis are treated as refinements of the UDRP investigation rather than independent first fields.

This ordering is an independent External recommendation only; it is not a project decision.

### Evidence Required Before Committing to a Field

- A concrete, bounded sample corpus (size, source URLs, extraction method) for the chosen candidate.  
- Explicit residual structural question(s) that survive confrontation with existing synthesis (WIPO Overview for UDRP-family fields; protocol documentation and published case studies for Kleros).  
- Demonstration that at least one hypothesis can be tested against primary public material without specialist credentials that the operator does not possess.  
- Preliminary estimate of time/cost to process a minimum viable sample.  
- Confirmation that Research Fit and Resource Fit can be kept observationally separate in the first cycle.

Absence of any of the above keeps the candidate in the reconnaissance rather than deployment state.

### Next Concrete Reconnaissance Action

Acquire and record a minimal, time-stamped sample of primary public material for the highest-priority candidate (UDRP decisions from a recent bounded window, or an equivalent Kleros subgraph export).  
Document the exact source URLs, extraction method, and any immediate observations about structure, completeness, and accessibility.  
This step tests technical source access and produces the first verifiable field trace without presupposing a final field selection.

Uncertainty remains explicit on residual novelty, practical saturation, and methodological confounds for every candidate. The filter itself is still provisional and is being tested by this exercise.
