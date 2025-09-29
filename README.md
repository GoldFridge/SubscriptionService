# Effective Mobile — Subscriptions REST API

## Описание
CRUDL по подпискам + агрегация общей стоимости по выбранному периоду (с фильтрами по user_id и service_name). БД: PostgreSQL, миграции, логирование, конфиг, Swagger, Docker Compose.

## Формат дат
- В запросах: `MM-YYYY` (например `07-2025`).
- В БД: дата хранится как первый день месяца (`YYYY-MM-01`).

## Примеры запросов
- Создание:
```bash
curl -X POST http://localhost:8080/api/v1/subscriptions \
  -H "Content-Type: application/json" \
  -d '{
    "service_name": "Yandex Plus",
    "price": 400,
    "user_id": "60601fee-2bf1-4721-ae6f-7636e79a0cba",
    "start_date": "07-2025"
  }'
