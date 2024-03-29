# Описание

Сервис отправки уведомлений для пользователя.
На данный момент реализовано уведомление по SMTP.
Сервис реализован по принципу pipeline, прослойками между микро-сервисами которого служат очереди RabbitMQ. 

Ссылка на репозиторий: `https://github.com/likeinlife/notifications_sprint_1`

# Ссылка на репозиторий 

Ссылка на репозиторий: `https://github.com/likeinlife/notifications_sprint_1`

# Авторы

* [@likeinlife](https://github.com/likeinlife)
* [@maxim-zaitsev](https://github.com/maxim-zaitsev)
* [@yandexwork](https://github.com/yandexwork)

## Вклад @likeinlife

- Оформление репозитория
- Создание диаграм
- Конфигурирование переменных окружения
- Пайплайн сервиса нотификации: получение юзеров, отправка уведомлений
- Настройка RabbitMQ: dead-letter-queue, exchanges, queues

## Вклад @maxim-zaitsev

- Создание админ-панели
- Создание сервиса регулярных уведомлений
- Конфигурирование nginx

## Вклад @yandexwork

- Написание АПИ
- Написание тестов АПИ

# Запуск и остановка

## Запуск

1. `make env` - сконфигурирует один файл из environment
2. `make up` - запустить контейнеры
3. `make create-admin password=... email=...` - создать аккаунт администратора
4. `make create-user n=...` - создать тестовых пользователей, n-штук

## Остановка

- `make down` - остановить контейнеры, но не удалить volumes
- `make downv` - удалить и контейнеры, и volumes

# Тестирование

- `make test`

# URLs

1. admin panel: http://127.0.0.1/admin , login=admin, password=123qwe
2. notify-api: http://127.0.0.1/notify/api/openapi
2. openapi: http://127.0.0.1/auth/api/openapi
2. mail: http://127.0.0.1:8025

# Сервисы

![services](./diagrams/out/to_be.png)

# Пайплайн

![pipeline](./diagrams/out/notify_pipeline.png)