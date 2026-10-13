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
