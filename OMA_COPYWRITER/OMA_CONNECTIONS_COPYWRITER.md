---
name: OMA_CONNECTIONS_COPYWRITER
description: Карта логических связей между юнитами копирайтерского стека. Платформа сопоставляет действия из блока ▶ СЛЕДУЮЩИЙ ШАГ с этой картой.
---

# OMA CONNECTIONS — КОПИРАЙТЕРСКИЙ СТЕК
# Продукт: OMA (One Man Army)
# Версия: 2026-04-03

---

## КАРТА СВЯЗЕЙ

### ВНУТРЕННИЕ СВЯЗИ КОПИРАЙТИНГА

**copywriting-core** → после текста страницы логично:
- «Отредактировать и убрать лишнее» → **copy-editing**
- «Написать рекламные объявления на основе текста» → **ad-copywriting**
- «Выстроить email-цепочку для посетителей этой страницы» → **email-copywriting**
- «Адаптировать текст для соцсетей» → **social-copywriting**
- «Проверить конверсию страницы» → **page-cro** (OMA_MARKETING)

**copy-editing** → после редактуры логично:
- «Адаптировать текст для соцсетей» → **social-copywriting**
- «Написать рекламные тексты на основе отредактированного» → **ad-copywriting**
- «Проверить конверсию текста на странице» → **page-cro** (OMA_MARKETING)

**email-copywriting** → после email-цепочки логично:
- «Написать текст страницы куда ведут письма» → **copywriting-core**
- «Настроить отслеживание открытий и кликов» → **analytics-tracking** (OMA_MARKETING)
- «Улучшить онбординг на основе email-сценариев» → **onboarding-cro** (OMA_MARKETING)

**ad-copywriting** → после рекламных текстов логично:
- «Запустить рекламные кампании с этими текстами» → **paid-ads** (OMA_MARKETING)
- «Проверить страницу куда ведёт реклама» → **page-cro** (OMA_MARKETING)
- «Адаптировать тексты для соцсетей» → **social-copywriting**

**social-copywriting** → после постов логично:
- «Выстроить контент-стратегию на длинную дистанцию» → **content-strategy** (OMA_MARKETING)
- «Записать короткие видео под этот контент» → **reels_producer** (OMA_MARKETING)
- «Написать рекламные креативы для продвижения постов» → **ad-copywriting**

**sales-copywriting** → после продающего текста логично:
- «Отредактировать и заострить» → **copy-editing**
- «Адаптировать текст под email-рассылку» → **email-copywriting**
- «Проверить конверсию страницы с этим текстом» → **page-cro** (OMA_MARKETING)

**brand-voice** → после определения голоса логично:
- «Написать тексты сайта в этом голосе» → **copywriting-core**
- «Написать email-письма в этом голосе» → **email-copywriting**
- «Адаптировать голос для соцсетей» → **social-copywriting**

**landing-page-anatomy** → после структуры лендинга логично:
- «Написать тексты для каждой секции» → **copywriting-core**
- «Проверить конверсию собранного лендинга» → **page-cro** (OMA_MARKETING)
- «Добавить SEO-оптимизацию» → **seo-audit** (OMA_MARKETING)

---

### КРОСС-МОДУЛЬНЫЕ СВЯЗИ

**Из OMA_COPYWRITER → OMA_MARKETING:**
- Текст написан → проверить конверсию → **page-cro**
- Email-цепочка готова → настроить аналитику → **analytics-tracking**
- Рекламные тексты → запустить кампании → **paid-ads**
- Контент для соцсетей → выстроить стратегию → **content-strategy**

**Из OMA_COPYWRITER → OMA_SALES:**
- Sales letter готов → выстроить скрипт продаж → **sales-scripts**
- Питч написан → подготовить коммерческое предложение → **proposal-writing**

**Из OMA_COPYWRITER → OMA_DOC_GEN:**
- Текст для КП → сгенерировать документ → **commercial-proposal**
- Структура презентации → сгенерировать презентацию → **presentation-generator**

---

## ТИПОВЫЕ ЦЕПОЧКИ

**Запуск нового лендинга:**
brand-voice → landing-page-anatomy → copywriting-core → copy-editing → ad-copywriting

**Email-маркетинг с нуля:**
brand-voice → email-copywriting → copywriting-core (страница) → analytics-tracking

**Рекламная кампания:**
brand-voice → ad-copywriting → copywriting-core (landing) → paid-ads

**Продающая страница:**
landing-page-anatomy → copywriting-core → copy-editing → sales-copywriting → page-cro
