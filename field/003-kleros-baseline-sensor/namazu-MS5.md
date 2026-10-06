[EXTERNAL]
Model: Namazu

FIELD: KLEROS
STAGE: BASELINE SENSOR TEST

---

### РЕЗУЛЬТАТ ПРОГОНА

**Цель:** Проверить, может ли Envoy построить воспроизводимый минимальный датчик для 10 реальных Kleros V2 disputes.

**Результат:** **0 V2 disputes получено в структурированном виде.**

---

### 1. ПОПЫТКИ ДОСТУПА К V2 DISPUTES

#### 1.1 Kleros V2 Core Subgraph (GraphQL)

**FACT:**
- Kleros документирует V2 Core Subgraph на Arbitrum с ID `3U95wXKP8fBpkMNn8mbroVkUTuh6KtHGa456pTixx9B2`.
- Документация указывает endpoint pattern: `https://gateway.thegraph.com/api/{API_KEY}/subgraphs/id/{SUBGRAPH_ID}`.

**OBSERVATION:**
- Запрос `curl` к endpoint без API key вернул пустой ответ (exit code 0, тело отсутствует).
- Попытка использовать `demo` вместо API key также вернула пустой ответ.
- Публичных Goldsky endpoints для V2 Core найдено не было (только для V1 Curate).

**UNKNOWN:**
- Работает ли endpoint с действительным API key.
- Существуют ли альтернативные публичные endpoints для V2 Core.

#### 1.2 Klerosboard (Arbitrum chain ID 42161)

**FACT:**
- Klerosboard имеет раздел `/42161/cases` для Arbitrum.
- При обращении через `web_fetch` страница возвращает только заголовок "Klerosboard 3.0" без списка cases.

**OBSERVATION:**
- Klerosboard, вероятно, загружает данные динамически через JavaScript/GraphQL.
- Статический fetch не получает case data.
- Прямые URL case pages (`/42161/cases/0` through `/42161/cases/9`) также возвращают пустой контент.

**UNKNOWN:**
- Работает ли Klerosboard для Arbitrum в браузере с включенным JavaScript.
- Есть ли у Klerosboard API endpoint для программного доступа.

#### 1.3 V2 Court UI (v2.kleros.builders)

**FACT:**
- v2.kleros.builders — это задокументированный V2 Court UI.
- URL маршрутизация включает `/#/cases/display/1/desc/all`.

**OBSERVATION:**
- Статический fetch возвращает SPA shell (React/Vue приложение) без данных.
- Данные загружаются динамически; без JavaScript execution content недоступен.
- Case #0 V2 Beta (Lemon) подтверждается в документации, но прямой доступ к его данным через статический fetch невозможен.

**UNKNOWN:**
- Какой конкретно GraphQL endpoint или data source использует v2.kleros.builders.

#### 1.4 Case Studies Documentation

**FACT:**
- Kleros docs подтверждают существование Case #0 V2 Beta: "Kleros Enterprise Consumer Dispute for Lemon on Arbitrum", создан в ноябре 2024.

**OBSERVATION:**
- Документация предоставляет narrative description, но не структурированные machine-readable данные.
- "View on Court" link в docs ведет к динамическому UI, непосредственно не доступному через fetch.

#### 1.5 Arbiscan / On-chain

**FACT:**
- Arbiscan существует как block explorer для Arbitrum.
- KlerosCore V2 deployment addresses документированы.

**OBSERVATION:**
- Прямой доступ к Arbiscan для получения списка disputes через KlerosCore contract не был реализован в этом прогоне.
- Это потребовало бы знания точного contract address и ABI для фильтрации событий `DisputeCreation`.

---

### 2. ЧТО БЫЛО ПОЛУЧЕНО (V1, НЕ V2)

**FACT:**
В процессе были получены данные для V1 cases, но это **не соответствует задаче**:

| Case ID | Chain | Source | Полученные данные |
|---|---|---|---|
| #1657 | Ethereum (1) | Klerosboard | Evidence period, voting period, appeal period, final decision, evidence text, justifications |
| #1013 | Gnosis (100) | Klerosboard | Court name (xDai Curation Hidden Voting), status (Commit), date |
| #1000 | Gnosis (100) | Klerosboard | Periods, court, start date, arbitrable address |
| #532 | Ethereum (1) | Klerosboard | Famous case (2020 US Election), evidence section exists |
| #357 | — | lemon.kleros.io | V1 Escrow dispute, question, 4 evidence items, 6 juror justifications, executed ruling |

**OBSERVATION:**
- V1 cases доступны и структурированы на Klerosboard.
- V2 cases на Klerosboard (Arbitrum) не возвращают данные через статический fetch.

---

### 3. ТАБЛИЦА ЦЕЛЕВОГО DATASET (V2)

| ID | Chain | Court | Date/Block | Status | Ruling | Rounds | Kit | Evidence | Source |
|---|---|---|---|---|---|---|---|---|---|
| — | — | — | — | — | — | — | — | — | — |
| — | — | — | — | — | — | — | — | — | — |
| ... | ... | ... | ... | ... | ... | ... | ... | ... | ... |

**Все 10 строк пусты.**

---

### 4. REPRODUCIBILITY TEST

| Критерий | Результат | Пояснение |
|---|---|---|
| **A. Discovery** | ❌ FAIL | Другой исследователь не может найти V2 case по ID без API key или JavaScript-enabled browser |
| **B. Structure** | ❌ FAIL | Основные поля V2 dispute не были получены |
| **C. Content Access** | ❌ FAIL | Evidence для V2 disputes не проверено |
| **D. Source Stability** | ⚠️ UNKNOWN | V2 data sources требуют credentials или dynamic execution |
| **E. Minimum Dataset** | ❌ FAIL | Таблица из 10 V2 disputes не построена |

---

### 5. LIMITATIONS

**Критические ограничения, препятствующие получению V2 данных:**

1. **Subgraph API Key Gate:** The Graph decentralized network query URL требует API key для V2 Core Subgraph.
2. **SPA UI:** v2.kleros.builders и Klerosboard Arbitrum — динамические приложения. Статический fetch не получает case data.
3. **No Documented Public Endpoint:** Нет задокументированного публичного GraphQL endpoint для V2 Core без аутентификации.
4. **Klerosboard Arbitrum Empty:** Chain 42161 pages на Klerosboard возвращают пустой контент через fetch.
5. **No Bulk V2 Case List:** Нет обнаруженного источника, предоставляющего список V2 cases в machine-readable формате.

**Вторичные ограничения:**
- Goldsky public endpoints найдены только для V1 Curate, не для V2 Core.
- Arbiscan on-chain filtering требует contract address + ABI + event signature knowledge.

---

### 6. SENSOR STATUS

**YELLOW — датчик частично работает для V1, но для V2 воспроизводимый минимальный датчик построить невозможно при текущих ограничениях доступа.**

**Объяснение:**
- Для Kleros V1 (Ethereum, Gnosis) датчик работает: cases доступны через Klerosboard с извлекаемой структурой.
- Для Kleros V2 (Arbitrum) — целевого поля по задаче — датчик не построен из-за API key gate и dynamic UI limitations.

---

### 7. NEXT OBSERVATION

**Следующий технический шаг:**

Получить The Graph API key и выполнить подтверждённый GraphQL запрос к V2 Core Subgraph для 10 disputes.

**Альтернативный шаг (если API key недоступен):**

Использовать Arbiscan с известным KlerosCore proxy address для фильтрации событий `DisputeCreation` и получения on-chain dispute IDs, затем коррелировать с Klerosboard или IPFS evidence.

**Почему это следующий шаг:**
- Это единственный подтверждённый путь к V2 structured data.
- Без преодоления API key gate или on-chain event filtering невозможно построить воспроизводимый V2 датчик.

---

### 8. UNKNOWN

1. Работает ли V2 Core Subgraph с действительным The Graph API key.
2. Есть ли у Klerosboard скрытый API endpoint для Arbitrum cases.
3. Какой точный KlerosCore proxy address на Arbitrum.
4. Доступны ли V2 dispute evidence через IPFS.
5. Сколько V2 disputes реально существует на Arbitrum.
6. Использует ли v2.kleros.builders тот же subgraph ID или другой data source.

---

**Не использовались ответы других External-узлов. Не принято решение за Envoy.**
