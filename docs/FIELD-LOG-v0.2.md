# FIELD LOG v0.2

Версия: v0.2. Дата: 2026-10-11.
Заменяет: FIELD-LOG-v0.1.md.
Status: PROVISIONAL.

## 0. Что изменилось относительно v0.1

- Введён слой провенанса `archived-external` —
  между raw-moment и Lead reconstruction.
- В Run Structure добавлено правило восстановления
  утраченного сырья: archived-external допустим,
  reconstruction недопустим, UNKNOWN — валиден.
- Ссылка на meta/operator-preferences.md
  (сквозная нумерация MS<N>).
- Ссылка на EXTERNALS-v0.2.md.

Не изменилось:

- Run Structure (1–7).
- Evidence States (FACT / OBSERVATION / HYPOTHESIS / UNKNOWN).
- External Independence.
- Run Naming.
- Git Rule.

## 1. Purpose

Field Log is the persistent operational record of Envoy
field work.

Its purpose is to preserve the research trajectory
independently of chat memory.

## 2. Run Structure

Every completed field run MUST produce:

1. A run record.
2. Preserved raw External outputs (or an explicit
   UNKNOWN / archived-external marker).
3. A separate Lead synthesis.
4. Explicit decision, if any.
5. Explicit next observation.
6. Git commit.
7. Git push to origin/main.

The next field run MUST NOT begin while the previous
completed run remains undocumented or unpushed.

## 3. Provenance

The following layers MUST remain distinguishable:

- raw-external — captured at the run moment.
- archived-external — re-supplied by the External node
  from its persistent chat at a stated date.
- RUN RECORD
- LEAD SYNTHESIS
- DECISION
- NEXT OBSERVATION

Raw External outputs MUST NOT be silently edited.

Errors, contamination, contradictions and deviations
are preserved and classified in the Lead synthesis.

## 3.1 Recovering lost raw output

If a run's raw output was not captured at the run moment:

- the External node may be asked to re-supply its
  earlier response from its persistent chat;
- the re-supplied response is archived as
  archived-external, not as raw-moment;
- the archive records: node, chat, MS<number>,
  date of re-supply;
- if the node no longer holds the verbatim response
  (e.g. only a conversation summary), the run
  records UNKNOWN;
- the Lead does not reconstruct the missing output
  from memory or from summary.

Lead reconstruction is never used as a substitute
for raw or archived output.

## 4. Evidence States

- FACT — directly established.
- OBSERVATION — directly observed but not necessarily
  independently established.
- HYPOTHESIS — proposed explanation or research
  proposition.
- UNKNOWN — unresolved.

No automatic transition is allowed:

Observation -> Fact
Hypothesis -> Fact
Unknown -> Assumption

## 5. External Independence

External nodes remain independent during their
individual runs unless the Lead explicitly initiates
an interaction phase.

External outputs must not be treated as a single
blended source.

## 6. Run Naming

Field runs use sequential identifiers:

001, 002, 003, ...

A run may contain multiple External responses.

External message numbering (MS<number>) is local to
each persistent chat. When aggregated by the Lead,
node prefix is required (e.g. GROK-MS5, KIMI-MS6).
See meta/operator-preferences.md and
docs/EXTERNALS-v0.2.md §8.

## 7. Git Rule

After every completed run:

1. Preserve raw outputs.
2. Complete the run record.
3. Complete Lead synthesis.
4. Record decision and next observation.
5. Commit.
6. Push to origin/main.
7. Verify local HEAD, remote HEAD and clean
   working tree.

Git is the persistent external memory of Envoy.

## 8. Version status

VERSION: v0.2
STATUS: PROVISIONAL
SUPERSEDES: FIELD-LOG-v0.1
