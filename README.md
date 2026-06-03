# 🤖 RAG Agent - Production Assistant

RAG агент для поддержки клиентов, который отвечает на вопросы ТОЛЬКО на основе документации компании.

## 🚀 Быстрый старт

```bash
curl -X POST https://n-wformatagent-evgenylubitel.amvera.io/webhook-test/senior-rag \
  -H "Content-Type:application/json" \
  -d '{"query":"Что такое RAG?","sessionId":"demo"}'
