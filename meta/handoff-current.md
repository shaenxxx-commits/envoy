# HANDOFF CURRENT — ENVOY

**Дата:** 2026-10-13
**Статус:** актуальный
**Основание:** handoff-protocol LAB (адаптируется)

Снимок текущего состояния Envoy. Передаётся новому
ведущему при смене чата.

## CURRENT STATE

    HEAD: 3b18cf7 (main = origin/main)
    ACTIVE PHASE: field-observation
    STATUS: open
    LAST COMPLETED: Run 005 (Kleros on-chain verification, GREEN)
    WORKING HYPOTHESES:
      - On-chain sensor V2 рабочий из nova (Run 005, GREEN).
      - Барьер Run 004 был свойством среды внешних,
        не поля (Run 005 подтвердил).
    KNOWN UNKNOWNs:
      - Полный размер популяции V2 disputes.
      - Все ли V2 disputes от одного arbitrable.
      - Репрезентативность выборки 290-295.
      - Расхождение MS-нумерации Grok: baseline MS5
        в чате vs grok-MS4.md в репо. Причина UNKNOWN.
      - Phase 4 (filter assessment) не оформлена.
      - docs/ROLES-v0.1.md — STATUS: PROVISIONAL.
    PENDING DECISION:
      - Расширение выборки V2 disputes (>= 10).
      - Phase 4 — оценка фильтра по 001.
      - docs/ROLES — обновление статуса.
    LAST RESPONSE NUMBER: MS90 (обновлять по каждому ответу)

## Repository

- Envoy: 3b18cf7 (main = origin/main)
- LAB (external source, метод координации):
  3abc90b (main-working)

## Run history

- 001 — Kleros field selection — CLOSED — только RUN.md
- 002 — Kleros reconnaissance — CLOSED — только RUN.md
- 003 — Baseline sensor — CLOSED — RUN + SYNTHESIS + RAW + 3 External
- 004 — On-chain sensor — CLOSED — RUN + SYNTHESIS + RAW + 3 External
- 005 — On-chain verification (local nova) — CLOSED — RUN + SYNTHESIS + COMMANDS — GREEN

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
- Расширение выборки V2 disputes (>= 10) не сделано.
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
