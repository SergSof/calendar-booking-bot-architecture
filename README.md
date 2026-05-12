# Calendar Booking Bot Architecture

Architecture design for a bot that allows guests to book meetings through an organizer's Google Calendar without exposing the organizer's calendar details.

## Task

The goal is to design the architecture of a meeting booking bot.

The system should cover:

- OAuth 2.0 authorization for the organizer
- Secure token storage and refresh flow
- Displaying free slots to guests without exposing private calendar events
- Booking a slot and creating an event in Google Calendar
- Protection from double booking
- Cancellation flow and notifications for both sides

## Deliverables

- Architecture document: `docs/architecture.md`
- Architecture diagram: `diagrams/architecture.md`
- Loom recording plan: `loom.md`
