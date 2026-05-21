# ИИ-агент планерок: расшифровка → поручения → контроль задач

> n8n + Telegram + OpenRouter workflow для строительной команды: руководитель отправляет текст расшифровки планерки, система выделяет поручения, записывает реестр задач и отправляет сводку в Telegram.

---

## Business Problem

После планерок и рабочих созвонов поручения часто остаются в устной форме: кто-то записал часть задач в блокнот, кто-то забыл срок, часть договоренностей теряется в переписке. Для строительной компании это особенно болезненно, потому что поручения привязаны к объектам, подрядчикам, договорам, поставкам и срокам.

Типовые проблемы ручного процесса:

- руководитель тратит время на протоколирование после встречи;
- исполнители получают задачи в разном виде и в разных каналах;
- сроки и ответственные фиксируются не всегда;
- сложно быстро увидеть, какие поручения появились на последней планерке;
- контроль статусов превращается в ручной обзвон или поиск по чатам.

---

## What Was Built

**Статус: 🚧 в разработке.** Workflow создан как MVP-заготовка в n8n Cloud; перед рабочей публикацией нужно подключить OpenRouter API, Google Sheets и выбрать таблицу реестра.

Создан MVP workflow в n8n, который принимает текст расшифровки или заметки планерки в Telegram, отправляет их в OpenRouter-compatible LLM, извлекает поручения в структурированный JSON, записывает результат в Google Sheets и отправляет руководителю Telegram-сводку.

| Feature | Description |
|---------|-------------|
| Telegram intake | Руководитель отправляет текст расшифровки или заметки планерки в бот |
| LLM gateway | n8n вызывает OpenRouter через OpenAI-compatible Chat Completions API |
| Action extraction | OpenRouter-модель извлекает задачи, исполнителей, сроки, объект и приоритет |
| Structured JSON | Результат сохраняется как `tasks_json` для дальнейшей обработки |
| Task register | Google Sheets получает строку реестра по каждой планерке |
| Telegram summary | Бот отправляет краткую сводку поручений обратно руководителю |
| Portfolio-ready MVP | Workflow можно показать как рабочий прототип AI Automation для строительства |

---

## Process Automated

1. Руководитель отправляет текст расшифровки планерки в Telegram-бот.
2. Telegram Trigger запускает workflow.
3. Code node готовит OpenRouter request body.
4. HTTP Request вызывает `https://openrouter.ai/api/v1/chat/completions`.
5. OpenRouter-модель выделяет поручения в JSON.
6. Code node нормализует данные для реестра и Telegram-сводки.
7. Google Sheets append сохраняет запись планерки.
8. Telegram отправляет итог: сколько поручений найдено, кому назначены, какие сроки и приоритеты.

---

## n8n Workflow

| Node | Role |
|------|------|
| `Telegram: Meeting Transcript` | Принимает входящий текст с расшифровкой или заметками планерки |
| `Prepare OpenRouter Request` | Собирает payload для OpenRouter Chat Completions API |
| `OpenRouter: Extract Action Items` | Извлекает поручения в JSON через OpenRouter-модель |
| `Build Task Register Row` | Готовит поля для Google Sheets и Telegram |
| `Google Sheets: Append Meeting Tasks` | Записывает строку в реестр планерок |
| `Telegram: Send Task Summary` | Возвращает руководителю краткий список задач |

Workflow создан в n8n Cloud:

- **Name:** `Meeting Transcript → Tasks Agent (OpenRouter)`
- **Workflow ID:** `4Be36kZCEGlagiXB`
- **Status:** draft / needs credentials setup before publish

---

## JSON Output

Модель возвращает строгую структуру:

```json
{
  "meeting_title": "Планерка Северный склад",
  "summary": "Выделено 3 поручения по смете, договору и поставке металла.",
  "tasks": [
    {
      "task": "Подготовить смету по объекту Северный склад",
      "assignee": "Иван",
      "due_date": "2026-05-22",
      "project": "Северный склад",
      "priority": "high",
      "source_quote": "Иван, до пятницы подготовь смету по объекту Северный склад"
    }
  ]
}
```

---

## Google Sheets Register

MVP сохраняет одну строку на планерку:

| Column | Description |
|--------|-------------|
| `created_at` | Время обработки |
| `chat_id` | Telegram chat id руководителя |
| `meeting_title` | Название планерки или объекта |
| `summary` | Краткое содержание |
| `tasks_count` | Количество найденных поручений |
| `tasks_json` | Полный JSON задач |
| `transcript` | Текст расшифровки или заметки планерки |
| `telegram_summary` | Текст отправленного сообщения |

Следующий шаг развития: развернуть `tasks_json` в отдельные строки по каждой задаче и добавить ежедневный контроль просрочек.

---

## Stack

| Layer | Tech |
|-------|------|
| Automation | n8n Cloud |
| Input channel | Telegram Bot API |
| LLM gateway | OpenRouter |
| Task extraction | OpenAI-compatible Chat Completions API |
| Data register | Google Sheets |
| Logic | JavaScript Code node |
| Notification | Telegram message |

---

## Business Impact

- **Экономия времени руководителя:** не нужно вручную писать протокол после каждой планерки.
- **Меньше потерянных поручений:** задачи извлекаются из расшифровки планерки и сохраняются в реестр.
- **Прозрачность ответственности:** у задачи есть исполнитель, срок, объект и приоритет.
- **Быстрый контроль:** руководитель сразу получает сводку в Telegram.
- **Основа для управления статусами:** реестр можно связать с CRM, задачником или ежедневными напоминаниями.

---

## Deployment Notes

Перед публикацией workflow нужно подключить credentials:

- `Telegram account` — уже используется существующим Telegram-ботом;
- `OpenRouter API Key` — HTTP Header Auth credential для извлечения поручений;
- `Google Sheets` — для записи в реестр;
- выбрать Google Sheet document и sheet в ноде `Google Sheets: Append Meeting Tasks`.

Секреты и токены не хранятся в репозитории.

Аудио-транскрибация вынесена в следующий этап: ее можно добавить перед OpenRouter через отдельный STT-сервис, например Whisper-compatible API, Deepgram, AssemblyAI или другой доступный провайдер.

---

## Portfolio Fit

Кейс закрывает требования вакансий AI Automation Specialist в строительной отрасли:

- Make / n8n;
- Telegram Bot API;
- OpenRouter / OpenAI-compatible LLM API;
- автоматизация постановки и контроля задач;
- работа с Google Sheets;
- строительная специфика: объекты, подрядчики, сроки, планерки;
- быстрый MVP, который можно внедрить в реальный бизнес-процесс.

---

## Domain

Строительство, планерки, управление задачами, AI Automation, Telegram-боты, n8n, Google Sheets, контроль поручений, проектное управление.

---

*Автор: Андрей Рыкунов | rykunov@gmail.com*
