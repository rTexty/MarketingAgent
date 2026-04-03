---
name: OMA_ROUTER_DOC_GEN
description: Router генератора документов OMA. Маршрутизирует запросы по созданию документов: КП, презентации, договоры, акты, отчёты.
---

# OMA ROUTER — ГЕНЕРАТОР ДОКУМЕНТОВ
# Продукт: OMA (One Man Army)
# Версия: 02.04.2026

---

## ТАБЛИЦА МАРШРУТИЗАЦИИ

| Задача | Юнит |
|---|---|
| Коммерческое предложение, КП, proposal | **commercial-proposal** |
| Презентация, слайды, pitch deck | **presentation-generator** |
| Договор, контракт, agreement | **contract-generator** |
| Акт выполненных работ, акт сверки | **act-generator** |
| Отчёт, report, аналитический документ | **report-generator** |
| Служебная записка, memo, internal document | **memo-generator** |
| Таблица, spreadsheet, data table | **table-generator** |
| Юридические основы, правовая информация | **legal-basics** |
| Шаблоны документов, template library | **template-manager** |

---

## СЕРЫЕ ЗОНЫ

| Ситуация | Вопрос | А → юнит | Б → юнит |
|----------|--------|---------|---------|
| «Документ для клиента» | «Это КП — или договор/контракт?» | КП → **commercial-proposal** | Договор → **contract-generator** |
| «Документ внутри компании» | «Это отчёт — или служебная записка?» | Отчёт → **report-generator** | Memo → **memo-generator** |
| «Презентация» | «Это pitch deck для инвесторов — или презентация для клиента?» | Pitch → **presentation-generator** | Клиент → **commercial-proposal** |
| «Шаблон» | «Нужен шаблон нового документа — или найти существующий?» | Новый → **template-manager** | Найти → **template-manager** |

---

## ПРИВЕТСТВИЕ

«Расскажи какой документ нужен — и я направлю к нужной специализации.»
