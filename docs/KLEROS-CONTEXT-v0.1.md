# Kleros V2 — рабочий контекст

**Версия:** v0.1 (черновик)
**Дата:** 2026-10-15
**Статус:** WORKING CONTEXT — смешанный слой
**Назначение:** собрать в одном месте всё, что мы знаем
о поле Kleros V2 на текущий момент, с явным разделением
уровней достоверности.

**Предупреждение:** документ намеренно содержит слои
разной достоверности. Каждый блок помечен. Смешивать
нельзя. При цитировании — указывать слой.

---

## Слой 1 — НАБЛЮДЕНО (FACT, on-chain, Envoy)

Уровень: подтверждено прямыми RPC-запросами с nova.

**Канал:**
- Единственный arbitrable:
  0xb5526d022962a1fff6ed32c93e8b714c901f4323
  = DisputeResolver (Kleros).
- Сеть: Arbitrum One (chain 42161).
- Период: 2024-11-14 -> 2026-10-15.

**Объём:**
- 300 disputes, IDs 0..299, без пропусков.
- Все resolved (period=execution, ruled=true).

**Структура:**
- 7 courts: 1 (General), 3 (Non-Technical),
  24 (Humanity), 29 (Consumo y Vecindad),
  31 (Automated Curation), 32 (Defensores del Cliente),
  34 (Agentic Commerce Court, официально).
- Court 34 — верхний (parent 33 -> 1).
- Courts 35+ не существуют.

**Активность по courts (волны):**

| Период    | Court | Disputes |
|-----------|-------|----------|
| 2025 Q2-Q3| 29    | 87       |
| 2026 Q2   | 32    | 36       |
| 2026 Q3   | 34    | 129+     |

**Операторы (tx.from, EOA):**

| Court | Доминирующий оператор                          | Доля      |
|-------|------------------------------------------------|-----------|
| 29    | 0xd0d5fad9380bcd518a2b387032583d700f570d0e    | 86/87 (99%) |
| 32    | 0xd0d5fad9380bcd518a2b387032583d700f570d0e    | 35/36 (97%) |
| 34    | 0xe66f7f8abef94c22e02fdc075fd5da5a0c5ba225    | 106/139 (76%) |
| --    | 0x9e51bbd7... (в 29 и 34)                      | минорный  |
| --    | 0xf1c7c037... (в 32 и 34)                      | минорный  |

**Пересечение 29 n 32 n 34 = пусто.**
Один оператор не работает во всех трёх.

**Шаблоны (MetaEvidence policyURI):**
- 46 уникальных в court 34.
- 2 доминирующих:
  - QmbEs5Ae8Sh5WaMAchUiNLhRqSe9ossQMaRV5mZ1L5uqom (46/135)
  - QmUbgqKuUvfsnWLP6o8GhZu8jcCaD31GUSZSSexe11fZco (37/135)
- Оба — испаноязычные consumer templates.
- Пересечение между courts 29/32/34 подтверждено (weak H1).

**Категория в MetaEvidence — user-supplied.** Не свойство суда.

**Рост:** 296 -> 300 disputes за несколько часов
работы. Поле активно.

---

## Слой 2 — ОТ ВНЕШНИХ (External-level, НЕ проверено Envoy)

Уровень: заявлено двумя и более внешними независимо,
но не подтверждено нами прямыми источниками.

**Оператор Lemon:**
- Lemon — аргентинский fintech / криптокошелёк,
  ~2.5M пользователей.
- Интегрировал Kleros в июне 2024 для consumer
  disputes до $100.
- Kleros называет это "Kleros Enterprise Consumer
  Dispute for Lemon" — первый V2 case.
- Источники, названные внешними:
  lemon.me/blog/alianza-kleros-justicia-descentralizada,
  Forbes Argentina, Cronista.

**Kleros Enterprise:**
- Отдельный продуктовый слой Kleros для корпоративных
  интеграций.
- Newsletter "Kleros Resuelve".

**Специализированный dispute kit:**
- GitHub PR (предположительно #2189, октябрь 2025):
  "New dispute kit gated for Argentinian consumer
  protection lawyers".
- Объясняет существование SBT-контрактов
  SBTACPLawyer, SBTACPExperience.

**Agentic Commerce Court:**
- Kleros changelog 2026-08-17: Commerce + Agentic
  Commerce courts live.
- Blog: "Agents, Jurors, and the Rules of Kleros'
  New Economy".

**Судебная система Аргентины:**
- Пилот в провинции Мендоса — соглашение Верховного
  суда Мендосы с Kleros, август-сентябрь 2024.
- Применяется в мировом суде департамента Лавалье.
- Использование — консультативное (не окончательное
  решение).
- Kleros Fellowship paper: "From Blockchain to Bench"
  (июнь 2025).
- Презентация на Merge Buenos Aires (март 2025).

**Регуляторный контекст:**
- Resolución 893/2025 — обновление фигуры
  Defensor del Cliente.
- Disposición 892/2025 — реформа SNAC
  (National Consumer Arbitration System).
- Решения Kleros могут иметь обязательную силу,
  если потребитель согласен.

**Политический контекст:**
- Правительство Хавьера Милея — дерегулирование,
  технологический реформизм.
- Реформа судебной системы (sistema acusatorio).
- План по легализации ИИ-агентов
  ("Sociedades Automatizadas").
- Federico Ast (CEO Kleros) публично поддерживает
  курс Милея.

**Независимое схождение:** Namazu и Grok дали эти
сведения независимо друг от друга, без координации.
Это повышает вероятность, но не делает FACT.

---

## Слой 3 — ГИПОТЕЗЫ (не проверено)

**H2: Поле Envoy — это не "Kleros V2", а
"Kleros Enterprise + Argentina consumer protection".**
- Согласуется со слоями 1 и 2.
- Требует проверки: содержат ли policyURI упоминания
  Lemon / Argentina.

**H3: Agentic Commerce Court — отдельный слой,
не связанный с нашим корпусом.**
- Court 34 официально Agentic, но заполнен consumer
  disputes.
- Возможно, Agentic-активность идёт по другому каналу,
  не через DisputeResolver.

**H4: Пилот в Мендосе и Lemon-интеграция — часть
одной государственной программы.**
- Согласуется с политическим контекстом.
- Требует проверки: связаны ли EOA-операторы
  с государственными структурами.

---

## Слой 4 — ЧТО ТРЕБУЕТ ПРОВЕРКИ (для Run 022)

Приоритет 1 (высокий):
1. Lemon blog URL — существует ли, содержит ли
   утверждения, приписанные внешними.
2. Kleros changelog 2026-08-17 — существует ли,
   что именно сказано.
3. GitHub PR про Argentina Consumer Protection
   dispute kit — существует ли, кто автор.

Приоритет 2 (средний):
4. Mendoza judicial pilot — существует ли публикация,
   подтверждает ли детали.
5. Resolución 893/2025 — существует ли, что в ней
   написано.
6. IPFS policyURI QmbEs5Ae8Sh5W... и
   QmUbgqKuUvfsnW... — доступны ли, что содержат.

Приоритет 3 (низкий):
7. Federico Ast публичные высказывания о Milei.
8. План по "Sociedades Automatizadas".
9. Связь EOA 0xd0d5fad9, 0xe66f7f8a с публичными
   организациями.

---

## Слой 5 — UNKNOWN

- Кто за EOA 0xd0d5fad9 и 0xe66f7f8a
  (организационно).
- Связаны ли они с Lemon или Мендосой.
- Есть ли другие arbitrable-контракты на Arbitrum V2
  помимо DisputeResolver.
- Есть ли другие сети, где активность выше.
- Почему три волны: 29 -> 32 -> 34.
- Существует ли Agentic-активность где-либо вообще,
  или это пока только позиционирование.

---

## Статус документа

Смешанный слой. Не для цитирования без указания
уровня. Обновляется после Run 022 (verification).
Не является Run record — это working context.

VERSION: v0.1
STATUS: WORKING CONTEXT
