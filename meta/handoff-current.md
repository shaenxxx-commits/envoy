# HANDOFF CURRENT — ENVOY

**Дата:** 2026-10-13
**Статус:** актуальный
**Основание:** handoff-protocol LAB (адаптируется)

Снимок текущего состояния Envoy. Передаётся новому
ведущему при смене чата.

## CURRENT STATE

    HEAD: 8ed7ad0 (main = origin/main)
    ACTIVE PHASE: field-observation
    STATUS: open
    LAST COMPLETED: Run 011 (Arbitrable identity = DisputeResolver, 7 courts)
    WORKING HYPOTHESES:
      - On-chain sensor V2 рабочий из nova (Runs 005-011).
      - Полное поле V2: 296 disputes, IDs 0..295.
      - Единственный arbitrable 0xb5526d...4323 =
        DisputeResolver (generic Kleros tool, ERC-792).
      - 7 courts: 1, 3, 24, 29, 31, 32, 34.
      - Court 34: 135, court 29: 87, court 32: 36.
      - Барьер Run 004 был свойством среды внешних.
    KNOWN UNKNOWNs:
      - Какой court драйвит всплеск в последние
        2 месяца (не разбито по court x time).
      - Реален ли court 34 = Agentic Commerce Court
        (по External Run 002, не перепроверено).
      - Текущий статус поля (активно / приостановлено).
      - Расхождение MS-нумерации Grok: baseline MS5
        в чате vs grok-MS4.md в репо. Причина UNKNOWN.
      - Phase 4 (filter assessment) не оформлена.
      - docs/ROLES-v0.1.md — STATUS: PROVISIONAL.
    PENDING DECISION:
      - Categorized summary (court x time) — Run 012.
      - Phase 4 — оценка фильтра по 001.
      - docs/ROLES — обновление статуса.
    LAST RESPONSE NUMBER: MS135 (обновлять по каждому ответу)

## Repository

- Envoy: 8ed7ad0 (main = origin/main)
- LAB (external source, метод координации):
  3abc90b (main-working)

## Run history

- 001 — Kleros field selection — CLOSED — только RUN.md
- 002 — Kleros reconnaissance — CLOSED — только RUN.md
- 003 — Baseline sensor — CLOSED — RUN + SYNTHESIS + RAW + 3 External
- 004 — On-chain sensor — CLOSED — RUN + SYNTHESIS + RAW + 3 External
- 005 — On-chain verification (local nova) — CLOSED — RUN + SYNTHESIS + COMMANDS — GREEN
- 006 — Corpus expansion — CLOSED — RUN + SYNTHESIS + COMMANDS + DISPUTES — 178 disputes — GREEN
- 007 — Arbitrable probe — CLOSED — RUN + SYNTHESIS + COMMANDS — single arbitrable in range
- 008 — Range probe — CLOSED — RUN + SYNTHESIS + COMMANDS + DISPUTES — 296 disputes, IDs 0..295
- 009 — Full corpus — CLOSED — RUN + SYNTHESIS + COMMANDS + DISPUTES — ID->block map, start block 274 289 504
- 010 — Descriptive summary — CLOSED — RUN + SYNTHESIS + COMMANDS — span ~697 days, 0.42/day
- 011 — Arbitrable identity — CLOSED — RUN + SYNTHESIS + COMMANDS + COURTS — DisputeResolver, 7 courts

## Documentation

- docs/: DDA-v0.1, FIELD-SELECTION-v0.1,
  ROLES-v0.1, ROADMAP-v0.1,
  EXTERNAL-BOOTSTRAP-v0.1, EXTERNAL-BOOTSTRAP-v0.2,
  EXTERNALS-v0.1 (superseded), EXTERNALS-v0.2,
  FIELD-LOG-v0.1 (superseded), FIELD-LOG-v0.2
- meta/: handoff-current.md, operator-preferences.md,
  handoff-protocol.md, changelog.md

## Роли

- Architect: shaen (Оператор)
- Lead: текущий ведущий
- External: Kimi K2 Thinking, Grok 4.5, Namazu (= Sakana AI)

## Что не сделано

- Phase 4 (filter assessment) по 001 не оформлена.
- docs/ROLES-v0.1.md — статус PROVISIONAL не снят.
- Categorized summary (court x time) не сделан.
- field/003 — расхождение MS-нумерации Grok
  зафиксировано, но причина UNKNOWN.

## Где смотреть

- docs/DDA-v0.1.md — метод
- docs/FIELD-LOG-v0.2.md — правила ведения Run
- docs/ROLES-v0.1.md — роли
- docs/EXTERNALS-v0.2.md — конфигурация внешних
- meta/handoff-protocol.md — протокол передачи ведущего
- meta/operator-preferences.md — правила работы с Оператором
- meta/changelog.md — история версий
- field/ — прогоны
- LAB (/home/shaen/nova-cortex-lab) — источник метода координации
