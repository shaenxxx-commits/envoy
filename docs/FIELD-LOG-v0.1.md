# FIELD LOG v0.1

## Purpose

Field Log is the persistent operational record of Envoy field work.

Its purpose is to preserve the research trajectory independently of chat memory.

## Run Structure

Every completed field run MUST produce:

1. A run record.
2. Preserved raw External outputs.
3. A separate Lead synthesis.
4. Explicit decision, if any.
5. Explicit next observation.
6. Git commit.
7. Git push to `origin/main`.

The next field run MUST NOT begin while the previous completed run remains undocumented or unpushed.

## Provenance

The following layers MUST remain distinguishable:

RAW EXTERNAL OUTPUT
→ RUN RECORD
→ LEAD SYNTHESIS
→ DECISION
→ NEXT OBSERVATION

Raw External outputs MUST NOT be silently edited.

Errors, contamination, contradictions and deviations are preserved and classified in the Lead synthesis.

## Evidence States

- FACT — directly established.
- OBSERVATION — directly observed but not necessarily independently established.
- HYPOTHESIS — proposed explanation or research proposition.
- UNKNOWN — unresolved.

No automatic transition is allowed:

Observation → Fact
Hypothesis → Fact
Unknown → Assumption

## External Independence

External nodes remain independent during their individual runs unless the Lead explicitly initiates an interaction phase.

External outputs must not be treated as a single blended source.

## Run Naming

Field runs use sequential identifiers:

001, 002, 003, ...

A run may contain multiple External responses.

External message numbering is preserved independently from Envoy run numbering.

## Git Rule

After every completed run:

1. Preserve raw outputs.
2. Complete the run record.
3. Complete Lead synthesis.
4. Record decision and next observation.
5. Commit.
6. Push to `origin/main`.
7. Verify local HEAD, remote HEAD and clean working tree.

Git is the persistent external memory of Envoy.
