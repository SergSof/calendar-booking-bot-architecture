# Архитектурная схема
```mermaid
  info
```
```mermaid
graph TD;
    A-->B;
    A-->C;
    B-->D;
    C-->D;
```

```mermaid
graph TD
    USER["Гость / Организатор"] --> TG["Telegram Bot"]

    TG --> BACKEND["Backend / Bot Service"]

    BACKEND --> DB["PostgreSQL"]
    BACKEND --> GOOGLE["Google Calendar API"]
    BACKEND --> NOTIFY["Notification Layer"]

    NOTIFY --> TG

    DB --> USERS["Пользователи"]
    DB --> ORG["Организаторы"]
    DB --> TOKENS["OAuth токены"]
    DB --> RULES["Правила доступности"]
    DB --> BOOKINGS["Бронирования"]

    GOOGLE --> BUSY["Проверка занятости"]
    GOOGLE --> EVENTS["Создание и отмена событий"]

    BACKEND --> LOCKS["Транзакции и уникальные ограничения"]
    LOCKS --> BOOKINGS
```

## Пояснение

- **Telegram Bot** — интерфейс для организатора и гостя.
- **Backend / Bot Service** — основная бизнес-логика: OAuth, генерация слотов, бронирование и отмена.
- **PostgreSQL** — хранение пользователей, правил доступности, токенов и бронирований.
- **Google Calendar API** — проверка занятости календаря, создание и отмена событий.
- **Notification Layer** — отправка подтверждений и уведомлений через Telegram.
- **Транзакции и уникальные ограничения** — защита от двойного бронирования.
