#  RAG Agent - Production Assistant

RAG агент для поддержки клиентов, который отвечает на вопросы ТОЛЬКО на основе документации компании.
Webhook → Validation → Cache → Intent Router → Parallel Search 
→ RRF Fusion → LLM Generation → Groundedness Check → Response

##  Безопасность

| Защита | Механизм |
|--------|----------|
| XSS | Блокировка `<`, `>` и JavaScript |
| SQL инъекции | Блокировка DROP, DELETE, INSERT, UPDATE, ALTER |
| DDoS | Rate limiting: 10 запросов/минуту |
| Валидация | Макс. длина сообщения: 500 символов |


##  Быстрый старт

```bash
curl -X POST https://n-wformatagent-evgenylubitel.amvera.io/webhook-test/senior-rag \
  -H "Content-Type:application/json" \
  -d '{"query":"Что такое RAG?","sessionId":"demo"}'
