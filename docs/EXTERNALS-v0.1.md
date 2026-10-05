# ENVOY — EXTERNALS v0.1

## 1. Purpose

External nodes are independent analytical nodes used by Envoy for field reconnaissance and controlled cross-analysis.

They are instruments of the Envoy method.

They do not own the project, define its field, or replace the Lead.

## 2. Initial External configuration

Envoy uses exactly three External nodes in the initial configuration:

1. Kimi
2. Grok
3. Sakana

All three must be started in clean sessions.

No existing conversation context is part of the initial Envoy External configuration.

## 3. Clean session

A clean External session means:

- a new conversation;
- no prior Envoy conversation history;
- no prior instructions from the Envoy project;
- no imported conclusions from other External nodes;
- no access to other External responses before the independent phase.

The same initial input should be used for all three nodes unless the experiment explicitly specifies otherwise.

## 4. Separation from previous projects

Previous conversations with Qwen, Grok, Sakana, or other models may exist in other projects.

They are not Envoy External sessions.

Historical material may be consulted later if explicitly designated as a source, but it must not be silently mixed with a clean External response.

Envoy provenance must remain separate:

Previous project material
!=
Envoy External observation
!=
Lead interpretation
!=
Envoy result

## 5. External role

An External node is asked to:

- inspect the supplied material;
- identify relevant structures;
- state uncertainties;
- identify alternative explanations;
- flag methodological problems;
- identify potentially useful observations;
- respond to other External nodes only when the protocol explicitly enters an interaction phase.

An External is not asked to:

- decide what Envoy ultimately does;
- invent field facts;
- claim access to unavailable information;
- present hypotheses as established facts;
- imitate another External;
- conceal uncertainty.

## 6. Independent phase

The first response of each External must be independent.

External A must not see B or C.

External B must not see A or C.

External C must not see A or B.

The purpose is to preserve independent observations before interaction.

## 7. Interaction phase

Only after the independent responses are preserved may selected External outputs be introduced into another External session.

The interaction order must be recorded.

Any structural change appearing after interaction must be distinguishable from what was already present in the independent phase.

## 8. Required identification

Every External response begins with:

[EXTERNAL]
Model: <model name>

Only the model identity is required.

Context, role descriptions, project history, or claims about the architecture must not be added to this header.

## 9. Provenance

Every External response must remain attributable to:

- model;
- session;
- input;
- interaction stage;
- timestamp where available.

The Lead must not rewrite an External observation into a form that obscures its origin.

If the Lead summarizes several External responses, the summary is a new Lead-level artifact and must not be presented as an External statement.

## 10. Unknown and uncertainty

External nodes must be allowed to state:

UNKNOWN
UNCERTAIN
INSUFFICIENT EVIDENCE
CANNOT VERIFY

These states are valid outputs.

Absence of a statement is not evidence of absence.

## 11. Initial External set is fixed

The initial Envoy configuration contains three External nodes.

Additional models are not added to the first field reconnaissance unless the configuration is explicitly revised and the revision is recorded.

This constraint exists to keep the first cross-run interpretable.

## 12. Initial task

The first External task is field reconnaissance.

The External nodes will independently assess the candidate fields using the current Envoy field-selection framework.

Initial candidates:

1. UDRP
2. Specific types of domain disputes
3. New TLD domain disputes
4. Kleros / crypto arbitration

The first phase is not intended to select a final field automatically.

Its purpose is to produce independent observations that can be compared by the Lead.

## 13. Method rule

Do not optimize the External protocol before testing it.

Run the initial independent phase.

Preserve all responses.

Then evaluate:

- agreement;
- divergence;
- missing information;
- unsupported assumptions;
- methodological confounds;
- discriminatory value of the field-selection filter.

Only after this comparison may the protocol be revised.

## 14. Initial status

STATUS: PROVISIONAL

External configuration: FIXED AT THREE

Models:
Kimi
Grok
Sakana

Session type:
CLEAN

Initial phase:
INDEPENDENT

First task:
FIELD RECONNAISSANCE
