---
name: OMA_CONNECTIONS_SECRETARY
description: Карта связей секретарского стека.
---

# OMA CONNECTIONS — СЕКРЕТАРЬ
# Продукт: OMA (One Man Army)
# Версия: 2026-04-03

---

## КАРТА СВЯЗЕЙ

**meeting-transcription** → после расшифровки:
- «Сделать саммари из расшифровки» → **meeting-summary**
- «Сохранить в базу знаний» → **knowledge-base**

**meeting-summary** → после саммари:
- «Распределить задачи по участникам» → **task-coordination**
- «Поставить следующую встречу» → **calendar-management**
- «Сохранить в базу знаний» → **knowledge-base**

**calendar-management** → после планирования:
- «Подготовить повестку встречи» → **meeting-summary** (pre-meeting)
- «Забронировать логистику» → **travel-logistics**

**email-triage** → после разбора почты:
- «Распределить задачи из писем» → **task-coordination**
- «Поставить встречу из письма» → **calendar-management**

**knowledge-base** → после наполнения:
- «Найти нужную информацию» — поиск по базе
- «Обновить документы» → **document-filing**

**task-coordination** → после распределения:
- «Проконтролировать дедлайны» — мониторинг
- «Поставить встречу по статусу» → **calendar-management**

**travel-logistics** → после бронирования:
- «Сохранить детали поездки» → **knowledge-base**
- «Синхронизировать с календарём» → **calendar-management**

**event-coordination** → после организации:
- «Разослать приглашения» → **calendar-management**
- «Сохранить материалы» → **document-filing**

**document-filing** → после систематизации:
- «Найти нужный документ» — поиск

---

## ТИПОВЫЕ ЦЕПОЧКИ

**Рабочий день:**
email-triage → task-coordination → calendar-management → meeting-transcription → meeting-summary

**Организация встречи:**
calendar-management → meeting-transcription → meeting-summary → task-coordination

**Подготовка к поездке:**
travel-logistics → calendar-management → document-filing
