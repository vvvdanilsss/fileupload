# File Upload with Django, Celery, and Docker

## Описание

Этот проект представляет собой REST API, созданный с использованием Django и Django REST Framework. Он позволяет загружать файлы на сервер и обрабатывать их асинхронно с помощью Celery.

## Сразу полезные ссылки

### Видео демонстрация работы приложения

[![Видео на YouTube](http://img.youtube.com/vi/Fz5GE3ITuBg/0.jpg)](http://www.youtube.com/watch?v=Fz5GE3ITuBg)

### Django CI/CD Pipeline

[Release #21](https://github.com/vvvdanilsss/fileupload/actions/runs/6408731917/job/17398380153)

## Особенности

- REST API для загрузки и списка файлов.
- Асинхронная обработка файлов с использованием Celery.
- Модель для хранения метаданных файлов.
- Docker-контейнеризация для удобства развертывания.
- Обработка различных типов файлов.
- Покрытие кода тестами.

## Технологии

- Python
- Django
- Django REST Framework
- Celery
- Docker
- PostgreSQL
- Redis

## Установка

### Зависимости

- Docker
- Docker Compose

### Предварительные шаги

- Убедитесь, что программа Docker Desktop запущена на вашем компьютере.

### Инструкции

1. Клонировать репозиторий:

   ```bash
   git clone https://github.com/vvvdanilsss/fileupload.git

   ```

2. Собрать и запустить Docker-контейнеры:

   ```bash
   docker-compose up --build
   
   ```

   **Примечание:** После сборки откройте новый терминальный окно и примените миграции:

   ```bash
   docker-compose run web python manage.py makemigrations
   docker-compose run web python manage.py migrate   
   ```

   Для запуска тестов используйте:
   
   ```bash
   docker-compose run web pytest myapp/tests/test.py
   
   ```

## Использование

- Откройте веб-браузер и перейдите по адресу `http://localhost:8000/`
- Загрузите файлы, используя интерфейс загрузки
- Просмотрите список загруженных файлов, нажав "Load Files"

## Автор

Данила Власов

- [Telegram](https://t.me/vdanilas_work)
- [GitHub](https://github.com/vvvdanilsss)

---

### Ответы на вопросы из ТЗ:

#### Как изменится архитектура при большой нагрузке?

- Можно ввести балансировщик нагрузки для распределения трафика между несколькими экземплярами приложения.
- Оптимизация запросов к базе данных и кеширование.

#### Какую нагрузку в RPS сможет выдержать ваш сервис?

Это зависит от множества факторов, включая характеристики сервера, оптимизацию кода и т.д. Для точной оценки необходимо провести нагрузочное тестирование.
