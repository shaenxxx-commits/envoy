MS5  
[EXTERNAL]  
Model: Grok 4.5  

FIELD: KLEROS  
STAGE: ON-CHAIN SENSOR TEST  

**Цель:** проверить техническую наблюдаемость Kleros V2 disputes непосредственно через on-chain события на Arbitrum One без The Graph API.

### 1. CONTRACT DISCOVERY

FACT: Официальный адрес KlerosCore (proxy) на Arbitrum One (Chain ID 42161):  
`0x991d2df165670b9cac3B022f4B68D65b664222ea`  

Источник: docs.kleros.io/reference/contracts/deployment-addresses (раздел Arbitrum One → Core Contracts). Документация прямо указывает использовать proxy-адрес.  

OBSERVATION: Адрес подтверждён несколькими страницами официальной документации Kleros. Независимая проверка через explorer в этом прогоне не удалась (см. ниже).

### 2. EVENT DISCOVERY

FACT: Документированное событие создания dispute в интерфейсе IArbitratorV2 / KlerosCore:  

```solidity
event DisputeCreation(uint256 indexed _disputeID, IArbitrableV2 indexed _arbitrable);
```

Источник: docs.kleros.io (Arbitrable Apps V2, KlerosCore reference).  

Из события извлекаются:  
- `_disputeID` (indexed) — идентификатор dispute;  
- `_arbitrable` (indexed) — адрес контракта, создавшего dispute.  

Court ID, timestamp/block, rounds, ruling и другие поля в самом событии DisputeCreation **не содержатся**. Их получение требует дополнительных view-вызовов или других событий (Ruling, AppealDecision и т.д.).  

OBSERVATION: event signature и поля подтверждены только документацией. Фактический topic0 / ABI из verified source на explorer в этом прогоне не извлекался.

### 3. ON-CHAIN EXTRACTION

Попытки:

- Открытие страницы https://arbiscan.io/address/0x991d2df165670b9cac3B022f4B68D65b664222ea и #events → инструмент вернул ошибку «Failed to retrieve page content».  
- Запросы к Arbiscan API (txlist, getLogs) →  
  `{"status":"0","message":"NOTOK","result":"You are using a deprecated V1 endpoint, switch to Etherscan API V2..."}`  
- Публичный RPC-запрос логов напрямую не выполнялся (в среде отсутствует настроенный archive RPC с возможностью eth_getLogs без ограничений).

FACT: В рамках доступных инструментов ни один реальный log DisputeCreation с Arbitrum One не был получен.  

UNKNOWN: количество и содержание фактических DisputeCreation событий на контракте в текущий момент.

### 4. DISPUTE IDENTIFICATION / MINIMUM DATASET

FACT: Реальные V2 dispute IDs из on-chain событий **не извлечены**.  

Ранее известные из публичных текстовых источников (blog.kleros.io) IDs 183 и 241 остаются только документационными примерами; они **не** подтверждены в этом прогоне чтением логов KlerosCore.  

Минимум 5 (желательно 10) реальных V2 disputes через on-chain канал **не получен**.

### REPRODUCIBILITY TEST

A. CONTRACT DISCOVERY — **PASS** (адрес официально задокументирован и стабилен как proxy).  
B. EVENT DISCOVERY — **PASS** (событие DisputeCreation документировано с точными полями).  
C. ON-CHAIN EXTRACTION — **FAIL** (explorer-страницы и публичный API Arbiscan в текущей среде недоступны / требуют ключ или V2 endpoint; RPC-логи не извлечены).  
D. DISPUTE IDENTIFICATION — **FAIL** (реальные ID не получены).  
E. MINIMUM DATASET — **FAIL** (0 фактически извлечённых on-chain disputes).

### SENSOR STATUS

**YELLOW**

On-chain путь теоретически подтверждён (контракт + событие), но практически минимальный набор из 5+ реальных V2 disputes извлечь не удалось.

**Что фактически удалось получить:**  
- официальный адрес KlerosCore proxy;  
- точное имя и сигнатуру события DisputeCreation;  
- перечень полей, которые событие даёт (disputeID + arbitrable).

**Где находится ограничение:**  
1. Отсутствие рабочего публичного доступа к eth_getLogs / Arbiscan Logs API без API-ключа (V1 endpoint deprecated).  
2. Невозможность статически прочитать страницу Events на arbiscan.io.  
3. Court ID, status, ruling, rounds не находятся в самом событии создания и требуют дополнительных вызовов, которые также не выполнены.

### NEXT OBSERVATION

Выполнить один конкретный eth_getLogs-запрос (или эквивалент через Arbiscan API V2 с ключом) к адресу `0x991d2df165670b9cac3B022f4B68D65b664222ea` за последние 100 000–500 000 блоков с фильтром по topic0 события DisputeCreation и зафиксировать первые 5–10 возвращённых логов (disputeID, blockNumber, transactionHash).
