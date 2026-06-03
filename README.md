#  RAG Agent - Production Assistant

Интеллектуальный ассистент для поддержки клиентов и сотрудников, который отвечает на вопросы **ТОЛЬКО на основе загруженной документации компании**, полностью исключая галлюцинации LLM.

---

##  НАЗНАЧЕНИЕ

- ✅ Полностью исключает галлюцинации LLM
- ✅ Каждый факт подтвержден цитатой из документа
- ✅ Готов к интеграции с любой CRM

---

##  КЛЮЧЕВЫЕ ВОЗМОЖНОСТИ

| № | Возможность | Описание |
|---|-------------|----------|
| 1 | **Гибридный поиск** | Semantic + BM25 + RRF fusion |
| 2 | **Self-RAG** | Автоматическая проверка качества ответа |
| 3 | **Многоуровневый кеш** | L1 память (TTL 5 минут) |
| 4 | **Production метрики** | Latency, groundedness, cost tracking |
| 5 | **Webhook API** | Готов к интеграции с любой CRM |

АРХИТЕКТУРА
Webhook →  Validation →  Cache →  Intent Router 
→  Parallel Search (Semantic + BM25 + Enrichment) 
→  RRF Fusion →  LLM Generation 
→  Groundedness Check →  Metrics →  Response

##  Быстрый старт

```bash
curl -X POST https://n-wformatagent-evgenylubitel.amvera.io/webhook-test/senior-rag \
  -H "Content-Type: application/json" \
  -d '{"query": "Что такое RAG?", "sessionId": "demo"}'
