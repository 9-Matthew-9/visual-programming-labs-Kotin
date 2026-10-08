Лабораторная работа №2 — Node-RED

1. Цель работы

Познакомиться с Node-RED и научиться собирать простые программы из готовых узлов.

2. Как я установил Node-RED

Node-RED запускался в Docker.

Адрес Node-RED:

http://localhost:1880

Версии:

Node-RED: 5.0.7

Node.js: v24.20.0

Данные контейнера сохраняются в папке lab2/nodered_data.

3. Что я сделал

Я собрал 12 потоков:

Inject → Debug — отправка и просмотр сообщения.

Function — обработка данных с помощью JavaScript.

Switch — разделение сообщений по условию.

Change — изменение полей сообщения.

Template — создание текста из данных.

HTTP Request — получение данных из внешнего API.

MQTT — отправка и получение сообщений через брокер.

HTTP GET — сделал свои API: /api/text, /api/info, /api/items.

Dashboard — сделал датчик температуры с Gauge и Chart.

Telegram — сделал /start, /help и echo.

Files — запись и чтение JSON-файла.

Context — сделал счётчик с сохранением значения.

4. Дополнительная ачивка

Я подключил OpenAPI/Swagger к API из Flow 08.

В Swagger UI видны мои GET-запросы, и их можно выполнить прямо из интерфейса.

Проверил:

/api/text → 200
/api/items?id=1 → 200
/api/items?id=999 → 404

5. Git

Все основные файлы работы сохранены в GitHub:

JSON-файлы потоков;

api.md;

report.md;

скриншоты.

Изменения отправлялись командами:

git add lab2
git commit -m "Complete lab 2"
git push

6. Что я понял

Я понял принцип работы Node-RED: один узел создаёт или получает сообщение, следующий его обрабатывает, а результат передаётся дальше по соединению.

Также разобрался с msg.payload, msg.topic, Function, HTTP, MQTT, Dashboard, Telegram, файлами и Context.

В дополнительной части я научился документировать API через Swagger и проверять запросы через Swagger UI.