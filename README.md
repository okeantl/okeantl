# Привет, я Валерий 

Python backend-разработчик. Пишу асинхронные API на FastAPI и люблю задачи про
конкурентность: чтобы одно место нельзя было продать дважды, а повторное
сообщение из очереди не списало деньги второй раз.

-  Сейчас делаю **Slotly** — сервис записи к мастерам
-  Изучаю AI-агентов: tool calling, RAG, MCP
-  Открыт к работе и заказам на Telegram-ботов и backend

##  Стек

![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat&logo=fastapi&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat&logo=postgresql&logoColor=white)
![SQLAlchemy](https://img.shields.io/badge/SQLAlchemy-D71F00?style=flat&logo=sqlalchemy&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-DC382D?style=flat&logo=redis&logoColor=white)
![RabbitMQ](https://img.shields.io/badge/RabbitMQ-FF6600?style=flat&logo=rabbitmq&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat&logo=docker&logoColor=white)
![Pytest](https://img.shields.io/badge/Pytest-0A9EDC?style=flat&logo=pytest&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=flat&logo=githubactions&logoColor=white)

##  Проекты

### [TicketFlow](https://github.com/okeantl/TicketFlow) — бронирование билетов
FastAPI · PostgreSQL · Redis · RabbitMQ · Docker Compose · testcontainers

- Бронь места на 5 минут через атомарный `SET NX EX` в Redis: из одновременных запросов место получает только один
- `SELECT ... FOR UPDATE` с сортировкой id мест — без двойных заказов и без deadlock
- Воркер оплаты идемпотентен: RabbitMQ доставляет at-least-once, повтор не спишет деньги дважды
- Ретраи через `x-retry-count`, битые сообщения уходят в DLQ
- CI на GitHub Actions: ruff, mypy, pytest на настоящих Postgres и Redis

### [Slotly](https://github.com/okeantl/slotly) — запись к мастерам (в разработке)
FastAPI · SQLAlchemy 2 (async) · Alembic · PostgreSQL · Docker · uv

- Пересечение записей запрещено на уровне БД: `EXCLUDE`-ограничение с `btree_gist`
- Ошибки целостности маппятся в HTTP по SQLSTATE: 409 при конфликте, 404 при битой ссылке
- Health-check `/health/ready`, строгий mypy, ruff и pre-commit
- Дальше в планах: AI-ассистент записи на tool calling

##  Связь

- Telegram: [@tl_miwqsd](https://t.me/tl_miwqsd)
- hh.ru: [резюме](https://hh.ru/resume/eb0dfaf2ff1138bd480039ed1f7733724f6e55)
