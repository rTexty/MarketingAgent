---
name: OMA_CONNECTIONS_DOC_GEN
description: Карта связей между юнитами генерации документов.
---

# OMA CONNECTIONS — ГЕНЕРАТОР ДОКУМЕНТОВ
# Продукт: OMA (One Man Army)
# Версия: 02.04.2026

---

## КАРТА СВЯЗЕЙ

**commercial-proposal** → после КП логично:
- «Создать презентацию на основе КП» → **presentation-generator**
- «Подготовить договор на основе КП» → **contract-generator**
- «Создать таблицу сравнения с конкурентами» → **table-generator**

**presentation-generator** → после презентации логично:
- «Написать КП на основе презентации» → **commercial-proposal**
- «Создать отчёт по материалам презентации» → **report-generator**

**contract-generator** → после договора логично:
- «Составить акт выполненных работ» → **act-generator**
- «Проверить юридические аспекты» → **legal-basics**
- «Сохранить как шаблон» → **template-manager**

**act-generator** → после акта логично:
- «Составить отчёт по проекту» → **report-generator**
- «Создать шаблон акта» → **template-manager**

**report-generator** → после отчёта логично:
- «Создать презентацию по итогам» → **presentation-generator**
- «Написать служебную записку по результатам» → **memo-generator**
- «Внести данные в таблицу» → **table-generator**

**memo-generator** → после memo логично:
- «Создать отчёт на основе memo» → **report-generator**
- «Сохранить как шаблон» → **template-manager**

**table-generator** → после таблицы логично:
- «Создать отчёт на основе данных» → **report-generator**
- «Включить в презентацию» → **presentation-generator**

**legal-basics** → после правовой информации логично:
- «Составить договор с учётом рекомендаций» → **contract-generator**
- «Проверить шаблоны на compliance» → **template-manager**

**template-manager** → после шаблонов логично:
- «Создать документ по шаблону» → [соответствующий юнит]
- «Проверить шаблоны на юридическую корректность» → **legal-basics**

---

## ТИПОВЫЕ ЦЕПОЧКИ

**Продажа клиенту:**
commercial-proposal → presentation-generator → contract-generator → act-generator

**Внутренняя отчётность:**
table-generator → report-generator → memo-generator

**Юридический процесс:**
legal-basics → contract-generator → act-generator → template-manager

**Подготовка к встрече:**
report-generator → presentation-generator → commercial-proposal
