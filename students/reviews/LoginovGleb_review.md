







Тема курсовой: Сервис прогресса и трекинга обучения (прогресс «До сессии успею»).
Студента (ки): Логинов Глеб Олегович
Группы: АС-63
Оценка:  10(десять)

Архитектура и полнота требований: 15
Качество кода и типизация: 9 (TypeScript + Zod/Prisma использованы, но встречается неявный any/мелкие места без явных типов — немного снижено)
Клиент (UI/UX, маршрутизация, состояние): 12
Сервер (REST, безопасность, валидация): 10
Данные и миграции/сидинг: 3

Документация API (OpenAPI/Swagger): +8 (есть openapi.yaml и Swagger UI /api-docs)
Тестирование (unit/integration backend + E2E frontend): +15 (есть unit/integration в apps/server/tests и Playwright e2e в apps/web/tests/e2e)
Деплой в Kubernetes (манифесты, HPA, сервисы): +15 (есть k8s/ с deployment/service/hpa/configmap/namespace)
CI (GitHub Actions): +7 (есть ci.yml, описан pipeline lint→tests→build→push)
Наблюдаемость/оптимизация (структурированные логи, метрики, Redis): +5 (Pino, metrics.ts с prom-client, redis.ts)