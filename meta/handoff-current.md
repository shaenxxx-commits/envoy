# HANDOFF CURRENT — ENVOY

**Дата:** 2026-10-14
**Статус:** актуальный
**Основание:** handoff-protocol LAB (адаптируется)

Снимок текущего состояния Envoy. Передаётся новому
ведущему при смене чата.

## CURRENT STATE

    HEAD: 297b5f8 (main = origin/main)
    ACTIVE PHASE: methodological-debt-closure
    STATUS: open
    LAST COMPLETED: Run 017 (Phase 4 filter assessment, filter retained)
    WORKING HYPOTHESES:
      - On-chain sensor V2 рабочий из nova (Runs 005-016).
      - 300 disputes через DisputeResolver (выросло с 296
        за сессию — поле активно).
      - Court 34: parent 33 → 1, верхний court (35-45 нет).
      - Все 300 disputes resolved (period=4, ruled=true).
      - Ruling distribution: 138 accept, 137 reject,
        18 refuse, 7 non-standard (multi-option kit).
      - Court 34 официально Agentic Commerce Court,
        но принимает heterogenous disputes через
        DisputeResolver.
      - Внешние (все 3) рекомендовали закрыть
        методологические долги — закрываем.
    KNOWN UNKNOWNs:
      - PolicyRegistry URI court 34.
      - disputeKitId per dispute.
      - Полнота корпуса ниже 164M (genesis V2).
      - Кто инициаторы (за DisputeResolver).
      - Fees / token per dispute.
      - Расхождение MS-нумерации Grok: baseline MS5
        в чате vs grok-MS4.md в репо. Причина UNKNOWN.
      - Phase 4 (filter assessment) не оформлена.
      - docs/ROLES-v0.1.md — STATUS: PROVISIONAL.
    PENDING DECISION:
      - docs/ROLES — снятие или сохранение статуса PROVISIONAL.
      - Интерпретация / ресурсный контур.
    LAST RESPONSE NUMBER: MS178 (обновлять по каждому ответу)

## Repository

- Envoy: 297b5f8 (main = origin/main)
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
- 012 — Court x time — CLOSED — RUN + SYNTHESIS — three product waves, court 34 spike
- 013 — Court 34 identity — CLOSED — RUN + SYNTHESIS + SAMPLES — general-purpose court
- 014 — Court 34 MetaEvidence — CLOSED — RUN + SYNTHESIS — 46 policyURIs, 2 dominant consumer templates (revision notice)
- 015 — External review — CLOSED — RUN + SYNTHESIS + REQUEST + RAW (3 responses) — court 34 label revised
- 016 — Court 34 structure — CLOSED — RUN + SYNTHESIS — parent 33, top court, all 300 resolved
- 017 — Filter assessment — CLOSED — RUN + SYNTHESIS — filter retained, A1-A3 candidates

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

- docs/ROLES-v0.1.md — статус PROVISIONAL не снят.
- PolicyRegistry URI court 34 не получен.
- Интерпретация / ресурсный контур не начаты.
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
