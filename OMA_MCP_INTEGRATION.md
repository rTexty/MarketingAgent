# OMA + MCP ИНТЕГРАЦИЯ
# Продукт: OMA (One Man Army)
# Версия: 02.04.2026

---

## АРХИТЕКТУРА

```
┌─────────────────────────────────────────────────────┐
│                    OMA СЛОЙ                          │
│  Скиллы (инструкции поведения) + Рутеры + Связи     │
│  Что делать, как говорить, какой формат результата   │
├─────────────────────────────────────────────────────┤
│                    MCP СЛОЙ                          │
│  Инструменты (tools) — реальные действия             │
│  Google Calendar, Gmail, Notion, Slack, HubSpot     │
├─────────────────────────────────────────────────────┤
│                 API / AUTH СЛОЙ                      │
│  OAuth2, API Keys, Permissions                      │
│  Аутентификация и авторизация                       │
└─────────────────────────────────────────────────────┘
```

**OMA-скиллы** = мозг (что делать)
**MCP-серверы** = руки (как делать)

Скилл говорит: «Создай событие в календаре на завтра в 14:00, участники: Иван и Мария».
MCP реально создаёт событие через Google Calendar API.

---

## MCP СЕРВЕРЫ — КАРТА ИНТЕГРАЦИЙ

### Tier 1: Базовые (подключить первыми)

| MCP Сервер | Что даёт | Модули OMA |
|---|---|---|
| **Google Workspace MCP** | Calendar, Gmail, Drive, Contacts | SECRETARY, HR |
| **Notion MCP** | Базы данных, страницы, wiki | SECRETARY, HR, DOC_GEN |
| **Slack MCP** | Сообщения, каналы, уведомления | SECRETARY, HR, SALES |

### Tier 2: Бизнес (подключить вторыми)

| MCP Сервер | Что даёт | Модули OMA |
|---|---|---|
| **HubSpot MCP** | CRM, contacts, deals, pipelines | SALES |
| **Linear MCP** | Задачи, проекты, sprints | SECRETARY |
| **GitHub MCP** | Repos, issues, PRs | (разработка) |

### Tier 3: Расширение

| MCP Сервер | Что даёт | Модули OMA |
|---|---|---|
| **Zapier MCP** | 5000+ интеграций (универсальный мост) | Все |
| **Activepieces MCP** | Альтернатива Zapier (open source) | Все |
| **Apollo.io MCP** | Lead generation, contacts | SALES, MARKETING |
| **Calendly MCP** | Scheduling links | SECRETARY |
| **Stripe MCP** | Платежи, подписки | SALES |

---

## МАППИНГ МОДУЛИ → MCP TOOLS

### OMA_SECRETARY

| Юнит | MCP Tools | Действия |
|---|---|---|
| calendar-management | Google Calendar MCP | `createEvent`, `getEvents`, `updateEvent`, `deleteEvent`, `checkAvailability` |
| email-triage | Gmail MCP | `listEmails`, `getEmail`, `sendEmail`, `createLabel`, `moveToLabel` |
| meeting-transcription | Google Meet MCP + Notion MCP | `getTranscript` → `createPage` |
| meeting-summary | Notion MCP | `createPage`, `updatePage` |
| knowledge-base | Notion MCP | `createDatabase`, `queryDatabase`, `createPage`, `updatePage` |
| task-coordination | Linear MCP / Notion MCP | `createIssue`, `updateIssue`, `queryIssues` |
| travel-logistics | Google Calendar MCP + Gmail MCP | `createEvent` + `sendEmail` |
| event-coordination | Google Calendar MCP + Notion MCP | `createEvent` + `createPage` |
| document-filing | Google Drive MCP | `createFile`, `createFolder`, `moveFile`, `listFiles` |

### OMA_SALES

| Юнит | MCP Tools | Действия |
|---|---|---|
| sales-strategy | Notion MCP | `createPage` — стратегия |
| lead-qualification | HubSpot MCP | `createContact`, `updateContact`, `createDeal`, `queryDeals` |
| cold-outreach | Gmail MCP + HubSpot MCP | `sendEmail` + `createContact`, `logActivity` |
| sales-scripts | Notion MCP | `createPage` — скрипт |
| proposal-writing | Notion MCP + Google Drive MCP | `createPage` / `createFile` |
| crm-optimization | HubSpot MCP | `createDeal`, `updateDeal`, `createPipeline`, `queryDeals` |
| negotiation | Notion MCP | `createPage` — подготовка |
| customer-success | HubSpot MCP | `getContact`, `updateContact`, `queryDeals` |
| sales-analytics | HubSpot MCP | `queryDeals`, `queryContacts` |

### OMA_HR

| Юнит | MCP Tools | Действия |
|---|---|---|
| job-description | Notion MCP | `createPage` — JD |
| resume-screening | Notion MCP | `createPage`, `queryDatabase` |
| interview-kit | Notion MCP | `createPage` — пакет |
| onboarding-plan | Notion MCP + Google Calendar MCP | `createPage` + `createEvent` |
| job-instructions | Notion MCP | `createPage` — инструкция |
| performance-review | Notion MCP | `createPage` — review |
| compensation-benefits | Notion MCP | `createPage` — пакет |
| hr-analytics | Notion MCP | `queryDatabase` — данные |
| corporate-culture | Notion MCP + Slack MCP | `createPage` + `sendMessage` |
| offboarding | Notion MCP + Google Calendar MCP | `createPage` + `createEvent` (exit interview) |

### OMA_DOC_GEN

| Юнит | MCP Tools | Действия |
|---|---|---|
| commercial-proposal | Google Drive MCP | `createFile` — PDF/Doc |
| presentation-generator | Google Drive MCP | `createFile` — Slides |
| contract-generator | Google Drive MCP + Notion MCP | `createFile` + `createPage` |
| act-generator | Google Drive MCP | `createFile` — PDF |
| report-generator | Google Drive MCP + Notion MCP | `createFile` + `createPage` |
| memo-generator | Gmail MCP + Notion MCP | `sendEmail` + `createPage` |
| table-generator | Google Sheets MCP | `createSheet`, `updateSheet` |
| legal-basics | Notion MCP | `createPage` — справка |
| template-manager | Notion MCP + Google Drive MCP | `createPage` + `createFile` |

### OMA_COPYWRITER / MARKETING / BIZ_ANALYTICS

Эти модули в основном генерируют контент (тексты, стратегии, расчёты). MCP-интеграции минимальны:
- Результат → **Notion MCP** (сохранить в базу знаний)
- Результат → **Google Drive MCP** (сохранить как файл)
- Публикация → **Slack MCP** (отправить в канал)

---

## НАСТРОЙКА — ПОШАГОВО

### Шаг 1: Google Workspace MCP

```json
// claude_desktop_config.json или mcp.json
{
  "mcpServers": {
    "google-workspace": {
      "command": "npx",
      "args": ["-y", "@googleworkspace/mcp-server"],
      "env": {
        "GOOGLE_CLIENT_ID": "your-client-id",
        "GOOGLE_CLIENT_SECRET": "your-client-secret",
        "GOOGLE_REDIRECT_URI": "http://localhost:3000/oauth2callback"
      }
    }
  }
}
```

**Что получаем:**
- Calendar: createEvent, getEvents, updateEvent, deleteEvent, checkAvailability
- Gmail: listEmails, getEmail, sendEmail, createLabel, moveToLabel
- Drive: createFile, createFolder, listFiles, moveFile, shareFile
- Contacts: getContact, createContact, updateContact

**OAuth scopes (минимальные):**
- `https://www.googleapis.com/auth/calendar`
- `https://www.googleapis.com/auth/gmail.modify`
- `https://www.googleapis.com/auth/drive.file`
- `https://www.googleapis.com/auth/contacts`

### Шаг 2: Notion MCP

```json
{
  "mcpServers": {
    "notion": {
      "command": "npx",
      "args": ["-y", "@notionhq/mcp-server"],
      "env": {
        "NOTION_API_KEY": "secret_xxxxxxxxxxxxx"
      }
    }
  }
}
```

**Что получаем:**
- createPage, getPage, updatePage, deletePage
- createDatabase, queryDatabase, updateDatabase
- search, appendBlock

### Шаг 3: Slack MCP

```json
{
  "mcpServers": {
    "slack": {
      "command": "npx",
      "args": ["-y", "@slack/mcp-server"],
      "env": {
        "SLACK_BOT_TOKEN": "xoxb-xxxxxxxxxxxxx",
        "SLACK_TEAM_ID": "TXXXXXXXXX"
      }
    }
  }
}
```

**Что получаем:**
- sendMessage, getChannelHistory, listChannels
- createChannel, inviteToChannel
- uploadFile, addReaction

### Шаг 4: HubSpot MCP

```json
{
  "mcpServers": {
    "hubspot": {
      "command": "npx",
      "args": ["-y", "hubspot-mcp-server"],
      "env": {
        "HUBSPOT_API_KEY": "pat-na1-xxxxxxxxxxxxx"
      }
    }
  }
}
```

**Что получаем:**
- Contacts: createContact, getContact, updateContact, searchContacts
- Deals: createDeal, getDeal, updateDeal, searchDeals, moveDealStage
- Pipelines: listPipelines, createPipeline
- Activities: logActivity, getActivities

---

## ОБНОВЛЕНИЕ SKILL-ФАЙЛОВ — ПАТТЕРН

Каждый skill-файл нужно обновить секцией «ИНСТРУМЕНТЫ»:

```markdown
## ИНСТРУМЕНТЫ (MCP)

Доступные инструменты для этого юнита:

| MCP | Tool | Когда использовать |
|---|---|---|
| Google Calendar | createEvent | Когда пользователь просит поставить встречу |
| Google Calendar | getEvents | Когда нужно показать расписание |
| Google Calendar | checkAvailability | Когда нужно найти свободное время |
| Notion | createPage | Когда нужно сохранить результат |

### ПРАВИЛА ИСПОЛЬЗОВАНИЯ ИНСТРУМЕНТОВ:
1. Не использовать инструмент без подтверждения пользователя
2. Сначала показать что будет сделано → подтверждение → действие
3. Если инструмент недоступен — сообщить и предложить альтернативу
4. Все действия логировать (что, когда, для кого)
```

---

## ПРИМЕРЫ ВЗАИМОДЕЙСТВИЯ

### Пример 1: Встреча через секретаря

```
Пользователь: Поставь встречу с Иваном на завтра в 14:00, тема: обсуждение Q2

Агент (OMA_SECRETARY + Google Calendar MCP):
1. Скилл определяет: это calendar-management
2. Проверяет availability через checkAvailability
3. Показывает пользователю:
   «Завтра в 14:00 у вас свободно. Создаю событие:
   📅 Обсуждение Q2
   🕑 Завтра, 14:00–14:30
   👥 Участники: Иван
   Подтвердить?»

4. Пользователь: Да
5. Агент вызывает createEvent → отправляет приглашение Ивану

━━━━━━━━━━━━━━━━━━━━━━━━━
▶ СЛЕДУЮЩИЙ ШАГ

Встреча создана — подготовьте повестку.

→ Составить повестку встречи
━━━━━━━━━━━━━━━━━━━━━━━━━
```

### Пример 2: Квалификация лида в CRM

```
Пользователь: Только что позвонил клиент из ООО «Ромашка», хочет demo

Агент (OMA_SALES + HubSpot MCP):
1. Скилл определяет: это lead-qualification
2. Задаёт BANT-вопросы
3. Пользователь отвечает
4. Агент создаёт contact + deal в HubSpot:
   createContact({
     company: "ООО Ромашка",
     email: "ivan@romashka.ru",
     phone: "+79991234567"
   })
   createDeal({
     name: "ООО Ромашка — Demo",
     stage: "Qualified",
     amount: 150000
   })

5. Показывает: «Лид создан в CRM. Deal на stage «Qualified».
   Запланировать демо?»

6. createEvent в Google Calendar на демо
```

### Пример 3: Резюме встречи → база знаний

```
Агент (OMA_SECRETARY + Notion MCP):
1. Получает стенограмму встречи (или пользователь вставляет)
2. Скилл делает резюме: решения, action items
3. createPage в Notion:
   - Title: «Резюме: [Тема] — [Дата]»
   - Database: Meeting Notes
   - Properties: Date, Participants, Decisions
   - Body: полное резюме

4. sendMessage в Slack:
   «Резюме встречи: [Тема] — [ссылка на Notion]»

5. createEvent для follow-up встречи (если нужна)
```

---

## БЕЗОПАСНОСТЬ

### Принципы:
1. **Minimal scopes**: запрашивать только нужные permissions
2. **User confirmation**: все записывающие действия — только после подтверждения
3. **Audit log**: логировать все MCP-действия (что, когда, от имени кого)
4. **Token rotation**: обновлять OAuth tokens регулярно
5. **No secrets in skills**: API keys — в env variables, не в skill-файлах

### Уровни доступа:
| Уровень | Действия | Подтверждение |
|---|---|---|
| Read-only | getEvents, listEmails, queryDatabase | Не нужно |
| Write (свои) | createEvent, createPage | Одно подтверждение |
| Write (чужие) | sendEmail, inviteToChannel | Двойное подтверждение |
| Delete | deleteEvent, deletePage | Двойное подтверждение + причина |

---

## ПЛАН ВНЕДРЕНИЯ

### Фаза 1: База (1–2 недели)
- [ ] Настроить Google Workspace MCP (Calendar + Gmail)
- [ ] Настроить Notion MCP
- [ ] Обновить OMA_SECRETARY скиллы (calendar-management, email-triage, meeting-summary)
- [ ] Обновить OMA_DOC_GEN скиллы (document-filing, template-manager)

### Фаза 2: Бизнес (2–3 недели)
- [ ] Настроить Slack MCP
- [ ] Настроить HubSpot MCP
- [ ] Обновить OMA_SALES скиллы (lead-qualification, cold-outreach, crm-optimization)
- [ ] Обновить OMA_HR скиллы (onboarding-plan, corporate-culture)

### Фаза 3: Автоматизация (2–3 недели)
- [ ] Настроить Zapier/Activepieces MCP (универсальные мосты)
- [ ] Создать цепочки: встреча → резюме → Slack → задача
- [ ] Создать цепочки: лид → CRM → follow-up email → демо
- [ ] Настроить Calendly MCP для scheduling

### Фаза 4: Расширение (по необходимости)
- [ ] Apollo.io MCP для lead generation
- [ ] Stripe MCP для платежей
- [ ] Linear MCP для проектного управления
- [ ] Кастомные MCP серверы для специфичных интеграций

---

## ТЕХНИЧЕСКАЯ РЕАЛИЗАЦИЯ

### Вариант A: Claude Desktop + локальные MCP

```
~/.config/claude/claude_desktop_config.json
```
Все MCP-серверы работают локально. Подходит для персонального использования.

### Вариант B: Claude Code + MCP в проекте

```
OMA_AGENTS/
├── .mcp/
│   ├── mcp.json              ← конфигурация MCP серверов
│   ├── servers/               ← локальные MCP серверы (если кастомные)
│   └── auth/                  ← OAuth tokens (gitignored)
├── OMA_MARKETING/
├── OMA_SALES/
...
```

### Вариант C: Серверная архитектура (для команды)

```
┌─────────────┐     ┌──────────────┐     ┌─────────────┐
│  OMA Agent  │────▶│  MCP Gateway │────▶│  Google API │
│  (Claude)   │     │  (Node.js)   │     │  Notion API │
│             │     │  Auth + Log  │     │  Slack API  │
└─────────────┘     └──────────────┘     │  HubSpot API│
                                          └─────────────┘
```

MCP Gateway — центральный прокси, который:
- Управляет аутентификацией (OAuth2 для всех пользователей)
- Логирует все действия
- Rate limiting
- Обработка ошибок и retry
