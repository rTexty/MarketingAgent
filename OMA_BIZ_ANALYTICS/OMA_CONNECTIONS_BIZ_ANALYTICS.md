---
name: OMA_CONNECTIONS_BIZ_ANALYTICS
description: Карта логических связей между юнитами бизнес-аналитики. Используется платформой для маршрутизации после выбора пользователем следующего шага.
---

# OMA CONNECTIONS — БИЗНЕС-АНАЛИТИКА
# Продукт: OMA (One Man Army)
# Версия: 02.04.2026

---

## КАК ИСПОЛЬЗОВАТЬ ЭТОТ ДОКУМЕНТ

Агент в блоке ▶ СЛЕДУЮЩИЙ ШАГ предлагает действие (глагол + результат).
Платформа сопоставляет это действие с картой ниже и маршрутизирует на нужный юнит.
Пользователь видит только действие — не имя юнита, не технику маршрутизации.

Формат карты:
[skill] → после него логично → [действие для пользователя] → [целевой skill]

---

## КАРТА СВЯЗЕЙ

---

### ЮНИТ-ЭКОНОМИКА

**unit-economics** → после расчёта юнит-экономики логично:
- «Проверить ROI по каждому каналу отдельно» → **channel-roi**
- «Посмотреть как LTV меняется по когортам» → **cohort-analysis**
- «Спрогнозировать выручку на основе текущих метрик» → **revenue-analytics**
- «Сравнить наши показатели с рынком» → **competitive-benchmarking**

---

### ROI И ЭФФЕКТИВНОСТЬ КАНАЛОВ

**channel-roi** → после расчёта ROI логично:
- «Посчитать полную юнит-экономику с учётом лучших каналов» → **unit-economics**
- «Посмотреть retention по когортам из каждого канала» → **cohort-analysis**
- «Оценить потенциал роста через лучший канал» → **market-sizing**
- «Спрогнозировать выручку на основе лучших каналов» → **revenue-analytics**

---

### ВЫРУЧКА И МОНЕТИЗАЦИЯ

**revenue-analytics** → после анализа выручки логично:
- «Разобраться почему выручка падает — когорты или каналы?» → **cohort-analysis** или **channel-roi**
- «Посчитать юнит-экономику на основе текущих данных» → **unit-economics**
- «Спрогнозировать размер рынка и наш потенциал» → **market-sizing**
- «Сравнить наши метрики с рынком» → **competitive-benchmarking**

---

### КОГОРТНЫЙ АНАЛИЗ

**cohort-analysis** → после когортного анализа логично:
- «Посчитать LTV и юнит-экономику по лучшим когортам» → **unit-economics**
- «Определить через какой канал приходят лучшие когорты» → **channel-roi**
- «Посмотреть динамику выручки по когортам» → **revenue-analytics**
- «Сравнить наши retention-показатели с рынком» → **competitive-benchmarking**

---

### РАЗМЕР РЫНКА

**market-sizing** → после оценки рынка логично:
- «Посчитать какую долю рынка мы можем занять» → **competitive-benchmarking**
- «Спрогнозировать выручку при захвате N% рынка» → **revenue-analytics**
- «Посчитать юнит-экономику под этот рынок» → **unit-economics**
- «Оценить ROI каналов для захвата рынка» → **channel-roi**

---

### КОНКУРЕНТНЫЙ АНАЛИЗ

**competitive-benchmarking** → после бенчмарков логично:
- «Посчитать нашу юнит-экономику относительно рынка» → **unit-economics**
- «Определить размер рынка и нашу потенциальную долю» → **market-sizing**
- «Посчитать ROI каналов относительно бенчмарков» → **channel-roi**
- «Посмотреть динамику выручки на фоне рынка» → **revenue-analytics**

---

### ФИНАНСОВАЯ МОДЕЛЬ

**financial-model** → после финмодели логично:
- «Разобрать откуда берётся рост (new/expansion/churn)» → **growth-accounting**
- «Посчитать юнит-экономику: насколько каждый клиент окупается» → **unit-economics**
- «Построить KPI-систему на основе финмодели» → **kpi-dashboard**
- «Посмотреть выручку в динамике и спрогнозировать» → **revenue-analytics**

---

### GROWTH ACCOUNTING

**growth-accounting** → после декомпозиции роста логично:
- «Построить финансовую модель с учётом найденных тормозов» → **financial-model**
- «Посчитать юнит-экономику: зависит ли рост от CAC» → **unit-economics**
- «Посмотреть retention по когортам: почему churn растёт» → **cohort-analysis**
- «Разобрать воронку: где теряем людей до активации» → **funnel-metrics**

---

### KPI-ДАШБОРД

**kpi-dashboard** → после проектирования KPI логично:
- «Построить финансовую модель для executive-level KPI» → **financial-model**
- «Разобрать декомпозицию роста — главный KPI-блок» → **growth-accounting**
- «Проанализировать воронку конверсии — operational-level KPI» → **funnel-metrics**
- «Посчитать юнит-экономику — KPI-блок юнитов» → **unit-economics**

---

### ВОРОНКА КОНВЕРСИИ

**funnel-metrics** → после анализа воронки логично:
- «Посчитать юнит-экономику с учётом потерь в воронке» → **unit-economics**
- «Посмотреть retention: удерживает ли продукт тех, кто прошёл воронку» → **cohort-analysis**
- «Построить KPI-дашборд с метриками воронки» → **kpi-dashboard**
- «Разобрать рост: влияет ли воронка на new MRR» → **growth-accounting**

---

## ТИПОВЫЕ ЦЕПОЧКИ РАБОТЫ

**Диагностика бизнеса с нуля:**
unit-economics → channel-roi → cohort-analysis → revenue-analytics

**Оценка нового рынка:**
market-sizing → competitive-benchmarking → unit-economics → revenue-analytics

**Оптимизация существующего бизнеса:**
revenue-analytics → cohort-analysis → channel-roi → unit-economics

**Подготовка к инвестициям:**
unit-economics → revenue-analytics → market-sizing → competitive-benchmarking

**Анализ падения выручки:**
revenue-analytics → cohort-analysis → channel-roi → unit-economics

**Полная финансовая картина:**
financial-model → growth-accounting → unit-economics → kpi-dashboard

**Диагностика конверсии:**
funnel-metrics → cohort-analysis → unit-economics → growth-accounting

**Система управления метриками:**
kpi-dashboard → financial-model → growth-accounting → funnel-metrics
