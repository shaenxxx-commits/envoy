# Field Run 028 — Kleros Field Closure

FIELD: KLEROS
STAGE: FIELD CLOSURE
STATUS: CLOSED (field closed, monitoring scheduled)
RESULT: weak for resources; revisit in 3-6 months

## Decision (Architect, 2026-11-14)

Kleros V2 through DisputeResolver is closed as an
active resource-seeking field. It is retained as a
monitored field with a scheduled revisit.

Per DDA §9: stopping is a valid result. The field
was investigated, the method produced distinguishable
observations, hypotheses were tested, and practical
points of application were identified as insufficient.

## Summary of what was established (Runs 005-027)

### Corpus

- 342 disputes (2024-11-14 .. 2026-11-14).
- 7 courts, court 34 top (parent 33 -> 1).
- Single arbitrable: DisputeResolver.
- All resolved (period=4, ruled=true).

### Operators

- 11 EOA senders total.
- Two large: 0xe66f7f8a (143) and 0xd0d5fad9 (131).
- One medium new: 0x6687c671 (21, all unique).
- Minor: six senders 1-4 disputes each.
- Identity of 0xe66f7f8a: UNKNOWN.

### Templates

- 95 on Lemon policy (PDF verified).
- 74 on generic consumer policy v2.1.0 (PDF verified).
- 173 on unique one-off templates (retail tail).

### Temporal

- Monthly average ~14. Median ~7.
- Bursts: 2025-05 (28), 2026-08/09 (46 + 96).
- Post-peak decline: Oct 40, Nov 13 (9 days).
- Recent months dominated by 0xe66f7f8a alone.

### External context (verified)

- Lemon integration: 12 June 2024 (blog).
- Kleros changelog: 2026-08-17 Agentic Commerce.
- GitHub PR #2189: Argentina consumer protection DK.
- Mendoza pilot: Acordada n°31.624.
- Resolución 893/2025: regulatory basis.
- Lemon user base: 5.5M (Aug 2026).

## Why the field is weak for resources

1. **Absolute volume.** ~0.5 disputes/day. Juror
   fee ~$0.60. Total economic footprint is negligible.

2. **Concentration.** 80% of recent activity from
   one or two operators. No market.

3. **Declining trend.** September peak passed.
   October-November show decline.

4. **Geography.** Argentina consumer protection.
   Regulated niche, entrance requires legal status
   or partnership.

5. **Infrastructure.** Kleros Enterprise is small,
   works with specific partners, not an open
   platform for third parties.

## Why the field stays monitored

1. **Model precedent.** Mendoza is the first case
   of blockchain arbitration integrated into a
   state judicial system. If it works, it may
   replicate elsewhere.

2. **Lemon growth.** 2.5M -> 5.5M users in two
   years. If dispute volume follows user growth,
   the field may grow faster than current trend.

3. **Regulatory tailwind.** Resolución 893/2025
   makes Kleros rulings binding when the consumer
   accepts. This is a legal foundation that could
   enable wider adoption.

4. **Unknown operator 0xe66f7f8a.** If identified
   and shown to be an independent actor (not Lemon),
   the field has a second real client.

## Revisit criteria

Scheduled check: **2027-02 (3 months)**, then
**2027-05 (6 months)** if no trigger fires.

### Trigger conditions (check earlier)

- Total disputes > 500.
- New operator with > 50 disputes appears.
- Public announcement of new Kleros Enterprise
  partner.
- Regulatory change in Argentina.
- Any external signal that Kleros Enterprise
  scales beyond Lemon.

### Metrics to collect at revisit

- Total disputes (delta vs 342).
- Unique senders (delta vs 11).
- Dominant operator share (is 0xe66f7f8a still
  dominant?).
- Any new burst periods.
- Any new templates.
- Any new public announcements from Kleros or
  Lemon.

## Decision

- Kleros field CLOSED as active resource search.
- Kleros field OPENED as monitored field.
- Next phase: new field selection.

## Next Observation

Run 029+: field selection for a new candidate
field. Existing candidates from Run 001:
- UDRP
- Specific types of domain disputes
- New TLD domain disputes

These were passed over in favor of Kleros in
Run 001. Re-evaluate them with the benefit of
hindsight.

## Provenance

All prior runs preserved in field/.
Kleros context in docs/KLEROS-CONTEXT-v0.1.md.
Figures in docs/KLEROS-FIGURES-v0.1.md.
