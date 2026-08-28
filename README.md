# Александр | Data Engineer

Инженер данных со специализацией на проектировании DWH, построении отказоустойчивых ELT/ETL-пайплайнов, продвинутом моделировании данных (Data Vault 2.0, Kimball) и интеграции данных в AI/RAG-сервисы.

---

## 🛠 Технологический стек

* **Языки & Среда:** Python (Pandas, FastAPI, Pydantic), SQL (DDL, DML, Window Functions), Bash, Docker, знаком с Java
* **Оркестрация & Инженерия данных:** Apache Airflow, Apache NiFi, DATAREON Platform, SAP BO Data Services, REST API, dbt Core
* **Базы данных & Хранилища:** PostgreSQL, Greenplum, ChromaDB (Vector Search)
* **Моделирование данных:** Data Vault 2.0, Kimball / Star Schema, SCD2, Нормализация (1NF–3NF)
* **AI & Data Applications:** RAG-архитектура, Sentence Transformers, Ollama, Qwen, Embeddings

---

## 📂 Проекты

### 1. [Automated ELT DWH Pipeline (Airflow & dbt Core)](https://github.com/lelik-bolek/eltdwh-airflow-dbt)
> **Фокус:** *End-to-End инженерия данных, оркестрация, контроль идемпотентности, историзация.*

* **Архитектура:** Полноценный конвейер из 6 DAG-ов в Airflow 2.9.2 с изоляцией зон ответственности: Airflow отвечает за Control Flow и валидацию файлового инжестинга, dbt Core — за SQL-трансформации внутри PostgreSQL.
* **Слои данных:** `staging` $\to$ `core` (Data Vault 2.0: Hubs, Links, Satellites с аудитом через `sat_source_load`) $\to$ `marts` (витрины фактов и измерений со слоем SCD2).
* **Артефакты:** Архитектурные C4-диаграммы (Container & Component в `.drawio` и `.png`), ADR-001 и практический Runbook по эксплуатации.

---

### 2. [Relational Modeling & Analytical DWH](https://github.com/lelik-bolek/DWH_Relational_Model)
> **Фокус:** *Реляционное моделирование, нормализация, проектирование фактов/измерений, SCD2.*

* **Архитектура:** Сквозной переход от нормализованной транзакционной схемы (3NF) к аналитической схеме «Звезда» (Kimball) в PostgreSQL.
* **Ключевые решения:** Реализация версионности сущностей по методологии Slowly Changing Dimensions Type 2 (SCD2) на суррогатных ключах и интервалах актуальности (`effective_from` / `effective_to`), изоляция схем и скрипты верификации целостности.
* **Артефакты:** C4-диаграммы, ADR по переходу 3NF $\to$ Star Schema, ER-диаграммы и Runbook.

---

### 3. [Corporate AI Bot & RAG Service](https://github.com/lelik-bolek/corporateAIBot_Ollama)
> **Фокус:** *Data Engineering + AI, векторный поиск, потоковая обработка контекста и API.*

* **Архитектура:** Локальный RAG-сервис на базе FastAPI, векторной базы данных ChromaDB и эмбеддинг-модели `intfloat/multilingual-e5-base` для интеграции корпоративной базы знаний с LLM (Ollama / Qwen).
* **Ключевые решения:** Chunking-стратегии, оптимизация retrieval-пайплайна по порогам сходства (`similarity threshold`, `top_k`), структурированная валидация запросов (Pydantic) и контейнеризация.

---

## 📐 Инженерные стандарты
Каждый проект сопровождается поддерживаемой технической документацией:
* **C4 Model Diagrams:** визуализация уровней Container и Component (исходники `.drawio` + `.png`).
* **ADR (Architecture Decision Records):** фиксация ключевых компромиссов, ограничений и обоснований решений.
* **Runbooks:** воспроизводимые инструкции для развертывания, тестирования и траблшутинга.

## 📬 Контакты
* **Сайт-портфолио:** [lelik-bolek.github.io](https://lelik-bolek.github.io/)
* **LinkedIn:** [Alexander Lelikov](https://www.linkedin.com/in/alexander-lelikov-alexander/)
* **Email:** [lelikov2@yandex.ru](mailto:lelikov2@yandex.ru)
