# Документация API — каталог гаджетов

## Назначение

В лабораторной работе я подключил тестовый API JSONing к Bubble через API Connector. API используется для получения списка гаджетов, создания, изменения и удаления записей.

**Адрес ресурса:**

`https://api.jsoning.com/mock/t3taiio8z1/gadgets`

## 1. GET — получение списка

**Метод:** `GET`

**URL:**

`https://api.jsoning.com/mock/t3taiio8z1/gadgets`

Возвращает список гаджетов.

Пример ответа:

```json
[
  {
    "id": "1",
    "name": "Pixel 9",
    "category": "Смартфоны",
    "price": 1200
  },
  {
    "id": "2",
    "name": "Galaxy S25",
    "category": "Смартфоны",
    "price": 1000
  },
  {
    "id": "3",
    "name": "Sony WH-1000XM5",
    "category": "Наушники",
    "price": 350
  }
]
```

## 2. POST — создание гаджета

**Метод:** `POST`

**URL:**

`https://api.jsoning.com/mock/t3taiio8z1/gadgets`

**Заголовок:**

`Content-Type: application/json`

Пример тела запроса:

```json
{
  "id": "4",
  "name": "Test Gadget",
  "category": "Наушники",
  "price": 150
}
```

Запрос передаёт данные нового гаджета во внешний API.

## 3. PUT — изменение гаджета

**Метод:** `PUT`

**Пример URL:**

`https://api.jsoning.com/mock/t3taiio8z1/gadgets/4`

**Заголовок:**

`Content-Type: application/json`

Пример тела запроса:

```json
{
  "name": "Test Gadget Updated",
  "category": "Наушники",
  "price": 175
}
```

Идентификатор гаджета передаётся в URL. Тело запроса содержит изменяемые данные.

## 4. DELETE — удаление гаджета

**Метод:** `DELETE`

**Пример URL:**

`https://api.jsoning.com/mock/t3taiio8z1/gadgets/4`

Тело запроса не требуется. Удаляемый гаджет определяется по ID в URL.

## Использование в Bubble

В API Connector настроены четыре вызова:

| Вызов | Метод | Назначение |
|---|---|---|
| Get Gadgets | GET | Получение списка |
| Create Gadget | POST | Создание записи |
| Update Gadget | PUT | Изменение записи |
| Delete Gadget | DELETE | Удаление записи |

GET используется для получения данных, а остальные вызовы выполняются через workflows приложения.

## Ограничение

JSONing — тестовый сервис. Пользовательские mock API могут удаляться ежедневно. Перед демонстрацией преподавателю нужно проверить, что созданный адрес продолжает работать.