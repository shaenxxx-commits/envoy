# HANDOFF CURRENT — ENVOY

**Дата:** 2026-10-14
**Статус:** актуальный
**Основание:** handoff-protocol LAB (адаптируется)

Снимок текущего состояния Envoy. Передаётся новому
ведущему при смене чата.

## CURRENT STATE

    HEAD: a776524 (main = origin/main)
    ACTIVE PHASE: context-consolidation
    STATUS: open
    LAST COMPLETED: docs/KLEROS-FIGURES-v0.1 (figures registry)
    WORKING HYPOTHESES:
      - On-chain sensor V2 рабочий из nova (Runs 005-020).
      - 300 disputes через DisputeResolver.
      - Court 34: parent 33 → 1, верхний court.
      - Weak H1 (SUPPORTED): policyURI шаблоны
        переиспользуются между courts 29, 32, 34.
      - Strong H1 (REFUTED, Run 020): нет EOA,
        работающего во всех трёх courts.
      - Минимум две независимые программы:
        0xd0d5fad9 (courts 29+32),
        0xe66f7f8a (court 34).
    KNOWN UNKNOWNs:
      - Автор general template v2.1.0.
      - Кто использует какой шаблон: все 5 EOA?
      - Off-chain идентичность 0xd0d5fad9 и 0xe66f7f8a.
      - Другие arbitrable-контракты на Arbitrum V2.
      - Agentic-активность где-либо вообще.
      - Связь с Milei/Sociedades Automatizadas.
      - PolicyRegistry URI court 34.
      - Расхождение MS-нумерации Grok: baseline MS5
        в чате vs grok-MS4.md в репо. Причина UNKNOWN.
      - Phase 4 (filter assessment) не оформлена.
      - docs/ROLES-v0.1.md — STATUS: PROVISIONAL.
    PENDING DECISION:
      - Обновить KLEROS-CONTEXT до v0.2 (Run 024).
      - Оператор-шаблон mapping (какой EOA какой шаблон).
      - Проверка других arbitrable (on-chain expansion).
    LAST RESPONSE NUMBER: MS236 (обновлять по каждому ответу)

## Repository

- Envoy: a776524 (main = origin/main)
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
- 018 — Consumer wave hypothesis — CLOSED — RUN + SYNTHESIS + raw — H1 supported (revision notice)
- 019 — External review of H1 — CLOSED — RUN + SYNTHESIS + REQUEST + RAW (3 responses) — H1 downgraded to weak
- 020 — Operator extraction — CLOSED — RUN + SYNTHESIS + raw — strong H1 refuted, two programs
- 021 — External review of direction — CLOSED — RUN + SYNTHESIS + REQUEST + RAW (3 responses)
- 022 — Verify external claims — CLOSED — RUN + SYNTHESIS + SOURCES + lemon-policy.pdf — 6/6 verified, Lemon confirmed
- 023 — Second policy URI — CLOSED — RUN + SYNTHESIS + general-consumer-policy.pdf — generic consumer policy, not Lemon

## Documentation

- docs/: DDA-v0.1, FIELD-SELECTION-v0.1,
  ROLES-v0.1 (superseded), ROLES-v0.2,
  ROADMAP-v0.1,
  EXTERNAL-BOOTSTRAP-v0.1, EXTERNAL-BOOTSTRAP-v0.2,
  EXTERNALS-v0.1 (superseded), EXTERNALS-v0.2,
  FIELD-LOG-v0.1 (superseded), FIELD-LOG-v0.2,
  KLEROS-CONTEXT-v0.1 (working context),
  KLEROS-FIGURES-v0.1 (figures registry)
- meta/: handoff-current.md, operator-preferences.md,
  handoff-protocol.md, changelog.md

## Роли

- Architect: shaen (Оператор)
- Lead: текущий ведущий
- External: Kimi K2 Thinking, Grok 4.5, Namazu (= Sakana AI)

## Что не сделано

- KLEROS-CONTEXT-v0.1 не обновлён до v0.2.
- Оператор-шаблон mapping не сделан.
- Resource Fit не начат.
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
