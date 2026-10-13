# HANDOFF CURRENT — ENVOY

**Дата:** 2026-10-13
**Статус:** актуальный
**Основание:** handoff-protocol LAB (адаптируется)

Снимок текущего состояния Envoy. Передаётся новому
ведущему при смене чата.

## CURRENT STATE

    HEAD: 692dcbb (main = origin/main)
    ACTIVE PHASE: field-observation
    STATUS: open
    LAST COMPLETED: Run 014 (Court 34 full MetaEvidence, 46 policyURIs, 2 dominant)
    WORKING HYPOTHESES:
      - On-chain sensor V2 рабочий из nova (Runs 005-014).
      - 296 disputes через DisputeResolver.
      - Три волны: 2025 Q2 court 29; 2026 Q2 court 32;
        2026 Q3 court 34 (129 из 146).
      - Court 34 = general-purpose court.
      - Всплеск 2026-Q3 = 2 испаноязычных consumer-шаблона
        (83 из 135, 61%).
      - «Agentic Commerce» = пользовательский тег (24/135),
        не свойство суда.
      - External claim Run 002 (court 34 = Agentic Commerce)
        опровергнут MetaEvidence.
    KNOWN UNKNOWNs:
      - Связаны ли три consumer-волны (29, 32, 34)
        в одну реальную программу.
      - Стоит ли за двумя доминирующими policyURI
        один продукт или несколько пользователей.
      - Текущий статус поля (активно / приостановлено).
      - Расхождение MS-нумерации Grok: baseline MS5
        в чате vs grok-MS4.md в репо. Причина UNKNOWN.
      - Phase 4 (filter assessment) не оформлена.
      - docs/ROLES-v0.1.md — STATUS: PROVISIONAL.
    PENDING DECISION:
      - Направление интерпретации:
        (1) Argentina consumer thread как кейс;
        (2) Agentic thread;
        (3) выход к Phase 4.
      - Phase 4 — оценка фильтра по 001.
      - docs/ROLES — обновление статуса.
    LAST RESPONSE NUMBER: MS151 (обновлять по каждому ответу)

## Repository

- Envoy: 692dcbb (main = origin/main)
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
- 014 — Court 34 MetaEvidence — CLOSED — RUN + SYNTHESIS — 46 policyURIs, 2 dominant consumer templates

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
- Направление интерпретации не выбрано.
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
