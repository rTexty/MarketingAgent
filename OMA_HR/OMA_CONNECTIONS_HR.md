---
name: OMA_CONNECTIONS_HR
description: Карта связей HR-стека.
---

# OMA CONNECTIONS — HR
# Продукт: OMA (One Man Army)
# Версия: 2026-04-03

---

## КАРТА СВЯЗЕЙ

**job-description** → после вакансии:
- «Отобрать кандидатов по резюме» → **resume-screening**
- «Подготовить вопросы для собеседования» → **interview-kit**

**resume-screening** → после screening:
- «Провести собеседование» → **interview-kit**
- «Определить зарплатную вилку для позиции» → **compensation-benefits**

**interview-kit** → после собеседования:
- «Определить компенсацию для выбранного кандидата» → **compensation-benefits**
- «Составить план адаптации» → **onboarding-plan**

**onboarding-plan** → после адаптации:
- «Написать должностную инструкцию» → **job-instructions**
- «Провести первую оценку» → **performance-review**

**job-instructions** → после инструкции:
- «Провести оценку по инструкции» → **performance-review**

**performance-review** → после оценки:
- «Пересмотреть компенсацию» → **compensation-benefits**
- «Определить план развития» → **onboarding-plan** (re-onboarding)

**compensation-benefits** → после компенсации:
- «Посмотреть HR-метрики по удержанию» → **hr-analytics**

**hr-analytics** → после аналитики:
- «Улучшить корпоративную культуру на основе данных» → **corporate-culture**
- «Оптимизировать процессы найма» → **job-description**

**corporate-culture** → после культуры:
- «Встроить ценности в онбординг» → **onboarding-plan**
- «Встроить ценности в оценку» → **performance-review**

**offboarding** → после увольнения:
- «Обновить вакансию» → **job-description**
- «Проанализировать причины ухода» → **hr-analytics**

---

## ТИПОВЫЕ ЦЕПОЧКИ

**Наём нового сотрудника:**
job-description → resume-screening → interview-kit → compensation-benefits → onboarding-plan

**Цикл развития сотрудника:**
onboarding-plan → job-instructions → performance-review → compensation-benefits

**Снижение оттока:**
hr-analytics → corporate-culture → compensation-benefits → onboarding-plan

**Увольнение и замена:**
offboarding → hr-analytics → job-description
