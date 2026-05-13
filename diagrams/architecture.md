# Архитектурная схема

```text
Гость / Организатор
        |
        v
 Telegram Bot
        |
        v
 Backend / Bot Service
        |
        +-----------------------------+
        |                             |
        v                             v
 PostgreSQL                 Google Calendar API
        |                             |
        v                             v
 Данные системы:             Проверка занятости,
 пользователи,               создание и отмена событий
 организаторы,
 OAuth-токены,
 правила доступности,
 бронирования

Backend / Bot Service
        |
        v
 Notification Layer
        |
        v
 Telegram Bot

Защита от двойного бронирования:
PostgreSQL transaction + UNIQUE constraint
