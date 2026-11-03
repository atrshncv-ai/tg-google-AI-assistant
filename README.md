# Telegram AI Assistant with Google Calendar

A Telegram bot — a personal AI assistant that manages tasks, reminders and events in **Google Calendar**.

> **Status: experiment** — a personal automation experiment (n8n workflow), not a production service.

## Problem

Manual task and reminder planning took time, and calendar integration was inconvenient.

## Solution

An n8n workflow ([`workflows/assistant-bot.json`](workflows/assistant-bot.json)) that connects Telegram, an LLM agent and Google Calendar:

- Telegram trigger → n8n **AI Agent** with tool-calling
- **Simple Memory** (conversation buffer) for context
- Google Calendar tools: create, update, delete and list events (`create_event`, `list_events`, …)
- Voice messages are transcribed (OpenAI transcription) and processed the same way
- Confirmation reply back in Telegram

Natural-language requests like "add a meeting tomorrow at 14:00" are parsed by the LLM and turned into calendar events.

## Stack

- Telegram Bot API
- n8n (AI Agent, OpenAI Chat Model)
- Google Calendar API (n8n Google Calendar tools)
- LLM with tool-calling (configurable model)

---

# Telegram AI Assistant с интеграцией Google Calendar

Telegram-бот — личный AI-ассистент с задачами, напоминаниями и трекингом в Google Calendar.

> **Статус: experiment** — личный эксперимент по автоматизации (n8n-workflow), не production-сервис.

## Проблема

Ручное планирование задач и напоминаний отнимало время, интеграция с календарём была неудобной.

## Решение

n8n-workflow ([`workflows/assistant-bot.json`](workflows/assistant-bot.json)), связывающий Telegram, LLM-агента и Google Calendar:

- Telegram-триггер → n8n **AI Agent** с tool-calling
- **Simple Memory** (буфер разговора) для контекста
- Google Calendar-инструменты: создание, обновление, удаление и список событий (`create_event`, `list_events`, …)
- Голосовые сообщения транскрибируются (OpenAI) и обрабатываются так же
- Подтверждение приходит обратно в Telegram

Запросы на естественном языке вроде «добавь встречу завтра в 14:00» разбираются LLM и превращаются в события календаря.

## Стек

- Telegram Bot API
- n8n (AI Agent, OpenAI Chat Model)
- Google Calendar API (n8n-инструменты Google Calendar)
- LLM с tool-calling (модель настраивается)

## License / Лицензия

Released under the MIT License. See [LICENSE](LICENSE).
Проект распространяется по лицензии MIT. См. [LICENSE](LICENSE).
