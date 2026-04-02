# OMA System — Progress & Continuation Guide

## Что сделано (2026-04-03)

### Установка
- Репозиторий MarketingAgent склонирован в `~/workspace/MarketingAgent`
- 14 superpowers-скиллов установлены в `~/.openclaw/skills/sp-*`
- Gateway перезапущен

### Модуль 1: OMA_MARKETING (оригинальный, не трогать)
- 32 скилла в `OMA_MARKETING/skills/`
- Router, Connections, Global Rules, Skill Template
- Был в репозитории изначально

### Модуль 2: OMA_BIZ_ANALYTICS (оригинальный, не трогать)
- 9 скиллов в `OMA_BIZ_ANALYTICS/skills/`
- Router, Connections, Global Rules
- Был в репозитории изначально

### Модуль 3: OMA_COPYWRITER ✅ ГОТОВ
- Router: `OMA_ROUTER_COPYWRITER.md` (8 юнитов, серые зоны, fallback)
- Connections: `OMA_CONNECTIONS_COPYWRITER.md` (внутренние + кросс-модульные связи)
- 8 скиллов (300+ строк каждый, с DOMAIN KNOWLEDGE, ДИАЛОГ-ПРОТОКОЛ, OUTPUT, АНТИ-ПАТТЕРНЫ, SELF-CHECK):
  1. `copywriting-core.md` — тексты для страниц/лендингов (PAS/BAB/AIDA, структура страниц, CTA, psychology)
  2. `copy-editing.md` — редактура: убирать воду, штампы, пассивный залог (3 уровня правок)
  3. `email-copywriting.md` — email-серии: welcome, nurture, re-engagement (subject lines, timing, метрики)
  4. `ad-copywriting.md` — рекламные объявления: Google/Meta/Яндекс (лимиты символов, формулы CTR, A/B)
  5. `social-copywriting.md` — посты для соцсетей: Telegram/LinkedIn/Instagram/Twitter (вирусные форматы, контент-план)
  6. `sales-copywriting.md` — продающие тексты: sales letters, VSL-скрипты, питч-деки (psychology, anchoring, objections)
  7. `brand-voice.md` — голос бренда: tone of voice, система слов, адаптация по каналам
  8. `landing-page-anatomy.md` — структура лендингов: типы (Lead Gen, SaaS, E-commerce, App), секции, конверсия

### Модуль 4: OMA_SALES ✅ ГОТОВ
- Router: `OMA_ROUTER_SALES.md` (9 юнитов)
- Connections: `OMA_CONNECTIONS_SALES.md`
- 9 скиллов:
  1. `sales-strategy.md` — стратегия продаж: ICP, каналы, воронка, структура отдела, KPI
  2. `lead-qualification.md` — квалификация: BANT/MEDDIC/CHAMP, scoring model, MQL/SQL
  3. `cold-outreach.md` — cold email последовательности (5-7 писем), cold call скрипты, персонализация 3 уровней
  4. `sales-scripts.md` — скрипты: discovery call, demo, обработка возражений (SPIN, Challenger, Sandler)
  5. `proposal-writing.md` — КП: структура winning proposal, адаптация по ACV, ROI
  6. `crm-optimization.md` — CRM: этапы воронки, поля, автоматизации, дашборды (HubSpot/Salesforce/Pipedrive/amoCRM)
  7. `negotiation.md` — переговоры: BATNA, ZOPA, работа со скидками, техники закрытия
  8. `customer-success.md` — post-sale: 30/60/90 onboarding, health score, удержание, expansion
  9. `sales-analytics.md` — метрики: pipeline coverage, win rate, velocity, forecast (3 метода)

### Модуль 5: OMA_HR ✅ ГОТОВ
- Router: `OMA_ROUTER_HR.md` (10 юнитов)
- Connections: `OMA_CONNECTIONS_HR.md`
- 10 скиллов:
  1. `job-description.md` — вакансии: структура, что привлекает кандидатов, отсеивающие факторы
  2. `resume-screening.md` — отбор: scoring matrix, red/green flags, воронка отбора
  3. `interview-kit.md` — собеседование: STAR-вопросы, scorecard, типы интервью
  4. `onboarding-plan.md` — адаптация: 30/60/90, чек-лист первого дня, buddy-система
  5. `job-instructions.md` — должностные инструкции и SOP
  6. `performance-review.md` — оценка: self-review, manager review, 360°, SBI feedback, PIP
  7. `compensation-benefits.md` — компенсации: зарплатные вилки, грейды, бенефиты, бонусы
  8. `hr-analytics.md` — метрики: turnover, time-to-hire, cost-per-hire, eNPS
  9. `corporate-culture.md` — культура: ценности, ритуалы, engagement-программы
  10. `offboarding.md` — увольнение: exit interview, knowledge transfer, alumni

### Модуль 6: OMA_SECRETARY 🔄 ЧАСТИЧНО ГОТОВ
- Router: `OMA_ROUTER_SECRETARY.md` (9 юнитов) ✅
- Connections: `OMA_CONNECTIONS_SECRETARY.md` ✅
- 6 из 9 скиллов готовы:
  1. `meeting-transcription.md` ✅
  2. `meeting-summary.md` ✅
  3. `calendar-management.md` ✅
  4. `email-triage.md` ✅
  5. `knowledge-base.md` ✅
  6. `task-coordination.md` ✅
- **НЕДОСТАЮЩИЕ (3 скилла):**
  7. `travel-logistics.md` — организация поездок: бронирование, маршруты, визы, отчёты о расходах
  8. `event-coordination.md` — организация мероприятий: конференции, митапы, вебинары, тимбилдинги
  9. `document-filing.md` — систематизация документов: архив, категоризация, retention policy, поиск

### Модуль 7: OMA_DOC_GEN ❌ НЕ НАЧАТ
- Нужно создать:
  - `OMA_ROUTER_DOC_GEN.md` — router с 9 юнитами (commercial-proposal, presentation-generator, contract-generator, act-generator, report-generator, memo-generator, table-generator, legal-basics, template-manager)
  - `OMA_CONNECTIONS_DOC_GEN.md` — карта связей
  - `skills/commercial-proposal.md` — коммерческие предложения: структура КП, расчёт стоимости, условия
  - `skills/presentation-generator.md` — презентации: структура слайдов, дизайн-принципы, storytelling
  - `skills/contract-generator.md` — договоры: типовые шаблоны (услуги, NDA, подряд), структура
  - `skills/act-generator.md` — акты: сдачи-приёма, выполненных работ, сверки
  - `skills/report-generator.md` — отчёты: ежемесячные, квартальные, годовые, по проектам
  - `skills/memo-generator.md` — служебные записки: внутренние, на согласование, на утверждение
  - `skills/table-generator.md` — таблицы: сметы, расчёты, сравнительные, данные
  - `skills/legal-basics.md` — правовые основы: типовые формулировки, существенные условия, риски
  - `skills/template-manager.md` — управление шаблонами: каталог, версионирование, кастомизация

## Структура каждого скилла (ОБЯЗАТЕЛЬНАЯ)

Каждый файл должен содержать минимум 300 строк и следующую структуру:

```
---
name: skill-name
description: Одно предложение — условия использования, не описание процесса.
---

# OMA SKILL · [НАЗВАНИЕ]
# Продукт: OMA (One Man Army)
# Версия: 2026-04-03

## КОМПЕТЕНЦИЯ
Кто ты и что делаешь (2-3 предложения) + ключевые возможности списком

## СТИЛЬ КОММУНИКАЦИИ
Тон + запрещённые фразы специфичные для юнита

## DOMAIN KNOWLEGE (5-6 тем с реальными данными)
1. **ТЕМА**: конкретные знания, формулы, benchmarks, research citations
2. ...

## ДИАЛОГ — ЭТАПНЫЙ ПРОТОКОЛ
Этап 0-6 с конкретными вопросами и объяснениями зачем каждый вопрос

## OUTPUT: ФИНАЛЬНЫЙ АРТЕФАКТ
Шаблон с конкретными полями

## АНТИ-ПАТТЕРНЫ — СПЕЦИФИЧЕСКИЕ
4-6 специфичных ошибок для этой профессии

## SELF-CHECK — СПЕЦИФИЧЕСКИЙ
Чек-лист перед выдачей результата
```

## Формат роутера (ОБЯЗАТЕЛЬНЫЙ)

```
---
name: OMA_ROUTER_[МОДУЛЬ]
description: Router [стека]. Маршрутизирует запросы на нужный юнит.
---

# Описание: роутер НЕ выполняет задачи, НЕ называет имена юнитов
# ТАБЛИЦА МАРШРУТИЗАЦИИ: задача → юнит
# СЕРЫЕ ЗОНЫ: уточняющий вопрос (ОДИН) с двумя вариантами → маршрутизация
# FALLBACK: уровни 1-2-3 (прямое/косвенное/неопределённость→Generic)
# ПРИВЕТСТВИЕ: одна строка
```

## Формат connections (ОБЯЗАТЕЛЬНЫЙ)

```
---
name: OMA_CONNECTIONS_[МОДУЛЬ]
description: Карта связей [стека].
---

# КАРТА СВЯЗЕЙ: [skill] → [действие для пользователя] → [целевой skill]
# КРОСС-МОДУЛЬНЫЕ СВЯЗИ: куда ведут следующие шаги в другие модули
# ТИПОВЫЕ ЦЕПОЧКИ: готовые сценарии
```

## Порядок работы

1. Дописать 3 недостающих скилла OMA_SECRETARY (travel-logistics, event-coordination, document-filing)
2. Создать OMA_DOC_GEN целиком (router + connections + 9 скиллов)
3. Сделать git commit + push с тем же токеном

## Качество

- Domain Knowledge — самая важная часть: реальные знания, а не поверхностные описания
- Диалог-протокол: этапы 0-6, конкретные вопросы с объяснениями зачем
- Output: шаблон с конкретными полями, который можно использовать сразу
- Anti-patterns: специфичные ошибки для каждой профессии
- Self-check: чек-лист перед выдачей
- Минимум 300 строк на файл

## Ссылки на эталонные файлы

- Router-эталон: `OMA_MARKETING/OMA_ROUTER_MARKETER.md` (6600 строк — самый подробный)
- Connections-эталон: `OMA_MARKETING/OMA_CONNECTIONS.md`
- Skill-эталон: `OMA_MARKETING/skills/OMA_Leva_copywriting.md` (311 строк, все секции)
- Skill-эталон (другой домен): `OMA_BIZ_ANALYTICS/skills/OMA_Aleksey_unit-economics.md` (298 строк)
- Template: `OMA_MARKETING/OMA_SKILL_TEMPLATE.md`
- Global Rules: `OMA_MARKETING/OMA_GLOBAL_RULES.md` (не дублировать в skill-файлах)
