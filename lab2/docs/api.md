# API лабораторной работы №2

## GET /api/text

Возвращает простой текст.

Пример запроса:

GET http://localhost:1880/api/text

Пример ответа:

Hello from Node-RED, Kotin!

HTTP-код: 200

---

## GET /api/info

Возвращает информацию о студенте и лабораторной работе.

Пример запроса:

GET http://localhost:1880/api/info

Пример ответа:

{
  "student": "Kotin",
  "lab": 2
}

HTTP-код: 200

---

## GET /api/items

Возвращает элемент по идентификатору.

Параметр:

id — целочисленный идентификатор элемента.

Пример успешного запроса:

GET http://localhost:1880/api/items?id=1

Пример ответа:

{
  "id": 1,
  "name": "Burger"
}

HTTP-код: 200

Пример запроса с ошибкой:

GET http://localhost:1880/api/items?id=999

Пример ответа:

{
  "error": "Item not found",
  "id": 999
}

HTTP-код: 404