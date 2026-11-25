# Music Store

![CI/CD Backend](https://github.com/papirosa1312/web_labs/actions/workflows/ci.yml/badge.svg)


# Запуск бекенду
```bash
cd backend
npm install
npm start
``` 

## API документація
* Специфікація OpenAPI: [docs/api/openapi.yaml](./docs/api/openapi.yaml)

![Swagger Editor](./docs/api/swagger_screenshot.png)

## Docker — Бекенд (Практична 6)
```bash
docker build -t music-store-api:1.0.0 ./backend
docker run --name music-api --rm -d -p 3000:3000 music-store-api:1.0.0
```
Порт: http://localhost:3000 (перевірка: http://localhost:3000/health)

Зупинка: `docker stop music-api`

## Docker — Перевірка та Фронтенд

### Перевірка встановлення
```bash
docker version
docker run hello-world
```

## CI/CD (Практична 7)

### Локальний запуск та тестування
cd backend
npm ci
npm test
npm start

### Пайплайн GitHub Actions
* Файл конфігурації: `.github/workflows/ci.yml`
* CI (`push` / `pull_request`): автоматичне встановлення Node.js 20 із кешуванням `npm`, чисте встановлення залежностей (`npm ci`) та запуск юніт-тестів (`npm test`).
* Delivery (Варіант B — Artifact): при пуші в main після успішних тестів збирається Docker-образ music-store-api:1.0.0, експортується у .tar через docker save та завантажується як артефакт music-store-api-image.
* Запуски та артефакти: вкладка Actions

## Observability (Практична 8)
* **Звіт (60 та 75 балів):** [docs/observability/report.md](./docs/observability/report.md)
* **JSON власного RED-дашборду:** [docs/observability/my-demo-red-dashboard.json](./docs/observability/my-demo-red-dashboard.json)

## Kubernetes: теоретична схема (Практична 9)
* **Опис та схема:** [docs/k8s-theory/description.md](./docs/k8s-theory/description.md)
* **Зображення схеми:** [docs/k8s-theory/k8s_architecture.png](./docs/k8s-theory/k8s_architecture.png)
