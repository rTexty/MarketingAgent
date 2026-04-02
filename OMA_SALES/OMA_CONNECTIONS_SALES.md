---
name: OMA_CONNECTIONS_SALES
description: Карта логических связей между юнитами продажного стека.
---

# OMA CONNECTIONS — ПРОДАЖИ
# Продукт: OMA (One Man Army)
# Версия: 2026-04-03

---

## КАРТА СВЯЗЕЙ

**sales-strategy** → после стратегии:
- «Написать скрипты для команды» → **sales-scripts**
- «Настроить CRM под стратегию» → **crm-optimization**
- «Запустить cold outreach» → **cold-outreach**
- «Определить систему квалификации лидов» → **lead-qualification**

**lead-qualification** → после квалификации:
- «Написать скрипты discovery» → **sales-scripts**
- «Настроить скоринг в CRM» → **crm-optimization**
- «Запустить outreach к квалифицированным лидам» → **cold-outreach**

**cold-outreach** → после outreach-последовательности:
- «Подготовить скрипт для звонка после письма» → **sales-scripts**
- «Написать КП для ответивших» → **proposal-writing**
- «Настроить отслеживание в CRM» → **crm-optimization**

**sales-scripts** → после скриптов:
- «Подготовить КП после discovery» → **proposal-writing**
- «Отработать технику переговоров» → **negotiation**
- «Настроить этапы в CRM» → **crm-optimization**

**proposal-writing** → после КП:
- «Подготовиться к переговорам по КП» → **negotiation**
- «Отследить результат в CRM» → **crm-optimization**

**crm-optimization** → после настройки CRM:
- «Посмотреть метрики и прогноз» → **sales-analytics**
- «Настроить скоринг лидов» → **lead-qualification**

**negotiation** → после переговоров:
- «Выстроить customer success после закрытия» → **customer-success**
- «Проанализировать что сработало/нет» → **sales-analytics**

**customer-success** → после customer success:
- «Настроить отслеживание здоровья клиентов» → **crm-optimization**
- «Спрогнозировать расширение выручки» → **sales-analytics**

**sales-analytics** → после аналитики:
- «Скорректировать стратегию на основе данных» → **sales-strategy**
- «Оптимизировать воронку в CRM» → **crm-optimization**

---

## КРОСС-МОДУЛЬНЫЕ СВЯЗИ

**Из OMA_SALES → OMA_COPYWRITER:**
- Написать тексты для outreach → **email-copywriting** / **ad-copywriting**
- Написать sales page → **sales-copywriting**

**Из OMA_SALES → OMA_MARKETING:**
- Настроить лидогенерацию → **paid-ads** / **content-strategy**
- Проверить конверсию посадочной → **page-cro**

**Из OMA_SALES → OMA_DOC_GEN:**
- Сгенерировать КП как документ → **commercial-proposal**
- Сгенерировать договор → **contract-generator**

---

## ТИПОВЫЕ ЦЕПОЧКИ

**Запуск продаж B2B:**
sales-strategy → lead-qualification → cold-outreach → sales-scripts → proposal-writing → negotiation

**Оптимизация существующего отдела:**
sales-analytics → crm-optimization → sales-scripts → customer-success

**Увеличение конверсии:**
lead-qualification → sales-scripts → negotiation → sales-analytics
