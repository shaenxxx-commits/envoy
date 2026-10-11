MS4  
[EXTERNAL]  
Model: Grok 4.5  

FIELD: KLEROS  
STAGE: INITIAL RECONNAISSANCE  

### 1. CURRENT STATE

**Действующие компоненты (FACT / OBSERVATION):**  
- Court V1: production-протокол на Ethereum Mainnet и Gnosis Chain с 2018 года. По документации разрешил более 1500 диспутов. Ядро — монолитный контракт KlerosLiquid.  
- Court V2: работает на Arbitrum One в статусе beta. По официальной документации и development updates (май–август 2026) обработано 100+ диспутов в beta.  
- Dispute Kits: Classic (live), Gated (live), GatedShutter (live), Shutter (in testing), partial-coherence (merged).  
- Vea Bridge: используется для cross-chain доставки rulings.  
- Atlas: backend-сервисы (IPFS, уведомления, keeper bots).  
- Продукты: Curate, Scout, Escrow (V1/V2), Proof of Humanity V2, Dispute Resolver (V1), Foresight, Governor/Zodiac интеграции.  
- Agentic Commerce Court (Court ID 34 на Arbitrum): создан, принимает тестовые и демонстрационные диспуты с AI-агентами в качестве jurors (август–сентябрь 2026).  

**Beta / experimental:**  
- Court V2 в целом остаётся в beta (аудит Certora проведён, но последующие упрощения контрактов не покрыты этим аудитом).  
- Agentic Commerce Court и AI-jurors эксперименты.  
- Forking dispute kit — в статусе draft.  
- Kleros CLI для агентов, AI jurors dashboard.  

**Заявленные, но ещё не реализованные или находящиеся в ранней стадии:**  
- Полноценный Forking Court (ID 0 зарезервирован, но не активен для обычных диспутов).  
- Более широкое production-развёртывание V2 за пределами beta с guardrails.  
- Масштабирование agentic arbitration как production-сервиса.  

Источники: docs.kleros.io/court/overview, development updates августа–сентября 2026, blog.kleros.io.  

### 2. ARCHITECTURE

Высокоуровневая структура (по документации):  

- **Court V1**: монолитный KlerosLiquid на Ethereum/Gnosis. Стейкинг PNK остаётся в кошельке юриста. Иерархия subcourts. Commit-reveal голосование. RNG на основе blockhash. Стандарты ERC-792 (arbitration) и ERC-1497 (evidence).  

- **Court V2**: модульная архитектура на Arbitrum.  
  - KlerosCore — координатор диспутов и исполнение rulings.  
  - SortitionModule — выбор юристов (с использованием Chainlink VRF).  
  - Pluggable Dispute Kits — механизмы разрешения.  
  - Vea Bridge — cross-chain.  
  - Стейкинг: PNK переводится в контракт.  

- **Dispute Kits**: Classic (plurality), Shutter (threshold encryption), Gated (SBT-eligibility), комбинации.  

- **Evidence / IPFS**: evidence загружается через Atlas на IPFS; MetaEvidence и templates используются для отображения.  

- **Jurors / staking / voting**: стейкинг PNK в конкретный court (с автоматическим стейкингом в parent courts). Случайный выбор пропорционально stake. Coherence-based rewards/slashing.  

- **Appeals / forking**: апелляции увеличивают число юристов; при достижении порога — jump в parent court. Forking Court зарезервирован для protocol-level споров.  

- **Другие**: PolicyRegistry, DisputeTemplateRegistry, keeper bots, subgraphs для индексации.  

Не описывается код; только заявленная и документированная структура.  

### 3. TRAJECTORY

**V1 → V2:** переход от монолитного контракта на L1 к модульной архитектуре на L2 (Arbitrum) с целью снижения стоимости, повышения гибкости и cross-chain поддержки.  

**2025–2026:**  
- Проведены внутренние review rounds и внешний аудит Certora (конец 2025 — начало 2026).  
- Упрощение контрактов Dispute Kits (май–июнь 2026).  
- Появление и тестирование Agentic Commerce Court (август 2026: 42 тестовых диспута разрешены).  
- Развитие AI-агентов как юристов (CLI, dashboard, live-демонстрации).  
- Усиление backend (Atlas), миграции фронтендов, поддержка новых сетей.  
- Forking kit перешёл в draft и governance discussion.  

**Структурные изменения:**  
- Замена монолита модульностью.  
- Перенос стейкинга в контракт.  
- Появление pluggable kits вместо единого механизма.  
- Ускорение agentic / AI-направлений.  
- Сохранение V1 в production при параллельной разработке V2.  

Проблемы, судя по материалам, толкающие изменения: стоимость L1, необходимость специализации механизмов голосования, потребность в cross-chain, интерес к agentic economy.  

Источники: docs.kleros.io, blog.kleros.io development updates 2026.  

### 4. CLAIMED vs BUILT

| Направление                  | CLAIMED                                      | BUILT / OBSERVED                                      | UNKNOWN                          |
|-----------------------------|----------------------------------------------|-------------------------------------------------------|----------------------------------|
| Court V2 production         | Next-gen upgrade                             | Beta с 100+ разрешёнными диспутами                    | Полный production без guardrails |
| Modular Dispute Kits        | Pluggable mechanisms                         | Classic, Gated, GatedShutter live; Shutter testing   | Стабильность всех kits           |
| Cross-chain (Vea)           | Multi-chain resolution                       | Используется, развитие oracles                       | Полнота маршрутов                |
| Agentic Commerce Court      | Court для AI-агентов                         | Court 34 создан, демонстрационные диспуты разрешены | Масштаб и устойчивость           |
| Forking                     | Protocol-level disputes                      | Spec и kit в draft                                   | Реализация                       |
| AI jurors                   | Agents as jurors                             | Эксперименты, CLI, live demos                        | Production reliability           |

### 5. REAL CASES

FACT / OBSERVATION из публичных материалов:  
- Dispute 183 (Arbitrum, Agentic Commerce Court): создан во время live stream 26 августа 2026, 5 AI-юристов, 1 раунд, 3 evidence items, ruling «Refund the buyer». Запись публична.  
- Dispute 241 (Arbitrum, Court 34): агентский контрактный спор (DocuSign + критерии), 5 юристов, ruling в пользу customer.  
- Август 2026: 42 тестовых диспута в Agentic Commerce Court, все разрешены.  
- V1: исторические дела доступны через court.kleros.io и subgraphs (более 1500 в сумме).  

Доступность:  
- ID, chain, court, status/ruling, rounds — извлекаются из UI / subgraph / on-chain.  
- Evidence: IPFS-ссылки, доступность зависит от persistence.  
- Juror/vote information: в V2 beta и Agentic Court — частично публична (justifications в demos).  
Воспроизводимость: через documented subgraph endpoints и публичные case links (v2.kleros.builders/#/cases/...).  

Полный произвольный sample в момент этого прогона не выгружался; приведены только публично задокументированные примеры.  

### 6. EMERGING STRUCTURES

OBSERVATION:  
- Dispute Kits как pluggable слой (особенно partial-coherence и forking в разработке).  
- Agentic Commerce Court и AI-jurors (параметры оптимизированы под короткие периоды, низкие fees).  
- Agent reputation / scoreboards (сторонние dashboard’ы отслеживают reliability агентов).  
- Kleros CLI и skills для агентов.  
- Усиление IPFS/Atlas как evidence infrastructure.  
- Cross-chain через Vea.  

Не предполагается, что эти направления являются единственными или главными; они наблюдаются как активно обсуждаемые и тестируемые в 2026.  

### 7. RESEARCH OBJECT

OBSERVATION: Получен комбинированный объект:  
- устоявшийся production arbitration protocol (V1);  
- развивающаяся модульная governance/arbitration architecture в beta (V2);  
- экспериментальная инфраструктура для agentic disputes (Agentic Commerce Court + AI jurors).  

Объект находится в состоянии параллельного существования зрелого слоя и быстро меняющегося экспериментального слоя. Чёткой границы «только V1» или «только agentic» на текущем этапе нет.  

### 8. UNKNOWN

- Точный текущий объём и распределение живых (не тестовых) диспутов V2 beta vs V1.  
- Долгосрочная persistence всех IPFS evidence.  
- Реальная доля AI-агентов среди юристов за пределами демонстрационных дел.  
- Стабильность и audit-coverage финальных контрактов V2 после упрощений.  
- Практическая готовность Forking Court.  
- Полнота и актуальность subgraph-данных для произвольной выборки.  
- Экономические параметры (fees, stakes) в Agentic Court при росте нагрузки.  

### 9. NEXT OBSERVATION

Следующий конкретный шаг:  
Выполнить воспроизводимый GraphQL-запрос к Core Subgraph V2 (Arbitrum) на последние 20–50 диспутов, зафиксировать поля (id, court, period, ruled, currentRuling, rounds, templateId), а также проверить доступность связанных evidence URI и case pages на v2.kleros.builders для 5–10 конкретных ID.  

Параллельно зафиксировать один полный публичный record Agentic Commerce Court диспута (включая justifications, если доступны).  

Это даст первый измеримый sample реального исследовательского объекта без перехода к анализу закономерностей.
