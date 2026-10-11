# HANDOFF CURRENT — ENVOY

**Дата:** 2026-10-09
**Статус:** актуальный
**Основание:** handoff-protocol LAB (адаптируется)

Снимок текущего состояния Envoy. Передаётся новому
ведущему при смене чата.

## CURRENT STATE

    HEAD: 4ac6959 (main = origin/main)
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
      - Namazu vs Sakana в EXTERNALS-v0.1 — рассинхрон.
      - Run 001/002 — raw внешних не сохранён.
      - Phase 4 (filter assessment) не оформлена.
    PENDING DECISION:
      - Ревизия EXTERNALS-v0.1 → v0.2
        (Namazu = Sakana, MS<N> — общее правило).
      - 001/002 — восстановить raw или пометить UNKNOWN.
      - Ревизия docs: ввести meta-слой, coordination-правила.
    LAST RESPONSE NUMBER: MS25

## Repository

- Envoy: 4ac6959 (main = origin/main)
- LAB (external source, метод координации):
  3abc90b (main-working)

## Run history

- 001 — Kleros field selection — CLOSED — только RUN.md
- 002 — Kleros reconnaissance — CLOSED — только RUN.md
- 003 — Baseline sensor — CLOSED — RUN + SYNTHESIS + RAW + 3 External
- 004 — On-chain sensor — CLOSED — RUN + SYNTHESIS + RAW + 3 External

## Documentation

- docs/: DDA-v0.1, FIELD-LOG-v0.1, FIELD-SELECTION-v0.1,
  ROLES-v0.1, ROADMAP-v0.1, EXTERNALS-v0.1,
  EXTERNAL-BOOTSTRAP-v0.1, EXTERNAL-BOOTSTRAP-v0.2
- meta/: создаётся (этот файл — первый)

## Роли

- Architect: shaen (Оператор)
- Lead: текущий ведущий
- External: Kimi K2 Thinking, Grok 4.5, Namazu (= Sakana AI)

## Что не сделано

- Handoff-protocol для Envoy не оформлен.
- Operator-preferences для Envoy не оформлен.
- Coordination-правила (MS<N>, пометки утверждений)
  не в docs.
- Формат raw-архива 001/002 не закрыт.

## Где смотреть

- docs/DDA-v0.1.md — метод
- docs/FIELD-LOG-v0.1.md — правила ведения Run
- docs/ROLES-v0.1.md — роли
- docs/EXTERNALS-v0.1.md — конфигурация внешних
- field/ — прогоны
- LAB (/home/shaen/nova-cortex-lab) — источник метода координации
