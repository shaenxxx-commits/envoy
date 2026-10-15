# CHANGELOG — ENVOY

История версий документов Envoy и meta-слоя.
Один документ = один раздел. Каждая запись фиксирует:
версию, дату, что изменилось, что не изменилось,
основание.

Формат: version — date — change — basis.

## docs/DDA-v0.1.md

- v0.1 — 2026-10-06 — создан — базовый метод.

## docs/ROLES-v0.1.md

- v0.1 — 2026-10-06 — создан — разделение ролей.
  STATUS: PROVISIONAL (не обновлён после выбора поля).

## docs/ROADMAP-v0.1.md

- v0.1 — 2026-10-06 — создан — рабочий roadmap.
  STATUS: PROVISIONAL.

## docs/FIELD-SELECTION-v0.1.md

- v0.1 — 2026-10-06 — создан — фильтр выбора поля.
  STATUS: PROVISIONAL.

## docs/EXTERNALS-v0.1.md

- v0.1 — 2026-10-06 — создан — конфигурация внешних.

## docs/EXTERNALS-v0.2.md

- v0.2 — 2026-10-09 — состав внешних зафиксирован
  по факту (Kimi K2 Thinking, Grok 4.5, Namazu = Sakana AI);
  MS<number> вынесен как общее правило; добавлен §4.1
  Persistent chat as historical carrier.
  Заменяет v0.1.
- v0.2 rev — 2026-10-11 — уточнения по замечаниям
  внешних (Kimi MS7, Namazu MS7, Grok MS6):
  бинарная граница archived-external;
  numbering локальный, не глобальный;
  aggregation rule с префиксом узла.
  Основание: внешняя ревизия работы ведущего.

## docs/EXTERNAL-BOOTSTRAP-v0.1.md

- v0.1 — 2026-10-06 — создан — bootstrap для внешних.

## docs/EXTERNAL-BOOTSTRAP-v0.2.md

- v0.2 — 2026-10-06 — рабочий язык (русский),
  обязательная MS-нумерация, требование читать
  репозиторий перед bootstrap-ack.
  Заменяет v0.1.

## docs/FIELD-LOG-v0.1.md

- v0.1 — 2026-10-06 — создан — правила ведения Run.

## docs/FIELD-LOG-v0.2.md

- v0.2 — 2026-10-11 — введён слой провенанса
  archived-external (§3, §3.1); Run Structure
  допускает archived-external вместо утраченного
  raw; правило восстановления сырья: archived-external
  допустим, reconstruction недопустим, UNKNOWN — валиден;
  MS<number> local, префикс узла при агрегации.
  Заменяет v0.1.
  Основание: восстановление сырья 001/002 через
  persistent-чаты внешних.

## meta/handoff-current.md

- v0.1 — 2026-10-09 — создан — снимок состояния
  Envoy. Первый meta-документ.

## meta/operator-preferences.md

- v0.1 — 2026-10-09 — создан — правила работы
  с Оператором (адаптировано из LAB).

## meta/handoff-protocol.md

- v0.1 — 2026-10-11 — создан — протокол передачи
  роли ведущего (адаптировано из LAB v0.3).
  STATUS: PROVISIONAL.
  Основание: срыв ведущего без протокола;
  восстановление состояния по чату вместо
  первичного источника.

## field/001-kleros-field-selection/

- 2026-10-06 — RUN.md создан.
- 2026-10-11 — добавлены RAW-EXTERNALS.md,
  grok-MS2.md, kimi-MS2.md (archived-external).
  Namazu — UNKNOWN.
  Основание: закрытие долга по FIELD-LOG
  Run Structure.

## field/002-kleros-field-reconnaissance/

- 2026-10-06 — RUN.md создан.
- 2026-10-11 — добавлены RAW-EXTERNALS.md,
  grok-MS4.md, kimi-MS4.md (archived-external).
  Namazu — UNKNOWN.
  Основание: закрытие долга по FIELD-LOG
  Run Structure.

## field/003-kleros-baseline-sensor/

- 2026-10-06 — Run 003 закрыт.
  RUN.md, SYNTHESIS.md, RAW-EXTERNALS.md,
  kimi-MS5.md, namazu-MS5.md, grok-MS4.md.
  SENSOR STATUS: YELLOW.
  Замечание: в persistent-чате Grok тот же ответ
  именуется MS5, в репо — MS4. Расхождение
  зафиксировано как UNKNOWN, ретро-переименование
  не применялось.

## field/004-kleros-onchain-sensor/

- 2026-10-09 — Run 004 закрыт.
  RUN.md, SYNTHESIS.md, RAW-EXTERNALS.md,
  grok-MS5.md, namazu-MS6.md, kimi-MS6.md.
  SENSOR STATUS: YELLOW.

## field/005-kleros-onchain-verification/

- 2026-10-13 — Run 005 закрыт.
  RUN.md, SYNTHESIS.md, COMMANDS.md.
  SENSOR STATUS: GREEN.
  Первое успешное on-chain извлечение V2 disputes
  с локальной машины nova (6 событий DisputeCreation,
  IDs 290-295).
  Зафиксировано расхождение: Namazu (Run 004, MS6)
  сообщил topic0 0x62e78dda..., канонический
  локально вычисленный — 0x141dfc18....
  Значение Namazu помечено как непроверенное
  и не используется.
  Основание: Next Observation из Run 004.

## field/006-kleros-corpus-expansion/

- 2026-10-13 — Run 006 закрыт.
  RUN.md, SYNTHESIS.md, COMMANDS.md, DISPUTES.md.
  SENSOR STATUS: GREEN (extended corpus).
  Пагинированный eth_getLogs (10 чанков по 10M блоков).
  178 уникальных V2 disputes, IDs 118-295,
  блоки 431 728 818 .. 514 090 528.
  Все от одного arbitrable 0xb5526d...4323.
  Основание: Next Observation из Run 005
  (расширение выборки до >= 10).
  Открыто: существуют ли ids < 118; есть ли
  другие arbitrable помимо 0xb5526d...4323.

## field/007-kleros-arbitrable-probe/

- 2026-10-13 — Run 007 закрыт.
  RUN.md, SYNTHESIS.md, COMMANDS.md.
  Arbitrable probe: снят фильтр по arbitrable,
  перезапрошен topic0 DisputeCreation.
  Результат: те же 178 событий, тот же единственный
  arbitrable 0xb5526d...4323.
  Второй arbitrable в диапазоне 414M..514M не обнаружен.
  Основание: первый probe из Next Observation Run 006.
  Открыто: range probe ниже 414M (Run 008).

## field/008-kleros-range-probe/

- 2026-10-13 — Run 008 закрыт.
  RUN.md, SYNTHESIS.md, COMMANDS.md, DISPUTES.md.
  Range probe: обход вглубь от 414M до 164M.
  Результат: поле V2 картировано.
  Итого 296 disputes, IDs 0..295 без пропусков.
  Все от одного arbitrable 0xb5526d...4323.
  Ниже 214M (50M блоков) — 0 событий.
  Граница поля: между 214M и 254M.
  Основание: второй probe из Next Observation Run 006.
  Открыто: точный start block; блоки для IDs 0..117.

## field/009-kleros-full-corpus/

- 2026-10-13 — Run 009 закрыт.
  RUN.md, SYNTHESIS.md, COMMANDS.md, DISPUTES.md.
  Полное извлечение корпуса V2.
  296 disputes, IDs 0..295 без пропусков.
  Start block (id 0): 274 289 504.
  End block (id 295): 514 090 528.
  Один arbitrable 0xb5526d...4323.
  Основание: Next Observation Run 008.
  Открыто: descriptive summary корпуса.

## field/010-kleros-descriptive-summary/

- 2026-10-13 — Run 010 закрыт.
  RUN.md, SYNTHESIS.md, COMMANDS.md.
  Descriptive summary корпуса V2.
  Span: 2024-11-14 .. 2026-10-12 (~697 дней).
  Плотность: 0.42 disputes/день.
  Кластеров (блоков с >1 dispute): 11.
  48% всех disputes — в последних 20M блоков.
  Никакой интерпретации, только описание.
  Основание: Next Observation Run 009.
  Открыто: направление интерпретации (требует решения Architect).

## field/011-kleros-arbitrable-identity/

- 2026-10-13 — Run 011 закрыт.
  RUN.md, SYNTHESIS.md, COMMANDS.md, COURTS.md.
  Идентификация единственного arbitrable:
  0xb5526d...4323 = DisputeResolver (Kleros).
  ERC-792 Arbitrable, не токен, не прокси.
  Распределение по 7 courts (IDs 1, 3, 24, 29, 31, 32, 34).
  Court 34: 135 disputes, court 29: 87, court 32: 36.
  MetaEvidence — испаноязычный consumer шаблон.
  Основание: Next Observation Run 010.
  Открыто: categorized summary (court x time).

## field/012-kleros-court-time/

- 2026-10-13 — Run 012 закрыт.
  RUN.md, SYNTHESIS.md.
  Categorized summary: court x time для 296 disputes.
  Три волны продукта:
    2025 Q2-Q3 — court 29 (Consumo y Vecindad);
    2026 Q2    — court 32 (Defensores del Cliente);
    2026 Q3    — court 34 (129 disputes за квартал).
  Всплеск последних месяцев = court 34.
  Основание: Next Observation Run 011.
  Открыто: идентификация court 34 (Run 002 предполагал
  Agentic Commerce Court, не перепроверено).

## field/013-kleros-court34-identity/

- 2026-10-14 — Run 013 закрыт.
  RUN.md, SYNTHESIS.md, SAMPLES.md.
  Идентификация court 34.
  10 сэмплов MetaEvidence: heterogeneous disputes
  (Image Generation, Services, Oracle,
  prediction_market, Agentic Commerce x1).
  Court 34 = general-purpose court, не Agentic-specific.
  Расхождение с Run 002 (External claims): не подтверждено.
  Основание: Next Observation Run 012.
  Открыто: кто драйвит всплеск 2026-Q3 (общий шаблон?).

## field/014-kleros-court34-metaevidence/

- 2026-10-14 — Run 014 закрыт.
  RUN.md, SYNTHESIS.md.
  Полная классификация MetaEvidence 135 court-34 disputes.
  46 уникальных policyURI.
  Доминируют 2 испаноязычных consumer-шаблона: 83 из 135 (61%).
  Категория — пользовательский тег, не свойство суда.
  «Agentic Commerce»: 24 из 135 (18%), пересекается с consumer-шаблонами.
  Расхождение с Run 002 подтверждено: court 34 ≠ Agentic-specific.
  Основание: Next Observation Run 013.
  Открыто: направление интерпретации (требует решения Architect).

## field/015-external-review-runs-011-014/

- 2026-10-15 — Run 015 закрыт.
  RUN.md, SYNTHESIS.md, REQUEST.md, RAW-EXTERNALS.md,
  kimi-MS9.md, namazu-MS8.md, grok-MS8.md.
  Внешняя ревизия Runs 011-014.
  Консенсус всех трёх: сначала закрыть методологические
  долги (Phase 4, ROLES), потом интерпретация.
  Расхождение: Kimi и Namazu — court 34 не Agentic;
  Grok — court 34 официально Agentic Commerce Court
  (по Kleros docs), consumer-содержимое не опровергает.
  Вывод: пересмотр Run 013/014. Court 34 = официально
  Agentic Commerce Court + consumer-доминирующий корпус.
  Revision notices добавлены в Run 013 и 014 (не переписаны).
  Основание: принцип внешней независимой проверки.
  Открыто: Run 016 — структурные параметры court 34
  (parent, disputeKit, PolicyRegistry), проверка courts > 34,
  полнота корпуса ниже 164M.

## field/016-kleros-court34-structure/

- 2026-10-15 — Run 016 закрыт.
  RUN.md, SYNTHESIS.md.
  Структурные параметры court 34.
  Parent = 33, цепочка 34 → 33 → 1 (General Court).
  Courts 35-45 не существуют; court 34 — верхний.
  Все 300 disputes: period=4 (execution), ruled=true.
  Ruling: 138 accept, 137 reject, 18 refuse, 6 ruling=3, 1 ruling=4.
  Корпус вырос 296 → 300 за сессию.
  Основание: структурные пробелы из External review (Run 015).
  Открыто: PolicyRegistry URI court 34; disputeKitId per dispute.

## field/017-filter-assessment/

- 2026-10-15 — Run 017 закрыт.
  RUN.md, SYNTHESIS.md.
  Phase 4 — оценка фильтра выбора поля (FIELD-SELECTION v0.1).
  Первое применение на реальных Runs 001-016.
  Итог: фильтр сохранён.
  Кандидаты на ревизию (не внесены):
    A1 — observation cost / operator cost;
    A2 — Existing Synthesis per-dimension;
    A3 — обязательная проверка Resource Fit в field cycle.
  Основание: ROADMAP Phase 4, FIELD-SELECTION §8.
  Ревизия v0.2 отложена до второго применения.

## docs/ROLES-v0.2.md

- v0.2 — 2026-10-15 — статус PROVISIONAL снят
  (первый field cycle завершён, Runs 001-017).
  Добавлен §14 (наблюдения по фактическому
  исполнению ролей в первом цикле).
  Добавлена ссылка на meta/handoff-protocol.md (§13).
  Заменяет ROLES-v0.1.
  Основание: ROADMAP Phase 4 завершена (Run 017),
  роли прошли проверку.
  Открыто: interaction phase (§7) не использовалась;
  поведение ролей при field stop не проверено.

## field/018-kleros-consumer-wave-hypothesis/

- 2026-10-15 — Run 018 закрыт.
  RUN.md, SYNTHESIS.md, raw-policy-uris.json.
  Гипотеза H1 проверена: три волны (courts 29, 32, 34) —
  один consumer dispute program, мигрирующий между судами.
  H1 поддержана, H0 опровергнута.
  Пересечение policyURI:
    QmUbgqKuUvfsnW — все три суда;
    QmbEs5Ae8Sh5W — courts 29 и 34;
    Qmassb4gkqJ — courts 32 и 34.
  Основание: Next Observation из Run 017 (Research contour).
  Открыто: оператор программы; причина миграции.

## field/019-external-review-h1/

- 2026-10-15 — Run 019 закрыт.
  RUN.md, SYNTHESIS.md, REQUEST.md, RAW-EXTERNALS.md,
  kimi-MS10.md, namazu-MS9.md, grok-MS9.md.
  Внешняя ревизия Run 018 (H1).
  Все три внешних: H1 слишком сильная.
  Overlap policyURI доказывает reuse шаблонов,
  не единую программу.
  Альтернативы: template library, marketplace,
  fork, разные операторы с общим boilerplate.
  Решение: H1 понижена до слабой формы.
    Weak H1 (SUPPORTED): шаблоны переиспользуются.
    Strong H1 (NOT SUPPORTED): одна программа.
  Revision notice добавлена в Run 018 (не переписан).
  Следующий шаг: tx.from для courts 29/32/34.
  Основание: стандарт внешней независимой проверки.

## field/020-operator-extraction/

- 2026-10-15 — Run 020 закрыт.
  RUN.md, SYNTHESIS.md, raw-senders.json.
  tx.from для всех 262 disputes courts 29, 32, 34.
  Доминирующие операторы:
    courts 29 и 32 — 0xd0d5fad9... (86/87, 35/36);
    court 34     — 0xe66f7f8a... (106/139).
  Пересечение 29 ∩ 32 ∩ 34 = ПУСТО.
  Strong H1 опровергнута.
  Weak H1 (template reuse) подтверждена.
  Картина: минимум две независимые программы
  плюс минорные участники.
  Основание: рекомендация внешних (Run 019).
  Открыто: off-chain идентификация операторов
  либо переход к Resource Fit.

## docs/KLEROS-CONTEXT-v0.1.md

- v0.1 — 2026-10-15 — создан.
  Рабочий контекст о Kleros V2 на 2026-10-15.
  Смешанный слой с явным разделением уровней:
    Слой 1 — НАБЛЮДЕНО (FACT, on-chain, Envoy);
    Слой 2 — ОТ ВНЕШНИХ (External-level, не проверено);
    Слой 3 — ГИПОТЕЗЫ;
    Слой 4 — ЧТО ТРЕБУЕТ ПРОВЕРКИ (для Run 022);
    Слой 5 — UNKNOWN.
  Основание: накопление внешних claims (Run 021)
  + собственные on-chain наблюдения (Runs 005-020).
  Открыто: проверка приоритетных источников (Run 022).

## field/022-verify-external-claims/

- 2026-10-15 — Run 022 закрыт.
  RUN.md, SYNTHESIS.md, SOURCES.md, lemon-policy.pdf.
  Верификация внешних claims из Run 021.
  6 из 6 priority 1-2 URL подтверждены (HTTP 200).
  Дополнительно: доминирующий policyURI в court 34
  декодирован — PDF "Política de Interpretación de
  Disputas Lemon".
  Lemon integration переведена из External-level
  в FACT.
  H2 (field = Kleros Enterprise + Argentina consumer)
  поддержана.
  Основание: Run 021 (recommendation внешних).
  Открыто: второй policyURI; вопрос multiple operators.

## field/023-second-policy-uri/

- 2026-10-15 — Run 023 закрыт.
  RUN.md, SYNTHESIS.md, general-consumer-policy.pdf.
  Второй доминирующий policyURI court 34.
  Title: "Política General de Disputas de Consumo v2.1.0".
  Не Lemon-specific — общая аргентинская consumer policy.
  Ссылки: Ley de Defensa del Consumidor, prepaid medicine,
  credit card law.
  Вывод: поле шире одного Lemon — минимум два различных
  шаблона (Lemon-branded + generic).
  Основание: Run 022 (next observation).
  Открыто: автор general template; соотношение операторов.
