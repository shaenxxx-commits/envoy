MS10
[EXTERNAL]
Model: Kimi K2 Thinking

---

## 1. Оценка метода (Вопрос 1)

### Размер выборки
**FACT:** Выборка 20/87 (23%) для court 29 и 20/36 (55%) для court 32.  
**OBSERVATION:** Для court 32 покрытие выборки >50%, что статистически устойчиво. Для court 29 — умеренное покрытие.  
**HYPOTHESIS:** Достаточность зависит от метода отбора.  
**UNKNOWN:** Был ли отбор случайным (random sampling), систематическим (каждый N-й) или целенаправленным (convenience sampling)?

**Критический риск:** Если выборка не случайная, пересечение policyURI может быть артефактом отбора (например, если взяты последние 20, а они принадлежат к одному батчу).

### Метод сверки
**FACT:** Сравнение хэшей IPFS (policyURI) across courts.  
**OBSERVATION:** Метод консервативен — разные хэши точно означают разный контент; одинаковые хэши, вероятно, означают идентичный контент (с учётом collision resistance keccak256).

---

## 2. Интерпретация policyURI (Вопрос 2)

### Статус evidence
**FACT:** PolicyURI — это IPFS hash содержания MetaEvidence/policy.  
**OBSERVATION:** Одинаковый hash в разных судах доказывает использование идентичного policy-шаблона.

### Альтернативные объяснения (не исключённые)
**HYPOTHESIS A (Template Library):** DisputeResolver или связанная инфраструктура предоставляет библиотеку шаблонов (Lemon SDK). Разные операторы/программы могут выбирать один и тот же шаблон из библиотеки.  
**HYPOTHESIS B (Fork с сохранением URI):** Программа форкается, но сохраняет policyURI (редко, но возможно).  
**HYPOTHESIS C (Resubmission):** Один и тот же disputant/operator повторно использует проверенный шаблон в разных контекстах.

**UNKNOWN:** Сопровождается ли policyURI идентичностью arbitrable contract (того же адреса `0xb552...4323` в судах 29 и 32)? Если нет — нет доказательства единой программы, есть доказательство общей библиотеки.

---

## 3. Подмена вывода? (Вопрос 3)

**ВЫВОД СЛИШКОМ СИЛЬНЫЙ.**

**Логическая цепочка в Run 018:**
Shared policyURI → shared program (H1)  
**Пропущенное звено:** Shared policyURI + shared arbitrable address → shared program instance.

**Корректная формулировка вывода:**
> "Наблюдается continuity of policy templates across courts 29, 32, 34, consistent with hypothesis of shared infrastructure or template library. Single-program hypothesis (H1) requires additional evidence of shared operator identity or arbitrable contract continuity."

**Конкретная ошибка:** Переход от "одинаковые шаблоны" к "одна эволюционирующая программа" — это leap of synthesis. Возможен сценарий: DisputeResolver как gateway service для multiple independent merchants, использующих общие шаблоны.

---

## 4. Что пропущено (Вопрос 4)

### Критически важное
**A. Arbitrable address continuity**  
Проверены ли адреса arbitrable contracts для сэмплов из courts 29/32? Если это тот же `0xb552...4323`, H1 подтверждена. Если разные адреса — H1 опровергнута (общий gateway, разные программы).

**B. DisputeID continuity**  
Наблюдается ли монотонное увеличение disputeID across courts (признак единого счётчика) или разные диапазоны?

**C. MetaEvidence timestamps**  
Внутри policyURI — есть ли temporal markers (version, date) или static content?

**D. Transaction origin analysis**  
Кто вызывает `createDispute` — один и тот же EOA/multisig или разные?

### Существенное
**E. PolicyURI provenance**  
Кто pinned IPFS content? Один operator или децентрализованное хранение?

**F. Court parameters evolution**  
Менялись ли параметры courts 29/32/34 (fees, stakes) до/после волн? Это могло бы объяснить миграцию.

---

## 5. Следующий шаг (Вопрос 5)

**Рекомендация: (b) причина миграции между courts**

### Обоснование
Но при условии уточнения методологии:
1. **Сначала проверить:** Является ли arbitrable contract идентичным across courts (тот же адрес)?
   - Если **ДА:** Это одна программа, мигрирующая между судами. Исследовать причины (court params, fees, dispute types).
   - Если **НЕТ:** Это разные программы с shared templates. Исследовать почему шаблоны общие (template marketplace).

2. **Затем:** Resource Fit assessment — только после определения, что мы изучаем (single program evolution vs template marketplace).

### Почему не (a) или (c) сейчас
**(a) Идентификация оператора:** Требует off-chain OSINT (website, API), что выходит за рамки on-chain sensor. Делать это сейчас — риск построить гипотезу на непроверяемых данных.  
**(c) Resource Fit:** Преждевременно. Мы не знаем, что изучаем (single instance vs multi-tenant gateway), поэтому не можем оценить resource requirements.

### Почему (b)
**Structural question:** Почему один и тот же (или похожий) dispute flow меняет court over time?
- Court 29 → 32: Может быть upgrade court (Defensores более специализированы, чем Consumo?)
- 32 → 34: Миграция на "новый" court (Agentic) или expansion capacity?

**Проверяемая гипотеза:** Courts как versions — когда параметры court N становятся suboptimal, программа мигрирует на court N+1.

---

## Итоговая оценка Run 018

| Критерий | Статус |
|----------|--------|
| Статистическая мощность | Приемлемая (для court 32 — высокая) |
| Логическая валидность | **Слабая** — leap от template к program |
| Доказательная база | Недостаточная для H1 (нужен arbitrable address check) |
| Методологический риск | Высокий (synthesis without identity verification) |

**Вердикт:** H1 plausible but not proven. Evidence supports "shared template infrastructure" strongly; "single evolving program" only if arbitrable address is identical across courts.

**Требуется:** Verification step — check arbitrable contract address for sampled disputes in courts 29/32 before proceeding to migration analysis.
