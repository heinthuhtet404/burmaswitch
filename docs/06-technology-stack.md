Technology Stack Decision
Backend

Python + FastAPI

Reason:

High performance
Modern async support
Easy microservice development
Database

PostgreSQL

Reason:

Strong transaction support
ACID compliance
Financial systems friendly
ORM

Initial Decision:

Raw SQL + SQLAlchemy Core

Reason:

ဒီ Project ရဲ့ ရည်ရွယ်ချက်က Database Engineering ကို နားလည်ဖို့ ဖြစ်လို့။

Queue

Celery + Redis

Cache

Redis

Container

Docker Compose

Testing
Pytest
Locust
Documentation
Swagger/OpenAPI
Markdown
Mermaid