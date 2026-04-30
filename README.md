# noterp-scanner

Фронт-часть сканера баркодов для Telegram-бота NotERP.

Открывается из бота как Telegram Web App — юзер наводит камеру на баркод, распознанное значение возвращается в бот через `WebApp.sendData(JSON)`.

## Структура

- `index.html` — единый файл со сканером (HTML + inline CSS + inline JS).
- `html5-qrcode` подключается с CDN (`jsdelivr`), Telegram WebApp SDK — с `telegram.org`.

## Поддерживаемые форматы

QR Code, EAN-13, EAN-8, Code 128, Code 39, UPC-A, UPC-E, ITF, Data Matrix.

## Поведение

1. При открытии — запрашивается доступ к камере (`facingMode: environment` — задняя).
2. После первого успешного распознавания — JSON с полями `{code, format, ts}` уходит в бот через `WebApp.sendData`, после чего Web App закрывается.
3. Кнопка «Отмена» закрывает Web App без отправки.

## Деплой

GitHub Pages из ветки `main` / папка корня. URL вида `https://it-romanov.github.io/noterp-scanner/`.

## Связь с проектом

Полный план трека и принятые архитектурные решения — в основном репо NotERP, файл `CLAUDE/scanner/PLAN.md`.
