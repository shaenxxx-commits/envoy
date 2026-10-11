# ENVOY — EXTERNALS v0.2

Версия: v0.2. Дата: 2026-10-09.
Rev: 2026-10-11 — уточнения по замечаниям внешних (§4.1, §8.1).
Заменяет: EXTERNALS-v0.1.md.
Status: PROVISIONAL.

## 0. Что изменилось относительно v0.1

- Состав внешних явно зафиксирован по фактическому
  состоянию: Kimi K2 Thinking, Grok 4.5, Namazu.
  Namazu = Sakana AI. В v0.1 третий узел назывался
  Sakana; фактически в чатах работает Namazu.
  Оба имени относятся к одной модели (Sakana AI).
- Правило MS<number> вынесено как общее для всех
  чатов Envoy (ведущего и внешних), а не только
  внешних. См. meta/operator-preferences.md.
- Добавлена ссылка на meta/operator-preferences.md
  и meta/handoff-current.md.

Не изменилось:

- Роль внешнего (§5).
- Независимость (§6).
- Interaction phase (§7).
- Evidence discipline (§10).
- No invented access (§12).
- Bootstrap acknowledgement (§16).

## 1. Purpose

External nodes are independent analytical nodes used
by Envoy for field reconnaissance and controlled
cross-analysis.

They are instruments of the Envoy method.
They do not own the project, define its field,
or replace the Lead.

## 2. Initial External configuration

Envoy uses exactly three External nodes:

1. Kimi K2 Thinking
2. Grok 4.5
3. Namazu (Sakana AI)

All three operate in persistent working chats with
clean Envoy initialization.

## 3. Clean Envoy initialization

A clean Envoy initialization means:

- the chat is not required to be newly created
  for each task;
- no prior Envoy project context is assumed
  at initialization;
- no prior Envoy instructions are assumed
  at initialization;
- no imported conclusions from other External nodes
  are assumed at initialization;
- no other External responses are available before
  the independent phase;
- after initialization, the chat may accumulate
  Envoy context.

The same initial bootstrap input should be used
for all three nodes unless explicitly specified.

## 4. Separation from previous projects

Previous conversations with the same models in other
projects are not Envoy External sessions.
Historical material may be consulted later if
explicitly designated as a source, but must not be
silently mixed with a clean External response.

Envoy provenance remains separate:

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
- respond to other External nodes only when the
  protocol explicitly enters an interaction phase.

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

## 7. Interaction phase

Only after independent responses are preserved may
selected External outputs be introduced into another
External session.

The interaction order must be recorded.

## 8. Required identification

### 8.1 Message numbering

MS<number> is the numbering rule for every
persistent working chat in Envoy (External nodes
and the Lead). See meta/operator-preferences.md.

Numbering is local, not global:

- Each chat maintains its own counter.
- Counters are not synchronized across chats.
- The same number (e.g. MS7) may exist in
  multiple chats simultaneously.

Every External response, including the bootstrap
acknowledgement, begins with MS<number> on the
first separate line.

The first response in a persistent External chat
is MS1. Each subsequent response increments by one.

Numbers must not be skipped, reused, or reset
during normal persistent work.

Every External response begins with:

MS<number>
[EXTERNAL]
Model: <model name>

Only the model identity is required.

Aggregation rule: whenever the Lead aggregates
responses from multiple nodes, node prefix is
mandatory (e.g. GROK-MS5, KIMI-MS6, NAMAZU-MS5).
Bare MS<number> refers to the local chat only.

### 8.2 Lead numbering

The Lead uses the same MS<number> rule in its own
working chat. See meta/operator-preferences.md.

## 9. Provenance

Every External response must remain attributable to:

- model;
- session;
- input;
- interaction stage;
- timestamp where available.

The Lead must not rewrite an External observation
into a form that obscures its origin.

If the Lead summarizes several External responses,
the summary is a new Lead-level artifact and must
not be presented as an External statement.

## 10. Unknown and uncertainty

External nodes must be allowed to state:

UNKNOWN
UNCERTAIN
INSUFFICIENT EVIDENCE
CANNOT VERIFY

These states are valid outputs.

Absence of a statement is not evidence of absence.

## 11. Initial External set is fixed

The initial Envoy configuration contains three
External nodes. Additional models are not added
unless the configuration is explicitly revised
and the revision is recorded.

## 12. No invented access

External nodes must not claim:

- access to private systems they cannot access;
- access to repository contents they have not
  actually received or inspected;
- knowledge of unpublished field events;
- actions performed by Envoy they did not observe;
- results of experiments not supplied to them.

## 13. Bootstrap acknowledgement

After receiving the bootstrap, the External node
must establish its operational state.

Initialization response must contain:

MS1
[EXTERNAL]
Model: <actual model name>

BOOTSTRAP: RECEIVED
ROLE: EXTERNAL
CONTEXT MODE: PERSISTENT

Then briefly identify:

- which rules are operational;
- what remains unknown;
- whether any part of the bootstrap is ambiguous.

Do not begin field reconnaissance until a separate
task is supplied.

## 14. Current External set and status

- Kimi K2 Thinking — MS current: 6 (Run 004)
- Grok 4.5 — MS current: 5 (Run 004)
- Namazu (Sakana AI) — MS current: 6 (Run 004)

Recorded as of the last completed run.
Live MS must be confirmed with the node.

## 15. Method rule

Do not optimize the External protocol before testing it.

Run the initial independent phase. Preserve all
responses. Then evaluate.

## 16. Version status

VERSION: v0.2
STATUS: PROVISIONAL
SUPERSEDES: EXTERNALS-v0.1

## 4.1 Persistent chat as historical carrier

External persistent chats preserve Envoy context
across runs. This is a property of the configuration,
not an accident.

Consequence:

- Responses from earlier runs remain recoverable
  through the same External chat.
- A recovered response is archived as
  archived-external, not as raw-moment.

Binary provenance boundary:

- raw-external — verbatim, captured at the run
  moment. Highest layer.
- archived-external — verbatim, re-supplied by the
  node from its persistent chat at a stated date.
  Requires: node, chat, MS<number>, date of
  re-supply.
- reconstructed-by-lead — Lead paraphrase, summary
  or memory. Never used for facts. Never carries
  archived-external or raw-external marks.
- UNKNOWN — the node no longer holds a verbatim
  response (e.g. only a conversation summary).

Mixed layers are forbidden. A response is either
verbatim from the node (raw or archived) or it is
not External output at all.
