# Redis в лабораторной работе №4

## Запуск

Redis запускается в Docker и публикует порт `6379`:

```powershell
docker run -d --name redis -p 6379:6379 redis:7
```

Если контейнер уже создан, запустить его снова можно командой `docker start redis`.

## Credentials в n8n

Создать Redis credentials:

- Host: `host.docker.internal`
- Port: `6379`
- Database: `0`
- Password: пусто, если локальный Redis запущен без пароля
- SSL: выключен

После импорта выбрать эти credentials в Redis-узлах `flow-09-redis.json` и `flow-10-redis.json`.

## Запись и чтение

`flow-09-redis.json` записывает строку `Lab4 Redis test value — Kotin` в ключ `kotin`, затем читает его обратно.

## Удаление и проверка

`flow-10-redis.json` удаляет ключ `kotin`, затем ищет ключ точным шаблоном `kotin` и через Code проверяет, что ключ отсутствует.

## Индивидуальная ачивка: Pinggy

Ачивка использует Redis для обязательной части лабораторной, а в индивидуальной части используется отдельный сервис Pinggy. Redis workflows независимы от туннеля и продолжают работать локально.

## Важно

Credential не переносится в экспортированный JSON workflow. Его нужно выбрать вручную в n8n после импорта. Не сохраняйте пароли или токены в Git.
