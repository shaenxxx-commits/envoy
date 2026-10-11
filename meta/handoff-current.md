# HANDOFF CURRENT — ENVOY

**Дата:** 2026-10-11
**Статус:** актуальный
**Основание:** handoff-protocol LAB (адаптируется)

Снимок текущего состояния Envoy. Передаётся новому
ведущему при смене чата.

## CURRENT STATE

    HEAD: a3d4348 (main = origin/main) — после этого
      коммита записываются meta/handoff-protocol.md
      и meta/changelog.md; их SHA — в следующем handoff.
    ACTIVE PHASE: documentation-coordination
    STATUS: open
    LAST COMPLETED: Run 004 (Kleros on-chain sensor, YELLOW)
    WORKING HYPOTHESES:
      - On-chain путь архитектурно правдоподобен,
        эмпирически не подтверждён (Run 004).
      - Sensor status YELLOW: документировано, не извлечено.
    KNOWN UNKNOWNs:
      - topic0 не проверен (единственный источник — Namazu).
      - Работает ли публичный RPC из nova — не проверено.
      - Расхождение MS-нумерации Grok: в persistent-чате
        baseline = MS5, в репо grok-MS4.md. Причина UNKNOWN.
      - Phase 4 (filter assessment) не оформлена.
      - docs/ROLES-v0.1.md — STATUS: PROVISIONAL,
        не обновлён после выбора поля.
    PENDING DECISION:
      - On-chain шаг (Next Observation из 004).
      - Phase 4 — оценка фильтра по 001.
      - docs/ROLES — обновление статуса.
    LAST RESPONSE NUMBER: MS61 (обновлять по каждому ответу)

## Repository

- Envoy: a3d4348 (main = origin/main)
  (+ handoff-protocol.md, changelog.md — в след. коммите)
- LAB (external source, метод координации):
  3abc90b (main-working)

## Run history

- 001 — Kleros field selection — CLOSED — только RUN.md
- 002 — Kleros reconnaissance — CLOSED — только RUN.md
- 003 — Baseline sensor — CLOSED — RUN + SYNTHESIS + RAW + 3 External
- 004 — On-chain sensor — CLOSED — RUN + SYNTHESIS + RAW + 3 External

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
- On-chain шаг (Next Observation 004) не выполнен.
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
