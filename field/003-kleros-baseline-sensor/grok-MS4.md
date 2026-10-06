MS4  
[EXTERNAL]  
Model: Grok 4.5  

FIELD: KLEROS  
STAGE: BASELINE SENSOR TEST  

**Цель прогона:** проверить возможность построения минимального воспроизводимого датчика реальных Kleros V2 disputes (Arbitrum One, resolved, публичный источник). Анализ закономерностей не проводился.

### 1. Попытка доступа к Kleros V2 Core Subgraph

**Endpoint, который использовался:**  
`https://gateway.thegraph.com/api/subgraphs/id/3U95wXKP8fBpkMNn8mbroVkUTuh6KtHGa456pTixx9B2`  
(документированный Mainnet Core Subgraph ID из docs.kleros.io)

**Запрос:**  
```graphql
{ disputes(first: 5) { id } }
```
и  
```graphql
{ _meta { block { number } } }
```

**Результат:**  
FACT: Оба запроса вернули ошибку:  
`{"errors":[{"message":"auth error: missing authorization header"}]}`

**Что не получилось:**  
Получение любых данных через documented GraphQL interface без API-ключа The Graph Studio.

**Причина:**  
Документация явно указывает, что decentralized network query URL требует `{YOUR_API_KEY}`. Публичный доступ без ключа отсутствует. Обход догадками не производился.

### 2. Попытка доступа через Kleros case UI / Klerosboard

**URL, которые проверялись:**  
- https://v2.kleros.builders/  
- https://v2.kleros.builders/#/cases/183/overview  
- https://v2.kleros.builders/#/cases/241/overview  
- https://klerosboard.com/  

**Результат:**  
OBSERVATION: Инструмент извлечения контента вернул «No content found» для всех указанных страниц.  
FACT: Это SPA (single-page application), контент загружается клиентским JavaScript после подключения. Статический fetch не возвращает данные дел.

**Публично задокументированные cases (из официальных материалов Kleros, не из UI):**  
Из blog.kleros.io и официальных постов:

| ID  | Chain     | Court                  | Date/Block     | Status   | Ruling              | Rounds | Kit     | Evidence          | Source                                      |
|-----|-----------|------------------------|----------------|----------|---------------------|--------|---------|-------------------|---------------------------------------------|
| 183 | Arbitrum  | Agentic Commerce (34) | 26 Aug 2026   | resolved | Refund the buyer   | 1      | UNKNOWN | 3 items (IPFS)   | blog.kleros.io (live stream record)        |
| 241 | Arbitrum  | Court 34              | ~Sep 2026     | resolved | customer (unanimous)| UNKNOWN| UNKNOWN | available (public)| YouTube / X (Kleros official) + case link  |

Дополнительно: в августе 2026 в Agentic Commerce Court подано и разрешено 42 тестовых диспута (официальный development update). Конкретные ID этих 42 дел в публичных текстовых материалах не перечислены.

**Сколько удалось получить:** 2 конкретных resolved cases с воспроизводимыми публичными ссылками + упоминание о 42 тестовых.  
**Предел:** невозможность программно или статически извлечь список дел из UI и subgraph без API-ключа / выполнения JavaScript.

### 3. On-chain data

FACT: Адреса контрактов V2 на Arbitrum One документированы (KlerosCore proxy: 0x991d2df165670b9cac3B022f4B68D65b664222ea и др.).  
OBSERVATION: Прямой запрос событий через публичный explorer возможен в принципе, но в рамках данного прогона полный список 10 resolved disputes через explorer не извлекался (требует ручного или скриптового разбора логов).  

### 4. Evidence

Для documented cases:  
- Dispute 183: FACT — 3 evidence items упоминаются как публичные (IPFS). Статус AVAILABLE по заявлению источника.  
- Dispute 241: OBSERVATION — evidence описано как public. Статус AVAILABLE по заявлению источника.  
Фактическая проверка содержимого IPFS URI в этом прогоне не выполнялась → для содержимого: UNKNOWN.

### REPRODUCIBILITY TEST

A. DISCOVERY  
FACT: Case по ID (183, 241) можно найти через публичные ссылки в официальных материалах Kleros (blog, X, YouTube). Самостоятельный discovery списка из 10 resolved cases через публичный интерфейс без ключа/JS — невозможен в рамках доступных инструментов.

B. STRUCTURE  
OBSERVATION: Для двух documented cases основные поля (ID, chain, court, status, ruling) совпадают между источниками. Полный набор полей (rounds, kit, exact block) для обоих не всегда указан.

C. CONTENT ACCESS  
OBSERVATION: Evidence заявлено как доступное; фактическая проверка URI не проводилась → UNKNOWN по содержимому.

D. SOURCE STABILITY  
FACT: Документированные subgraph endpoints и UI существуют.  
OBSERVATION: Subgraph требует авторизации; UI — SPA.

E. MINIMUM DATASET  
OBSERVATION: Таблицу минимальной структуры можно построить только для 2 cases. Для 10 cases — нет.

**Количество полученных cases:** 2 (максимум, который удалось зафиксировать с воспроизводимыми публичными источниками без API-ключа и без выполнения клиентского JS).

**Ограничение возникло на уровне:**  
1) Subgraph — обязательный API key.  
2) Case UI — SPA, статический fetch не возвращает данные.  
3) Отсутствие публичного bulk-списка resolved V2 disputes в текстовом/CSV виде.

Данные получены только через официальные текстовые публикации Kleros (blog.kleros.io, X-посты, документация). Прямой программный доступ к живому списку дел в этом прогоне не состоялся.

### SENSOR STATUS

**YELLOW**  

Минимальный воспроизводимый датчик частично работает: два конкретных resolved V2 dispute (Arbitrum) с основными полями можно независимо найти и зафиксировать по публичным ссылкам.  

Главные ограничения:  
- documented GraphQL endpoint требует API-ключ (не является working public API);  
- case UI является SPA и не отдаёт данные при статическом доступе;  
- нет публичного готового списка ≥10 resolved V2 disputes, который можно было бы скачать без дополнительных инструментов/ключей;  
- evidence URI доступность подтверждена только заявлением источников, а не прямой проверкой содержимого.

### NEXT OBSERVATION

Выполнить один конкретный, документированный GraphQL-запрос к Core Subgraph V2 (с использованием временного API-ключа The Graph Studio, если он будет предоставлен) на `disputes(first: 20, where: {ruled: true}, orderBy: createdAtBlock, orderDirection: desc)` и зафиксировать возвращаемые поля + наличие evidence references. Параллельно проверить вручную 5 case pages на v2.kleros.builders по известным ID.
