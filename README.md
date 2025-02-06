![CI/CD](https://github.com/Waynejey/kittygram_final/actions/workflows/main.yml/badge.svg)

# Kittygram Backend

## Описание проекта

Kittygram - это веб-приложение для любителей кошек, позволяющее загружать и просматривать фотографии питомцев.

Проект реализован на Django и предоставляет API для фронтенда, аутентификации пользователей и управления контентом.


## Стек технологий

- **Backend**: Python 3, Django, Django Rest Framework (DRF)
- **Аутентификация**: Djoser
- **База данных**: PostgreSQL / SQLite (для локального тестирования)
- **Контейнеризация**: Docker, Docker Compose
- **Веб-сервер**: Nginx
- **CI/CD**: GitHub Actions

## Развертывание проекта

```bash
# Клонируем репозиторий
git clone https://github.com/Waynejey/kittygram_final.git
```

### Запуск через Docker

```bash
# Запускаем контейнеры
docker compose -f docker-compose.production.yml up -d
docker compose -f docker-compose.production.yml exec backend python manage.py migrate
docker compose -f docker-compose.production.yml exec backend python manage.py collectstatic
docker compose -f docker-compose.production.yml exec backend cp -r /app/collected_static/. /static/static/
```

## Переменные окружения `.env`

Пример файла `.env`:

```ini
SECRET_KEY=your_secret_key
DEBUG=False
ALLOWED_HOSTS=yourdomain.com,localhost,127.0.0.1

# Настройки базы данных
POSTGRES_USER=django_user
POSTGRES_PASSWORD=mysecretpassword
POSTGRES_DB=django
DB_HOST=db
DB_PORT=5432
```

## Автор

**Waynejey** - разработчик проекта.
